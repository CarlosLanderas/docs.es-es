---
title: <customBinding>
ms.date: 03/30/2017
ms.assetid: 9da4f960-f64e-4d8a-894d-2b09eba5ce4b
ms.openlocfilehash: cdaaacf0dfa75209d001f6e8d6ac7175816048aa
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140798"
---
# <a name="custombinding"></a><span data-ttu-id="9a83d-101">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9a83d-101">\<customBinding></span></span>

<span data-ttu-id="9a83d-102">Proporciona el control completo sobre la pila de la mensajería para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9a83d-102">Provides full control over the messaging stack for the user.</span></span>

<span data-ttu-id="9a83d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a83d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9a83d-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9a83d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9a83d-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="9a83d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9a83d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**customBinding >**</span><span class="sxs-lookup"><span data-stu-id="9a83d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customBinding>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="9a83d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a83d-107">Syntax</span></span>

```xml
<customBinding>
  <binding name="String"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
    <compositeDuplex clientBaseAddress="Uri" />
    <reliableSession acknowledgementInterval="TimeSpan"
                     advancedFlowControl="Boolean"
                     bufferedMessagesQuota="Integer"
                     inactivityTimeout="TimeSpan"
                     maxPendingChannels="Integer"
                     maxRetryCount="Integer"
                     ordered="Boolean" />
    <pnrpPeerResolver />
    <windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
    <sslStreamSecurity requireClientCertificate="Boolean" />
    <transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              contextMode="Cookie"
              defaultProtectionLevel="Sign"
              enableKeyDerivation="false"
              keyEntropyMode="ClientEntropy"
              messageProtectionOrder="SignBeforeEncryptAndEncryptSignature"
              securityVersion="WSSecurityXXX2005">
      <localClientSettings cacheCookies="false"
                           detectReplays="false"
                           maxCookieCachingTime="00:07:24" />
      <localServiceSettings replayCacheSize="9"
                            maxClockSkew="00:00:03"
                            replayWindow="00:07:22.2190000" />
    </security>
    <binaryMessageEncoding maxReadPoolSize="Integer"
                           maxWritePoolSize="Integer"
                           maxSessionSize="Integer" />
    <httpsTransport manualAddressing="Boolean"
                    maxMessageSize="Integer"
                    authenticationScheme="Negotiate"
                    bypassProxyOnLocal="Boolean"
                    hostNameComparisonMode="Exact"
                    mapAddressingHeadersToHttpHeaders="Boolean"
                    proxyaddress="Uri"
                    realm="String"
                    requireClientCertificate="Boolean" />
    <peerTransport manualAddressing="false"
                   maxMessageSize="20002"
                   listenIPAddress="202.10.1.9"
                   messageAuthentication="false"
                   peerNodeAuthenticationMode="None"
                   port="1000" />
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean">
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                            issuedCookieLifeTime="TimeSpan"
                            maxStatefulNegotiations="Integer"
                            replayCacheSize="Integer"
                            maxClockSkew="TimeSpan"
                            negotiationTimeout="TimeSpan"
                            replayWindow="TimeSpan"
                            inactivityTimeout="TimeSpan"
                            sessionKeyRenewalInterval="TimeSpan"
                            sessionKeyRolloverInterval="TimeSpan"
                            reconnectOnTransportFailure="Boolean"
                            maxConcurrentSessions="Integer"
                            timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
    </security>
    <security defaultAlgorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
              authenticationMode="UserNameForAnonymous"
              bootstrapBindingConfiguration="String"
              bootstrapBindingSectionName="String"
              defaultProtectionLevel="None/Sign/EncryptAndSign"
              requireDerivedKeys="Boolean"
              securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
              includeTimestamp="Boolean"
              keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
              messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
              protectTokens="Boolean"
              requireSecurityContextCancellation="Boolean"
              securityVersion=" WSSecurityJan2004/WSSecurityXXX2005"
              requireSignatureConfirmation="Boolean" >
      <localClientSettings cacheCookies="Boolean"
                           detectReplays="Boolean"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           maxCookieCachingTime="TimeSpan"
                           replayWindow="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           timestampValidityDuration="TimeSpan"
                           cookieRenewalThresholdPercentage="Integer" />
      <localServiceSettings detectReplays="Boolean"
                           issuedCookieLifeTime="TimeSpan"
                           maxStatefulNegotiations="Integer"
                           replayCacheSize="Integer"
                           maxClockSkew="TimeSpan"
                           negotiationTimeout="TimeSpan"
                           replayWindow="TimeSpan"
                           inactivityTimeout="TimeSpan"
                           sessionKeyRenewalInterval="TimeSpan"
                           sessionKeyRolloverInterval="TimeSpan"
                           reconnectOnTransportFailure="Boolean"
                           maxConcurrentSessions="Integer"
                           timestampValidityDuration="TimeSpan" />
      <federationParameters trustVersion="WSTrustApr2004/WSTrustFeb2005" />
      <genericIssuedTokenParameters>
        <localIssuerIssuedTokenParameters keyType="SymmetricKey/PublicKey"
                                          keySize="Integer"
                                          tokenType="String" />
        <issuedTokenParametersEndpointAddress address="URI"
                                              bindingConfiguration="String"
                                              binding="String" />
        <issuedTokenClient localIssuerChannelBehaviors="String"
                           cacheIssuedTokens="Boolean"
                           maxIssuedTokenCachingTime="TimeSpan"
                           keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy" />
        <issuedTokenClientBehavior issuerAddress="String"
                                   behaviorConfiguration="String" />
        <issuedTokenClientBehavior address="URI"
                                   bindingConfiguration="String"
                                   binding="String" />
      </genericIssuedTokenParameters>
    </security>
  </binding>
</customBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9a83d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a83d-108">Attributes and Elements</span></span>

<span data-ttu-id="9a83d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a83d-109">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="9a83d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a83d-110">Attributes</span></span>

|<span data-ttu-id="9a83d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="9a83d-111">Attribute</span></span>|<span data-ttu-id="9a83d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a83d-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="9a83d-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="9a83d-113">closeTimeout</span></span>|<span data-ttu-id="9a83d-114">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse.</span><span class="sxs-lookup"><span data-stu-id="9a83d-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9a83d-115">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a83d-116">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9a83d-116">The default is 00:01:00.</span></span>|
|<span data-ttu-id="9a83d-117">name</span><span class="sxs-lookup"><span data-stu-id="9a83d-117">name</span></span>|<span data-ttu-id="9a83d-118">Cadena que contiene el nombre de configuración del enlace.</span><span class="sxs-lookup"><span data-stu-id="9a83d-118">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="9a83d-119">Este valor es una cadena definida por el usuario que actúa como cadena de identificación para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9a83d-119">This value is a user-defined string that acts as the identification string for the custom binding.</span></span> <span data-ttu-id="9a83d-120">A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre.</span><span class="sxs-lookup"><span data-stu-id="9a83d-120">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9a83d-121">Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9a83d-121">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|
|<span data-ttu-id="9a83d-122">openTimeout</span><span class="sxs-lookup"><span data-stu-id="9a83d-122">openTimeout</span></span>|<span data-ttu-id="9a83d-123">Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse.</span><span class="sxs-lookup"><span data-stu-id="9a83d-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9a83d-124">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a83d-125">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9a83d-125">The default is 00:01:00.</span></span>|
|<span data-ttu-id="9a83d-126">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="9a83d-126">receiveTimeout</span></span>|<span data-ttu-id="9a83d-127">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse.</span><span class="sxs-lookup"><span data-stu-id="9a83d-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9a83d-128">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a83d-129">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9a83d-129">The default is 00:01:00.</span></span>|
|<span data-ttu-id="9a83d-130">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="9a83d-130">sendTimeout</span></span>|<span data-ttu-id="9a83d-131">Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse.</span><span class="sxs-lookup"><span data-stu-id="9a83d-131">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9a83d-132">Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-132">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9a83d-133">El valor predeterminado es 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="9a83d-133">The default is 00:01:00.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9a83d-134">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a83d-134">Child Elements</span></span>

|<span data-ttu-id="9a83d-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a83d-135">Element</span></span>|<span data-ttu-id="9a83d-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a83d-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9a83d-137">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="9a83d-137">\<compositeDuplex></span></span>](compositeduplex.md)|<span data-ttu-id="9a83d-138">Especifica la mensajería bidireccional para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9a83d-138">Specifies two-way messaging to the custom binding.</span></span> <span data-ttu-id="9a83d-139">Se usa con los transportes que no permiten comunicaciones dúplex de manera nativa, como, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="9a83d-139">It is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="9a83d-140">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="9a83d-140">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span><br /><br /> <span data-ttu-id="9a83d-141">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="9a83d-141">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="9a83d-142">El atributo `ClientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="9a83d-142">This client address is provided by the `ClientBaseAddress` attribute.</span></span><br /><br /> <span data-ttu-id="9a83d-143">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-143">This element is of type <xref:System.ServiceModel.Configuration.CompositeDuplexElement>.</span></span>|
|[<span data-ttu-id="9a83d-144">\<pnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="9a83d-144">\<pnrpPeerResolver></span></span>](pnrppeerresolver.md)|<span data-ttu-id="9a83d-145">Especifica una resolución de nombre de mismo nivel de protocolo de resolución de nombres de mismo nivel (PNRP).</span><span class="sxs-lookup"><span data-stu-id="9a83d-145">Specifies a Peer Name Resolution Protocol (PNRP) peer name resolver.</span></span> <span data-ttu-id="9a83d-146">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-146">This element is of type <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>.</span></span>|
|[<span data-ttu-id="9a83d-147">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="9a83d-147">\<reliableSession></span></span>](reliablesession.md)|<span data-ttu-id="9a83d-148">Especifica el valor para la mensajería de confianza de WS.</span><span class="sxs-lookup"><span data-stu-id="9a83d-148">Specifies the setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="9a83d-149">Cuando este elemento se agrega a un enlace personalizado, el canal resultante puede admitir las convicciones de la entrega exactamente una vez.</span><span class="sxs-lookup"><span data-stu-id="9a83d-149">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span> <span data-ttu-id="9a83d-150">Este elemento es del tipo <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-150">This element is of type <xref:System.ServiceModel.Configuration.ReliableSessionElement>.</span></span>|
|[<span data-ttu-id="9a83d-151">> de seguridad de \<</span><span class="sxs-lookup"><span data-stu-id="9a83d-151">\<security></span></span>](security-of-custombinding.md)|<span data-ttu-id="9a83d-152">Especifica las opciones de seguridad del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9a83d-152">Specifies the options for security of the custom binding.</span></span> <span data-ttu-id="9a83d-153">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-153">This element is of type <xref:System.ServiceModel.Configuration.SecurityElement>.</span></span>|
|[<span data-ttu-id="9a83d-154">\<sección sslstreamsecurity ></span><span class="sxs-lookup"><span data-stu-id="9a83d-154">\<sslStreamSecurity></span></span>](sslstreamsecurity.md)|<span data-ttu-id="9a83d-155">Especifica la configuración de seguridad para un enlace de secuencia SSL.</span><span class="sxs-lookup"><span data-stu-id="9a83d-155">Specifies the security settings for a SSL stream binding.</span></span> <span data-ttu-id="9a83d-156">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-156">This element is of type <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>.</span></span>|
|[<span data-ttu-id="9a83d-157">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="9a83d-157">\<transactionFlow></span></span>](transactionflow.md)|<span data-ttu-id="9a83d-158">Especifica que el enlace soporta el flujo de transacción, y el protocolo que va a ser utilizado por el atributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="9a83d-158">Specifies that the binding supports transaction flow, and the protocol to be used by the `transactionProtocol` attribute.</span></span> <span data-ttu-id="9a83d-159">Este elemento es del tipo <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-159">This element is of type <xref:System.ServiceModel.Configuration.TransactionFlowElement>.</span></span>|
|[<span data-ttu-id="9a83d-160">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="9a83d-160">\<windowsStreamSecurity></span></span>](windowsstreamsecurity.md)|<span data-ttu-id="9a83d-161">Especifica las opciones de seguridad de transmisión del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9a83d-161">Specifies the options for streaming security of the custom binding.</span></span> <span data-ttu-id="9a83d-162">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9a83d-162">This element is of type <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9a83d-163">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a83d-163">Parent Elements</span></span>

