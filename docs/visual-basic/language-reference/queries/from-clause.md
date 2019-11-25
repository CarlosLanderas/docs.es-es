---
title: From (Cláusula)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: a63fb41fc2b0ad885acf76ad5d56e446922f5b90
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343777"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="16487-102">From (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16487-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="16487-103">Specifies one or more range variables and a collection to query.</span><span class="sxs-lookup"><span data-stu-id="16487-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16487-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16487-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="16487-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="16487-105">Parts</span></span>  
  
|<span data-ttu-id="16487-106">Término</span><span class="sxs-lookup"><span data-stu-id="16487-106">Term</span></span>|<span data-ttu-id="16487-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="16487-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="16487-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="16487-108">Required.</span></span> <span data-ttu-id="16487-109">A *range variable* used to iterate through the elements of the collection.</span><span class="sxs-lookup"><span data-stu-id="16487-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="16487-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span><span class="sxs-lookup"><span data-stu-id="16487-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="16487-111">Must be an enumerable type.</span><span class="sxs-lookup"><span data-stu-id="16487-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="16487-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="16487-112">Optional.</span></span> <span data-ttu-id="16487-113">Tipo de `element`.</span><span class="sxs-lookup"><span data-stu-id="16487-113">The type of `element`.</span></span> <span data-ttu-id="16487-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span><span class="sxs-lookup"><span data-stu-id="16487-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="16487-115">Requerido.</span><span class="sxs-lookup"><span data-stu-id="16487-115">Required.</span></span> <span data-ttu-id="16487-116">Refers to the collection to be queried.</span><span class="sxs-lookup"><span data-stu-id="16487-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="16487-117">Must be an enumerable type.</span><span class="sxs-lookup"><span data-stu-id="16487-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16487-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16487-118">Remarks</span></span>  
 <span data-ttu-id="16487-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span><span class="sxs-lookup"><span data-stu-id="16487-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="16487-120">These variables are called *range variables*.</span><span class="sxs-lookup"><span data-stu-id="16487-120">These variables are called *range variables*.</span></span> <span data-ttu-id="16487-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span><span class="sxs-lookup"><span data-stu-id="16487-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="16487-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="16487-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="16487-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span><span class="sxs-lookup"><span data-stu-id="16487-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="16487-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span><span class="sxs-lookup"><span data-stu-id="16487-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="16487-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span><span class="sxs-lookup"><span data-stu-id="16487-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="16487-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span><span class="sxs-lookup"><span data-stu-id="16487-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="16487-127">The following code example shows both syntax options for the `From` clause.</span><span class="sxs-lookup"><span data-stu-id="16487-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="16487-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span><span class="sxs-lookup"><span data-stu-id="16487-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="16487-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span><span class="sxs-lookup"><span data-stu-id="16487-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="16487-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span><span class="sxs-lookup"><span data-stu-id="16487-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="16487-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span><span class="sxs-lookup"><span data-stu-id="16487-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="16487-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span><span class="sxs-lookup"><span data-stu-id="16487-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="16487-133">You can refine the query in the following ways:</span><span class="sxs-lookup"><span data-stu-id="16487-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="16487-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span><span class="sxs-lookup"><span data-stu-id="16487-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="16487-135">Use the `Where` clause to filter the query result.</span><span class="sxs-lookup"><span data-stu-id="16487-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="16487-136">Sort the result by using the `Order By` clause.</span><span class="sxs-lookup"><span data-stu-id="16487-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="16487-137">Group similar results together by using the `Group By` clause.</span><span class="sxs-lookup"><span data-stu-id="16487-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="16487-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span><span class="sxs-lookup"><span data-stu-id="16487-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="16487-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span><span class="sxs-lookup"><span data-stu-id="16487-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="16487-140">Use the `Distinct` clause to ignore duplicate query results.</span><span class="sxs-lookup"><span data-stu-id="16487-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="16487-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span><span class="sxs-lookup"><span data-stu-id="16487-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16487-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16487-142">Example</span></span>  
 <span data-ttu-id="16487-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span><span class="sxs-lookup"><span data-stu-id="16487-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="16487-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span><span class="sxs-lookup"><span data-stu-id="16487-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="16487-145">The `For Each` loop displays the company name for each customer in the query result.</span><span class="sxs-lookup"><span data-stu-id="16487-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="16487-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="16487-146">See also</span></span>

- [<span data-ttu-id="16487-147">Consultas</span><span class="sxs-lookup"><span data-stu-id="16487-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="16487-148">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16487-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="16487-149">For Each...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="16487-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="16487-150">For...Next (instrucción)</span><span class="sxs-lookup"><span data-stu-id="16487-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="16487-151">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="16487-152">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="16487-153">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="16487-154">Distinct (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="16487-155">Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="16487-156">Group Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="16487-157">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="16487-158">Let (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="16487-159">Skip (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="16487-160">Take (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="16487-161">Skip While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="16487-162">Take While (cláusula)</span><span class="sxs-lookup"><span data-stu-id="16487-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
