---
title: Tipos numéricos de punto flotante - referencia de C#
description: Información general de los tipos de punto flotante integrados de C#
ms.date: 10/22/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 23aa33c6887db48a12f995efc5e1e2220d30216c
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552277"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="629ae-103">Tipos numéricos de punto flotante (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="629ae-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="629ae-104">Los **tipos de punto flotante** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#real-literals).</span><span class="sxs-lookup"><span data-stu-id="629ae-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="629ae-105">Todos los tipos de punto flotante también son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="629ae-105">All floating-point types are also value types.</span></span> <span data-ttu-id="629ae-106">Todos los tipos de punto flotante numéricos admiten operadores [aritméticos](../operators/arithmetic-operators.md), [de comparación](../operators/comparison-operators.md) y de [igualdad](../operators/equality-operators.md).</span><span class="sxs-lookup"><span data-stu-id="629ae-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="629ae-107">Características de los tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="629ae-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="629ae-108">C# admite los siguientes tipos de punto flotante predefinidos:</span><span class="sxs-lookup"><span data-stu-id="629ae-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="629ae-109">Palabra clave/tipo de C#</span><span class="sxs-lookup"><span data-stu-id="629ae-109">C# type/keyword</span></span>|<span data-ttu-id="629ae-110">Intervalo aproximado</span><span class="sxs-lookup"><span data-stu-id="629ae-110">Approximate range</span></span>|<span data-ttu-id="629ae-111">Precisión</span><span class="sxs-lookup"><span data-stu-id="629ae-111">Precision</span></span>|<span data-ttu-id="629ae-112">Tamaño</span><span class="sxs-lookup"><span data-stu-id="629ae-112">Size</span></span>|<span data-ttu-id="629ae-113">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="629ae-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="629ae-114">De ±1,5 x 10<sup>-45</sup> a ±3,4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="629ae-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="629ae-115">De 6 a 9 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="629ae-115">~6-9 digits</span></span>|<span data-ttu-id="629ae-116">4 bytes</span><span class="sxs-lookup"><span data-stu-id="629ae-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="629ae-117">De ±5,0 × 10<sup>−324</sup> a ±1,7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="629ae-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="629ae-118">De 15 a 17 dígitos aproximadamente</span><span class="sxs-lookup"><span data-stu-id="629ae-118">~15-17 digits</span></span>|<span data-ttu-id="629ae-119">8 bytes</span><span class="sxs-lookup"><span data-stu-id="629ae-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="629ae-120">De ±1,0 x 10<sup>-28</sup> to ±7,9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="629ae-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="629ae-121">28-29 dígitos</span><span class="sxs-lookup"><span data-stu-id="629ae-121">28-29 digits</span></span>|<span data-ttu-id="629ae-122">16 bytes</span><span class="sxs-lookup"><span data-stu-id="629ae-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="629ae-123">En la tabla anterior, cada palabra clave de tipo de C# de la columna ubicada más a la izquierda es un alias del tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="629ae-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="629ae-124">Son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="629ae-124">They are interchangeable.</span></span> <span data-ttu-id="629ae-125">Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="629ae-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="629ae-126">El valor predeterminado de cada tipo de punto flotante es cero, `0`.</span><span class="sxs-lookup"><span data-stu-id="629ae-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="629ae-127">Cada uno de los tipos de punto flotante tiene las constantes `MinValue` y `MaxValue` que proporcionan el valor finito mínimo y máximo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="629ae-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="629ae-128">Los tipos `float` y `double` también brindan constantes que representan valores infinitos y no numéricos.</span><span class="sxs-lookup"><span data-stu-id="629ae-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="629ae-129">Por ejemplo, el tipo `double` ofrece las siguientes constantes: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> y <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="629ae-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="629ae-130">Como el tipo `decimal` tiene más precisión y un intervalo más reducido que `float` y `double`, es adecuado para los cálculos financieros y monetarios.</span><span class="sxs-lookup"><span data-stu-id="629ae-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="629ae-131">Puede combinar tipos [enteros](integral-numeric-types.md) y tipos de punto flotante en una expresión.</span><span class="sxs-lookup"><span data-stu-id="629ae-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="629ae-132">En este caso, los tipos enteros se convierten a tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="629ae-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="629ae-133">La evaluación de la expresión se realiza según las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="629ae-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="629ae-134">Si uno de los tipos de punto flotante es `double`, la expresión se evalúa como `double` o [bool](bool.md) en comparaciones relacionales y de igualdad.</span><span class="sxs-lookup"><span data-stu-id="629ae-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="629ae-135">Si no hay ningún tipo `double` en la expresión, esta se evalúa como `float` o [bool](bool.md) en comparaciones relacionales o de igualdad.</span><span class="sxs-lookup"><span data-stu-id="629ae-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="629ae-136">Una expresión de punto flotante puede contener los siguientes conjuntos de valores:</span><span class="sxs-lookup"><span data-stu-id="629ae-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="629ae-137">Cero positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="629ae-137">Positive and negative zero</span></span>
- <span data-ttu-id="629ae-138">Infinito positivo y negativo</span><span class="sxs-lookup"><span data-stu-id="629ae-138">Positive and negative infinity</span></span>
- <span data-ttu-id="629ae-139">Valor no numérico (NaN)</span><span class="sxs-lookup"><span data-stu-id="629ae-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="629ae-140">El conjunto finito de valores distintos de cero</span><span class="sxs-lookup"><span data-stu-id="629ae-140">The finite set of nonzero values</span></span>

