---
title: Procedimiento para buscar caracteres en una cadena (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: bc72c4370ff408a60f48aa020a16dae7f48f702a
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140961"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a>Procedimiento para buscar caracteres en una cadena (LINQ) (C#)
Como la clase <xref:System.String> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> genérica, cualquier cadena puede consultarse como una secuencia de caracteres. Pero esto no es un uso habitual de LINQ. Para operaciones de coincidencia de patrones complejas, use la clase <xref:System.Text.RegularExpressions.Regex>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene. Tenga en cuenta que la consulta se "reutiliza" después de que se ejecute la primera vez. Esto es posible porque la propia consulta no almacena ningún resultado real.  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.  
  
## <a name="see-also"></a>Vea también

- [LINQ y cadenas (C#)](./linq-and-strings.md)
- [Procedimiento para combinar consultas LINQ con expresiones regulares (C#)](./how-to-combine-linq-queries-with-regular-expressions.md)
