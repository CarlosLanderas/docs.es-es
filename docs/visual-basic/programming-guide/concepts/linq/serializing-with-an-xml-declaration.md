---
title: Serializar con una declaración XML
ms.date: 07/20/2015
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
ms.openlocfilehash: 96c95b4c94290016684721a194ca31a836a49740
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350630"
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="f8bf8-102">Serializing with an XML Declaration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8bf8-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="f8bf8-103">En este tema se describe cómo controlar si la serialización genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="f8bf8-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="f8bf8-104">Generación de declaración XML</span><span class="sxs-lookup"><span data-stu-id="f8bf8-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="f8bf8-105">La serialización en <xref:System.IO.File> o <xref:System.IO.TextWriter> mediante el método <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> o el método <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="f8bf8-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="f8bf8-106">Cuando serializa en <xref:System.Xml.XmlWriter>, la configuración del escritor (especificada en un objeto <xref:System.Xml.XmlWriterSettings>) determina si se genera una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="f8bf8-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="f8bf8-107">Si está serializando en una cadena mediante el método `ToString`, el XML resultante no incluirá una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="f8bf8-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="f8bf8-108">Serializar con una declaración XML</span><span class="sxs-lookup"><span data-stu-id="f8bf8-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="f8bf8-109">En el ejemplo siguiente se crea un <xref:System.Xml.Linq.XElement>, se guarda el documento en un archivo y, a continuación, se imprime el archivo en la consola:</span><span class="sxs-lookup"><span data-stu-id="f8bf8-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="f8bf8-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f8bf8-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="f8bf8-111">Serializar sin una declaración XML</span><span class="sxs-lookup"><span data-stu-id="f8bf8-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="f8bf8-112">En el siguiente ejemplo se muestra cómo guardar un <xref:System.Xml.Linq.XElement> en un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="f8bf8-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="f8bf8-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f8bf8-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8bf8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8bf8-114">See also</span></span>

- [<span data-ttu-id="f8bf8-115">Serializing XML Trees (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8bf8-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