<span data-ttu-id="629ae-141">Para obtener más información sobre estos valores, vea el estándar IEEE para aritmética binaria de punto flotante, disponible en el sitio web de [IEEE](https://www.ieee.org).</span><span class="sxs-lookup"><span data-stu-id="629ae-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="629ae-142">Puede usar [cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md) o [cadenas con formato numérico personalizado](../../../standard/base-types/custom-numeric-format-strings.md) para dar formato a un valor de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="629ae-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="629ae-143">Literales reales</span><span class="sxs-lookup"><span data-stu-id="629ae-143">Real literals</span></span>

<span data-ttu-id="629ae-144">El tipo de un literal real viene determinado por su sufijo, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="629ae-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="629ae-145">El literal sin sufijo o con el sufijo `d` o `D` es del tipo `double`</span><span class="sxs-lookup"><span data-stu-id="629ae-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="629ae-146">El literal con el sufijo `f` o `F` es del tipo `float`</span><span class="sxs-lookup"><span data-stu-id="629ae-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="629ae-147">El literal con el sufijo `m` o `M` es del tipo `decimal`</span><span class="sxs-lookup"><span data-stu-id="629ae-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="629ae-148">En el código siguiente se muestra un ejemplo de cada uno de ellos:</span><span class="sxs-lookup"><span data-stu-id="629ae-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="629ae-149">En el ejemplo anterior también se muestra el uso de `_` como un *separador de dígitos*, que se admite a partir de C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="629ae-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="629ae-150">Puede usar el separador de dígitos con todos los tipos de literales numéricos.</span><span class="sxs-lookup"><span data-stu-id="629ae-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="629ae-151">También puede usar la notación científica; es decir, especificar una parte exponencial de un literal real, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="629ae-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="629ae-152">Conversiones</span><span class="sxs-lookup"><span data-stu-id="629ae-152">Conversions</span></span>

<span data-ttu-id="629ae-153">Solo hay una conversión implícita entre los tipos numéricos de punto flotante: de `float` a `double`.</span><span class="sxs-lookup"><span data-stu-id="629ae-153">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="629ae-154">Sin embargo, puede convertir un tipo de punto flotante a cualquier otro tipo de punto flotante con la [conversión explícita](../operators/type-testing-and-cast.md#cast-operator-).</span><span class="sxs-lookup"><span data-stu-id="629ae-154">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="629ae-155">Para obtener más información, consulte [Conversiones numéricas integradas](numeric-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="629ae-155">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="629ae-156">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="629ae-156">C# language specification</span></span>

<span data-ttu-id="629ae-157">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="629ae-157">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="629ae-158">Tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="629ae-158">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="629ae-159">El tipo decimal</span><span class="sxs-lookup"><span data-stu-id="629ae-159">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="629ae-160">Literales reales</span><span class="sxs-lookup"><span data-stu-id="629ae-160">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="629ae-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="629ae-161">See also</span></span>

- [<span data-ttu-id="629ae-162">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="629ae-162">C# reference</span></span>](../index.md)
- [<span data-ttu-id="629ae-163">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="629ae-163">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="629ae-164">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="629ae-164">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="629ae-165">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="629ae-165">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="629ae-166">Cadenas con formato numérico estándar</span><span class="sxs-lookup"><span data-stu-id="629ae-166">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="629ae-167">Valores numéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="629ae-167">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
