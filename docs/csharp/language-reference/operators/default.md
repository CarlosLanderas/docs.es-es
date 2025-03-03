---
title: Operador default (referencia de C#)
ms.custom: seodec18
description: Uso del operador default para generar el valor predeterminado de un tipo
ms.date: 08/01/2019
helpviewer_keywords:
- default keyword [C#]
ms.openlocfilehash: 6503e82a42f116a7ba8461ae060592377579f255
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039049"
---
# <a name="default-operator-c-reference"></a>Operador default (Referencia de C#)

El operador `default` genera el [valor predeterminado](../keywords/default-values-table.md) de un tipo. El argumento del operador `default` debe ser el nombre de un tipo o un parámetro de tipo.

En el ejemplo siguiente se muestra el uso del operador `default`:

[!code-csharp-interactive[default of T](~/samples/csharp/language-reference/operators/DefaultOperator.cs#WithOperand)]

También se usa la palabra clave `default` como etiqueta de mayúsculas y minúsculas predeterminada dentro de una [instrucción `switch`](../keywords/switch.md).

## <a name="default-literal"></a>Literal default

A partir C# de 7.1, puede usar el literal `default` para generar el valor predeterminado de un tipo cuando el compilador puede deducir el tipo de expresión. La expresión literal `default` genera el mismo valor que la expresión `default(T)` cuando se deduce el tipo `T`. Puede usar el literal `default` en cualquiera de los casos siguientes:

- En la asignación o inicialización de una variable.
- En la declaración del valor predeterminado de un [parámetro de método opcional](../../methods.md#optional-parameters-and-arguments).
- En una llamada al método para proporcionar un valor de argumento.
- En una [instrucción `return`](../keywords/return.md) o como una expresión de un [miembro con cuerpo de expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

En el ejemplo siguiente se muestra el uso del literal `default`:

[!code-csharp-interactive[default literal](~/samples/csharp/language-reference/operators/DefaultOperator.cs#DefaultLiteral)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte la sección [Expresiones de valor predeterminado](~/_csharplang/spec/expressions.md#default-value-expressions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para más información sobre el literal `default`, consulte la [nota de propuesta de características](~/_csharplang/proposals/csharp-7.1/target-typed-default.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Tabla de valores predeterminados](../keywords/default-values-table.md)
- [Elementos genéricos en .NET](../../../standard/generics/index.md)
