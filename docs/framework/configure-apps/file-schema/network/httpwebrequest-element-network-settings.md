---
title: Elemento <httpWebRequest> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: d33dadc14510feb00e05ca557b507b0cf8fa0dd0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087458"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="325e2-102">\<elemento > httpWebRequest (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="325e2-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="325e2-103">Personaliza los parámetros de la solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="325e2-103">Customizes Web request parameters.</span></span>  

<span data-ttu-id="325e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="325e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="325e2-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="325e2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="325e2-106">&nbsp;&nbsp;[ \**&nbsp;&nbsp;\<\** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="325e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\</span></span>
<span data-ttu-id="325e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpWebRequest >**</span><span class="sxs-lookup"><span data-stu-id="325e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**</span></span>

## <a name="syntax"></a><span data-ttu-id="325e2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="325e2-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="325e2-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="325e2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="325e2-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="325e2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="325e2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="325e2-111">Attributes</span></span>  
  
|<span data-ttu-id="325e2-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="325e2-112">**Attribute**</span></span>|<span data-ttu-id="325e2-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="325e2-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="325e2-114">Especifica la longitud máxima de un encabezado de respuesta, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="325e2-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="325e2-115">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="325e2-115">The default is 64.</span></span> <span data-ttu-id="325e2-116">Un valor de-1 indica que no se impondrá ningún límite de tamaño en los encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="325e2-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="325e2-117">Especifica la longitud máxima de una respuesta de error, en kilobytes.</span><span class="sxs-lookup"><span data-stu-id="325e2-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="325e2-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="325e2-118">The default is 64.</span></span> <span data-ttu-id="325e2-119">Un valor de-1 indica que no se impondrá ningún límite de tamaño en la respuesta de error.</span><span class="sxs-lookup"><span data-stu-id="325e2-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="325e2-120">Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado, en bytes.</span><span class="sxs-lookup"><span data-stu-id="325e2-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="325e2-121">El valor predeterminado es -1.</span><span class="sxs-lookup"><span data-stu-id="325e2-121">The default is -1.</span></span> <span data-ttu-id="325e2-122">Un valor de-1 indica que no se impondrá ningún límite de tamaño en la carga.</span><span class="sxs-lookup"><span data-stu-id="325e2-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="325e2-123">Especifica si está habilitado el análisis de encabezados no seguros.</span><span class="sxs-lookup"><span data-stu-id="325e2-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="325e2-124">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="325e2-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="325e2-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="325e2-125">Child Elements</span></span>  
 <span data-ttu-id="325e2-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="325e2-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="325e2-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="325e2-127">Parent Elements</span></span>  
  
|<span data-ttu-id="325e2-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="325e2-128">**Element**</span></span>|<span data-ttu-id="325e2-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="325e2-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="325e2-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="325e2-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="325e2-131">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="325e2-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="325e2-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="325e2-132">Remarks</span></span>  
 <span data-ttu-id="325e2-133">De forma predeterminada, el .NET Framework aplica estrictamente la RFC 2616 para el análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="325e2-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="325e2-134">Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, lo que hará que el método <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> inicie una <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="325e2-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="325e2-135">Si **useUnsafeHeaderParsing** se establece en **true**, no se producirá <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> en este caso; sin embargo, la aplicación será vulnerable a varias formas de ataques de análisis de URI.</span><span class="sxs-lookup"><span data-stu-id="325e2-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="325e2-136">La mejor solución es cambiar el servidor para que la respuesta no incluya caracteres de control.</span><span class="sxs-lookup"><span data-stu-id="325e2-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="325e2-137">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="325e2-137">Configuration Files</span></span>  
 <span data-ttu-id="325e2-138">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="325e2-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="325e2-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="325e2-139">Example</span></span>  
 <span data-ttu-id="325e2-140">En el ejemplo siguiente se muestra cómo especificar una longitud de encabezado máxima mayor que la normal.</span><span class="sxs-lookup"><span data-stu-id="325e2-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="325e2-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="325e2-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="325e2-142">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="325e2-142">Network Settings Schema</span></span>](index.md)