|<span data-ttu-id="9a83d-164">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a83d-164">Element</span></span>|<span data-ttu-id="9a83d-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a83d-165">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="9a83d-166">enlaces</span><span class="sxs-lookup"><span data-stu-id="9a83d-166">bindings</span></span>|<span data-ttu-id="9a83d-167">Contiene todos los enlaces para las aplicaciones de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="9a83d-167">Contains all bindings for Windows Communication Foundation applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9a83d-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a83d-168">Remarks</span></span>

<span data-ttu-id="9a83d-169">Los enlaces personalizados proporcionan el control completo sobre la pila de mensajería WCF.</span><span class="sxs-lookup"><span data-stu-id="9a83d-169">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="9a83d-170">Los enlaces diseñados especialmente se pueden crear agregando los elementos de configuración para las entidades concretas.</span><span class="sxs-lookup"><span data-stu-id="9a83d-170">Special tailored bindings can be created my adding the configuration elements for specific entities.</span></span> <span data-ttu-id="9a83d-171">Por ejemplo, el usuario puede combinar la sección `httpsTransport`, sección `reliableSession` y la sección `security` para crear https fiables y seguros basados en el enlace.</span><span class="sxs-lookup"><span data-stu-id="9a83d-171">For example, the user can combine the `httpsTransport` section, `reliableSession` section and the `security` section to create a reliable and secure https based binding.</span></span>

