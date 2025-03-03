---
title: Ejemplo de federación
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: 271790e08476533fc1d83e22c5a0daf2f1eaa42a
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716923"
---
# <a name="federation-sample"></a>Ejemplo de federación
Este ejemplo muestra la seguridad aliada.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Windows Communication Foundation (WCF) proporciona compatibilidad para la implementación de arquitecturas de seguridad federadas a través del `wsFederationHttpBinding`. El `wsFederationHttpBinding` proporciona un enlace seguro, confiable e interoperable que implica el uso de HTTP como mecanismo de transporte subyacente para la comunicación de solicitud-respuesta, y Text/XML, como el formato de conexión para la codificación. Para obtener más información acerca de la Federación en WCF, consulte [Federación](../../../../docs/framework/wcf/feature-details/federation.md).  
  
 El escenario se compone de 4 partes:  
  
- Servicio de la librería  
  
- STS BookStore  
  
- STS HomeRealm  
  
- Cliente de librería  
  
 El servicio de librería admite dos operaciones, `BrowseBooks` y `BuyBook`. Permite el acceso anónimo a la operación `BrowseBooks`, pero requiere acceso autenticado para tener acceso a la operación `BuyBooks`. La autenticación toma el formulario de un token emitido por el STS BookStore. El archivo de configuración para el Servicio de librería dirige los clientes a la STS BookStore mediante `wsFederationHttpBinding`.  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 STS BookStore requiere a continuación que los clientes se autentiquen mediante un token emitido por el STS HomeRealm. De nuevo, el archivo de configuración para el STS BookStore dirige los clientes al STS HomeRealm mediante `wsFederationHttpBinding`.  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 La secuencia de eventos, al tener acceso a la operación `BuyBook`, es como sigue:  
  
1. El cliente autentica el STS HomeRealm mediante las credenciales de Windows.  
  
2. El STS HomeRealm emite un token que se puede utilizar para autenticar el STS BookStore.  
  
3. El cliente autentica el STS BookStore mediante el token emitido por el STS HomeRealm.  
  
4. El STS BookStore emite un token que se puede utilizar para autenticar el servicio BookStore.  
  
5. El cliente autentica el servicio de BookStore mediante el token emitido por el STS BookStore.  
  
6. El cliente tiene acceso a la operación `BuyBook`.  
  
 Vea las instrucciones siguientes acerca de cómo configurar y ejecutar este ejemplo.  
  
> [!NOTE]
> Para ejecutar este ejemplo, debe tener permisos de escritura en el directorio **wwwroot** .  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Abra la ventana de comandos de SDK. En la ruta de acceso del ejemplo, ejecute Setup.bat. Esto crea directorios virtuales requeridos para obtener el ejemplo e instala los certificados necesarios con permisos adecuados.  
  
    > [!NOTE]
    > El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK. Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK. Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK. En [!INCLUDE[wv](../../../../includes/wv-md.md)], debe asegurarse de que esté instalada la Compatibilidad con la administración de IIS 6.0, porque la instalación utiliza los scripts de administrador de IIS. Al ejecutar el script de instalación en [!INCLUDE[wv](../../../../includes/wv-md.md)], se requieren privilegios de administrador.  
  
2. Abra FederationSample. sln en Visual Studio y seleccione **compilar solución** en el menú **compilar** . De esta forma se compilan los archivos de proyecto comunes, servicio Bookstore, STS Bookstore, STS HomeRealm, y los implementa en IIS. De esta forma también se compila la aplicación cliente Bookstore y coloca el BookStoreClient.exe ejecutable en la carpeta FederationSample\BookStoreClient\bin\Debug.  
  
3. Haga doble clic en BookStoreClient.exe. Se muestra la ventana BookStoreClient.  
  
4. Puede examinar los libros disponibles en la librería haciendo clic en **examinar libros**.  
  
5. Para comprar un libro determinado, seleccione el libro en la lista y haga clic en **comprar libro**. La aplicación se inicia y autentica mediante la autenticación de Windows con el Servicio de token de seguridad de HomeRealm.  
  
     El ejemplo se configura para permitirles a los usuarios comprar libros que cuesten 15$ o menos. Intentar comprar libros que cuesten más de 15 $ provoca que el cliente reciba un mensaje de acceso denegado en el servicio de almacén de libros.  
  
    > [!NOTE]
    > El ejemplo no actualiza el límite de crédito del usuario después de una compra. Puede comprar repetidamente libros dentro del límite de crédito del usuario (fijo).  
  
#### <a name="to-clean-up"></a>Para realizar una limpieza  
  
1. Ejecute Cleanup.bat. De esta forma se eliminan los directorios virtuales que se crearon durante la instalación y también se quitan los certificados instalados durante la instalación.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
