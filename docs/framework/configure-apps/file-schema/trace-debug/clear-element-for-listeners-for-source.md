---
title: <clear> elemento de <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 4567f236397435e89371ca4c80730ff964fddd21
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088930"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="c980f-102">\<borrar > elemento para \<agentes de escucha > para \<origen ></span><span class="sxs-lookup"><span data-stu-id="c980f-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="c980f-103">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c980f-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="c980f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c980f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c980f-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c980f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="c980f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<orígenes**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="c980f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="c980f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**origen**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="c980f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="c980f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-source.md) ></span><span class="sxs-lookup"><span data-stu-id="c980f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="c980f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**clear >**</span><span class="sxs-lookup"><span data-stu-id="c980f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c980f-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c980f-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c980f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c980f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c980f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c980f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c980f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="c980f-113">Attributes</span></span>  
 <span data-ttu-id="c980f-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c980f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c980f-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c980f-115">Child Elements</span></span>  
 <span data-ttu-id="c980f-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c980f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c980f-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c980f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c980f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c980f-118">Element</span></span>|<span data-ttu-id="c980f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c980f-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c980f-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c980f-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c980f-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c980f-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="c980f-122">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c980f-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="c980f-123">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c980f-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="c980f-124">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c980f-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c980f-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c980f-125">Remarks</span></span>  
 <span data-ttu-id="c980f-126">El elemento `<clear>` quita todos los agentes de escucha de la colección de `Listeners` para un origen de seguimiento, incluido el <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="c980f-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="c980f-127">Puede usar el elemento `<clear>` antes de usar el elemento `<add>` para estar seguro de que no hay ningún otro agente de escucha activo en la colección.</span><span class="sxs-lookup"><span data-stu-id="c980f-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c980f-128">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c980f-128">Configuration File</span></span>  
 <span data-ttu-id="c980f-129">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c980f-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c980f-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c980f-130">Example</span></span>  
 <span data-ttu-id="c980f-131">En el ejemplo siguiente se muestra cómo utilizar el elemento `<clear>` antes de utilizar los elementos `<add>` para agregar los agentes de escucha `console` y `textListener` a la colección de `Listeners` para la `TraceSourceApp`de origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c980f-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="c980f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c980f-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="c980f-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="c980f-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c980f-134">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c980f-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
