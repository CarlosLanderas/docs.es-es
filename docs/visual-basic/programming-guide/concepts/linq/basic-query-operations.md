---
title: Operaciones básicas de consulta
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: e9a646d60bb22507f4c6bcbcdf9222fd0ed18f02
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345757"
---
# <a name="basic-query-operations-visual-basic"></a>Operaciones básicas de consulta (Visual Basic)
En este tema se proporciona una breve introducción a las expresiones [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] en Visual Basic y a algunos de los tipos de operaciones típicas que se realizan en una consulta. Para obtener más información, consulta los temas siguientes:  
  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Consultas](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Tutorial: escribir consultas en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Especificar el origen de datos (desde)  
 En una consulta de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], el primer paso es especificar el origen de datos que desea consultar. Por lo tanto, la cláusula `From` de una consulta siempre aparece primero. Los operadores de consulta seleccionan y dan forma al resultado en función del tipo de origen.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 La cláusula `From` especifica el origen de datos, el `customers`y una *variable de rango*, `cust`. La variable de rango es como una variable de iteración de bucle, salvo que en una expresión de consulta no se produce ninguna iteración real. Cuando se ejecuta la consulta, a menudo con un bucle `For Each`, la variable de rango sirve como referencia a cada elemento sucesivo de `customers`. Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente. Para obtener ejemplos de consultas escritas con y sin tipos explícitos, vea [relaciones de tipos en operaciones de consulta (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Para obtener más información sobre cómo usar la cláusula `From` en Visual Basic, vea [cláusula FROM](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtrar datos (dónde)  
 Probablemente, la operación de consulta más común es aplicar un filtro en forma de expresión booleana. A continuación, la consulta devuelve solo los elementos para los que la expresión es verdadera. Se utiliza una cláusula `Where` para realizar el filtrado. El filtro especifica los elementos del origen de datos que se van a incluir en la secuencia resultante. En el ejemplo siguiente, solo se incluyen los clientes que tienen una dirección en Londres.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Puede utilizar operadores lógicos como `And` y `Or` para combinar expresiones de filtro en una cláusula `Where`. Por ejemplo, para devolver solo los clientes que son de Londres y cuyo nombre es Devon, use el código siguiente:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Para devolver los clientes de Londres o París, use el código siguiente:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Para obtener más información sobre cómo usar la cláusula `Where` en Visual Basic, vea [cláusula WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Datos de ordenación (order by)  
 A menudo resulta cómodo ordenar los datos devueltos en un orden determinado. La cláusula `Order By` hará que los elementos de la secuencia devuelta se ordenen en un campo o campos especificados. Por ejemplo, la siguiente consulta ordena los resultados en función de la propiedad `Name`. Dado que `Name` es una cadena, los datos devueltos se ordenarán alfabéticamente, de la a a la Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Para ordenar los resultados en orden inverso, de la Z a la A, use la cláusula `Order By...Descending`. El valor predeterminado es `Ascending` cuando no se especifica ni `Ascending` ni `Descending`.  
  
 Para obtener más información sobre cómo usar la cláusula `Order By` en Visual Basic, vea [cláusula order by](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Seleccionar datos (Select)  
 La cláusula `Select` especifica la forma y el contenido de los elementos devueltos. Por ejemplo, puede especificar si los resultados van a ser completos `Customer` objetos, solo una `Customer` propiedad, un subconjunto de propiedades, una combinación de propiedades de varios orígenes de datos o algún nuevo tipo de resultado basado en un cálculo. Cuando la cláusula `Select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*.  
  
 Para recuperar una colección que consta de objetos completos `Customer`, seleccione la variable de rango en sí:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Si una instancia de `Customer` es un objeto grande que tiene muchos campos y todo lo que desea recuperar es el nombre, puede seleccionar `cust.Name`, tal y como se muestra en el ejemplo siguiente. La inferencia de tipo local reconoce que esto cambia el tipo de resultado de una colección de objetos de `Customer` a una colección de cadenas.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Para seleccionar varios campos del origen de datos, tiene dos opciones:  
  
- En la cláusula `Select`, especifique los campos que desea incluir en el resultado. El compilador definirá un tipo anónimo que tiene esos campos como sus propiedades. Para obtener más información, vea [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Dado que los elementos devueltos en el ejemplo siguiente son instancias de un tipo anónimo, no se puede hacer referencia al tipo por su nombre en ningún lugar del código. El nombre designado por el compilador para el tipo contiene caracteres que no son válidos en el código de Visual Basic normal. En el ejemplo siguiente, los elementos de la colección devueltos por la consulta en `londonCusts4` son instancias de un tipo anónimo.  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     O bien,  
  
- Defina un tipo con nombre que contenga los campos concretos que desea incluir en el resultado y cree e inicialice instancias del tipo en la cláusula `Select`. Utilice esta opción solo si tiene que utilizar resultados individuales fuera de la colección en la que se devuelven, o bien, si tiene que pasarlos como parámetros en las llamadas de método. El tipo de `londonCusts5` en el ejemplo siguiente es IEnumerable (of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Para obtener más información sobre cómo usar la cláusula `Select` en Visual Basic, vea [cláusula SELECT](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Combinar datos (combinación y combinación de grupo)  
 Puede combinar más de un origen de datos en la cláusula `From` de varias maneras. Por ejemplo, el código siguiente usa dos orígenes de datos y combina implícitamente las propiedades de ambos en el resultado. La consulta selecciona estudiantes cuyos apellidos empiezan por una vocal.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> Puede ejecutar este código con la lista de estudiantes creados en [Cómo: crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 La palabra clave `Join` es equivalente a una `INNER JOIN` en SQL. Combina dos colecciones en función de los valores de clave coincidentes entre los elementos de las dos colecciones. La consulta devuelve todos o parte de los elementos de la colección que tienen valores de clave coincidentes. Por ejemplo, el código siguiente duplica la acción de la combinación implícita anterior.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` combina colecciones en una sola colección jerárquica, al igual que un `LEFT JOIN` en SQL. Para obtener más información, vea cláusula [join](../../../../visual-basic/language-reference/queries/join-clause.md) y Group [join](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Agrupar datos (agrupar por)  
 Puede Agregar una cláusula `Group By` para agrupar los elementos del resultado de una consulta de acuerdo con uno o varios campos de los elementos. Por ejemplo, el código siguiente agrupa estudiantes por año de clase.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Si ejecuta este código mediante la lista de estudiantes creados en [Cómo: crear una lista de elementos](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), la salida de la instrucción `For Each` es:  
  
 Año: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, lance  
  
 Año: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng, Hanying  
  
 Adams, Terry  
  
 Año: actualizado  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 La variación que se muestra en el código siguiente ordena los años de la clase y, a continuación, ordena los estudiantes de cada año por Apellido.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Para obtener más información sobre `Group By`, consulte [cláusula Group by](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic.IEnumerable%601>
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
