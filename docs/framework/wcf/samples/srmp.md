---
title: SRMP
ms.date: 03/30/2017
ms.assetid: cf37078c-dcb4-45e0-acaf-2f196521b226
ms.openlocfilehash: 0ee11b67dcd9c7251df17dc7523dc20765e157c5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716692"
---
# <a name="srmp"></a>SRMP
Este ejemplo muestra cómo llevar a cabo la comunicación en cola por transacciones utilizando Message Queuing (MSMQ) a través de HTTP.  
  
 En la comunicación con colas, el cliente se comunica con el servicio mediante una cola. Más exactamente, el cliente envía los mensajes a una cola. El servicio recibe los mensajes de la cola. El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.  
  
 MSMQ permite al uso de HTTP (incluso el uso de HTTPS) para enviar los mensajes a una cola. En este ejemplo, se muestra el uso de la comunicación en cola de Windows Communication Foundation (WCF) y cómo enviar mensajes a través de HTTP. MSMQ utiliza un protocolo llamado SRMP, que es un protocolo basado en SOAP para la comunicación sobre HTTP.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4. Antes de ejecutar el ejemplo en **Agregar o quitar componentes de Windows**, asegúrese de que MSMQ está instalado con compatibilidad con http. Instalando la compatibilidad HTTP se instala automáticamente Internet Information Services (IIS) y se agrega la compatibilidad con protocolos en IIS para MSMQ.  
  
5. Si desea asegurarse de que HTTP se utiliza para la comunicación, puede permitirle a MSMQ ejecutarse en modo endurecido. Esto asegurar que ningún mensaje dirigido a cualquier cola hospedada en el equipo puede llegar utilizando cualquier transporte no HTTP.  
  
6. Después de haber seleccionado MSMQ para ejecutarse en modo endurecido, el equipo requiere un reinicio en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
7. Ejecute el servicio.  
  
8. Ejecute el cliente. Aseguúrese de que cambia la dirección del extremo para señalar al nombre de equipo o dirección IP en lugar del host local. El cliente envía un mensaje y sale.  
  
## <a name="requirements"></a>Requisitos de  
 Para ejecutar este ejemplo, IIS se debe instalar en el servicio y en los equipos cliente además de en MSMQ.  
  
## <a name="demonstrates"></a>Demostraciones  
 En el ejemplo se muestra el envío de mensajes en cola WCF mediante MSMQ sobre HTTP. Esto también se denomina mensajería de SRMP. Cuando se envía un mensaje en cola, MSMQ en el equipo emisor transfiere los mensajes al administrador receptor de cola mediante TCP o transporte HTTP. Eligiendo SRMP, el usuario indica la opción de HTTP como un transporte para la transferencia de la cola. SRMP Secure habilita el uso de HTTPS.  
  
## <a name="example"></a>Ejemplo  
 El código muestra de este ejemplo está basado en el ejemplo de transacción. El modo en que se envía un mensaje a la cola y se recibe un mensaje de la cola utilizando SRMP es igual al modo en que se envían y reciben mensajes mediante un protocolo Native.  
  
 La configuración para el cliente se cambia para indicar la opción del protocolo de transferencia de la cola. El protocolo de transferencia de la cola puede ser uno de Nativo, SRMP o SrmpSecure. De forma predeterminada, el protocolo de transferencia es Nativo. El cliente y el servicio se especifican en la configuración para utilizar SRMP en este ejemplo.  
  
 Hay respecto a limitaciones a SRMP la seguridad de transporte. La seguridad de transporte de MSMQ predeterminada requiere Active Directory, que a su vez requiere que el administrador de cola emisor y el administrador de cola receptor residan en el mismo dominio de Windows. Esto no es posible al enviar los mensajes sobre el límite del HTTP. Como tal, la seguridad de transporte predeterminada no funciona. La seguridad de transporte se debe establecer para Certificar si se desea la seguridad de transporte. El modo de seguridad también se puede utilizar para proteger el mensaje. En este ejemplo, transporte y el modo de seguridad están desactivados para mostrar la mensajería de SRMP.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint name="OrderProcessorEndpoint"  
           address=  
          "net.msmq://localhost/private/ServiceModelSamplesSrmp"   
           bindingConfiguration="srmpBinding"   
           binding="netMsmqBinding"   
           contract="IOrderProcessor" />  
    </client>  
    <bindings>  
      <netMsmqBinding>  
        <binding name="srmpBinding"  
                 queueTransferProtocol="Srmp">  
          <security mode="None" />  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
  
</configuration>  
```  
  
 Al ejecutar el ejemplo, se produce el resultado siguiente.  
  
```console  
Processing Purchase Order: 556b70be-31ee-4a3b-8df4-ed5e538015a4   
Customer: somecustomer.com   
OrderDetails   
    Order LineItem: 54 of Blue Widget @unit price: $29.99   
    Order LineItem: 890 of Red Widget @unit price: $45.89   
    Total cost of this order: $42461.56   
    Order status: Pending  
```  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\SRMP`  
