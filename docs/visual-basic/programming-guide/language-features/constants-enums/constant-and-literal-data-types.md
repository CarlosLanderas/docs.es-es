---
title: Tipos de datos constantes y literales
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333730"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="4839c-102">Tipos de datos constantes y literales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4839c-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="4839c-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span><span class="sxs-lookup"><span data-stu-id="4839c-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="4839c-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span><span class="sxs-lookup"><span data-stu-id="4839c-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="4839c-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span><span class="sxs-lookup"><span data-stu-id="4839c-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="4839c-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span><span class="sxs-lookup"><span data-stu-id="4839c-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="4839c-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span><span class="sxs-lookup"><span data-stu-id="4839c-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="4839c-108">The compiler determines the type of the constant from the type of the expression.</span><span class="sxs-lookup"><span data-stu-id="4839c-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="4839c-109">A numeric integer literal is cast by default to the `Integer` data type.</span><span class="sxs-lookup"><span data-stu-id="4839c-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="4839c-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span><span class="sxs-lookup"><span data-stu-id="4839c-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="4839c-111">Literals and Type Coercion</span><span class="sxs-lookup"><span data-stu-id="4839c-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="4839c-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="4839c-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="4839c-113">The following example produces an error:</span><span class="sxs-lookup"><span data-stu-id="4839c-113">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="4839c-114">The error results from the representation of the literal.</span><span class="sxs-lookup"><span data-stu-id="4839c-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="4839c-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span><span class="sxs-lookup"><span data-stu-id="4839c-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="4839c-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span><span class="sxs-lookup"><span data-stu-id="4839c-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="4839c-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span><span class="sxs-lookup"><span data-stu-id="4839c-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="4839c-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="4839c-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="4839c-119">The following example demonstrates correct usage of type characters and enclosing characters:</span><span class="sxs-lookup"><span data-stu-id="4839c-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="4839c-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4839c-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="4839c-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4839c-121">Data type</span></span>|<span data-ttu-id="4839c-122">Enclosing character</span><span class="sxs-lookup"><span data-stu-id="4839c-122">Enclosing character</span></span>|<span data-ttu-id="4839c-123">Appended type character</span><span class="sxs-lookup"><span data-stu-id="4839c-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="4839c-124">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-124">(none)</span></span>|<span data-ttu-id="4839c-125">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="4839c-126">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-126">(none)</span></span>|<span data-ttu-id="4839c-127">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="4839c-128">"</span><span class="sxs-lookup"><span data-stu-id="4839c-128">"</span></span>|<span data-ttu-id="4839c-129">C</span><span class="sxs-lookup"><span data-stu-id="4839c-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="4839c-130">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="4839c-131">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-131">(none)</span></span>|<span data-ttu-id="4839c-132">D or @</span><span class="sxs-lookup"><span data-stu-id="4839c-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="4839c-133">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-133">(none)</span></span>|<span data-ttu-id="4839c-134">R or #</span><span class="sxs-lookup"><span data-stu-id="4839c-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="4839c-135">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-135">(none)</span></span>|<span data-ttu-id="4839c-136">I or %</span><span class="sxs-lookup"><span data-stu-id="4839c-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="4839c-137">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-137">(none)</span></span>|<span data-ttu-id="4839c-138">L or &</span><span class="sxs-lookup"><span data-stu-id="4839c-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="4839c-139">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-139">(none)</span></span>|<span data-ttu-id="4839c-140">S</span><span class="sxs-lookup"><span data-stu-id="4839c-140">S</span></span>|  
|`Single`|<span data-ttu-id="4839c-141">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-141">(none)</span></span>|<span data-ttu-id="4839c-142">F or !</span><span class="sxs-lookup"><span data-stu-id="4839c-142">F or !</span></span>|  
|`String`|<span data-ttu-id="4839c-143">"</span><span class="sxs-lookup"><span data-stu-id="4839c-143">"</span></span>|<span data-ttu-id="4839c-144">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="4839c-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4839c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="4839c-145">See also</span></span>

- [<span data-ttu-id="4839c-146">Constantes definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="4839c-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [<span data-ttu-id="4839c-147">Declarar una constante</span><span class="sxs-lookup"><span data-stu-id="4839c-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [<span data-ttu-id="4839c-148">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="4839c-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="4839c-149">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4839c-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="4839c-150">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4839c-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="4839c-151">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="4839c-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="4839c-152">How to: Declare an Enumeration</span><span class="sxs-lookup"><span data-stu-id="4839c-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="4839c-153">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="4839c-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="4839c-154">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="4839c-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="4839c-155">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="4839c-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