<span data-ttu-id="9a83d-172">Un enlace individual define la pila de mensajes mediante la especificación de los elementos de configuración para los elementos de la pila en el orden que aparecen en la pila.</span><span class="sxs-lookup"><span data-stu-id="9a83d-172">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="9a83d-173">Cada elemento define y configura un elemento de la pila.</span><span class="sxs-lookup"><span data-stu-id="9a83d-173">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="9a83d-174">Debe haber un único elemento de transporte en cada enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9a83d-174">There must be one and only one transport element in each custom binding.</span></span> <span data-ttu-id="9a83d-175">Sin este elemento, la pila de la mensajería está incompleta.</span><span class="sxs-lookup"><span data-stu-id="9a83d-175">Without this element, the messaging stack is incomplete.</span></span>

<span data-ttu-id="9a83d-176">El orden de aparición de los elementos en la pila es importante, porque es el orden en el que las operaciones se aplican al mensaje.</span><span class="sxs-lookup"><span data-stu-id="9a83d-176">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="9a83d-177">El orden recomendado de elementos de pila es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a83d-177">The recommended order of stack elements is the following:</span></span>

1. <span data-ttu-id="9a83d-178">Transacciones (opcional)</span><span class="sxs-lookup"><span data-stu-id="9a83d-178">Transactions (optional)</span></span>

