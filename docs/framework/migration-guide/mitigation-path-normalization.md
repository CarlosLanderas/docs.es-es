---
title: 'Mitigación: normalización de la ruta de acceso'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 1e7b540975b84320d099ca004df5b6a87aa60f6a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457887"
---
# <a name="mitigation-path-normalization"></a>Mitigación: normalización de la ruta de acceso
A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, la normalización de la ruta de acceso en .NET Framework ha cambiado.  
  
## <a name="what-is-path-normalization"></a>¿Qué es la normalización de la ruta de acceso?  
 La normalización de una ruta de acceso implica la modificación de la cadena que identifica a una ruta de acceso o archivo de manera que sea conforme con una ruta de acceso válida en el sistema operativo de destino. La normalización implica normalmente:  
  
- La canonicalización del componente y los separadores de directorios.  
  
- La aplicación del directorio actual en una ruta de acceso relativa.  
  
- La evaluación del directorio relativo (`.`) o el directorio principal (`..`) en una ruta de acceso.  
  
- El recorte de caracteres especificados.  
  
## <a name="the-changes"></a>Cambios  
 A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, la normalización de la ruta de acceso ha cambiado de las siguientes maneras:  
  
- El tiempo de ejecución se aplaza para la función [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo con el objetivo de normalizar las rutas de acceso.  
  
- La normalización ya no implica el recorte del final de los segmentos de directorio (como el espacio al final de un nombre de directorio).  
  
- Compatibilidad de la sintaxis de la ruta de acceso del dispositivo con plena confianza ( incluido `\\.\`) y, para las API de E/S del archivo en mscorlib.dll, `\\?\`.  
  
- El tiempo de ejecución o valida las rutas de acceso de la sintaxis del dispositivo.  
  
- Es compatible el uso de la sintaxis del dispositivo para obtener acceso a los flujos de datos alternativos.  
  
## <a name="impact"></a>Impacto  

Para las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior, estos cambios están activados de forma predeterminada. Deben mejorar el rendimiento a la vez que permiten a los métodos obtener acceso a las rutas de acceso a las que no se podía obtener acceso anteriormente.  
  
Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o posterior, no se ven afectadas por este cambio.  
  
## <a name="mitigation"></a>Mitigación  
 Las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior pueden optar por no recibir este cambio y usar la normalización heredada agregando lo siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
Las aplicaciones que tienen como destino .NET Framework 4.6.1 o versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, pueden habilitar los cambios en la normalización de rutas de acceso agregando la línea siguiente a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de aplicaciones](application-compatibility.md)
