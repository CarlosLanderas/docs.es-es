---
title: Procedimiento para analizar una cadena (C#)
ms.date: 07/20/2015
ms.assetid: 81e5686c-9658-42d8-a7e3-b11be0a2c98b
ms.openlocfilehash: 086a4baecee9ee927b08d6da53d16324ef32e8a8
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140978"
---
# <a name="how-to-parse-a-string-c"></a><span data-ttu-id="cb5c5-102">Procedimiento para analizar una cadena (C#)</span><span class="sxs-lookup"><span data-stu-id="cb5c5-102">How to: Parse a String (C#)</span></span>

<span data-ttu-id="cb5c5-103">En este tema se muestra cómo analizar una cadena para crear un árbol XML en C#.</span><span class="sxs-lookup"><span data-stu-id="cb5c5-103">This topic shows how to parse a string to create an XML tree in C#.</span></span>

## <a name="example"></a><span data-ttu-id="cb5c5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb5c5-104">Example</span></span>

<span data-ttu-id="cb5c5-105">El siguiente código de C# muestra cómo analizar una cadena XML:</span><span class="sxs-lookup"><span data-stu-id="cb5c5-105">The following C# code shows how to parse an XML string:</span></span>

```csharp
XElement contacts = XElement.Parse(
    @"<Contacts>
        <Contact>
            <Name>Patrick Hines</Name>
            <Phone Type=""home"">206-555-0144</Phone>
            <Phone Type=""work"">425-555-0145</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>10</NetWorth>
        </Contact>
        <Contact>
            <Name>Gretchen Rivas</Name>
            <Phone Type=""mobile"">206-555-0163</Phone>
            <Address>
            <Street1>123 Main St</Street1>
            <City>Mercer Island</City>
            <State>WA</State>
            <Postal>68042</Postal>
            </Address>
            <NetWorth>11</NetWorth>
        </Contact>
    </Contacts>");
Console.WriteLine(contacts);
```

<span data-ttu-id="cb5c5-106">El nodo `Contacts` raíz tiene dos nodos `Contact`.</span><span class="sxs-lookup"><span data-stu-id="cb5c5-106">The root `Contacts` node has two `Contact` nodes.</span></span> <span data-ttu-id="cb5c5-107">Para acceder a algunos datos específicos en su XML analizado, use el método [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements), que en este caso devuelve los elementos secundarios del nodo raíz `Contacts`.</span><span class="sxs-lookup"><span data-stu-id="cb5c5-107">To access some specific data in your parsed XML, use the [XElement.Elements()](xref:System.Xml.Linq.XContainer.Elements) method, which in this case returns the child elements of the root `Contacts` node.</span></span> <span data-ttu-id="cb5c5-108">En el siguiente ejemplo se imprime el primer nodo `Contact` en la consola:</span><span class="sxs-lookup"><span data-stu-id="cb5c5-108">The following example prints the first `Contact` node to the console:</span></span>

```csharp
List<XElement> contactNodes = contacts.Elements("Contact").ToList();
Console.WriteLine(contactNodes[0]);
```

## <a name="see-also"></a><span data-ttu-id="cb5c5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb5c5-109">See also</span></span>

- [<span data-ttu-id="cb5c5-110">Procedimiento para buscar un elemento con un atributo específico (C#)</span><span class="sxs-lookup"><span data-stu-id="cb5c5-110">How to find an element with a specific attribute (C#)</span></span>](how-to-find-an-element-with-a-specific-attribute.md)
