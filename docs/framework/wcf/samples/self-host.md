---
title: Probar internamente
ms.date: 03/30/2017
helpviewer_keywords:
- Self hosted service
- Self Host Sample [Windows Communication Foundation]
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
ms.openlocfilehash: 9077f2b00c97ae2a2106a50780cfd2cd9596c1ec
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716318"
---
# <a name="self-host"></a>Probar internamente
Este ejemplo muestra cómo implementar un servicio autohospedado en una aplicación de la consola. Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md). Se ha cambiado el nombre al archivo de configuración de servicio de Web.config a App.config y se ha modificado para configurar una dirección base, que el host utiliza. El código fuente del servicio se ha modificado para implementar una función `Main` estática que crea y abre un host de servicio que proporciona la dirección base configurada. La implementación del servicio se ha modificado para escribir la salida en la consola para cada operación. No se ha modificado el cliente, salvo para configurar la dirección del extremo correcta del servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El ejemplo implementa una función principal estática para crear <xref:System.ServiceModel.ServiceHost> para el tipo `CalculatorService` determinado, como se muestra en el código de ejemplo siguiente.  
  
```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost =   
           new ServiceHost(typeof(CalculatorService)))  
    {  
        // Open the ServiceHost to create listeners   
        // and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 Cuando un servicio se hospeda en Internet Information Services (IIS) o el Servicio de activación de procesos de Windows (WAS), el entorno de hospedaje proporciona la dirección base del servicio. En el caso de que sea autohospedado, deberá especificar la dirección base. Esto se hace mediante el elemento `add`, el elemento secundario de [\<baseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), el elemento secundario de [\<host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), el elemento secundario del [servicio\<](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) como se muestra en la configuración del ejemplo siguiente.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
  ...  
</service>  
```  
  
 Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de hospedaje y persistencia de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193961)
