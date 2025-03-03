---
title: Procedimiento para crear un servicio que emplee un validador de certificado personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: b2407c293de7f11b90586f5a55bd759a4ea734aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795681"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a>Procedimiento para crear un servicio que emplee un validador de certificado personalizado
En este tema se muestra cómo implementar un validador del certificado personalizado y cómo configurar el cliente o credenciales del servicio para reemplazar la lógica de validación de certificado predeterminada por el validador del certificado personalizado.  
  
 Si el certificado X. 509 se usa para autenticar un cliente o servicio, Windows Communication Foundation (WCF) utiliza de forma predeterminada el almacén de certificados de Windows y la API de cifrado para validar el certificado y para asegurarse de que es de confianza. La funcionalidad integrada de validación del certificado no es suficiente y a veces se debe cambiar. WCF proporciona una manera fácil de cambiar la lógica de validación, ya que permite a los usuarios agregar un validador de certificado personalizado. Si se especifica un validador de certificado personalizado, WCF no utiliza la lógica de validación de certificado integrada, sino que se basa en el validador personalizado en su lugar.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-a-custom-certificate-validator"></a>Crear un validador de certificado personalizado  
  
1. Defina una clase nueva derivada a partir de <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
2. Implemente el método <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> abstracto. El certificado que se debe validar se pasa como un argumento al método. Si el certificado pasado no es válido según la lógica de la validación, este método inicia <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>. Si el certificado es válido, el método vuelve al autor de la llamada.  
  
    > [!NOTE]
    > Para devolver errores de autenticación al cliente, genere una <xref:System.ServiceModel.FaultException> en el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a>Especificar un validador de certificado personalizado en configuración de servicio  
  
1. Agregue un [ \<elemento Behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) y un [ \<> serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) al elemento [ \<> de System. ServiceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) .  
  
2. Agregue un [ \<> de comportamiento](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) y establezca `name` el atributo en un valor adecuado.  
  
3. Agregue [ \<](../../configure-apps/file-schema/wcf/servicecredentials.md) un`<behavior>` > serviceCredentials al elemento.  
  
4. Agregue un elemento `<clientCertificate>` al elemento `<serviceCredentials>`.  
  
5. Agregue [ \<](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) un`<clientCertificate>` > de autenticación al elemento.  
  
6. Defina el atributo `customCertificateValidatorType` en el tipo de validador. El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.  
  
7. Defina el atributo `certificateValidationMode` a `Custom`.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a>Especificar un validador de certificado personalizado mediante la configuración del cliente  
  
1. Agregue un [ \<elemento Behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) y un [ \<> serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) al elemento [ \<> de System. ServiceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) .  
  
2. Agregue un [ \<elemento > de endpointBehaviors](../../configure-apps/file-schema/wcf/endpointbehaviors.md) .  
  
3. Agregue un elemento `<behavior>` y establezca el atributo `name` en un valor adecuado.  
  
4. Agregue un elemento de [ \<> clientCredentials](../../configure-apps/file-schema/wcf/clientcredentials.md) .  
  
5. Agregue un [ \<> serviceCertificate](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).  
  
6. Agregue un [ \<> de autenticación](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) como se muestra en el ejemplo siguiente.  
  
7. Defina el atributo `customCertificateValidatorType` en el tipo de validador.  
  
8. Defina el atributo `certificateValidationMode` a `Custom`. El ejemplo siguiente define el atributo en el espacio de nombres y nombre del tipo.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"   
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a>Especificar un validador de certificado personalizado mediante el código en el servicio  
  
1. Especifique el validador de certificado personalizado en la propiedad <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>. Puede obtener acceso a las credenciales de servicio mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.  
  
2. Establezca la propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a>Especificar un validador de certificado personalizado mediante el código en el cliente  
  
1. Especifique el validador de certificado personalizado mediante la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>. Puede obtener acceso a las credenciales de cliente mediante la propiedad <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>. (La clase de cliente generada por la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) siempre deriva de la <xref:System.ServiceModel.ClientBase%601> clase).  
  
2. Establezca la propiedad <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>DESCRIPCIÓN  
 El ejemplo siguiente muestra una implementación de un validador de certificado personalizado y su uso en el servicio.  
  
### <a name="code"></a>Código  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
