---
title: Consultas en LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: 52f48fcacd6fbd92e4fd0531c5e1fa3577496941
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738482"
---
# <a name="queries-in-linq-to-entities"></a>Consultas en LINQ to Entities
Una consulta es una expresión que recupera datos de un origen de datos. Las consultas se suelen expresar en un lenguaje de consulta especializado, como SQL para bases de datos relacionales y XQuery para XML. Por lo tanto, los programadores han tenido que aprender un lenguaje de consultas nuevo para cada tipo de origen de datos o formato de datos que consultan. Language-Integrated Query (LINQ) ofrece un modelo coherente y más sencillo para trabajar con los datos de varios formatos y orígenes de datos. En una consulta de LINQ siempre se trabaja con objetos de programación.  
  
 Una operación de consulta de LINQ consta de tres acciones: obtener el origen o los orígenes de datos, crear la consulta y ejecutar la consulta.  
  
 Los orígenes de datos que implementan las interfaces genéricas <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> pueden consultarse a través de LINQ. Las instancias de la clase <xref:System.Data.Objects.ObjectQuery%601> genérica, que implementa la interfaz de <xref:System.Linq.IQueryable%601> genérica, actúan como origen de datos para las consultas de LINQ to Entities. La clase <xref:System.Data.Objects.ObjectQuery%601> genérica representa una consulta que devuelve una colección de cero o más objetos con tipo. También puede permitir que el compilador infiera el tipo de una entidad C# mediante la palabra clave `var` (Dim in Visual Basic).  
  
 En la consulta se especifica exactamente la información que se desea recuperar del origen de datos. Una consulta también puede especificar cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva. En LINQ, una consulta se almacena en una variable. Si la consulta devuelve una secuencia de valores, la propia variable de la consulta debe ser de un tipo que se pueda consultar. Esta variable de consulta no realiza ninguna acción y no devuelve datos; solamente almacena la información de la consulta. Tras crear una consulta debe ejecutarla para recuperar los datos.  
  
## <a name="query-syntax"></a>Sintaxis de consulta  
 Las consultas de LINQ to Entities se pueden formular en dos sintaxis diferentes: sintaxis de expresiones de consulta y sintaxis de consultas basadas en métodos. La sintaxis de las expresiones de C# consulta es nueva en 3,0 y Visual Basic 9,0, y consta de un conjunto de cláusulas escritas en una sintaxis declarativa similar a TRANSACT-SQL o XQuery. Sin embargo, el Common Language Runtime de .NET Framework (CLR) no puede leer la sintaxis de expresiones de consulta en sí. Por lo tanto, en tiempo de compilación, las expresiones de consulta se traducen a algo que CLR no comprende: las llamadas a métodos. Estos métodos se conocen como *operadores de consulta estándar*. Como programador, tiene la opción de llamarlos directamente utilizando la sintaxis de método en lugar de la sintaxis de consulta. Para obtener más información, vea [Query Syntax and Method Syntax in LINQ](../../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ).  
  
### <a name="query-expression-syntax"></a>Sintaxis de expresiones de consulta  
 Las expresiones de consulta son una sintaxis de consulta declarativa. Esta sintaxis permite a un programador escribir consultas en un lenguaje de alto nivel que tenga un formato similar al de Transact-SQL. Si se utiliza la sintaxis de expresiones de consulta, se pueden realizar incluso operaciones complejas de filtrado, ordenación y agrupamiento en orígenes de datos con código mínimo. Para obtener más información, [consulte operaciones básicas de consulta (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Para obtener ejemplos que muestran cómo utilizar la sintaxis de expresiones de consulta, vea los siguientes temas:  
  
- [Ejemplos de sintaxis de expresiones de consulta: proyección](query-expression-syntax-examples-projection.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: filtrado](query-expression-syntax-examples-filtering.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: ordenación](query-expression-syntax-examples-ordering.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: operadores de agregado](query-expression-syntax-examples-aggregate-operators.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: particionamiento](query-expression-syntax-examples-partitioning.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: operadores de combinación](query-expression-syntax-examples-join-operators.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: operadores de elementos](query-expression-syntax-examples-element-operators.md)  
  
- [Ejemplos de sintaxis de expresiones de consulta: agrupación](query-expression-syntax-examples-grouping.md)  
  
- [Ejemplos de sintaxis de expresión de consulta: navegar por relaciones](query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Sintaxis de consultas basadas en métodos  
 Otra forma de crear consultas LINQ to Entities es mediante el uso de consultas basadas en métodos. La sintaxis de las consultas basadas en métodos es una secuencia de llamadas de método directo a los métodos de operador de LINQ, pasando expresiones lambda como parámetros. Para obtener más información, vea [Lambda Expressions](../../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) (Expresiones lambda). Para obtener ejemplos que muestran cómo utilizar la sintaxis basada en métodos, vea los siguientes temas:  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: proyección](method-based-query-syntax-examples-projection.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: filtrado](method-based-query-syntax-examples-filtering.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: ordenación](method-based-query-syntax-examples-ordering.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: operadores de agregación](method-based-query-syntax-examples-aggregate-operators.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: partición](method-based-query-syntax-examples-partitioning.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: conversión](method-based-query-syntax-examples-conversion.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: operadores de combinación](method-based-query-syntax-examples-join-operators.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: operadores de elementos](method-based-query-syntax-examples-element-operators.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: agrupación](method-based-query-syntax-examples-grouping.md)  
  
- [Ejemplos de sintaxis de consultas basadas en métodos: navegar por relaciones](method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Vea también

- [LINQ to Entities](linq-to-entities.md)
- [Introducción a LINQ en C#](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Introducción a LINQ en Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Entity Framework opciones de combinación y consultas compiladas](https://go.microsoft.com/fwlink/?LinkId=199591)
