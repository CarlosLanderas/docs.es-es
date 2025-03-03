---
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 6761d090206e55e58001ea2bb885eaa69f26d9eb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738641"
---
# <a name="tcptransport"></a>\<tcpTransport >
Define un transporte del TCP que puede ser utilizado por un canal para la transferencia de mensajes de un enlace personalizado.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tcpTransport >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|channelInitializationTimeout|Obtiene o establece el límite de tiempo para inicializar un canal que se va a aceptar.  El tiempo máximo que un canal puede estar en el estado de inicialización antes de que se desconecte, en segundos. Esta cuota incluye el tiempo que una conexión TCP puede realizar para autenticarse a sí misma mediante el protocolo de trama de mensajes de .NET. Un cliente debe enviar algunos datos iniciales antes de que el servidor tenga información suficiente para realizar la autenticación. El valor predeterminado es 30 segundos.|  
|connectionBufferSize|Obtiene o establece el tamaño del búfer usado para transmitir un bloque del mensaje serializado en la conexión del cliente o servicio.|  
|hostNameComparisonMode|Obtiene o establece un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.|  
|listenBacklog|El número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio web. El atributo `connectionLeaseTimeout` limita el tiempo durante el cual el cliente espera a ser conectado antes de iniciar una excepción de conexión. Esta es una propiedad del nivel de socket que controla el número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio web. Cuando ListenBacklog es demasiado bajo, WCF dejará de aceptar solicitudes y, por lo tanto, quitará nuevas conexiones hasta que el servidor confirme algunas de las conexiones en cola existentes. El valor predeterminado es 16 * número de procesadores.|  
|manualAddressing|Obtiene o establece un valor que indica si se requiere la dirección manual del mensaje.|  
|maxBufferPoolSize|Obtiene o establece el tamaño máximo de cualquier grupo de búferes utilizado por el transporte.|  
|maxBufferSize|Obtiene o establece el tamaño máximo del búfer que se va a usar. Para mensajes transmitidos por secuencias, este valor debería ser por lo menos el tamaño máximo posible de los encabezados de mensaje, que se leen en modo almacenado en búfer.|  
|maxOutputDelay|Obtiene o establece el intervalo máximo de tiempo que un bloque de mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.|  
|maxPendingAccepts|Obtiene o establece el número máximo de operaciones de aceptación asincrónica pendientes disponibles para procesar conexiones entrantes en el servicio.|  
|maxPendingConnections|Obtiene o establece el número máximo de conexiones pendientes de distribución en el servicio.|  
|maxReceivedMessageSize|Obtiene y establece el tamaño máximo permitido del mensaje que se puede recibir.|  
|portSharingEnabled|Un valor booleano que especifica si el uso compartido de puerto TCP está habilitado para esta conexión. Si éste es `false`, cada enlace utilizará su propio puerto exclusivo. De manera predeterminada, es `false`.<br /><br /> Este valor sólo es pertinente a los servicios. Los clientes no se ven afectados.<br /><br /> Para usar esta configuración se necesita que se habilite el servicio de puerto TCP compartido Windows Communication Foundation (WCF), cambiando su tipo de inicio a manual o automático.|  
|teredoEnabled|Un valor booleano que especifica si Teredo (una tecnología para direccionar clientes que están detrás de firewalls) está habilitada. De manera predeterminada, es `false`.<br /><br /> Esta propiedad habilita Teredo para el socket TCP subyacente. Para obtener más información, vea [información general sobre Teredo](https://go.microsoft.com/fwlink/?LinkId=95339).<br /><br /> Esta propiedad solo se aplica en [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] y [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)]. [!INCLUDE[wv](../../../../../includes/wv-md.md)] tiene una opción de configuración del equipo para Teredo, por lo que al ejecutar Vista, se omite esta propiedad. Teredo requiere que los equipos de servicio y del cliente tengan la pila de Microsoft IPv6 instalada y correctamente configurada para el uso de Teredo. Para obtener más información acerca de cómo configurar Teredo, vea [información general sobre Teredo](https://go.microsoft.com/fwlink/?LinkId=95339). Para obtener más información, vea [centros de tecnología de Windows Server 2003](https://go.microsoft.com/fwlink/?LinkId=49888).|  
|transferMode|Obtiene o establece un valor que indica si los mensajes están almacenados en búfer o se transmiten por secuencias mediante el transporte orientado a la conexión.|  
|connectionPoolSettings|Especifica valores adicionales del grupo de conexiones para un enlace de canalización con nombre.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<> de enlace](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 Este transporte utiliza los URI del formulario "net.tcp://hostname:port/path." Otros componentes URI son opcionales.  
  
 El elemento `tcpTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte TCP. Este transporte está optimizado para la comunicación de WCF a WCF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportes](../../../wcf/feature-details/transports.md)
- [Elección del transporte](../../../wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
