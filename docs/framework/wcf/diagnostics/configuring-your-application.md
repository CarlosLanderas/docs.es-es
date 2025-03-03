---
title: Configuración de su aplicación
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 4e19e4d0ecb6bc90402f99dddd280ee1dbcf7ea0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798152"
---
# <a name="configuring-your-application"></a>Configuración de su aplicación
Windows Communication Foundation (WCF) usa el sistema de configuración de .NET y permite configurar los servicios en el ámbito de la máquina y de la aplicación.  
  
 Las opciones de configuración definidas por WCF se encuentran `<system.serviceModel>` en el grupo de secciones. Para obtener más información sobre cómo configurar un servicio WCF, vea los temas siguientes:  
  
- [Configuración de servicios](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Los valores de configuración definidos por la aplicación se definen en el grupo de la sección `<appSettings>`. Para obtener más información sobre la configuración de la aplicación en los archivos de configuración de .net, consulte [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Utilización del editor de configuración  
 La [herramienta editor de configuración de WCF (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md) permite a los administradores y desarrolladores crear y modificar la configuración de los servicios WCF mediante una interfaz gráfica de usuario. Con esta herramienta, puede administrar la configuración de enlaces, comportamientos, servicios y diagnósticos de WCF sin tener que editar directamente los archivos de configuración XML.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Edición de los archivos de configuración en Visual Studio  
 Para editar el archivo de configuración de un proyecto de servicio de WCF en Visual Studio, haga clic con el botón derecho en él en **Explorador de soluciones** y elija el elemento de menú contextual **Editar configuración de WCF** . Esto inicia la [herramienta editor de configuración (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
> Si edita el archivo de configuración de un proyecto de servicio Web WCF en Visual Studio haciendo clic en él con el botón secundario en **Explorador de soluciones**, observe que falta el elemento de menú contextual **Editar configuración de WCF** . Para solucionar este problema, haga clic en el menú **herramientas** y elija **Editor de configuración de servicio WCF**. Después, puede hacer clic con el botón secundario en un archivo de configuración y usar el elemento de menú contextual **Editar configuración de WCF** .  
  
## <a name="see-also"></a>Vea también

- [Herramienta del editor de configuración (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Configuración de servicios](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
