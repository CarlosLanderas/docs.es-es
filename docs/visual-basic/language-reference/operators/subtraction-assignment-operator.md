---
title: -= (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: 44cb226d64e9f0b86c6566eb25fbafd6323a6d4c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347808"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="33843-102">-= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33843-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="33843-103">Resta el valor de una expresión del valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="33843-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33843-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33843-104">Syntax</span></span>  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="33843-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="33843-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="33843-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="33843-106">Required.</span></span> <span data-ttu-id="33843-107">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="33843-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="33843-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="33843-108">Required.</span></span> <span data-ttu-id="33843-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="33843-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33843-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33843-110">Remarks</span></span>  
 <span data-ttu-id="33843-111">El elemento del lado izquierdo del operador `-=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="33843-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="33843-112">La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="33843-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="33843-113">El operador `-=` primero resta el valor de la expresión (en el lado derecho del operador) del valor de la variable o de la propiedad (en el lado izquierdo del operador).</span><span class="sxs-lookup"><span data-stu-id="33843-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="33843-114">A continuación, el operador asigna el resultado de la operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="33843-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="33843-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="33843-115">Overloading</span></span>  
 <span data-ttu-id="33843-116">Se puede *sobrecargar*el [operador-(Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) , lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="33843-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="33843-117">La sobrecarga del operador `-` afecta al comportamiento del operador `-=`.</span><span class="sxs-lookup"><span data-stu-id="33843-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="33843-118">Si el código usa `-=` en una clase o estructura que sobrecarga `-`, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="33843-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="33843-119">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="33843-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33843-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33843-120">Example</span></span>  
 <span data-ttu-id="33843-121">En el ejemplo siguiente se usa el operador `-=` para restar una variable `Integer` de otra y asignar el resultado a la última variable.</span><span class="sxs-lookup"><span data-stu-id="33843-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="33843-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="33843-122">See also</span></span>

- [<span data-ttu-id="33843-123">Operador-(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33843-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="33843-124">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="33843-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="33843-125">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="33843-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="33843-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33843-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="33843-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="33843-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="33843-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="33843-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
