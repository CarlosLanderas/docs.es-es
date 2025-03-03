---
title: Configuración de la transacción ServiceModel
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: e8c8c9ebff259ccd991768afb8cdf9925a66aad0
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141612"
---
# <a name="servicemodel-transaction-configuration"></a>Configuración de la transacción ServiceModel
Windows Communication Foundation (WCF) proporciona tres atributos para configurar transacciones para un servicio: `transactionFlow`, `transactionProtocol`y `transactionTimeout`.  
  
## <a name="configuring-transactionflow"></a>Configuración de transactionFlow  
 La mayoría de los enlaces predefinidos que proporciona WCF contienen los atributos `transactionFlow` y `transactionProtocol`, de modo que puede configurar el enlace para aceptar las transacciones entrantes de un punto de conexión específico mediante un protocolo de flujo de transacciones específico. Además, puede usar el elemento `transactionFlow` y su atributo `transactionProtocol` para compilar su propio enlace personalizado. Para obtener más información acerca de cómo establecer los elementos de configuración, vea [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) y el [esquema de configuración de WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).  
  
 El atributo `transactionFlow` especifica si el flujo de transacciones está habilitado para los extremos de servicio que utilizan el enlace.  
  
## <a name="configuring-transactionprotocol"></a>Configuración de transactionProtocol  
 El atributo `transactionProtocol` especifica el protocolo de transacción a utilizar con extremos de servicio que utilizan el enlace.  
  
 El siguiente es un ejemplo de una sección de configuración que configura el enlace especificado para que admita el flujo de transacciones, así como un uso del protocolo WS-AtomicTransaction.  
  
```xml  
<netNamedPipeBinding>  
   <binding name="test"  
      closeTimeout="00:00:10"  
      openTimeout="00:00:20"   
      receiveTimeout="00:00:30"  
      sendTimeout="00:00:40"  
      transactionFlow="true"  
      transactionProtocol="WSAtomicTransactionOctober2004"  
      hostNameComparisonMode="WeakWildcard"  
      maxBufferSize="1001"  
      maxConnections="123"   
      maxReceivedMessageSize="1000">  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="configuring-transactiontimeout"></a>Configuración de transactionTimeout  
 Puede configurar el atributo `transactionTimeout` para su servicio WCF en el elemento `behavior` del archivo de configuración. El siguiente código muestra cómo hacerlo:  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 El atributo `transactionTimeout` especifica el período dentro del que una nueva transacción creada en el servicio debe completarse. Se utiliza como tiempo de espera <xref:System.Transactions.TransactionScope> para cualquier operación que establezca una nueva transacción y si se aplica <xref:System.ServiceModel.OperationBehaviorAttribute>, la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> se establece en `true`.  
  
 El tiempo de espera especifica la duración desde la creación de la transacción hasta la finalización de la fase 1 en el protocolo de confirmación de dos fases.  
  
 Si este atributo se establece dentro de una sección de configuración de `service`, debería aplicar al menos un método del servicio correspondiente con <xref:System.ServiceModel.OperationBehaviorAttribute>, en el que la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> se establece en `true`.  
  
 Tenga en cuenta que el valor de tiempo de espera usado es el valor más pequeño entre este ajuste de configuración de `transactionTimeout` y cualquier propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.  
  
## <a name="see-also"></a>Vea también

- [\<> de enlace](../../configure-apps/file-schema/wcf/bindings.md)
- [Esquema de configuración de WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)
