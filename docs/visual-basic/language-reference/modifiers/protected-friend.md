---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: f92021f5f0dab9762470c270bdd5182187d587e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351323"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="136a7-102">Friend protegido (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="136a7-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="136a7-103">La combinación de palabras claves `Protected Friend` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="136a7-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="136a7-104">Confiere acceso de [confianza](friend.md) y acceso [protegido](protected.md) en los elementos declarados, por lo que son accesibles desde cualquier lugar del mismo ensamblado, desde su propia clase y desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="136a7-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="136a7-105">Solo puede especificar `Protected Friend` en miembros de clases; no se puede aplicar `Protected Friend` a los miembros de una estructura porque las estructuras no se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="136a7-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="136a7-106">En Visual Studio, al seleccionar la ayuda F1 en `protected friend` se proporciona ayuda para [Protected](protected.md) o [Friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="136a7-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="136a7-107">El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="136a7-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="136a7-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="136a7-108">Rules</span></span>

<span data-ttu-id="136a7-109">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="136a7-109">**Declaration Context.**</span></span> <span data-ttu-id="136a7-110">Solo se puede usar `Protected Friend` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="136a7-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="136a7-111">Esto significa que el contexto de la declaración de un elemento `Protected` debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="136a7-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="136a7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="136a7-112">See also</span></span>

- [<span data-ttu-id="136a7-113">Public</span><span class="sxs-lookup"><span data-stu-id="136a7-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="136a7-114">Protected</span><span class="sxs-lookup"><span data-stu-id="136a7-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="136a7-115">Friend</span><span class="sxs-lookup"><span data-stu-id="136a7-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="136a7-116">Private</span><span class="sxs-lookup"><span data-stu-id="136a7-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="136a7-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="136a7-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="136a7-118">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="136a7-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="136a7-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="136a7-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="136a7-120">Estructuras</span><span class="sxs-lookup"><span data-stu-id="136a7-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="136a7-121">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="136a7-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
