---
ms.openlocfilehash: f672645fb98f511f7e1326c9c584b287a0fae7dc
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67859339"
---
### <a name="long-path-support"></a>Compatibilidad con rutas de acceso con formato largo

|   |   |
|---|---|
|Detalles|A partir de las aplicaciones destinadas a .NET Framework 4.6.2, se admiten las rutas de acceso largas (de hasta 32 000 caracteres) y se ha quitado la limitación de 260 caracteres (o <code>MAX_PATH</code>) para las longitudes de ruta de acceso. Para las aplicaciones que se vuelven a compilar para .NET Framework 4.6.2, las rutas de acceso de código que antes iniciaban una excepción <xref:System.IO.PathTooLongException?displayProperty=name> porque una ruta de acceso superaba los 260 caracteres ahora iniciarán una excepción <xref:System.IO.PathTooLongException?displayProperty=name> solo en las condiciones siguientes:<ul><li>La longitud de la ruta de acceso es mayor que <xref:System.Int16.MaxValue> (32 767) caracteres.</li><li>El sistema operativo devuelve <code>COR_E_PATHTOOLONG</code> o su equivalente.</li></ul>Para las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, el entorno de ejecución inicia automáticamente una excepción <xref:System.IO.PathTooLongException?displayProperty=name> cada vez que una ruta de acceso supera los 260 caracteres.|
|Sugerencia|Para las aplicaciones que tienen como destino .NET Framework 4.6.2, se puede rechazar la compatibilidad con rutas de acceso largas si no es adecuada si se agrega lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.BlockLongPaths=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, se puede incluir la compatibilidad con rutas de acceso largas si se agrega lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.BlockLongPaths=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Redestinación|

