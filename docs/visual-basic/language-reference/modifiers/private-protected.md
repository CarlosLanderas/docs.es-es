---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351339"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="2e16f-102">Privado protegido (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e16f-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="2e16f-103">La combinación de palabras claves `Private Protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="2e16f-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="2e16f-104">Un miembro de `Private Protected` es accesible para todos los miembros de la clase contenedora, así como para los tipos derivados de la clase contenedora, pero solo si se encuentran en el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2e16f-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="2e16f-105">Solo puede especificar `Private Protected` en miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="2e16f-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="2e16f-106">Visual Basic 15,5 y versiones posteriores admiten el modificador de acceso `Private Protected`.</span><span class="sxs-lookup"><span data-stu-id="2e16f-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="2e16f-107">Para usarlo, puede Agregar el siguiente elemento al archivo de proyecto de Visual Basic (\*. vbproj).</span><span class="sxs-lookup"><span data-stu-id="2e16f-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="2e16f-108">Siempre que Visual Basic 15,5 o posterior esté instalado en el sistema, le permite aprovechar todas las características de lenguaje compatibles con la versión más reciente del compilador de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="2e16f-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="2e16f-109">Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="2e16f-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2e16f-110">En Visual Studio, al seleccionar la ayuda F1 en `private protected` se proporciona ayuda para [privado](private.md) o [protegido](protected.md).</span><span class="sxs-lookup"><span data-stu-id="2e16f-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="2e16f-111">El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="2e16f-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="2e16f-112">Reglas</span><span class="sxs-lookup"><span data-stu-id="2e16f-112">Rules</span></span>

- <span data-ttu-id="2e16f-113">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="2e16f-113">**Declaration Context.**</span></span> <span data-ttu-id="2e16f-114">Solo se puede usar `Private Protected` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="2e16f-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="2e16f-115">Esto significa que el contexto de la declaración de un elemento `Protected` debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2e16f-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="2e16f-116">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="2e16f-116">Behavior</span></span>

- <span data-ttu-id="2e16f-117">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="2e16f-117">**Access Level.**</span></span> <span data-ttu-id="2e16f-118">Todo el código de una clase puede tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="2e16f-118">All code in a class can access its elements.</span></span> <span data-ttu-id="2e16f-119">El código de cualquier clase que se deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a todos los elementos `Private Protected` de la clase base.</span><span class="sxs-lookup"><span data-stu-id="2e16f-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="2e16f-120">Sin embargo, el código de cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede tener acceso a la clase base `Private Protected` elementos.</span><span class="sxs-lookup"><span data-stu-id="2e16f-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="2e16f-121">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="2e16f-121">**Access Modifiers.**</span></span> <span data-ttu-id="2e16f-122">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="2e16f-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="2e16f-123">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2e16f-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="2e16f-124">El modificador `Private Protected` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e16f-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="2e16f-125">[Instrucción de clase](../../../visual-basic/language-reference/statements/class-statement.md) de una clase anidada</span><span class="sxs-lookup"><span data-stu-id="2e16f-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="2e16f-126">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e16f-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="2e16f-127">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e16f-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="2e16f-128">[Instrucción delegada](../../../visual-basic/language-reference/statements/delegate-statement.md) de un delegado anidado en una clase</span><span class="sxs-lookup"><span data-stu-id="2e16f-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="2e16f-129">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e16f-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="2e16f-130">[Instrucción enum](../../../visual-basic/language-reference/statements/enum-statement.md) de una enumeración anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="2e16f-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="2e16f-131">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e16f-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="2e16f-132">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e16f-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="2e16f-133">[Instrucción de interfaz](../../../visual-basic/language-reference/statements/interface-statement.md) de una interfaz anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="2e16f-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="2e16f-134">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e16f-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="2e16f-135">[Instrucción Structure](../../../visual-basic/language-reference/statements/structure-statement.md) de una estructura anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="2e16f-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="2e16f-136">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2e16f-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="2e16f-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e16f-137">See also</span></span>

- [<span data-ttu-id="2e16f-138">Public</span><span class="sxs-lookup"><span data-stu-id="2e16f-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="2e16f-139">Protected</span><span class="sxs-lookup"><span data-stu-id="2e16f-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="2e16f-140">Friend</span><span class="sxs-lookup"><span data-stu-id="2e16f-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="2e16f-141">Private</span><span class="sxs-lookup"><span data-stu-id="2e16f-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="2e16f-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="2e16f-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="2e16f-143">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2e16f-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="2e16f-144">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="2e16f-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="2e16f-145">Estructuras</span><span class="sxs-lookup"><span data-stu-id="2e16f-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="2e16f-146">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="2e16f-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