2. <span data-ttu-id="9a83d-179">Mensajería de confianza (opcional)</span><span class="sxs-lookup"><span data-stu-id="9a83d-179">Reliable Messaging (optional)</span></span>

3. <span data-ttu-id="9a83d-180">Seguridad (opcional)</span><span class="sxs-lookup"><span data-stu-id="9a83d-180">Security (optional)</span></span>

4. <span data-ttu-id="9a83d-181">Transporte</span><span class="sxs-lookup"><span data-stu-id="9a83d-181">Transport</span></span>

5. <span data-ttu-id="9a83d-182">Codificador (opcional)</span><span class="sxs-lookup"><span data-stu-id="9a83d-182">Encoder (optional)</span></span>

<span data-ttu-id="9a83d-183">Utilice un enlace personalizado cuando uno de los enlaces proporcionados por el sistema no cumpla los requisitos del servicio.</span><span class="sxs-lookup"><span data-stu-id="9a83d-183">Use a custom binding when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="9a83d-184">Se pudo utilizar un enlace personalizado, por ejemplo, para habilitar el uso de un nuevo transporte o un nuevo codificador en un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="9a83d-184">A custom binding could be used, for example, to enable the use of a new transport or a new encoder at a service endpoint.</span></span>

<span data-ttu-id="9a83d-185">Un enlace personalizado se construye utilizando uno de <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> de una colección de elementos de enlace que se apilan en un orden específico:</span><span class="sxs-lookup"><span data-stu-id="9a83d-185">A custom binding is constructed using one of the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="9a83d-186">En la parte superior hay un <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> opcional que permite el flujo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9a83d-186">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> that allows flowing transactions.</span></span>

