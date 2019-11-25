---
title: Serializar árboles XML
ms.date: 07/20/2015
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
ms.openlocfilehash: 6b91078ff7f1b0410f97be9bc9ed3601f3ca0733
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351043"
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="2c6e4-102">Serializing XML Trees (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c6e4-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="2c6e4-103">Serializar un árbol XML significa generar XML a partir de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="2c6e4-104">Puede serializarlo en un archivo, en una implementación concreta de la clase <xref:System.IO.TextWriter> o en una implementación concreta de un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="2c6e4-105">Puede controlar diversos aspectos del proceso de serialización.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="2c6e4-106">Por ejemplo, puede decidir si desea agregar una sangría al XML serializado y si desea escribe una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c6e4-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2c6e4-107">In This Section</span></span>  
  
|<span data-ttu-id="2c6e4-108">Tema</span><span class="sxs-lookup"><span data-stu-id="2c6e4-108">Topic</span></span>|<span data-ttu-id="2c6e4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c6e4-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2c6e4-110">Mantener un espacio en blanco al serializar</span><span class="sxs-lookup"><span data-stu-id="2c6e4-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="2c6e4-111">Describe cómo controlar el comportamiento de los espacios en blanco a la hora de serializar árboles XML.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="2c6e4-112">Serializing with an XML Declaration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c6e4-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="2c6e4-113">Describe cómo serializar un árbol XML que incluya una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="2c6e4-114">Serializar en archivos, escritores de texto y escritores XML</span><span class="sxs-lookup"><span data-stu-id="2c6e4-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="2c6e4-115">Describe cómo serializar un documento en un <xref:System.IO.File>, un <xref:System.IO.TextWriter> o un <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="2c6e4-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c6e4-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="2c6e4-117">Describe cómo crear un <xref:System.Xml.XmlReader> que permita a otro módulo leer los contenidos de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="2c6e4-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c6e4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c6e4-118">See also</span></span>

- [<span data-ttu-id="2c6e4-119">Programming Guide (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c6e4-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
