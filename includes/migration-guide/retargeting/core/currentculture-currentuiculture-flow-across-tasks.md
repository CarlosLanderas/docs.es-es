---
ms.openlocfilehash: de40d16dbb5e7a7a49ae0988342b3eb75bc078c5
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804578"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>CurrentCulture y CurrentUICulture fluyen entre tareas

|   |   |
|---|---|
|Detalles|A partir de la versión 4.6 de .NET Framework, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> y <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> se almacenan en el <xref:System.Threading.ExecutionContext?displayProperty=name> del subproceso, que fluye entre las operaciones asincrónicas. Esto significa que los cambios en <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> se verán reflejados en las tareas que después se ejecutan de forma asincrónica. Esto difiere del comportamiento de las versiones anteriores de .NET Framework (en las que se restablecían <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> y <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> en todas las tareas asincrónicas).|
|Sugerencia|Las aplicaciones afectadas por este cambio pueden solucionar el problema si se establece explícitamente el valor <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> deseado como la primera operación de una tarea asincrónica. Como alternativa, el comportamiento anterior (de que <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> no fluyan) se puede incluir si se establece el modificador de compatibilidad siguiente:<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>WPF ha solucionado este problema en .NET Framework 4.6.2. También se ha corregido en .NET Framework 4.6, 4.6.1 a través de [KB 3139549](https://support.microsoft.com/kb/3139549). Las aplicaciones destinadas a .NET Framework 4.6 o una versión posterior obtendrán automáticamente el comportamiento correcto en las aplicaciones de WPF: <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name>) se conservará entre las operaciones del distribuidor.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType></li><li><xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType></li><li><xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType></li></ul>|

