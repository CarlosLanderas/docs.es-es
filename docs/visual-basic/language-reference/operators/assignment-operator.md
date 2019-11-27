---
title: = (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 75f303219b9bf32613989f65f90a9096ef70e02e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350201"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="00a7c-102">= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00a7c-102">= Operator (Visual Basic)</span></span>
<span data-ttu-id="00a7c-103">Asigna un valor a una variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="00a7c-103">Assigns a value to a variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00a7c-104">Syntax</span></span>  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a><span data-ttu-id="00a7c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="00a7c-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="00a7c-106">Cualquier variable que se pueda escribir o cualquier propiedad.</span><span class="sxs-lookup"><span data-stu-id="00a7c-106">Any writable variable or any property.</span></span>  
  
 `value`  
 <span data-ttu-id="00a7c-107">Cualquier literal, constante o expresión.</span><span class="sxs-lookup"><span data-stu-id="00a7c-107">Any literal, constant, or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00a7c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00a7c-108">Remarks</span></span>  
 <span data-ttu-id="00a7c-109">El elemento del lado izquierdo del signo igual (`=`) puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="00a7c-109">The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="00a7c-110">La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="00a7c-110">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="00a7c-111">El operador `=` asigna el valor de su derecha a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="00a7c-111">The `=` operator assigns the value on its right to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00a7c-112">El operador `=` también se usa como operador de comparación.</span><span class="sxs-lookup"><span data-stu-id="00a7c-112">The `=` operator is also used as a comparison operator.</span></span> <span data-ttu-id="00a7c-113">Para obtener más información, vea [operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md).</span><span class="sxs-lookup"><span data-stu-id="00a7c-113">For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="00a7c-114">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="00a7c-114">Overloading</span></span>  
 <span data-ttu-id="00a7c-115">El operador `=` solo se puede sobrecargar como operador de comparación relacional, no como operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="00a7c-115">The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span> <span data-ttu-id="00a7c-116">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="00a7c-116">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00a7c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00a7c-117">Example</span></span>  
 <span data-ttu-id="00a7c-118">En el siguiente ejemplo se muestra el operador de asignación.</span><span class="sxs-lookup"><span data-stu-id="00a7c-118">The following example demonstrates the assignment operator.</span></span> <span data-ttu-id="00a7c-119">El valor de la derecha se asigna a la variable de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="00a7c-119">The value on the right is assigned to the variable on the left.</span></span>  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="00a7c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="00a7c-120">See also</span></span>

- [<span data-ttu-id="00a7c-121">Operador &=</span><span class="sxs-lookup"><span data-stu-id="00a7c-121">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="00a7c-122">Operador \*=</span><span class="sxs-lookup"><span data-stu-id="00a7c-122">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="00a7c-123">Operador +=</span><span class="sxs-lookup"><span data-stu-id="00a7c-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="00a7c-124">-= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00a7c-124">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="00a7c-125">/= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00a7c-125">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="00a7c-126">\\= (operador)</span><span class="sxs-lookup"><span data-stu-id="00a7c-126">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="00a7c-127">Operador ^=</span><span class="sxs-lookup"><span data-stu-id="00a7c-127">^= Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [<span data-ttu-id="00a7c-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="00a7c-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="00a7c-129">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="00a7c-129">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="00a7c-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="00a7c-130">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="00a7c-131">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="00a7c-131">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
