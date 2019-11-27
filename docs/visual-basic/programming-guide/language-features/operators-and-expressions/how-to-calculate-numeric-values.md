---
title: 'Cómo: Calcular valores numéricos'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: d213f6b5a4abf8c52d8872ae36e89796183ff27c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348966"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="dcacc-102">Cómo: Calcular valores numéricos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dcacc-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="dcacc-103">Puede calcular valores numéricos mediante el uso de expresiones numéricas.</span><span class="sxs-lookup"><span data-stu-id="dcacc-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="dcacc-104">Una *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos y operadores que actúan sobre esos valores.</span><span class="sxs-lookup"><span data-stu-id="dcacc-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="dcacc-105">Calcular valores numéricos</span><span class="sxs-lookup"><span data-stu-id="dcacc-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="dcacc-106">Para calcular un valor numérico</span><span class="sxs-lookup"><span data-stu-id="dcacc-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="dcacc-107">Combinar uno o más literales numéricos, constantes y variables en una expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="dcacc-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="dcacc-108">En el ejemplo siguiente se muestran algunas expresiones numéricas válidas.</span><span class="sxs-lookup"><span data-stu-id="dcacc-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="dcacc-109">Las tres primeras líneas muestran un literal, una constante y una variable.</span><span class="sxs-lookup"><span data-stu-id="dcacc-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="dcacc-110">Cada uno de ellos forma una expresión numérica válida por sí sola.</span><span class="sxs-lookup"><span data-stu-id="dcacc-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="dcacc-111">La línea final muestra una combinación de una variable con dos literales.</span><span class="sxs-lookup"><span data-stu-id="dcacc-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="dcacc-112">Tenga en cuenta que una expresión numérica no forma una instrucción Visual Basic completa.</span><span class="sxs-lookup"><span data-stu-id="dcacc-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="dcacc-113">Debe utilizar la expresión como parte de una instrucción completa.</span><span class="sxs-lookup"><span data-stu-id="dcacc-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="dcacc-114">Para almacenar un valor numérico</span><span class="sxs-lookup"><span data-stu-id="dcacc-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="dcacc-115">Puede usar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dcacc-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="dcacc-116">En el ejemplo anterior, el valor de la expresión en el lado derecho del operador igual (`=`) se asigna a la variable `j` en el lado izquierdo del operador, por lo que `j` se evalúa como 276.</span><span class="sxs-lookup"><span data-stu-id="dcacc-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="dcacc-117">Para obtener más información, vea [Instrucciones (Guía de programación de C#)](../../../../visual-basic/language-reference/statements/index.md).</span><span class="sxs-lookup"><span data-stu-id="dcacc-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="dcacc-118">Varios operadores</span><span class="sxs-lookup"><span data-stu-id="dcacc-118">Multiple Operators</span></span>  
 <span data-ttu-id="dcacc-119">Si la expresión numérica contiene más de un operador, el orden en el que se evalúan viene determinado por las reglas de prioridad de los operadores.</span><span class="sxs-lookup"><span data-stu-id="dcacc-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="dcacc-120">Para invalidar las reglas de prioridad de los operadores, incluya expresiones entre paréntesis, como en el ejemplo anterior. primero se evalúan las expresiones delimitadas.</span><span class="sxs-lookup"><span data-stu-id="dcacc-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="dcacc-121">Para invalidar la prioridad de operador normal</span><span class="sxs-lookup"><span data-stu-id="dcacc-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="dcacc-122">Use paréntesis para encerrar las operaciones que desea que se realicen en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="dcacc-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="dcacc-123">En el ejemplo siguiente se muestran dos resultados diferentes con los mismos operandos y operadores.</span><span class="sxs-lookup"><span data-stu-id="dcacc-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="dcacc-124">En el ejemplo anterior, el cálculo de `j` realiza primero el operador de suma (`+`) porque los paréntesis alrededor de `(67 + i)` invalidan la prioridad normal y el valor asignado a `j` es 276 (4 veces 69).</span><span class="sxs-lookup"><span data-stu-id="dcacc-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="dcacc-125">El cálculo de `k` realiza los operadores en su prioridad normal (`*` antes `+`) y el valor asignado a `k` es 270 (268 más 2).</span><span class="sxs-lookup"><span data-stu-id="dcacc-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="dcacc-126">Para obtener más información, vea [precedencia de operadores en Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="dcacc-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcacc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcacc-127">See also</span></span>

- [<span data-ttu-id="dcacc-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="dcacc-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="dcacc-129">Comparaciones de valores</span><span class="sxs-lookup"><span data-stu-id="dcacc-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="dcacc-130">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="dcacc-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="dcacc-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dcacc-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="dcacc-132">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="dcacc-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="dcacc-133">Combinación eficaz de operadores</span><span class="sxs-lookup"><span data-stu-id="dcacc-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