- <span data-ttu-id="9a83d-187">A continuación hay un <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> opcional que proporciona una sesión y un mecanismo de orden, como se define en la especificación WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="9a83d-187">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> that provides a session and ordering mechanism as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="9a83d-188">Esta noción de sesión puede cruzar SOAP y transportar intermediarios.</span><span class="sxs-lookup"><span data-stu-id="9a83d-188">This notion of a session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="9a83d-189">A continuación hay un elemento de enlace de seguridad opcional que proporciona las características de seguridad como la autorización, autenticación, protección y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="9a83d-189">Next is an optional security binding element that provides security features like authorization, authentication, protection, and confidentiality.</span></span> <span data-ttu-id="9a83d-190">Windows Communication Foundation (WCF) proporciona los siguientes elementos de enlace de seguridad:</span><span class="sxs-lookup"><span data-stu-id="9a83d-190">The following security binding elements are provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.SecurityBindingElement>

  - <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>

- <span data-ttu-id="9a83d-191">A continuación están los modelos de mensaje opcionales especificados por elementos de enlace:</span><span class="sxs-lookup"><span data-stu-id="9a83d-191">Next are the optional message-patterns specified by binding elements:</span></span>

- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>

- <span data-ttu-id="9a83d-192">A continuación, se encuentran los elementos de enlace de asistentes/actualizaciones de transporte opcionales:</span><span class="sxs-lookup"><span data-stu-id="9a83d-192">Next are the optional transport upgrades/helpers binding elements:</span></span>

  - <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="9a83d-193">A continuación hay un elemento de enlace de codificación del mensaje requerido.</span><span class="sxs-lookup"><span data-stu-id="9a83d-193">Next is a required message encoding binding element.</span></span> <span data-ttu-id="9a83d-194">Puede utilizar su propio transporte o utilizar uno de los siguientes enlaces de codificación del mensaje:</span><span class="sxs-lookup"><span data-stu-id="9a83d-194">You can use your own transport or use one of the following message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

- <span data-ttu-id="9a83d-195">En la parte inferior hay un elemento de transporte necesario.</span><span class="sxs-lookup"><span data-stu-id="9a83d-195">At the bottom is a required transport element.</span></span> <span data-ttu-id="9a83d-196">Puede utilizar su propio transporte o usar uno de los elementos de enlace de transporte proporcionados por Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="9a83d-196">You can use your own transport or use one of transport binding elements provided by Windows Communication Foundation (WCF):</span></span>

  - <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

  - <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

  - <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

  - <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

  - <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

