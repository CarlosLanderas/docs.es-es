---
title: Palabras clave como nombres de elementos en código
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 4cdcda7c5c78481af1633bf29d75070c521ab393
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347394"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="3ccd8-102">Palabras clave como nombres de elementos en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ccd8-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="3ccd8-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="3ccd8-104">For example, you can create a variable named `Loop`.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="3ccd8-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#8)]  
  
 <span data-ttu-id="3ccd8-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span><span class="sxs-lookup"><span data-stu-id="3ccd8-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="3ccd8-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="3ccd8-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="3ccd8-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="3ccd8-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ccd8-111">Your program also might include element names provided by other referenced assemblies.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="3ccd8-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span><span class="sxs-lookup"><span data-stu-id="3ccd8-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccd8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ccd8-113">See also</span></span>

- [<span data-ttu-id="3ccd8-114">Visual Basic Naming Conventions</span><span class="sxs-lookup"><span data-stu-id="3ccd8-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="3ccd8-115">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="3ccd8-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="3ccd8-116">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3ccd8-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
