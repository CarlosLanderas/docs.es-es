---
title: 'Tabla de valores predeterminados: referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre los valores predeterminados de los tipos de C#.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 2f1ad5cc029b93261153e46d854cd8bf3e31ce92
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428527"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="57c6d-103">Tabla de valores predeterminados (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="57c6d-103">Default values table (C# reference)</span></span>

<span data-ttu-id="57c6d-104">En la tabla siguiente se muestran los valores predeterminados de los tipos de C#:</span><span class="sxs-lookup"><span data-stu-id="57c6d-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="57c6d-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="57c6d-105">Type</span></span>|<span data-ttu-id="57c6d-106">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="57c6d-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="57c6d-107">Cualquier tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="57c6d-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="57c6d-108">Cualquier [tipo numérico entero integrado](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="57c6d-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="57c6d-109">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="57c6d-109">0 (zero)</span></span>|
|<span data-ttu-id="57c6d-110">Cualquier [tipo numérico de punto flotante integrado](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="57c6d-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="57c6d-111">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="57c6d-111">0 (zero)</span></span>|
|[<span data-ttu-id="57c6d-112">bool</span><span class="sxs-lookup"><span data-stu-id="57c6d-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="57c6d-113">char</span><span class="sxs-lookup"><span data-stu-id="57c6d-113">char</span></span>](../builtin-types/char.md)|<span data-ttu-id="57c6d-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="57c6d-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="57c6d-115">enum</span><span class="sxs-lookup"><span data-stu-id="57c6d-115">enum</span></span>](enum.md)|<span data-ttu-id="57c6d-116">Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="57c6d-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="57c6d-117">struct</span><span class="sxs-lookup"><span data-stu-id="57c6d-117">struct</span></span>](struct.md)|<span data-ttu-id="57c6d-118">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="57c6d-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="57c6d-119">Cualquier [tipo de valor que acepta valores NULL](../builtin-types/nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="57c6d-119">Any [nullable value type](../builtin-types/nullable-value-types.md)</span></span>|<span data-ttu-id="57c6d-120">Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.</span><span class="sxs-lookup"><span data-stu-id="57c6d-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="57c6d-121">Este valor predeterminado también se conoce con el valor *null* de un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="57c6d-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="57c6d-122">Use el [operador predeterminado](../operators/default.md) para generar el valor predeterminado de un tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57c6d-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="57c6d-123">A partir de C# 7.1, se puede usar el [literal `default`](../operators/default.md#default-literal) para inicializar una variable con el valor predeterminado de su tipo:</span><span class="sxs-lookup"><span data-stu-id="57c6d-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="57c6d-124">Para un tipo de valor, el constructor implícito sin parámetros también genera el valor predeterminado del tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="57c6d-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="57c6d-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="57c6d-125">C# language specification</span></span>

<span data-ttu-id="57c6d-126">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="57c6d-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="57c6d-127">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="57c6d-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="57c6d-128">Constructores predeterminados</span><span class="sxs-lookup"><span data-stu-id="57c6d-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="57c6d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="57c6d-129">See also</span></span>

- [<span data-ttu-id="57c6d-130">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="57c6d-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="57c6d-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="57c6d-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="57c6d-132">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="57c6d-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="57c6d-133">Constructores</span><span class="sxs-lookup"><span data-stu-id="57c6d-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
