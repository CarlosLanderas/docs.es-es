---
title: Ejecución en paralelo en ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: 0ada258f74338fc7cbc9435fdea8fc896bd2efd6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782714"
---
# <a name="side-by-side-execution-in-adonet"></a>Ejecución en paralelo en ADO.NET
La ejecución en paralelo en el .NET Framework es la capacidad de ejecutar una aplicación en un equipo que tiene varias versiones de .NET Framework instaladas, exclusivamente con la versión para la que se compiló la aplicación. Para obtener información detallada sobre la configuración de la ejecución en paralelo, vea [ejecución en paralelo](../../deployment/side-by-side-execution.md).  
  
 Una aplicación compilada con una versión de la .NET Framework puede ejecutarse en una versión diferente de la .NET Framework. Sin embargo, se recomienda compilar una versión de la aplicación para cada versión instalada de la .NET Framework y ejecutarlas por separado. En cualquier escenario, debe tener en cuenta los cambios en ADO.NET entre versiones que pueden afectar a la compatibilidad con versiones posteriores o a la compatibilidad con versiones anteriores de la aplicación.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Compatibilidad con versiones anteriores y posteriores  
 La compatibilidad con versiones posteriores significa que una aplicación se puede compilar con una versión anterior del .NET Framework, pero se seguirá ejecutando correctamente en una versión posterior de la .NET Framework. El código ADO.NET escrito para la versión 1,1 de .NET Framework es compatible con versiones posteriores.  
  
 La compatibilidad con versiones anteriores significa que una aplicación se compila para una versión más reciente del .NET Framework, pero continúa ejecutándose en versiones anteriores de la .NET Framework sin pérdida de funcionalidad. Por supuesto, este no será el caso de las características introducidas en una nueva versión del .NET Framework.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Proveedor de datos .NET Framework para ODBC  
 A partir de la versión 1,1, el proveedor de datos de<xref:System.Data.Odbc>.NET Framework para ODBC () se incluye como parte de la .NET Framework. El proveedor de datos de ODBC está disponible para .NET Framework los desarrolladores de la versión 1,0 como descarga web desde el [Centro para desarrolladores de acceso a datos y almacenamiento](https://go.microsoft.com/fwlink/?linkid=4173). El espacio de nombres para el proveedor de datos de .NET Framework descargado para ODBC es **Microsoft. Data. ODBC**.  
  
 Si tiene una aplicación desarrollada para la .NET Framework versión 1,0 que usa el proveedor de datos de ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en la .NET Framework versión 1,1 o posterior, debe actualizar el espacio de nombres de ODBC DAT. un proveedor a **System. Data. ODBC**. A continuación, debe volver a compilarla para la versión más reciente de la .NET Framework.  
  
 Si tiene una aplicación desarrollada para la .NET Framework versión 2,0 o posterior que usa el proveedor de datos de ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en la .NET Framework versión 1,0, debe descargar el proveedor de datos de ODBC e instalarlo. en el sistema .NET Framework versión 1,0. A continuación, debe cambiar el espacio de nombres para el proveedor de datos ODBC a **Microsoft. Data. ODBC**y volver a compilar la aplicación para la .NET Framework versión 1,0.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Proveedor de datos .NET Framework para Oracle  
 A partir de la versión 1,1, el proveedor de datos de<xref:System.Data.OracleClient>.NET Framework para Oracle () se incluye como parte de la .NET Framework. El proveedor de datos está disponible para .NET Framework los desarrolladores de la versión 1,0 como descarga web desde el [Centro para desarrolladores de acceso a datos y almacenamiento](https://go.microsoft.com/fwlink/?linkid=4173).  
  
 Si tiene una aplicación desarrollada para la .NET Framework versión 2,0 o posterior que usa el proveedor de datos para conectarse a su origen de datos y desea ejecutar dicha aplicación en la .NET Framework versión 1,0, debe descargar el proveedor de datos e instalarlo en el. NE T Framework versión 1,0 sistema.  
  
## <a name="code-access-security"></a>Seguridad de acceso del código  
 Los proveedores de datos .NET Framework de la versión de .NET Framework<xref:System.Data.SqlClient>1,0 <xref:System.Data.OleDb>(,) son necesarios para ejecutarse con el permiso FullTrust. Cualquier intento de usar los proveedores de datos de .NET Framework k de la .NET Framework versión 1,0 en una zona con un permiso menor que <xref:System.Security.SecurityException>FullTrust produce una excepción.  
  
 Sin embargo, a partir de la versión 2,0 de .NET Framework, todos los proveedores de datos .NET Framework se pueden usar en zonas de confianza parcial. Además, se ha agregado una nueva característica de seguridad a los proveedores de datos de .NET Framework en la .NET Framework versión 1,1. Esta característica le permite restringir las cadenas de conexión que se pueden utilizar en una zona de seguridad determinada. Es posible también deshabilitar el uso de contraseñas en blanco para una zona de seguridad determinada. Para obtener más información, consulta [Code Access Security and ADO.NET](code-access-security.md).  
  
 Dado que cada instalación del .NET Framework tiene un archivo Security. config independiente, no hay ningún problema de compatibilidad con la configuración de seguridad. Sin embargo, si la aplicación depende de las capacidades de seguridad adicionales de ADO.NET incluidas en la .NET Framework versión 1,1 y versiones posteriores, no podrá distribuirla a un sistema de la versión 1,0.  
  
## <a name="sqlcommand-execution"></a>Ejecución de SqlCommand  
 A partir de la versión 1,1 de .NET Framework, se <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ha cambiado la forma en que se ejecutan los comandos en el origen de datos.  
  
 En la versión 1,0 de .NET Framework <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> , ejecutó todos los comandos en el contexto del procedimiento almacenado **sp_executesql** . Como resultado, los comandos que influyen en el estado de la conexión (Activar NOCOUNT, por ejemplo) sólo se aplican a la ejecución del comando actual. Mientras la conexión permanece abierta, los comandos que se ejecutan posteriormente no modifican el estado de la conexión.  
  
 En la .NET Framework versión 1,1 y versiones posteriores <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> , solo ejecuta un comando en el contexto del procedimiento almacenado **sp_executesql** si el comando contiene parámetros, lo que proporciona una ventaja de rendimiento. Como consecuencia, si un comando que influye en el estado de la conexión se incluye en un comando sin parámetros, modifica el estado de la conexión de todos los comandos posteriores que se ejecuten mientras la conexión esté abierta.  
  
 Tomemos como ejemplo el siguiente lote de comandos, que se ejecuta en una llamada a <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 En la .NET Framework versión 1,1 y posteriores, NOCOUNT permanecerá en para los comandos posteriores que se ejecuten mientras la conexión esté abierta. En la versión .NET Framework 1,0, NOCOUNT solo está activado para la ejecución del comando actual.  
  
 Este cambio puede afectar a la compatibilidad con versiones anteriores y posteriores de la aplicación si depende del comportamiento de <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> para cualquiera de las dos versiones del .NET Framework.  
  
 En el caso de las aplicaciones que se ejecutan en versiones anteriores y posteriores de la .NET Framework, puede escribir el código para asegurarse de que el comportamiento es el mismo independientemente de la versión en la que se ejecuta. Si desea asegurarse de que un comando modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda ejecutar el comando usando <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>. Si desea asegurarse de que un comando no modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda incluir los comandos para restablecer el estado de la conexión en el comando. Por ejemplo:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](ado-net-overview.md)
- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
