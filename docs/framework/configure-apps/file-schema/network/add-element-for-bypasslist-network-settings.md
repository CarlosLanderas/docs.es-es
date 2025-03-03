---
title: Elemento <add> para bypasslist (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 1db0ba3b0a213de1175e6e0cee347753d2a413b7
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699611"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<agregar > elemento para BypassList (configuración de red)
Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BypassList >** ](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|**address**|Expresión regular que describe una dirección IP o un nombre DNS.|  
  
### <a name="child-elements"></a>Elemento secundario  
 Ninguno.  
  
### <a name="parent-elements"></a>Elemento principal  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `add` inserta expresiones regulares que describen las direcciones IP o los nombres de servidor DNS en la lista de direcciones que omiten un servidor proxy.  
  
 El valor del atributo `address` debe ser una expresión regular que describe un conjunto de direcciones IP o nombres de host.  
  
 Debe tener precaución al especificar una expresión regular para este elemento. La expresión regular "[a-z] +\\. contoso\\. com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com. Para que solo coincida con un host del dominio contoso.com, use un delimitador ("$"): "[a-z] +\\. contoso\\. com $".  
  
 Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se agregan dos direcciones a la lista de omisiones. El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuya dirección IP comienza con 192,168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
