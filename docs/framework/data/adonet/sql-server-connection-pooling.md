---
title: Agrupación de conexiones de SQL Server (ADO.NET)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e51d44e-7c4e-4040-9332-f0190fe36f07
ms.openlocfilehash: 2c73bec644a9a76ba05d3299183e8f1643c8e870
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794320"
---
# <a name="sql-server-connection-pooling-adonet"></a>Agrupación de conexiones de SQL Server (ADO.NET)
La conexión a un servidor de bases de datos suele constar de varios pasos que requieren mucho tiempo. Se debe establecer un canal físico, como un socket o una canalización con nombre, debe tener lugar el protocolo de enlace con el servidor, se debe analizar la información de la cadena de conexión, el servidor debe autenticar la conexión, se deben ejecutar comprobaciones para la inscripción en la transacción actual, etc.  
  
 En la práctica, la mayoría de las aplicaciones solamente utilizan unas cuantas configuraciones diferentes para las conexiones. Esto significa que durante la ejecución de la aplicación, muchas conexiones idénticas se abrirán y cerrarán de forma repetida. Para minimizar el costo de la apertura de conexiones, ADO.NET usa una técnica de optimización denominada *agrupación*de conexiones.  
  
 La agrupación de conexiones reduce el número de veces que es necesario abrir nuevas conexiones. El *concentrador* mantiene la propiedad de la conexión física. Para administrar las conexiones, mantiene un conjunto de conexiones activas para cada configuración de conexión dada. Cada vez que un usuario llama a `Open` en una conexión, el agrupador comprueba si hay una conexión disponible en el grupo. Si hay disponible una conexión agrupada, la devuelve a la persona que llama en lugar de abrir una nueva. Cuando la aplicación llama a `Close` en la conexión, el agrupador la devuelve al conjunto agrupado de conexiones activas en lugar de cerrarla. Una vez que la conexión vuelve al grupo, ya está preparada para volverse a utilizar en la siguiente llamada a `Open`.  
  
 Solo se pueden agrupar conexiones con la misma configuración. ADO.NET mantiene varios grupos al mismo tiempo, uno para cada configuración. Las conexiones se dividen en grupos por cadena de conexión, y por identidad de Windows si se utiliza seguridad integrada. Las conexiones también se agrupan en función de si están incluidas en una transacción. Cuando se usa <xref:System.Data.SqlClient.SqlConnection.ChangePassword%2A>, la instancia de <xref:System.Data.SqlClient.SqlCredential> afecta al grupo de conexiones. Distintas instancias de <xref:System.Data.SqlClient.SqlCredential> usarán diferentes grupos de conexiones, incluso si el identificador de usuario y la contraseña son iguales.  
  
 La agrupación de conexiones puede mejorar de forma considerable el rendimiento y la escalabilidad de la aplicación. De forma predeterminada, la agrupación de conexiones está habilitada en ADO.NET. A menos que la deshabilite explícitamente, el agrupador optimiza las conexiones a medida que se abren y cierran en la aplicación. También puede proporcionar varios modificadores de cadena de conexión para controlar el comportamiento de agrupación de conexiones. Para obtener más información, vea "Control de la agrupación de conexiones con palabras clave de cadena de conexión" más adelante en este tema.  
  
> [!NOTE]
> Cuando se habilita la agrupación de conexiones, y si se produce un error de tiempo de expiración u otro error de inicio de sesión, se producirá una excepción y los intentos de conexión posteriores producirán errores durante los cinco segundos siguientes, el "período de bloqueo". Si la aplicación intenta conectarse dentro del período de bloqueo, se volverá a producir la primera excepción. Los errores que se produzcan después de que finalice un período de bloqueo darán lugar a nuevos períodos de bloqueo que serán el doble de largos que el período de bloqueo anterior, hasta un máximo de un minuto.  
  
