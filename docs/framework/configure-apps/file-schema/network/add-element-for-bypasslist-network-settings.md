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
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="cd4f4-102">\<agregar > elemento para BypassList (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="cd4f4-103">Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[<span data-ttu-id="cd4f4-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="cd4f4-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cd4f4-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="cd4f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>  
<span data-ttu-id="cd4f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<BypassList >** ](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>  
<span data-ttu-id="cd4f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd4f4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd4f4-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd4f4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cd4f4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cd4f4-111">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd4f4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cd4f4-112">Attributes</span></span>  
  
|<span data-ttu-id="cd4f4-113">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-113">**Attribute**</span></span>|<span data-ttu-id="cd4f4-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="cd4f4-115">**address**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-115">**address**</span></span>|<span data-ttu-id="cd4f4-116">Expresión regular que describe una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd4f4-117">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="cd4f4-117">Child Elements</span></span>  
 <span data-ttu-id="cd4f4-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd4f4-119">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="cd4f4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cd4f4-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-120">**Element**</span></span>|<span data-ttu-id="cd4f4-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cd4f4-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="cd4f4-122">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="cd4f4-123">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd4f4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd4f4-124">Remarks</span></span>  
 <span data-ttu-id="cd4f4-125">El elemento `add` inserta expresiones regulares que describen las direcciones IP o los nombres de servidor DNS en la lista de direcciones que omiten un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="cd4f4-126">El valor del atributo `address` debe ser una expresión regular que describe un conjunto de direcciones IP o nombres de host.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="cd4f4-127">Debe tener precaución al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="cd4f4-128">La expresión regular "[a-z] +\\. contoso\\. com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="cd4f4-129">Para que solo coincida con un host del dominio contoso.com, use un delimitador ("$"): "[a-z] +\\. contoso\\. com $".</span><span class="sxs-lookup"><span data-stu-id="cd4f4-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="cd4f4-130">Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cd4f4-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cd4f4-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="cd4f4-131">Configuration Files</span></span>  
 <span data-ttu-id="cd4f4-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cd4f4-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd4f4-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd4f4-133">Example</span></span>  
 <span data-ttu-id="cd4f4-134">En el ejemplo siguiente se agregan dos direcciones a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="cd4f4-135">El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuya dirección IP comienza con 192,168.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd4f4-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd4f4-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="cd4f4-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="cd4f4-137">Network Settings Schema</span></span>](index.md)