<span data-ttu-id="9a83d-197">La tabla siguiente resume las opciones de cada nivel.</span><span class="sxs-lookup"><span data-stu-id="9a83d-197">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="9a83d-198">Capa</span><span class="sxs-lookup"><span data-stu-id="9a83d-198">Layer</span></span>|<span data-ttu-id="9a83d-199">Opciones</span><span class="sxs-lookup"><span data-stu-id="9a83d-199">Options</span></span>|<span data-ttu-id="9a83d-200">Requerido</span><span class="sxs-lookup"><span data-stu-id="9a83d-200">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="9a83d-201">Flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="9a83d-201">Transaction Flow</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="9a83d-202">No</span><span class="sxs-lookup"><span data-stu-id="9a83d-202">No</span></span>|
|<span data-ttu-id="9a83d-203">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="9a83d-203">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="9a83d-204">No</span><span class="sxs-lookup"><span data-stu-id="9a83d-204">No</span></span>|
|<span data-ttu-id="9a83d-205">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9a83d-205">Security</span></span>|<span data-ttu-id="9a83d-206">Simétrico, Asimétrico, Nivel de transporte</span><span class="sxs-lookup"><span data-stu-id="9a83d-206">Symmetric, Asymmetric, Transport-Level</span></span>|<span data-ttu-id="9a83d-207">No</span><span class="sxs-lookup"><span data-stu-id="9a83d-207">No</span></span>|
|<span data-ttu-id="9a83d-208">Cambiar forma</span><span class="sxs-lookup"><span data-stu-id="9a83d-208">Shape Change</span></span>|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>|<span data-ttu-id="9a83d-209">No</span><span class="sxs-lookup"><span data-stu-id="9a83d-209">No</span></span>|
|<span data-ttu-id="9a83d-210">Actualizaciones de transporte</span><span class="sxs-lookup"><span data-stu-id="9a83d-210">Transport Upgrades</span></span>|<span data-ttu-id="9a83d-211">Secuencia de SSL, secuencia de Windows, Resolución del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="9a83d-211">SSL stream, Windows stream, Peer Resolver</span></span>|<span data-ttu-id="9a83d-212">No</span><span class="sxs-lookup"><span data-stu-id="9a83d-212">No</span></span>|
|<span data-ttu-id="9a83d-213">Codificación</span><span class="sxs-lookup"><span data-stu-id="9a83d-213">Encoding</span></span>|<span data-ttu-id="9a83d-214">Texto, binario, MTOM, personalizado</span><span class="sxs-lookup"><span data-stu-id="9a83d-214">Text, Binary, MTOM, Custom</span></span>|<span data-ttu-id="9a83d-215">Sí</span><span class="sxs-lookup"><span data-stu-id="9a83d-215">Yes</span></span>|
|<span data-ttu-id="9a83d-216">Transporte</span><span class="sxs-lookup"><span data-stu-id="9a83d-216">Transport</span></span>|<span data-ttu-id="9a83d-217">TCP, canalizaciones con nombre, http, HTTPS, versiones de MSMQ, personalizado</span><span class="sxs-lookup"><span data-stu-id="9a83d-217">TCP, Named Pipes, HTTP, HTTPS, flavors of MSMQ, Custom</span></span>|<span data-ttu-id="9a83d-218">Sí</span><span class="sxs-lookup"><span data-stu-id="9a83d-218">Yes</span></span>|

<span data-ttu-id="9a83d-219">Además, puede definir sus propios elementos de enlace e insertarlos entre cualquiera de las capas definidas anteriores.</span><span class="sxs-lookup"><span data-stu-id="9a83d-219">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

<span data-ttu-id="9a83d-220">Para obtener información sobre cómo utilizar un enlace personalizado para modificar un enlace proporcionado por el sistema, consulte [Cómo: personalizar un enlace proporcionado por el sistema](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="9a83d-220">For a discussion on how to use a custom binding to modify a system-provided binding, see [How to: Customize a System-Provided Binding](../../../wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9a83d-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a83d-221">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.Configuration.BindingsSection>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9a83d-222">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="9a83d-222">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="9a83d-223">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9a83d-223">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9a83d-224">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9a83d-224">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9a83d-225">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9a83d-225">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9a83d-226">customBinding (elemento)</span><span class="sxs-lookup"><span data-stu-id="9a83d-226">customBinding Element</span></span>](custombinding.md)
- [<span data-ttu-id="9a83d-227">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9a83d-227">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9a83d-228">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9a83d-228">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9a83d-229">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9a83d-229">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
