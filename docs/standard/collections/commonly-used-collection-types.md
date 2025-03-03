---
title: Tipos de colección utilizados normalmente
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- objects [.NET Framework], grouping in collections
- generics [.NET Framework], collections
- IList interface, grouping data in collections
- IDictionary interface, grouping data in collections
- grouping data in collections, generic collection types
- Collections classes
- generic collections
ms.assetid: f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c21a1303cd67f5f5de42241f4d5ada929e68bf2c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589890"
---
# <a name="commonly-used-collection-types"></a>Tipos de colección utilizados normalmente
Los tipos de colecciones son las variaciones comunes de las colecciones de datos, como tablas hash, colas, pilas, bolsas, diccionarios y listas.  
  
 Las colecciones se basan en las interfaces <xref:System.Collections.ICollection>, <xref:System.Collections.IList>, <xref:System.Collections.IDictionary> o en sus equivalentes genéricos. La interfaz <xref:System.Collections.IList> y la interfaz <xref:System.Collections.IDictionary> se derivan ambas de la interfaz <xref:System.Collections.ICollection>; por lo tanto, todas las colecciones se basan en la interfaz <xref:System.Collections.ICollection> directa o indirectamente. En colecciones basadas en la interfaz <xref:System.Collections.IList> (como <xref:System.Array>, <xref:System.Collections.ArrayList> o <xref:System.Collections.Generic.List%601>) o directamente en la interfaz <xref:System.Collections.ICollection> (como <xref:System.Collections.Queue>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Stack>, <xref:System.Collections.Concurrent.ConcurrentStack%601> o <xref:System.Collections.Generic.LinkedList%601>), cada elemento contiene un solo valor. En colecciones basadas en la interfaz <xref:System.Collections.IDictionary> (como las clases <xref:System.Collections.Hashtable> y <xref:System.Collections.SortedList>, y las clases genéricas <xref:System.Collections.Generic.Dictionary%602> y <xref:System.Collections.Generic.SortedList%602>), o en las clases <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, cada elemento contiene una clave y un valor.  La clase <xref:System.Collections.ObjectModel.KeyedCollection%602> es única porque es una lista de valores con claves insertadas en los valores y, por lo tanto, se comporta como una lista y como un diccionario.  
  
 Las colecciones genéricas son la mejor solución para elementos fuertemente tipados. Sin embargo, si su lenguaje no admite genéricos, el espacio de nombres <xref:System.Collections> incluye colecciones base, como <xref:System.Collections.CollectionBase>, <xref:System.Collections.ReadOnlyCollectionBase> y <xref:System.Collections.DictionaryBase>, que son clases base abstractas que se pueden extender para crear clases de colección fuertemente tipadas. Cuando se requiere un acceso eficaz a una colección multiproceso, utilice las colecciones genéricas del espacio de nombres <xref:System.Collections.Concurrent>.  
  
 Las colecciones pueden variar en función de cómo se almacenan los elementos, cómo se ordenan, cómo se realizan las búsquedas y cómo se realizan las comparaciones. La clase <xref:System.Collections.Queue> y la clase genérica <xref:System.Collections.Generic.Queue%601> proporcionan listas de tipo “el primero en entrar es el primero en salir”, mientras que la clase <xref:System.Collections.Stack> y la clase genérica <xref:System.Collections.Generic.Stack%601> proporcionan listas de tipo “el último en entrar es el primero en salir”. La clase <xref:System.Collections.SortedList> y la clase genérica <xref:System.Collections.Generic.SortedList%602> proporcionan versiones ordenadas de la clase <xref:System.Collections.Hashtable> y de la clase genérica <xref:System.Collections.Generic.Dictionary%602>. El acceso a los elementos de <xref:System.Collections.Hashtable> o de <xref:System.Collections.Generic.Dictionary%602> solo es posible mediante la clave del elemento, pero el acceso a los elementos de <xref:System.Collections.SortedList> o de <xref:System.Collections.ObjectModel.KeyedCollection%602> es posible mediante la clave o mediante el índice del elemento. Los índices de todas las colecciones son de base cero, excepto <xref:System.Array>, que permite matrices que no son de base cero.  
  
 La característica LINQ to Objects permite usar consultas LINQ para obtener acceso a los objetos en memoria mientras el tipo de objeto implemente la interfaz <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>. Las consultas LINQ proporcionan un modelo común para el acceso a datos; suelen ser más concisas y legibles que los bucles `foreach` estándar, y proporcionan capacidades de filtrado, ordenación y agrupación. Las consultas LINQ también pueden mejorar el rendimiento. Para más información, vea [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) y [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Colecciones y estructuras de datos](../../../docs/standard/collections/index.md)|Describe los diversos tipos de colecciones disponibles en .NET Framework, incluidas las pilas, colas, listas, matrices y diccionarios.|  
|[Tipos de las colecciones Hashtable y Dictionary](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Describe las características de los tipos de diccionario basado en hash genéricos y no genéricos.|  
|[Tipos de colecciones ordenadas](../../../docs/standard/collections/sorted-collection-types.md)|Describe las clases que proporcionan funcionalidad de ordenación para las listas y los conjuntos.|  
|[Genéricos](../../../docs/standard/generics/index.md)|Describe la característica de genéricos, incluidas las colecciones, los delegados y las interfaces genéricos proporcionados por .NET Framework. Proporciona vínculos a la documentación de características para C#, Visual Basic y Visual C++, así como a tecnologías de apoyo como la reflexión.|  
  
## <a name="reference"></a>Referencia  
 <xref:System.Collections?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
  
 <xref:System.Collections.ICollection?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.ICollection%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IList?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IList%601?displayProperty=nameWithType>  
  
 <xref:System.Collections.IDictionary?displayProperty=nameWithType>  
  
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
