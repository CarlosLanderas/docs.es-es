---
title: Procedimiento para extraer un protocolo y un número de puerto de una dirección URL
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
ms.openlocfilehash: f2704e3fb5ceb68609a475d52e11030177ad760b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138722"
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a>Procedimiento para extraer un protocolo y un número de puerto de una dirección URL
En los siguientes ejemplos se extrae un protocolo y un número de puerto de una dirección URL.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo usa el método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> para devolver el protocolo seguido de dos puntos y del número de puerto.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 El patrón de la expresión regular `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` puede interpretarse como se muestra en la tabla siguiente.  
  
|Modelo|DESCRIPCIÓN|  
|-------------|-----------------|  
|`^`|Comenzar la búsqueda de coincidencia al principio de la cadena.|  
|`(?<proto>\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Asigne a este grupo el nombre `proto`.|  
|`://`|Buscar coincidencias con un signo de dos puntos seguido por dos barras diagonales.|  
|`[^/]+?`|Buscar coincidencias con una o más apariciones (pero el menor número posible) de cualquier carácter que no sea una barra diagonal.|  
|`(?<port>:\d+)?`|Buscar una coincidencia con cero o una aparición de una coma seguida de uno o más caracteres decimales. Asigne a este grupo el nombre `port`.|  
|`/`|Buscar una coincidencia con una barra diagonal.|  
  
 El método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> expande la secuencia de reemplazo `${proto}${port}`, que concatena el valor de los dos grupos con nombre capturados en el patrón de expresión regular. Resulta cómodo concatenar explícitamente las cadenas recuperadas del objeto de la colección devueltas por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>.  
  
 El ejemplo usa el método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> con dos sustituciones, `${proto}` y `${port}`, para incluir los grupos capturados en la cadena de salida. En su lugar, puede recuperar los grupos capturados del objeto de coincidencia <xref:System.Text.RegularExpressions.GroupCollection>, como se muestra en el siguiente código.  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Expresiones regulares de .NET](../../../docs/standard/base-types/regular-expressions.md)
