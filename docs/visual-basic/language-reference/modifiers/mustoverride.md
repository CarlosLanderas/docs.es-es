---
title: MustOverride
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351490"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="ec435-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec435-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="ec435-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span><span class="sxs-lookup"><span data-stu-id="ec435-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec435-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec435-104">Remarks</span></span>  
 <span data-ttu-id="ec435-105">You can use `MustOverride` only in a property or procedure declaration statement.</span><span class="sxs-lookup"><span data-stu-id="ec435-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="ec435-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="ec435-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ec435-107">Reglas</span><span class="sxs-lookup"><span data-stu-id="ec435-107">Rules</span></span>  
  
- <span data-ttu-id="ec435-108">**Incomplete Declaration.**</span><span class="sxs-lookup"><span data-stu-id="ec435-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="ec435-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span><span class="sxs-lookup"><span data-stu-id="ec435-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="ec435-110">**Combined Modifiers.**</span><span class="sxs-lookup"><span data-stu-id="ec435-110">**Combined Modifiers.**</span></span> <span data-ttu-id="ec435-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span><span class="sxs-lookup"><span data-stu-id="ec435-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="ec435-112">**Shadowing and Overriding.**</span><span class="sxs-lookup"><span data-stu-id="ec435-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="ec435-113">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="ec435-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="ec435-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="ec435-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="ec435-115">**Alternate Terms.**</span><span class="sxs-lookup"><span data-stu-id="ec435-115">**Alternate Terms.**</span></span> <span data-ttu-id="ec435-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span><span class="sxs-lookup"><span data-stu-id="ec435-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="ec435-117">El modificador `MustOverride` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ec435-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ec435-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ec435-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ec435-119">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ec435-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ec435-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ec435-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec435-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec435-121">See also</span></span>

- [<span data-ttu-id="ec435-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ec435-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="ec435-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="ec435-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="ec435-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="ec435-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="ec435-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="ec435-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="ec435-126">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ec435-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ec435-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec435-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
