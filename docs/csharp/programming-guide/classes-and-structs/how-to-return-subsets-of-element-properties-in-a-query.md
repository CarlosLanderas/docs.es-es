---
title: Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 1266b866d671854c787d907b91f654c128681de9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970457"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta (Guía de programación de C#)
Use un tipo anónimo en una expresión de consulta cuando se cumplan estas dos condiciones:  
  
- Solo quiere algunas de las propiedades de cada elemento de origen.  
  
- No es necesario almacenar los resultados de la consulta fuera del ámbito del método en el que se ejecuta la consulta.  
  
 Si solo quiere devolver una propiedad o campo de cada elemento de origen, puede usar simplemente el operador de punto en la cláusula `select`. Por ejemplo, para devolver solo el `ID` de cada `student`, escriba la cláusula `select` como sigue:  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar un tipo anónimo para devolver solo un subconjunto de las propiedades de cada elemento de origen que coincida con la condición especificada.  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 Tenga en cuenta que, si no se especifica ningún nombre, el tipo anónimo usa los nombres del elemento de origen para sus propiedades. Para asignar nombres nuevos a las propiedades del tipo anónimo, escriba la instrucción `select` como sigue:  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Si lo intenta en el ejemplo anterior, también debe cambiar la instrucción `Console.WriteLine`:  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
Para ejecutar este código, copie y pegue la clase en una aplicación de consola de C# con una directiva `using` de System.Linq.
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Tipos anónimos](./anonymous-types.md)
- [LINQ en C#](../../linq/index.md)
