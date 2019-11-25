---
title: <switches> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 4aeb3cb0cd75f0fb27e3b359b86da61a77b491c7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088801"
---
# <a name="switches-element"></a><span data-ttu-id="24800-102">\<modificadores > elemento</span><span class="sxs-lookup"><span data-stu-id="24800-102">\<switches> Element</span></span>
<span data-ttu-id="24800-103">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="24800-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="24800-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="24800-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="24800-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="24800-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="24800-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<modificadores** ></span><span class="sxs-lookup"><span data-stu-id="24800-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="24800-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24800-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24800-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="24800-108">Attributes and Elements</span></span>  
 <span data-ttu-id="24800-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="24800-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24800-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="24800-110">Attributes</span></span>  
 <span data-ttu-id="24800-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="24800-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="24800-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="24800-112">Child Elements</span></span>  
  
|<span data-ttu-id="24800-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="24800-113">Element</span></span>|<span data-ttu-id="24800-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="24800-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24800-115">\<add></span><span class="sxs-lookup"><span data-stu-id="24800-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="24800-116">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="24800-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24800-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="24800-117">Parent Elements</span></span>  
  
|<span data-ttu-id="24800-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="24800-118">Element</span></span>|<span data-ttu-id="24800-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="24800-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="24800-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24800-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="24800-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="24800-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24800-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24800-122">Remarks</span></span>  
 <span data-ttu-id="24800-123">Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="24800-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="24800-124">Si el modificador es un <xref:System.Diagnostics.BooleanSwitch>, puede activarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="24800-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="24800-125">Si el modificador es un <xref:System.Diagnostics.TraceSwitch>, puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24800-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24800-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24800-126">Example</span></span>  
 <span data-ttu-id="24800-127">En el ejemplo siguiente se muestra cómo utilizar el elemento **\<modificador >** para establecer el modificador de `General` seguimiento en el nivel de <xref:System.Diagnostics.TraceLevel> y habilitar el modificador de seguimiento booleano `Data`.</span><span class="sxs-lookup"><span data-stu-id="24800-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24800-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="24800-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="24800-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="24800-129">Trace and Debug Settings Schema</span></span>](index.md)
