---
title: Período de duración
ms.date: 07/20/2015
helpviewer_keywords:
- static variables [Visual Basic], lifetime
- static variables [Visual Basic], Visual Basic
- declared elements [Visual Basic], lifetime
- Shared variable lifetime [Visual Basic]
- lifetime [Visual Basic], declared elements
- lifetime [Visual Basic], Visual Basic
- lifetime [Visual Basic]
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
ms.openlocfilehash: 05a39388e8aa9681af60cf86a3df8346d744b69e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345311"
---
# <a name="lifetime-in-visual-basic"></a>Período de duración en Visual Basic
La *duración* de un elemento declarado es el período de tiempo durante el cual está disponible para su uso. Las variables son los únicos elementos que tienen duración. Para este propósito, el compilador trata los parámetros de procedimiento y la función devuelve como casos especiales de variables. La duración de una variable representa el período de tiempo durante el que puede contener un valor. Su valor puede cambiar a lo largo de su duración, pero siempre contiene algún valor.  
  
## <a name="different-lifetimes"></a>Diferentes duraciones  
 Una *variable miembro* (declarada en el nivel de módulo, fuera de cualquier procedimiento) tiene normalmente la misma duración que el elemento en el que se declara. Una variable no compartida declarada en una clase o estructura existe como una copia independiente para cada instancia de la clase o estructura en la que se declara. Cada una de estas variables tiene la misma duración que su instancia. Sin embargo, una variable de `Shared` solo tiene una duración, que dura todo el tiempo que se ejecuta la aplicación.  
  
 Una *variable local* (declarada dentro de un procedimiento) solo existe mientras se ejecuta el procedimiento en el que se declara. Esto se aplica también a los parámetros de ese procedimiento y a cualquier devolución de función. Sin embargo, si ese procedimiento llama a otros procedimientos, las variables locales conservan sus valores mientras se ejecutan los procedimientos llamados.  
  
## <a name="beginning-of-lifetime"></a>Inicio de la duración  
 La duración de una variable local comienza cuando el control entra en el procedimiento en el que se declara. Cada variable local se inicializa en el valor predeterminado para su tipo de datos en cuanto el procedimiento comienza a ejecutarse. Cuando el procedimiento encuentra una instrucción `Dim` que especifica valores iniciales, establece esas variables en esos valores, aunque el código ya tenga asignados otros valores.  
  
 Cada miembro de una variable de estructura se inicializa como si fuera una variable independiente. Del mismo modo, cada elemento de una variable de matriz se inicializa individualmente.  
  
 Las variables declaradas dentro de un bloque dentro de un procedimiento (como un bucle `For`) se inicializan en la entrada al procedimiento. Estas inicializaciones surten efecto tanto si el código ejecuta el bloque como si no.  
  
## <a name="end-of-lifetime"></a>Fin de la vigencia  
 Cuando finaliza un procedimiento, no se conservan los valores de sus variables locales y Visual Basic recupera su memoria. La próxima vez que llame al procedimiento, todas sus variables locales se crean nuevo y se reinicializan.  
  
 Cuando finaliza una instancia de una clase o estructura, sus variables no compartidas pierden su memoria y sus valores. Cada nueva instancia de la clase o estructura crea y reinicializa sus variables no compartidas. Sin embargo, `Shared` variables se conservan hasta que la aplicación deja de ejecutarse.  
  
## <a name="extension-of-lifetime"></a>Extensión de duración  
 Si declara una variable local con la palabra clave `Static`, su duración es mayor que el tiempo de ejecución de su procedimiento. En la tabla siguiente se muestra cómo la declaración de procedimiento determina cuánto tiempo existe una variable de `Static`.  
  
|Ubicación y uso compartido de procedimientos|Comienza la duración de la variable estática|Finaliza la duración de la variable estática|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|En un módulo (compartido de forma predeterminada)|La primera vez que se llama al procedimiento|Cuando la aplicación deja de ejecutarse|  
|En una clase, `Shared` (el procedimiento no es un miembro de instancia)|La primera vez que se llama al procedimiento en una instancia específica o en el propio nombre de clase o estructura|Cuando la aplicación deja de ejecutarse|  
|En una instancia de una clase, no `Shared` (el procedimiento es un miembro de instancia)|La primera vez que se llama al procedimiento en la instancia específica|Cuando se libera la instancia para la recolección de elementos no utilizados (GC)|  
  
## <a name="static-variables-of-the-same-name"></a>Variables estáticas con el mismo nombre  
 Puede declarar variables estáticas con el mismo nombre en más de un procedimiento. Si lo hace, el compilador de Visual Basic considera que cada variable es un elemento independiente. La inicialización de una de estas variables no afecta a los valores de los demás. Lo mismo se aplica si se define un procedimiento con un conjunto de sobrecargas y se declara una variable estática con el mismo nombre en cada sobrecarga.  
  
## <a name="containing-elements-for-static-variables"></a>Elementos que contienen para variables estáticas  
 Puede declarar una variable local estática dentro de una clase, es decir, dentro de un procedimiento de esa clase. Sin embargo, no se puede declarar una variable local estática dentro de una estructura, ya sea como un miembro de estructura o como una variable local de un procedimiento dentro de esa estructura.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se declara una variable con la palabra clave [static](../../../../visual-basic/language-reference/modifiers/static.md) . (Tenga en cuenta que no necesita la palabra clave `Dim` cuando la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) usa un modificador como `Static`).  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrKeywords#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#13)]  
  
### <a name="comments"></a>Comentarios  
 En el ejemplo anterior, la variable `applesSold` sigue existiendo después de que el procedimiento `runningTotal` vuelve al código de llamada. La próxima vez que se llama a `runningTotal`, `applesSold` conserva su valor calculado anteriormente.  
  
 Si `applesSold` se hubiera declarado sin usar `Static`, los valores acumulados anteriores no se conservarían entre las llamadas a `runningTotal`. La próxima vez que se llame a `runningTotal`, `applesSold` se habrían vuelto a crear e inicializar en 0, y `runningTotal` habrían devuelto simplemente el mismo valor con el que se llamó.  
  
### <a name="compiling-the-code"></a>Compilar el código  
 Puede inicializar el valor de una variable local estática como parte de su declaración. Si declara una matriz para que sea `Static`, puede inicializar su rango (número de dimensiones), la longitud de cada dimensión y los valores de cada uno de los elementos.  
  
### <a name="security"></a>Seguridad  
 En el ejemplo anterior, puede generar la misma duración declarando `applesSold` en el nivel de módulo. Sin embargo, si cambia el ámbito de una variable de esta manera, el procedimiento ya no tendrá acceso exclusivo a él. Dado que otros procedimientos podían acceder a `applesSold` y cambiar su valor, el total acumulado podría ser poco confiable y el código podría ser más difícil de mantener.  
  
## <a name="see-also"></a>Vea también

- [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
