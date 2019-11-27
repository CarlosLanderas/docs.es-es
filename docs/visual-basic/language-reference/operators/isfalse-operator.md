---
title: IsFalse (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349528"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="5125a-102">IsFalse (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5125a-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="5125a-103">Determina si una expresión es `False`.</span><span class="sxs-lookup"><span data-stu-id="5125a-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="5125a-104">No se puede llamar a `IsFalse` explícitamente en el código, pero el compilador Visual Basic puede usarlo para generar código a partir de cláusulas `AndAlso`.</span><span class="sxs-lookup"><span data-stu-id="5125a-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="5125a-105">Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una cláusula `AndAlso`, debe definir `IsFalse` en esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="5125a-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="5125a-106">El compilador tiene en cuenta los operadores `IsFalse` y `IsTrue` como un *par coincidente*.</span><span class="sxs-lookup"><span data-stu-id="5125a-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="5125a-107">Esto significa que si define uno de ellos, también debe definir el otro.</span><span class="sxs-lookup"><span data-stu-id="5125a-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5125a-108">El operador de `IsFalse` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="5125a-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="5125a-109">Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="5125a-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5125a-110">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5125a-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5125a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5125a-111">Example</span></span>  
 <span data-ttu-id="5125a-112">En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los operadores `IsFalse` y `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="5125a-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="5125a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5125a-113">See also</span></span>

- [<span data-ttu-id="5125a-114">IsTrue (operador)</span><span class="sxs-lookup"><span data-stu-id="5125a-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="5125a-115">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="5125a-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="5125a-116">AndAlso (operador)</span><span class="sxs-lookup"><span data-stu-id="5125a-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