## <a name="pool-creation-and-assignment"></a>Creación y asignación del grupo  
 Cuando se abre una conexión por primera vez, se crea un grupo de conexión basado en un algoritmo de coincidencia exacta que asocia el grupo con la cadena de conexión de la conexión. Cada grupo de conexión se asocia con una cadena de conexión distinta. Si se abre una nueva conexión y la cadena de conexión no coincide exactamente con un grupo existente, se crea un nuevo grupo. Las conexiones se agrupan por proceso, por dominio de aplicación, por cadena de conexión y, cuando se utiliza seguridad integrada, por identidad de Windows. Las cadenas de conexión también deben ser una coincidencia exacta; las palabras clave indicadas en un orden diferente para la misma conexión se agruparán por separado.  
  
 En el siguiente ejemplo con C#, se crean tres nuevos objetos <xref:System.Data.SqlClient.SqlConnection>, pero solo se necesitan dos grupos de conexión para administrarlos. Observe que las cadenas de conexión primera y segunda difieren en el valor asignado a `Initial Catalog`.  
  
```csharp
using (SqlConnection connection = new SqlConnection(  
  "Integrated Security=SSPI;Initial Catalog=Northwind"))  
    {  
        connection.Open();        
        // Pool A is created.  
    }  
  
using (SqlConnection connection = new SqlConnection(  
  "Integrated Security=SSPI;Initial Catalog=pubs"))  
    {  
        connection.Open();        
        // Pool B is created because the connection strings differ.  
    }  
  
using (SqlConnection connection = new SqlConnection(  
  "Integrated Security=SSPI;Initial Catalog=Northwind"))  
    {  
        connection.Open();        
        // The connection string matches pool A.  
    }  
```  
  
 Si no se especifica `MinPoolSize` en la cadena de conexión o se especifica como cero, las conexiones del grupo se cerrarán tras un período de inactividad. No obstante, si el `MinPoolSize` especificado es mayor que cero, el grupo de conexión no se destruye hasta que se descarga el `AppDomain` y finaliza el proceso. El mantenimiento de grupos inactivos o vacíos supone una sobrecarga mínima para el sistema.  
  
> [!NOTE]
> El grupo se borra automáticamente cuando se produce un error irrecuperable, como una conmutación por error.  
  
## <a name="adding-connections"></a>Agregar conexiones  
 Para cada cadena de conexión única se crea un grupo de conexión. Cuando se crea un grupo, se crean y agregan al grupo varios objetos de conexión y se satisface así el requisito de tamaño mínimo del grupo. Las conexiones se agregan al grupo cuando es necesario, hasta el tamaño máximo del grupo especificado (100 es el valor predeterminado), y se liberan de nuevo en el grupo cuando se cierran o eliminan.  
  
 Cuando se solicita un objeto <xref:System.Data.SqlClient.SqlConnection>, se obtiene del grupo si se encuentra disponible una conexión que se pueda utilizar. Una conexión de este tipo debe estar sin utilizar, tener un contexto de transacción coincidente o no estar asociada con ningún contexto de transacción y tener un vínculo válido al servidor.  
  
 El agrupador de conexiones satisface las solicitudes de conexión al reasignar las conexiones conforme se liberan de nuevo en el grupo. Si se ha alcanzado el tamaño máximo del grupo y no hay disponible ninguna conexión que se pueda utilizar, la solicitud se pone en la cola. A continuación, el concentrador intenta reclamar las conexiones hasta que se agota el tiempo de espera (el valor predeterminado es 15 segundos). Si no puede satisfacer la solicitud antes de que se agote el tiempo de espera de la conexión, se inicia una excepción.  
  
> [!CAUTION]
> Se recomienda encarecidamente cerrar siempre la conexión cuando se termine de utilizar para que regrese al grupo. Para ello, puede usar los `Close` métodos o `Dispose` del `Connection` objeto o abrir todas las conexiones dentro de una `using` instrucción de C#, o una `Using` instrucción de Visual Basic. Es posible que las conexiones que no se cierran explícitamente no se puedan agregar ni puedan regresar al grupo. Para obtener más información, vea Using [instrucción](../../../csharp/language-reference/keywords/using-statement.md)o [cómo: Desechar un recurso](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md) del sistema para Visual Basic.  
  
