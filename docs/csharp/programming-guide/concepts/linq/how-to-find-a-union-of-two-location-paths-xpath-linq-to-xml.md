---
title: Procedimiento para buscar la unión de dos rutas de acceso a ubicaciones (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 17a3310f367cb68b3b80b1a3f30af40428f6d2c7
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141211"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a>Procedimiento para buscar la unión de dos rutas de acceso a ubicaciones (XPath-LINQ to XML) (C#)
XPath permite buscar la unión de los resultados de dos rutas de ubicación XPath.  
  
 La expresión XPath es:  
  
 `//Category|//Price`  
  
 Puede conseguir los mismos resultados usando el operador de consulta estándar <xref:System.Linq.Enumerable.Concat%2A>.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo busca todos los elementos `Category` y todos los elementos `Price` y los concatena en una única recopilación. Tenga en cuenta que la consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] llama a <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> para ordenar los resultados. Los resultados de la evaluación de la expresión XPath también están en el orden del documento.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  