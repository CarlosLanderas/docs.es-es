---
title: Elemento <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
ms.openlocfilehash: 9d9eedf52f5d711412e4549e39e6ea23abb68ff3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968904"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="a8c4b-102">\<TimeSpan_LegacyFormatMode elemento ></span><span class="sxs-lookup"><span data-stu-id="a8c4b-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="a8c4b-103">Determina si el tiempo de ejecución conserva el comportamiento heredado en operaciones de formato con valores <xref:System.TimeSpan?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="a8c4b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8c4b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8c4b-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8c4b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a8c4b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<** TimeSpan_LegacyFormatMode ></span><span class="sxs-lookup"><span data-stu-id="a8c4b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="a8c4b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8c4b-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a8c4b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a8c4b-108">Attributes and Elements</span></span>

<span data-ttu-id="a8c4b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a8c4b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8c4b-110">Attributes</span></span>

|<span data-ttu-id="a8c4b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a8c4b-111">Attribute</span></span>|<span data-ttu-id="a8c4b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8c4b-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a8c4b-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a8c4b-114">Especifica si el Runtime usa el comportamiento de formato heredado con valores <xref:System.TimeSpan?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="a8c4b-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a8c4b-115">enabled Attribute</span></span>

|<span data-ttu-id="a8c4b-116">Valor</span><span class="sxs-lookup"><span data-stu-id="a8c4b-116">Value</span></span>|<span data-ttu-id="a8c4b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8c4b-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a8c4b-118">El motor en tiempo de ejecución no restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="a8c4b-119">El motor en tiempo de ejecución restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a8c4b-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a8c4b-120">Child Elements</span></span>

<span data-ttu-id="a8c4b-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a8c4b-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a8c4b-122">Parent Elements</span></span>

|<span data-ttu-id="a8c4b-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8c4b-123">Element</span></span>|<span data-ttu-id="a8c4b-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8c4b-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a8c4b-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a8c4b-126">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a8c4b-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8c4b-127">Remarks</span></span>

<span data-ttu-id="a8c4b-128">A partir de la .NET Framework 4, la estructura de <xref:System.TimeSpan?displayProperty=nameWithType> implementa la interfaz <xref:System.IFormattable> y admite operaciones de formato con cadenas de formato estándar y personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="a8c4b-129">Si un método de análisis encuentra un especificador de formato no compatible o una cadena de formato, produce una <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="a8c4b-130">En versiones anteriores del .NET Framework, la estructura de <xref:System.TimeSpan> no implementaba <xref:System.IFormattable> y no admitía cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="a8c4b-131">Sin embargo, muchos desarrolladores suponían erróneamente que <xref:System.TimeSpan> admitía un conjunto de cadenas de formato y las usaban en [operaciones de formato compuesto](../../../../standard/base-types/composite-formatting.md) con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a8c4b-132">Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con cadenas de formato no admitidas normalmente inician una <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="a8c4b-133">Sin embargo, dado que <xref:System.TimeSpan> no implementó <xref:System.IFormattable>, el tiempo de ejecución omitió la cadena de formato y, en su lugar, llamó al método <xref:System.TimeSpan.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a8c4b-134">Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no produjo una <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="a8c4b-135">En los casos en los que el código heredado pasa un método de formato compuesto y una cadena de formato no válida, y ese código no se puede volver a compilar, puede usar el elemento `<TimeSpan_LegacyFormatMode>` para restaurar el comportamiento de la <xref:System.TimeSpan> heredada.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="a8c4b-136">Al establecer el `enabled` atributo de este elemento en `true`, el método de formato compuesto produce una llamada a <xref:System.TimeSpan.ToString?displayProperty=nameWithType> en lugar de <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>y no se produce una <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="a8c4b-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8c4b-137">Example</span></span>

<span data-ttu-id="a8c4b-138">En el ejemplo siguiente se crea una instancia de un objeto <xref:System.TimeSpan> e intenta aplicarle formato con el método <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> mediante una cadena de formato estándar no compatible.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="a8c4b-139">Al ejecutar el ejemplo en el .NET Framework 3,5 o en una versión anterior, se muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a8c4b-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```console
12:30:45
```

<span data-ttu-id="a8c4b-140">Esto difiere notablemente de la salida si ejecuta el ejemplo en el .NET Framework 4 o una versión posterior:</span><span class="sxs-lookup"><span data-stu-id="a8c4b-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```console
Invalid Format
```

<span data-ttu-id="a8c4b-141">Sin embargo, si agrega el archivo de configuración siguiente al directorio del ejemplo y, a continuación, ejecuta el ejemplo en el .NET Framework 4 o una versión posterior, la salida es idéntica a la generada por el ejemplo cuando se ejecuta en .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="a8c4b-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a8c4b-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8c4b-142">See also</span></span>

- [<span data-ttu-id="a8c4b-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a8c4b-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a8c4b-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a8c4b-144">Configuration File Schema</span></span>](../index.md)
