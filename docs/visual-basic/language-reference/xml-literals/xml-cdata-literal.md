---
title: Literal de CDATA XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 72e899e7bd30f2edf0e88207bb3b75bdf36fa11c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349431"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="21862-102">Literal de CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21862-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="21862-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span><span class="sxs-lookup"><span data-stu-id="21862-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21862-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21862-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="21862-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="21862-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="21862-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="21862-106">Required.</span></span> <span data-ttu-id="21862-107">Denotes the start of the XML CDATA section.</span><span class="sxs-lookup"><span data-stu-id="21862-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="21862-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="21862-108">Required.</span></span> <span data-ttu-id="21862-109">Text content to appear in the XML CDATA section.</span><span class="sxs-lookup"><span data-stu-id="21862-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="21862-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="21862-110">Required.</span></span> <span data-ttu-id="21862-111">Denotes the end of the section.</span><span class="sxs-lookup"><span data-stu-id="21862-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21862-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21862-112">Return Value</span></span>  
 <span data-ttu-id="21862-113">Un objeto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="21862-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21862-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21862-114">Remarks</span></span>  
 <span data-ttu-id="21862-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span><span class="sxs-lookup"><span data-stu-id="21862-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="21862-116">A XML CDATA section can contain any text.</span><span class="sxs-lookup"><span data-stu-id="21862-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="21862-117">This includes reserved XML characters.</span><span class="sxs-lookup"><span data-stu-id="21862-117">This includes reserved XML characters.</span></span> <span data-ttu-id="21862-118">The XML CDATA section ends with the sequence "]]>".</span><span class="sxs-lookup"><span data-stu-id="21862-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="21862-119">This implies the following points:</span><span class="sxs-lookup"><span data-stu-id="21862-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="21862-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span><span class="sxs-lookup"><span data-stu-id="21862-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="21862-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span><span class="sxs-lookup"><span data-stu-id="21862-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="21862-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span><span class="sxs-lookup"><span data-stu-id="21862-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21862-123">An XML literal can span multiple lines but does not use line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="21862-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="21862-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="21862-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="21862-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="21862-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21862-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21862-126">Example</span></span>  
 <span data-ttu-id="21862-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span><span class="sxs-lookup"><span data-stu-id="21862-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="21862-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="21862-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="21862-129">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="21862-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="21862-130">Literales XML</span><span class="sxs-lookup"><span data-stu-id="21862-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="21862-131">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21862-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
