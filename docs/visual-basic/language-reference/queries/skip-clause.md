---
title: Skip (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: c582b014bad4fa8fa3165d2b756f4bc955840cfc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349653"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="6ccbe-102">Skip (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ccbe-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="6ccbe-103">Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ccbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ccbe-104">Syntax</span></span>  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="6ccbe-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="6ccbe-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="6ccbe-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-106">Required.</span></span> <span data-ttu-id="6ccbe-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ccbe-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ccbe-108">Remarks</span></span>  
 <span data-ttu-id="6ccbe-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="6ccbe-110">The number of elements to skip is identified by the `count` parameter.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="6ccbe-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="6ccbe-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="6ccbe-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="6ccbe-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6ccbe-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="6ccbe-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ccbe-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6ccbe-116">Example</span></span>  
 <span data-ttu-id="6ccbe-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="6ccbe-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span><span class="sxs-lookup"><span data-stu-id="6ccbe-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6ccbe-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ccbe-119">See also</span></span>

- [<span data-ttu-id="6ccbe-120">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ccbe-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="6ccbe-121">Consultas</span><span class="sxs-lookup"><span data-stu-id="6ccbe-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="6ccbe-122">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6ccbe-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="6ccbe-123">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6ccbe-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="6ccbe-124">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6ccbe-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="6ccbe-125">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6ccbe-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="6ccbe-126">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="6ccbe-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
