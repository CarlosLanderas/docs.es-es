---
title: Procedimiento para buscar elementos descendientes (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c90651502629284c67cc16de8a1aa59c392ae178
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141102"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="4db97-102">Procedimiento para buscar elementos descendientes (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="4db97-102">How to find descendant elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="4db97-103">En este tema se muestra cómo obtener los elementos descendientes con un nombre particular.</span><span class="sxs-lookup"><span data-stu-id="4db97-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="4db97-104">La expresión XPath es `//Name`.</span><span class="sxs-lookup"><span data-stu-id="4db97-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4db97-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4db97-105">Example</span></span>  
 <span data-ttu-id="4db97-106">Este ejemplo busca todos los descendientes con el nombre `Name`.</span><span class="sxs-lookup"><span data-stu-id="4db97-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="4db97-107">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4db97-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="4db97-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="4db97-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
