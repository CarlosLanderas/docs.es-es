---
title: Operador <<=
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: cc89e0dadc7148b21e695a53a2e746a00ed66441
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350953"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="2bfaf-102">\<\<= operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bfaf-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="2bfaf-103">Realiza un desplazamiento aritmético a la izquierda en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bfaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bfaf-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="2bfaf-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="2bfaf-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2bfaf-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-106">Required.</span></span> <span data-ttu-id="2bfaf-107">Variable o propiedad de un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="2bfaf-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="2bfaf-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-108">Required.</span></span> <span data-ttu-id="2bfaf-109">Expresión numérica de un tipo de datos que se amplía a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bfaf-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2bfaf-110">Remarks</span></span>  
 <span data-ttu-id="2bfaf-111">El elemento del lado izquierdo del operador `<<=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2bfaf-112">La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="2bfaf-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2bfaf-113">El operador `<<=` primero realiza un desplazamiento aritmético a la izquierda en el valor de la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="2bfaf-114">A continuación, el operador asigna de nuevo el resultado de la operación a esa variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="2bfaf-115">Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="2bfaf-116">En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits que quedan a la derecha se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2bfaf-117">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="2bfaf-117">Overloading</span></span>  
 <span data-ttu-id="2bfaf-118">Se puede *sobrecargar*el [operador < <](../../../visual-basic/language-reference/operators/left-shift-operator.md) , lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2bfaf-119">La sobrecarga del operador `<<` afecta al comportamiento del operador `<<=`.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="2bfaf-120">Si el código usa `<<=` en una clase o estructura que sobrecarga `<<`, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2bfaf-121">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2bfaf-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bfaf-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2bfaf-122">Example</span></span>  
 <span data-ttu-id="2bfaf-123">En el ejemplo siguiente se usa el operador `<<=` para desplazar el modelo de bits de una variable de `Integer` a la izquierda en la cantidad especificada y asignar el resultado a la variable.</span><span class="sxs-lookup"><span data-stu-id="2bfaf-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="2bfaf-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bfaf-124">See also</span></span>

- [<span data-ttu-id="2bfaf-125">Operador <<</span><span class="sxs-lookup"><span data-stu-id="2bfaf-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="2bfaf-126">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="2bfaf-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="2bfaf-127">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="2bfaf-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="2bfaf-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2bfaf-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2bfaf-129">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="2bfaf-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2bfaf-130">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="2bfaf-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
