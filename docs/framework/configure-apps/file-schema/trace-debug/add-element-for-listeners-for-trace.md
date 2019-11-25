---
title: <add> elemento de <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: eb3e9cf4a6d138998cfde865cda8ed4146be26d0
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088985"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="813b2-102">\<agregar > elemento para \<agentes de escucha > para \<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="813b2-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="813b2-103">Agrega un agente de escucha a la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="813b2-103">Adds a listener to the **Listeners** collection.</span></span>  

<span data-ttu-id="813b2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="813b2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="813b2-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="813b2-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="813b2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](trace-element.md) > de seguimiento</span><span class="sxs-lookup"><span data-stu-id="813b2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="813b2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-trace.md) ></span><span class="sxs-lookup"><span data-stu-id="813b2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="813b2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**</span><span class="sxs-lookup"><span data-stu-id="813b2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="813b2-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="813b2-109">Syntax</span></span>  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="813b2-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="813b2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="813b2-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="813b2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="813b2-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="813b2-112">Attributes</span></span>  
  
|<span data-ttu-id="813b2-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="813b2-113">Attribute</span></span>|<span data-ttu-id="813b2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="813b2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="813b2-115">**type**</span><span class="sxs-lookup"><span data-stu-id="813b2-115">**type**</span></span>|<span data-ttu-id="813b2-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="813b2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="813b2-117">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="813b2-117">Specifies the type of the listener.</span></span> <span data-ttu-id="813b2-118">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="813b2-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="813b2-119">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="813b2-119">**initializeData**</span></span>|<span data-ttu-id="813b2-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="813b2-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="813b2-121">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="813b2-121">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="813b2-122">**name**</span><span class="sxs-lookup"><span data-stu-id="813b2-122">**name**</span></span>|<span data-ttu-id="813b2-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="813b2-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="813b2-124">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="813b2-124">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="813b2-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="813b2-125">Child Elements</span></span>  
  
|<span data-ttu-id="813b2-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="813b2-126">Element</span></span>|<span data-ttu-id="813b2-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="813b2-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="813b2-128">\<filter></span><span class="sxs-lookup"><span data-stu-id="813b2-128">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="813b2-129">Agrega un filtro a un agente de escucha en la colección de `Listeners` para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="813b2-129">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="813b2-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="813b2-130">Parent Elements</span></span>  
  
|<span data-ttu-id="813b2-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="813b2-131">Element</span></span>|<span data-ttu-id="813b2-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="813b2-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="813b2-133">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="813b2-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="813b2-134">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="813b2-134">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="813b2-135">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="813b2-135">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="813b2-136">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="813b2-136">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="813b2-137">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="813b2-137">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="813b2-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="813b2-138">Remarks</span></span>  
 <span data-ttu-id="813b2-139">Las clases <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.Trace> comparten la misma colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="813b2-139">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="813b2-140">Si agrega un objeto de escucha a la colección en una de estas clases, la otra clase utiliza el mismo agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="813b2-140">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="813b2-141">Las clases de agente de escucha derivan de la <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="813b2-141">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="813b2-142">Si no especifica el atributo `name` del agente de escucha de seguimiento, el <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="813b2-142">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="813b2-143">Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="813b2-143">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="813b2-144">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar nombres únicos para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales dentro de las colecciones <xref:System.Diagnostics.Debug.Listeners%2A> y <xref:System.Diagnostics.Trace.Listeners%2A>.</span><span class="sxs-lookup"><span data-stu-id="813b2-144">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="813b2-145">Al agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre, solo se agrega un agente de escucha de seguimiento de ese tipo y nombre a la colección de `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="813b2-145">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="813b2-146">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la colección de `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="813b2-146">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="813b2-147">El valor del atributo **initializeData** depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="813b2-147">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="813b2-148">No todos los agentes de escucha de seguimiento requieren que se especifique **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="813b2-148">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="813b2-149">Al usar el atributo `initializeData`, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="813b2-149">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="813b2-150">Esta advertencia se produce porque los valores de configuración se validan con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="813b2-150">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="813b2-151">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="813b2-151">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="813b2-152">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus atributos **initializeData** .</span><span class="sxs-lookup"><span data-stu-id="813b2-152">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="813b2-153">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="813b2-153">Trace listener class</span></span>|<span data-ttu-id="813b2-154">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="813b2-154">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="813b2-155">El valor `useErrorStream` del constructor de <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="813b2-155">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="813b2-156">Establezca el atributo `initializeData` en "`true`" para escribir los resultados de seguimiento y depuración en <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" para escribir en <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="813b2-156">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="813b2-157">Nombre del archivo en el que se escribe el <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="813b2-157">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="813b2-158">Nombre del nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="813b2-158">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="813b2-159">Nombre del archivo en el que escribe el <xref:System.Diagnostics.EventSchemaTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="813b2-159">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="813b2-160">Nombre del archivo en el que escribe el <xref:System.Diagnostics.TextWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="813b2-160">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="813b2-161">Nombre del archivo en el que escribe el <xref:System.Diagnostics.XmlWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="813b2-161">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="813b2-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="813b2-162">Example</span></span>  
 <span data-ttu-id="813b2-163">En el ejemplo siguiente se muestra cómo usar **\<agregar >** elementos para agregar los agentes de escucha `MyListener` y `MyEventListener` a la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="813b2-163">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="813b2-164">`MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="813b2-164">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="813b2-165">`MyEventListener` crea una entrada en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="813b2-165">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="813b2-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="813b2-166">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="813b2-167">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="813b2-167">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="813b2-168">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="813b2-168">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
