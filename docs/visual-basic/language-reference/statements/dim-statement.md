---
title: Dim (Instrucción)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: ac66ffdba622673ef42017d147c05b2a2733dede
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343767"
---
# <a name="dim-statement-visual-basic"></a>Instrucción Dim (Visual Basic)

Declara y asigna espacio de almacenamiento para una o más variables.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a>Elementos

- `attributelist`

  Opcional. Vea [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).

- `accessmodifier`

  Opcional. Puede ser uno de los siguientes:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

  Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

- `Shared`

  Opcional. Vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).

- `Shadows`

  Opcional. Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

- `Static`

  Opcional. Vea [static](../../../visual-basic/language-reference/modifiers/static.md).

- `ReadOnly`

  Opcional. Vea [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).

- `WithEvents`

Opcional. Especifica que se trata de variables de objeto que hacen referencia a las instancias de una clase que puede generar eventos. Vea [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).

- `variablelist`

  Obligatorio. Lista de variables que se declaran en esta instrucción.

  `variable [ , variable ... ]`

  Cada `variable` tiene la sintaxis y las partes siguientes:

  `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`

  |Parte|Descripción|
  |---|---|
  |`variablename`|Obligatorio. nombre de la variable. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
  |`boundslist`|Opcional. Lista de los límites de cada dimensión de una variable de matriz.|
  |`New`|Opcional. Crea una nueva instancia de la clase cuando se ejecuta la instrucción `Dim`.|
  |`datatype`|Opcional. Tipo de datos de la variable.|
  |`With`|Opcional. Presenta la lista de inicializadores de objeto.|
  |`propertyname`|Opcional. Nombre de una propiedad de la clase en la que se va a crear una instancia.|
  |`propinitializer`|Obligatorio después de `propertyname` =. Expresión que se evalúa y asigna al nombre de la propiedad.|
  |`initializer`|Opcional si no se especifica `New`. Expresión que se evalúa y se asigna a la variable cuando se crea.|

## <a name="remarks"></a>Comentarios

El compilador Visual Basic usa la instrucción `Dim` para determinar el tipo de datos de la variable y otra información, como el código que puede tener acceso a la variable. En el ejemplo siguiente se declara una variable que contiene un valor `Integer`.

```vb
Dim numberOfStudents As Integer
```

Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

Para un tipo de referencia, use la palabra clave `New` para crear una nueva instancia de la clase o la estructura especificada por el tipo de datos. Si utiliza `New`, no utiliza una expresión de inicializador. En su lugar, se proporcionan argumentos, si son necesarios, al constructor de la clase a partir de la cual se crea la variable.

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

Puede declarar una variable en un procedimiento, un bloque, una clase, una estructura o un módulo. No se puede declarar una variable en un archivo de código fuente, un espacio de nombres o una interfaz. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Una variable que se declara en el nivel de módulo, fuera de cualquier procedimiento, es una variable o *campo* *miembro* . Las variables de miembro están en el ámbito a lo largo de su clase, estructura o módulo. Una variable que se declara en el nivel de procedimiento es una *variable local*. Las variables locales están en el ámbito solo dentro de su procedimiento o bloque.

Los modificadores de acceso siguientes se usan para declarar variables fuera de un procedimiento: `Public`, `Protected`, `Friend`, `Protected Friend`y `Private`. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