> [!NOTE]
> No llame a `Close` o a `Dispose` en un objeto `Connection`, un objeto `DataReader` o cualquier otro objeto administrado en el método `Finalize` de la clase. En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase. Si la clase no dispone de recursos no administrados, no incluya un método `Finalize` en la definición de clase. Para obtener más información, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).  
  
Para obtener más información sobre los eventos asociados a la apertura y el cierre de conexiones, vea [Audit login Event Class](/sql/relational-databases/event-classes/audit-login-event-class) y [Audit Logout Event Class](/sql/relational-databases/event-classes/audit-logout-event-class) en la documentación de SQL Server.  
  
## <a name="removing-connections"></a>Cómo quitar conexiones  
 El agrupador de conexiones quita una conexión del grupo después de haber estado inactiva unos 4-8 minutos o si detecta que se ha roto la conexión con el servidor. Tenga en cuenta que una conexión rota solo puede detectarse después de intentar comunicarse con el servidor. Si se encuentra que una conexión ya no está conectada al servidor, se marca como no válida. Las conexiones no válidas se quitan del grupo de conexión solo cuando se cierran o reclaman.  
  
 Si existe una conexión en un servidor que ha desaparecido, se puede extraer del grupo aunque el agrupador de conexiones no haya detectado la conexión rota y la haya marcado como no válida. El motivo es que la sobrecarga de comprobar que la conexión es aún válida eliminaría los beneficios de tener un concentrador y ocasionaría que se produjera otro viaje de ida y vuelta (round trip) al servidor. Cuando esto ocurre, el primer intento para usar la conexión detectará que ésta se ha roto y se iniciará una excepción.  
  
## <a name="clearing-the-pool"></a>Borrado del grupo  
 ADO.net 2,0 presentó dos nuevos métodos para borrar el Grupo: <xref:System.Data.SqlClient.SqlConnection.ClearAllPools%2A> y <xref:System.Data.SqlClient.SqlConnection.ClearPool%2A>. `ClearAllPools` borra los grupos de conexión de un proveedor dado, y `ClearPool` borra el grupo de conexión que está asociado a una conexión concreta. Si en el momento de la llamada se están usando conexiones, se marcan de forma adecuada. Cuando se cierran, se descartan en lugar de devolverse al grupo.  
  
## <a name="transaction-support"></a>Compatibilidad con transacciones  
 Las conexiones se extraen del grupo y se asignan en función del contexto de transacción. A menos que se especifique `Enlist=false` en la cadena de conexión, el grupo de conexión garantiza que la conexión está dada de alta en el contexto de <xref:System.Transactions.Transaction.Current%2A>. Cuando se cierra una conexión y se devuelve al grupo con una transacción `System.Transactions` dada de alta, se reserva de forma que la siguiente solicitud de ese grupo de conexiones con la misma transacción `System.Transactions` devolverá la misma conexión, si está disponible. Si se emite dicha solicitud y no hay conexiones agrupadas disponibles, se extrae una conexión de la parte sin transacción del grupo y se le da de alta. Si no hay conexiones disponibles en cualquier área del grupo, se crea y da de alta una nueva conexión.  
  
 Cuando se cierra una conexión, se libera de nuevo en el grupo y en la subdivisión adecuada en función de su contexto de transacción. Por lo tanto, puede cerrar la conexión sin generar un error, incluso aunque aún haya pendiente una transacción distribuida. Esto permite confirmar o anular la transacción distribuida más adelante.  
  
## <a name="controlling-connection-pooling-with-connection-string-keywords"></a>Control de la agrupación de conexiones con palabras clave de cadena de conexión  
 La propiedad `ConnectionString` del objeto <xref:System.Data.SqlClient.SqlConnection> admite pares clave-valor de cadena de conexión que se pueden utilizar para ajustar el comportamiento de la lógica de agrupación de conexiones. Para obtener más información, consulta <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
