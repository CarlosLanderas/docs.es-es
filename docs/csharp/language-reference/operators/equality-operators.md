---
title: 'Operadores de igualdad: referencia de C#'
description: Obtenga más información sobre los operadores de comparación de igualdad de C# y el tipo de igualdad de C#.
ms.date: 06/26/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 11d2161004af5199d9e501f8ab1e3c0382e6bfe7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039033"
---
# <a name="equality-operators-c-reference"></a>Operadores de igualdad (referencia de C#)

Los operadores [`==` (igualdad)](#equality-operator-) y [`!=` (desigualdad)](#inequality-operator-) comprueban si los operandos son iguales.

## <a name="equality-operator-"></a>Operador de igualdad ==

El operador de igualdad `==` devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.

### <a name="value-types-equality"></a>Igualdad entre tipos de valor

Los operandos de los [tipos de valor integrados](../keywords/value-types-table.md) son iguales si sus valores son iguales:

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> Para los operadores `==`, [`<`, `>`, `<=` y `>=`](comparison-operators.md), si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`. Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`. Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Dos operandos del mismo tipo [enum](../keywords/enum.md) son iguales si los valores correspondientes del tipo entero subyacente son iguales.

Los tipos [struct](../keywords/struct.md) definidos por el usuario no son compatibles con el operador `==` de forma predeterminada. Para admitir el operador `==`, un elemento struct definido por el usuario debe [sobrecargarlo](operator-overloading.md).

A partir de C# 7.3, los operadores `==` y `!=` son compatibles con las [tuplas](../../tuples.md) de C#. Para obtener más información, vea la sección [Igualdad y tuplas](../../tuples.md#equality-and-tuples) del artículo [Tipos de tupla de C#](../../tuples.md).

### <a name="reference-types-equality"></a>Igualdad entre tipos de referencia

De forma predeterminada, dos operandos de tipo de referencia son iguales si hacen referencia al mismo objeto:

[!code-csharp[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

Como se muestra en el ejemplo, el operador `==` es compatible de forma predeterminada con los tipos de referencia definidos por el usuario. Sin embargo, un tipo de referencia puede sobrecargar el operador `==`. Si un tipo de referencia sobrecarga el operador `==`, use el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> para comprobar si dos referencias de ese tipo hacen referencia al mismo objeto.

### <a name="string-equality"></a>Igualdad entre cadenas

Dos operandos [string](../builtin-types/reference-types.md#the-string-type) son iguales si ambos son `null`, o bien si las instancias de ambas cadenas tienen la misma longitud y los mismos caracteres en cada posición de caracteres:

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

Es la comparación de ordinales que distingue entre mayúsculas de minúsculas. Para obtener más información sobre la comparación de cadenas, vea [Cómo comparar cadenas en C# ](../../how-to/compare-strings.md).

### <a name="delegate-equality"></a>Igualdad entre delegados

Dos operandos de [delegado](../../programming-guide/delegates/index.md) con el mismo tipo de entorno de ejecución son iguales cuando ambos son `null`, o bien cuando sus listas de invocación tienen la misma longitud y las mismas entradas en cada posición:

[!code-csharp-interactive[delegate equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#DelegateEquality)]

Para obtener más información, vea la sección sobre los [operadores de igualdad entre delegados](~/_csharplang/spec/expressions.md#delegate-equality-operators) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Los delegados que se producen mediante la evaluación de [expresiones lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) semánticamente idénticas no son iguales, tal como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[from identical lambdas](~/samples/csharp/language-reference/operators/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a>Operador de desigualdad !=

El operador de desigualdad (`!=`) devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`. Para los operandos de los [tipos integrados](../keywords/built-in-types-table.md), la expresión `x != y` genera el mismo resultado que la expresión `!(x == y)`. Para obtener más información sobre la igualdad de tipos, vea la sección [Operador de igualdad](#equality-operator-).

En el siguiente ejemplo se muestra el uso del operador `!=`:

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `==` y `!=`. Si un tipo sobrecarga uno de los dos operadores, también debe sobrecargar el otro.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [Comparaciones de igualdad](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [Operadores de comparación](comparison-operators.md)