La palabra clave `Dim` es opcional y normalmente se omite si se especifica cualquiera de los siguientes modificadores: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`o `WithEvents`.

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

Si `Option Explicit` es on (valor predeterminado), el compilador requiere una declaración para cada variable que se use. Para obtener más información, vea [Option Explicit (instrucción](../../../visual-basic/language-reference/statements/option-explicit-statement.md)).

## <a name="specifying-an-initial-value"></a>Especificar un valor inicial

Puede asignar un valor a una variable cuando se crea. Para un tipo de valor, se usa un *inicializador* para proporcionar una expresión que se va a asignar a la variable. La expresión se debe evaluar como una constante que se puede calcular en tiempo de compilación.

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

Si se especifica un inicializador y no se especifica un tipo de datos en una cláusula `As`, se usa la *inferencia de tipos* para deducir el tipo de datos del inicializador. En el ejemplo siguiente, tanto `num1` como `num2` están fuertemente tipados como enteros. En la segunda declaración, la inferencia de tipos infiere el tipo a partir del valor 3.

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

La inferencia de tipos se aplica en el nivel de procedimiento. No se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz. Para obtener más información sobre la inferencia de tipos, vea [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [inferencia de tipo local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

Para obtener información sobre lo que ocurre cuando no se especifica un tipo de datos o un inicializador, vea [valores y tipos de datos predeterminados](../../../visual-basic/language-reference/statements/dim-statement.md#default) más adelante en este tema.

Puede usar un *inicializador de objeto* para declarar instancias de tipos con nombre y anónimos. En el código siguiente se crea una instancia de una clase `Student` y se utiliza un inicializador de objeto para inicializar las propiedades.

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

Para obtener más información sobre los inicializadores de objeto, vea [Cómo: declarar un objeto usando un inicializador](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)de objeto, [inicializadores de objeto: tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), y [tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="declaring-multiple-variables"></a>Declarar varias variables

Puede declarar varias variables en una instrucción de declaración, especificando el nombre de la variable para cada una de ellas y siguiendo cada nombre de matriz entre paréntesis. Las variables se separan con comas.

```vb
Dim lastTime, nextTime, allTimes() As Date
```

Si se declara más de una variable con una `As` cláusula, no se puede proporcionar un inicializador para ese grupo de variables.

Puede especificar tipos de datos diferentes para variables diferentes mediante una cláusula de `As` independiente para cada variable que declare. Cada variable toma el tipo de datos especificado en la primera cláusula `As` encontrada después de su parte `variablename`.

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a>Matrices

Puede declarar una variable para que contenga una *matriz*, que puede contener varios valores. Para especificar que una variable contiene una matriz, siga el `variablename` inmediatamente con paréntesis. Para obtener más información sobre las matrices, consulte [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).

Puede especificar el límite inferior y superior de cada dimensión de una matriz. Para ello, incluya una `boundslist` dentro de los paréntesis. Para cada dimensión, el `boundslist` especifica el límite superior y, opcionalmente, el límite inferior. El límite inferior es siempre cero, tanto si se especifica como si no. Cada índice puede variar de cero a través de su valor de límite superior.

Las dos instrucciones siguientes son equivalentes. Cada instrucción declara una matriz de 21 elementos `Integer`. Al tener acceso a la matriz, el índice puede variar de 0 a 20.

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

La instrucción siguiente declara una matriz bidimensional de tipo `Double`. La matriz tiene 4 filas (3 + 1) de 6 columnas (5 + 1) cada una. Tenga en cuenta que un límite superior representa el valor más alto posible para el índice, no la longitud de la dimensión. La longitud de la dimensión es el límite superior más uno.

```vb
Dim matrix2(3, 5) As Double
```

Una matriz puede tener de 1 a 32 dimensiones.

Puede dejar todos los límites en blanco en una declaración de matriz. Si lo hace, la matriz tiene el número de dimensiones que especifique, pero no se inicializa. Tiene un valor de `Nothing` hasta que inicializa al menos algunos de sus elementos. La instrucción `Dim` debe especificar límites para todas las dimensiones o para ninguna dimensión.

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

Si la matriz tiene más de una dimensión, debe incluir comas entre paréntesis para indicar el número de dimensiones.

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

Puede declarar una *matriz de longitud cero* declarando una de las dimensiones de la matriz para que sea-1. Una variable que contiene una matriz de longitud cero no tiene el valor `Nothing`. Ciertas funciones Common Language Runtime requieren matrices de longitud cero. Si intenta obtener acceso a una matriz de este tipo, se produce una excepción en tiempo de ejecución. Para más información, consulte [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).

Puede inicializar los valores de una matriz mediante un literal de matriz. Para ello, incluya los valores de inicialización entre llaves (`{}`).

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

En el caso de las matrices multidimensionales, la inicialización de cada dimensión independiente se incluye entre llaves en la dimensión externa. Los elementos se especifican en orden de fila principal.

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

Para obtener más información sobre los literales de matriz, vea [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="default"></a>Valores y tipos de datos predeterminados

En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.

|¿Tipo de datos especificado?|¿Inicializador especificado?|Ejemplo|Resultado|
|---|---|---|---|
|No|No|`Dim qty`|Si [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) está establecido en OFF (valor predeterminado), la variable se establece en `Nothing`.<br /><br /> Si `Option Strict` está activado, se produce un error en tiempo de compilación.|
|No|Sí|`Dim qty = 5`|Si [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) es on (valor predeterminado), la variable toma el tipo de datos del inicializador. Vea [inferencia de tipo de local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.<br /><br /> Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.|
|Sí|No|`Dim qty As Integer`|La variable se inicializa con el valor predeterminado del tipo de datos. Vea la tabla que aparece más adelante en esta sección.|
|Sí|Sí|`Dim qty  As Integer = 5`|Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.|

Si especifica un tipo de datos pero no especifica un inicializador, Visual Basic inicializa la variable en el valor predeterminado para su tipo de datos. En la tabla siguiente se muestran los valores de inicialización predeterminados.

|Tipo de datos|Valor predeterminado|
|---|---|
|Todos los tipos numéricos (incluidos `Byte` y `SByte`)|0|
|`Char`|Binario 0|
|Todos los tipos de referencia (incluidos `Object`, `String`y todas las matrices)|`Nothing`|
|`Boolean`|`False`|
|`Date`|12:00 A.M. del 1 de enero del año 1 (01/01/0001 12:00:00 AM)|

Cada elemento de una estructura se inicializa como si fuera una variable independiente. Si declara la longitud de una matriz pero no inicializa sus elementos, cada elemento se inicializa como si fuera una variable independiente.

## <a name="static-local-variable-lifetime"></a>Duración de la variable local estática

Una variable local `Static` tiene una duración más larga que la del procedimiento en el que se declara. Los límites de la duración de la variable dependen de dónde se declara el procedimiento y de si se `Shared`.

|Declaración de procedimiento|Variable inicializada|La variable deja de existir|
|---|---|---|
|En un módulo|La primera vez que se llama al procedimiento|Cuando el programa detiene la ejecución|
|En una clase o estructura, el procedimiento es `Shared`|La primera vez que se llama al procedimiento en una instancia específica o en la propia clase o estructura|Cuando el programa detiene la ejecución|
|En una clase o estructura, el procedimiento no es `Shared`|La primera vez que se llama al procedimiento en una instancia específica|Cuando se libera la instancia para la recolección de elementos no utilizados (GC)|

## <a name="attributes-and-modifiers"></a>Atributos y modificadores

Solo puede aplicar atributos a las variables de miembro, no a las variables locales. Un atributo aporta información a los metadatos del ensamblado, lo que no es significativo para el almacenamiento temporal, como las variables locales.

En el nivel de módulo, no se puede usar el modificador `Static` para declarar variables de miembro. En el nivel de procedimiento, no se puede usar `Shared`, `Shadows`, `ReadOnly`, `WithEvents`o cualquier modificador de acceso para declarar variables locales.

Puede especificar qué código puede tener acceso a una variable proporcionando un `accessmodifier`. Las variables de miembro de clase y módulo (fuera de cualquier procedimiento) tienen como valor predeterminado el acceso privado y las variables miembro de estructura tienen como valor predeterminado el acceso público. Los niveles de acceso se pueden ajustar con los modificadores de acceso. No se pueden usar modificadores de acceso en variables locales (dentro de un procedimiento).

Solo puede especificar `WithEvents` en variables de miembro, no en variables locales dentro de un procedimiento. Si especifica `WithEvents`, el tipo de datos de la variable debe ser un tipo de clase específico, no `Object`. No se puede declarar una matriz con `WithEvents`. Para obtener más información sobre los eventos, vea [eventos](../../../visual-basic/programming-guide/language-features/events/index.md).

> [!NOTE]
> El código fuera de una clase, estructura o módulo debe calificar el nombre de una variable miembro con el nombre de esa clase, estructura o módulo. El código fuera de un procedimiento o bloque no puede hacer referencia a ninguna variable local dentro de ese procedimiento o bloque.

## <a name="releasing-managed-resources"></a>Liberar recursos administrados

El recolector de elementos no utilizados de .NET Framework elimina los recursos administrados sin necesidad de codificación adicional por su parte. Sin embargo, puede forzar la eliminación de un recurso administrado en lugar de esperar al recolector de elementos no utilizados.

Si una clase contiene un recurso especialmente valioso y escaso (como una conexión de base de datos o un identificador de archivo), es posible que no desee esperar hasta la siguiente recolección de elementos no utilizados para limpiar una instancia de clase que ya no está en uso. Una clase puede implementar la interfaz <xref:System.IDisposable> para proporcionar una manera de liberar recursos antes de una recolección de elementos no utilizados. Una clase que implementa esa interfaz expone un método `Dispose` al que se puede llamar para obligar a que se liberen recursos valiosos de forma inmediata.

La instrucción `Using` automatiza el proceso de adquisición de un recurso, la ejecución de un conjunto de instrucciones y la eliminación del recurso. Sin embargo, el recurso debe implementar la interfaz <xref:System.IDisposable>. Para obtener más información, vea [Using (Instrucción)](../../../visual-basic/language-reference/statements/using-statement.md).

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se declaran variables mediante la instrucción `Dim` con varias opciones.

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se enumeran los números primos entre 1 y 30. El ámbito de las variables locales se describe en los comentarios de código.

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, la variable `speedValue` se declara en el nivel de clase. La palabra clave `Private` se utiliza para declarar la variable. Cualquier procedimiento de la clase `Car` puede tener acceso a la variable.

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a>Vea también

- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)
- [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Option Explicit (instrucción)](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Option Infer (instrucción)](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Página Compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Declarar un objeto usando un inicializador de objeto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
