---
title: Equilibrio de carga
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: c9a1e889ab5adcb8f0eb5ea851c81a4f9ee56e95
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138543"
---
# <a name="load-balancing"></a>Equilibrio de carga
Una manera de aumentar la capacidad de las aplicaciones de Windows Communication Foundation (WCF) es escalarlas horizontalmente mediante su implementación en una granja de servidores con equilibrio de carga. Se puede equilibrar la carga de las aplicaciones WCF mediante técnicas de equilibrio de carga estándar, como equilibradores de carga de software como equilibrio de carga de red de Windows, así como dispositivos de equilibrio de carga basados en hardware.  
  
 En las secciones siguientes se describen las consideraciones para el equilibrio de carga de aplicaciones WCF compiladas con varios enlaces proporcionados por el sistema.  
  
## <a name="load-balancing-with-the-basic-http-binding"></a>Equilibrio de carga con el enlace HTTP básico  
 Desde la perspectiva del equilibrio de carga, las aplicaciones WCF que se comunican mediante el <xref:System.ServiceModel.BasicHttpBinding> no son diferentes de otros tipos comunes de tráfico de red HTTP (contenido HTML estático, páginas ASP.NET o servicios web ASMX). Los canales WCF que usan este enlace son sin estado inherentemente y terminan sus conexiones cuando se cierra el canal. Como tal, <xref:System.ServiceModel.BasicHttpBinding> funciona bien con técnicas de equilibrio de carga de HTTP existentes.  
  
 De forma predeterminada, <xref:System.ServiceModel.BasicHttpBinding> envía un encabezado HTTP de conexión en mensajes con un valor `Keep-Alive`, que permite a los clientes establecer conexiones permanentes a los servicios que las admiten. Esta configuración proporciona un rendimiento mejorado ya que las conexiones previamente establecidas se pueden reutilizar para enviar los mensajes subsiguientes al mismo servidor. Sin embargo, la reutilización de la conexión puede hacer que los clientes se asocien con un servidor concreto dentro de la granja con la carga equilibrada, lo que reduce la eficacia del equilibrio de carga por turnos (round-robin). Si este comportamiento no es adecuado, `Keep-Alive` de HTTP puede estar deshabilitado en el servidor utilizando la propiedad <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> con <xref:System.ServiceModel.Channels.CustomBinding> o <xref:System.ServiceModel.Channels.Binding> definido por el usuario. En el ejemplo siguiente se muestra cómo hacerlo usando la configuración.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service   
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"   
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Con la configuración simplificada introducida en .NET Framework 4, se puede lograr el mismo comportamiento mediante la siguiente configuración simplificada.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](./samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a>Equilibrio de carga con los enlaces WSHttp y WSDualHttp  
 <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.WSDualHttpBinding> pueden tener la carga equilibrada gracias a las técnicas de equilibrio de carga de HTTP siempre que se hagan algunas modificaciones a la configuración de enlace predeterminada.  
  
- Desactive el establecimiento del contexto de seguridad: puede lograrse definiendo la propiedad <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> de <xref:System.ServiceModel.WSHttpBinding> en `false`. Como alternativa, si se requieren sesiones de seguridad, es posible usar sesiones de seguridad con estado como se describe en el tema [sesiones seguras](./feature-details/secure-sessions.md) . Las sesiones de seguridad con estado permiten al servicio seguir estando sin estado ya que se transmitirá todo el estado para la sesión de seguridad con cada solicitud como parte del token de seguridad de protección. Tenga en cuenta que para habilitar una sesión de seguridad con estado, es necesario utilizar <xref:System.ServiceModel.Channels.CustomBinding> o <xref:System.ServiceModel.Channels.Binding> definido por el usuario ya que no se exponen los valores de configuración necesarios en <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.WSDualHttpBinding> que son proporcionados por el sistema.  
  
- No utilice las sesiones confiables. Esta característica está desactivada de forma predeterminada.  
  
## <a name="load-balancing-the-nettcp-binding"></a>Equilibrio de carga del enlace Net.TCP  
 Puede equilibrarse la carga de <xref:System.ServiceModel.NetTcpBinding> mediante técnicas de equilibrio de carga de nivel IP. Sin embargo, <xref:System.ServiceModel.NetTcpBinding> agrupa de forma predeterminada las conexiones TCP para reducir la latencia de conexión. Ésta es una optimización que interfiere con el mecanismo básico del equilibrio de carga. El valor de configuración principal para optimizar <xref:System.ServiceModel.NetTcpBinding> es el tiempo de espera de la concesión, que forma parte de la configuración del grupo de conexiones. La agrupación de conexiones produce conexiones de cliente que se asociarán a servidores concretos dentro de la granja. Como la duración de esas conexiones aumenta (un factor controlado por el valor de tiempo de espera de la concesión), la distribución de carga en varios servidores de la granja pasa a estar sin equilibrar. Como resultado, aumentará el tiempo medio de la llamada. Así, al utilizar <xref:System.ServiceModel.NetTcpBinding> en escenarios con carga equilibrada, considere reducir el tiempo de espera de concesión predeterminado utilizado por el enlace. Un tiempo de espera de concesión de 30 segundos es un punto de inicio razonable para los escenarios con carga equilibrada, aunque el valor óptimo depende de la aplicación. Para obtener más información sobre el tiempo de espera de concesión de canal y otras cuotas de transporte, consulte [cuotas de transporte](./feature-details/transport-quotas.md).  
  
 Para obtener el máximo rendimiento en escenarios con carga equilibrada, considere utilizar <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> o <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).  
  
## <a name="see-also"></a>Vea también

- [Procedimientos recomendados de hospedaje de Internet Information Services](./feature-details/internet-information-services-hosting-best-practices.md)
