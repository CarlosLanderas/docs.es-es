---
title: Valores devueltos de referencia
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: 2d2a302a899fbde549161469f281d3e580bcb71f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352534"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Compatibilidad con los valores devueltos de referencia (Visual Basic)

A partir C# de 7,0, C# el lenguaje admite *valores devueltos de referencia*. Una manera de comprender los valores devueltos de referencia es que son lo contrario de los argumentos que se pasan por referencia a un método. Cuando se modifica un argumento pasado por referencia, los cambios se reflejan en el valor de la variable en el autor de la llamada. Cuando un método proporciona un valor devuelto de referencia a un llamador, las modificaciones realizadas en el valor devuelto de referencia por el autor de la llamada se reflejan en los datos del método llamado.

Visual Basic no permite crear métodos con valores devueltos de referencia, pero permite usar valores devueltos de referencia. En otras palabras, puede llamar a un método con un valor devuelto de referencia y modificar el valor devuelto, y los cambios en el valor devuelto de referencia se reflejan en los datos del método llamado.

## <a name="modifying-the-ref-return-value-directly"></a>Modificar el valor devuelto de la referencia directamente

En el caso de los métodos que siempre se ejecutan correctamente y que no tienen parámetros `ByRef`, puede modificar el valor devuelto de referencia directamente. Para ello, se asigna el nuevo valor a las expresiones que devuelven el valor devuelto de referencia.

En el C# ejemplo siguiente se define un método `NumericValue.IncrementValue` que incrementa un valor interno y lo devuelve como un valor devuelto de referencia.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

Después, el autor de la llamada modifica el valor devuelto de referencia en el siguiente ejemplo de Visual Basic. Tenga en cuenta que la línea con la llamada al método `NumericValue.IncrementValue` no asigna un valor al método. En su lugar, asigna un valor al valor devuelto de referencia que devuelve el método.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Usar un método auxiliar

En otros casos, puede que no siempre sea deseable modificar el valor devuelto de referencia de una llamada al método directamente. Por ejemplo, un método de búsqueda que devuelve una cadena puede no encontrar siempre una coincidencia. En ese caso, desea modificar el valor devuelto de referencia solo si la búsqueda se realiza correctamente.

En el C# ejemplo siguiente se muestra este escenario. Define una clase `Sentence` escrita en C# incluye un método `FindNext` que busca la palabra siguiente en una oración que comienza con una subcadena especificada. La cadena se devuelve como un valor devuelto de referencia, y una variable `Boolean` que se ha pasado mediante referencia al método indica si la búsqueda se ha realizado correctamente. El valor devuelto de referencia indica que el llamador no solo puede leer el valor devuelto; también puede modificarla, y esa modificación se refleja en los datos incluidos internamente en la clase `Sentence`.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

La modificación directa del valor devuelto de referencia en este caso no es confiable, ya que es posible que la llamada al método no encuentre una coincidencia y devuelva la primera palabra de la oración. En ese caso, el autor de la llamada modifica accidentalmente la primera palabra de la frase. El autor de la llamada puede evitar que devuelva un `null` (o `Nothing` en Visual Basic). Pero en ese caso, si se intenta modificar una cadena cuyo valor es `Nothing` se produce una <xref:System.NullReferenceException>. Si el autor de la llamada también puede evitar que devuelva <xref:System.String.Empty?displayProperty=nameWithType>, pero esto requiere que el llamador defina una variable de cadena cuyo valor sea <xref:System.String.Empty?displayProperty=nameWithType>. Aunque el autor de la llamada puede modificar esa cadena, la propia modificación no sirve para ningún propósito, ya que la cadena modificada no tiene ninguna relación con las palabras de la frase almacenada por la clase `Sentence`.

La mejor manera de controlar este escenario es pasar el valor devuelto de referencia por referencia a un método auxiliar. A continuación, el método auxiliar contiene la lógica para determinar si la llamada al método se realizó correctamente y, si lo hizo, para modificar el valor devuelto de referencia. En el ejemplo siguiente se proporciona una posible implementación.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Vea también

- [Pasar argumentos por valor y por referencia](passing-arguments-by-value-and-by-reference.md)
- [Procedimientos en Visual Basic](index.md)