## <a name="pool-fragmentation"></a>Fragmentación de grupos  
 La fragmentación de grupos es un problema común en muchas aplicaciones web en las que la aplicación puede crear gran cantidad de grupos que no se liberan hasta que finaliza el proceso. El resultado es un gran número de conexiones abiertas que consumen memoria, lo que da lugar a un bajo rendimiento.  
  
### <a name="pool-fragmentation-due-to-integrated-security"></a>Fragmentación de grupos debido a la seguridad integrada  
 Las conexiones se agrupan de acuerdo con la cadena de conexión y la identidad del usuario. Por lo tanto, si utiliza autenticación básica o autenticación de Windows en el sitio web y un inicio de sesión de seguridad integrada, obtendrá un grupo por usuario. Aunque de esta manera se mejora el rendimiento de las posteriores solicitudes de base de datos de un solo usuario, ese usuario no podrá aprovechar las conexiones realizadas por otros usuarios. Además, como resultado habrá una conexión como mínimo por usuario al servidor de bases de datos. Se trata de un efecto secundario de una determinada arquitectura de aplicaciones web que los desarrolladores deben sopesar frente a los requisitos de seguridad y auditoría.  
  
### <a name="pool-fragmentation-due-to-many-databases"></a>Fragmentación de grupos debido a muchas bases de datos  
 Muchos proveedores de acceso a Internet hospedan varios sitios web en un único servidor. Puede que utilicen una sola base de datos para confirmar un inicio de sesión de autenticación de formularios y luego abran una conexión a una base de datos específica para ese usuario o grupo de usuarios. La conexión a la base de datos de autenticación es agrupada y utilizada por todo el mundo. Sin embargo, hay un grupo independiente de conexiones con cada base de datos, lo que implica un aumento del número de conexiones con el servidor.  
  
 Este es también un efecto secundario del diseño de la aplicación. Existe, sin embargo, una forma relativamente sencilla de evitarlo sin comprometer la seguridad cuando se establece conexión con SQL Server. En lugar de realizar una conexión a una base de datos diferente por cada usuario o grupo, realice una conexión a la misma base de datos en el servidor y, a continuación, ejecute la instrucción USE de Transact-SQL para cambiar a la base de datos deseada. En el siguiente fragmento de código se muestra la creación de una conexión inicial con la base de datos `master` y el cambio a la base de datos deseada especificada en la variable de cadena `databaseName`.  
  
```vb  
' Assumes that command is a valid SqlCommand object and that  
' connectionString connects to master.  
    command.Text = "USE DatabaseName"  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
// Assumes that command is a SqlCommand object and that  
// connectionString connects to master.  
command.Text = "USE DatabaseName";  
using (SqlConnection connection = new SqlConnection(  
  connectionString))  
  {  
    connection.Open();  
    command.ExecuteNonQuery();  
  }  
```  
  
## <a name="application-roles-and-connection-pooling"></a>Roles de aplicación y agrupación de conexiones  
 Una vez activada una función de aplicación de SQL Server al llamar al procedimiento almacenado de sistema `sp_setapprole`, no se puede restablecer el contexto de seguridad de la conexión. Sin embargo, cuando se habilita la agrupación, la conexión se devuelve al grupo y se produce un error al utilizar de nuevo la conexión agrupada. Para obtener más información, vea el artículo de Knowledge base "[errores de rol de aplicación SQL con agrupación de recursos de OLE DB](https://support.microsoft.com/default.aspx?scid=KB;EN-US;Q229564)".  
  
### <a name="application-role-alternatives"></a>Alternativas a los roles de aplicación  
 Se recomienda aprovechar las ventajas de los mecanismos de seguridad que se pueden usar en lugar de roles de aplicación. Para obtener más información, vea [crear roles de aplicación en SQL Server](./sql/creating-application-roles-in-sql-server.md).  
  
## <a name="see-also"></a>Vea también

- [Agrupación de conexiones](connection-pooling.md)
- [SQL Server y ADO.NET](./sql/index.md)
- [Contadores de rendimiento](performance-counters.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
