---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352241"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="3eeb4-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3eeb4-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="3eeb4-102">Specifies the return value of the property or function.</span><span class="sxs-lookup"><span data-stu-id="3eeb4-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eeb4-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3eeb4-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eeb4-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3eeb4-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="3eeb4-105">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="3eeb4-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eeb4-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3eeb4-106">Remarks</span></span>  
 <span data-ttu-id="3eeb4-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span><span class="sxs-lookup"><span data-stu-id="3eeb4-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="3eeb4-108">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="3eeb4-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eeb4-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3eeb4-109">Example</span></span>  
 <span data-ttu-id="3eeb4-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span><span class="sxs-lookup"><span data-stu-id="3eeb4-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3eeb4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eeb4-111">See also</span></span>

- [<span data-ttu-id="3eeb4-112">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="3eeb4-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
