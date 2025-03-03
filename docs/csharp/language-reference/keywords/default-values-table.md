---
title: 'Tabla de valores predeterminados: referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre los valores predeterminados de los tipos de C#.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 48aa294fa9e37e2e138444e493faa5474011097e
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "74551820"
---
# <a name="default-values-table-c-reference"></a>Tabla de valores predeterminados (referencia de C#)

En la tabla siguiente se muestran los valores predeterminados de los tipos de C#:

|Tipo|Valor predeterminado|
|---------|------------------|
|Cualquier tipo de referencia|`null`|
|Cualquier [tipo numérico entero integrado](../builtin-types/integral-numeric-types.md)|0 (cero)|
|Cualquier [tipo numérico de punto flotante integrado](../builtin-types/floating-point-numeric-types.md)|0 (cero)|
|[bool](../builtin-types/bool.md)|`false`|
|[char](../builtin-types/char.md)|`'\0'` (U+0000)|
|[enum](enum.md)|Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.|
|[struct](struct.md)|El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|Cualquier [tipo de valor que acepta valores NULL](../builtin-types/nullable-value-types.md)|Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida. Este valor predeterminado también se conoce con el valor *null* de un tipo de valor que acepta valores NULL.|

Use el [operador predeterminado](../operators/default.md) para generar el valor predeterminado de un tipo, tal y como se muestra en el ejemplo siguiente:

```csharp
int a = default(int);
```

A partir de C# 7.1, se puede usar el [literal `default`](../operators/default.md#default-literal) para inicializar una variable con el valor predeterminado de su tipo:

```csharp
int a = default;
```

Para un tipo de valor, el constructor implícito sin parámetros también genera el valor predeterminado del tipo, como se muestra en el ejemplo siguiente:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Valores predeterminados](~/_csharplang/spec/variables.md#default-values)
- [Constructores predeterminados](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Constructores](../../programming-guide/classes-and-structs/constructors.md)
