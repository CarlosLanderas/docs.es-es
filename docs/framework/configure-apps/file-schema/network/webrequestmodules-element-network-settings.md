---
title: Elemento <webRequestModules> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: e119d9ce1f8bb6f07f8050612550db459a2f065c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697459"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="ab208-102">\<el elemento > webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="ab208-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="ab208-103">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="ab208-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[<span data-ttu-id="ab208-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ab208-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ab208-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ab208-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="ab208-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="ab208-106">&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab208-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab208-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab208-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ab208-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ab208-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ab208-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab208-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ab208-110">Attributes</span></span>  
 <span data-ttu-id="ab208-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ab208-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ab208-112">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="ab208-112">Child Elements</span></span>  
  
|<span data-ttu-id="ab208-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="ab208-113">**Element**</span></span>|<span data-ttu-id="ab208-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ab208-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ab208-115">add</span><span class="sxs-lookup"><span data-stu-id="ab208-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ab208-116">Agrega un módulo de solicitud web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab208-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="ab208-117">clear</span><span class="sxs-lookup"><span data-stu-id="ab208-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ab208-118">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab208-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="ab208-119">remove</span><span class="sxs-lookup"><span data-stu-id="ab208-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="ab208-120">Quita un módulo de solicitud web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab208-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ab208-121">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="ab208-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ab208-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="ab208-122">**Element**</span></span>|<span data-ttu-id="ab208-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ab208-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ab208-124">system.net</span><span class="sxs-lookup"><span data-stu-id="ab208-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="ab208-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="ab208-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab208-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab208-126">Remarks</span></span>  
 <span data-ttu-id="ab208-127">El elemento `webRequestModules` registra los descendientes de la clase <xref:System.Net.WebRequest> para controlar las solicitudes de información a los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="ab208-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="ab208-128">Los módulos de solicitud Web deben implementar la interfaz <xref:System.Net.IWebRequestCreate>.</span><span class="sxs-lookup"><span data-stu-id="ab208-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="ab208-129">El .NET Framework incluye módulos de solicitud Web para los URI que comienzan con `http://`, `https://`y `file://`.</span><span class="sxs-lookup"><span data-stu-id="ab208-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="ab208-130">Solo puede invalidar los módulos predeterminados Si registra un módulo personalizado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ab208-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ab208-131">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ab208-131">Configuration Files</span></span>  
 <span data-ttu-id="ab208-132">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ab208-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab208-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab208-133">Example</span></span>  
 <span data-ttu-id="ab208-134">En el ejemplo siguiente se registra el módulo HTTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ab208-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="ab208-135">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="ab208-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab208-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab208-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="ab208-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="ab208-137">Network Settings Schema</span></span>](index.md)
