---
ms.openlocfilehash: 86cdb845c436f424bbcc70e0736568031143b204
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567464"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine está obsoleto

La constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> está marcada con el atributo [Obsolete](xref:System.ObsoleteAttribute) a partir de .NET Core 3.0 (versión preliminar 8).

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 8)

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Core 3.0 (versión preliminar 8), se ha aplicado el atributo [Obsolete](xref:System.ObsoleteAttribute) a la constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>. El uso de la constante genera una advertencia del compilador. En versiones anteriores de .NET Core y .NET Framework, no estaba marcada como “Obsolete”.

Este cambio se realizó para admitir Visual Basic como lenguaje para el desarrollo multiplataforma. La constante `vbNewLine` equivale a `\r\n`, la secuencia de caracteres de nueva línea en Windows. En los sistemas basados en Unix, el carácter de nueva línea es `\n`.

#### <a name="recommended-action"></a>Acción recomendada

El mensaje del atributo [Obsolete](xref:System.ObsoleteAttribute) para `vbNewLine` incluye la siguiente recomendación:

> Para un retorno de carro y un avance de línea, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf). Para la nueva línea de la plataforma actual, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Visual Basic

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
