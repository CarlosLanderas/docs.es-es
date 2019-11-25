---
title: Funciones matemáticas derivadas
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 73cf56dd72f2baac0474d6f5c4e88228a1fe38cf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349850"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="52981-102">Funciones matemáticas derivadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52981-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="52981-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span><span class="sxs-lookup"><span data-stu-id="52981-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="52981-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span><span class="sxs-lookup"><span data-stu-id="52981-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="52981-105">Función</span><span class="sxs-lookup"><span data-stu-id="52981-105">Function</span></span>|<span data-ttu-id="52981-106">Derived equivalents</span><span class="sxs-lookup"><span data-stu-id="52981-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="52981-107">Secant (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="52981-107">Secant (Sec(x))</span></span>|<span data-ttu-id="52981-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="52981-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="52981-109">Cosecant (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="52981-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="52981-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="52981-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="52981-111">Cotangent (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="52981-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="52981-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="52981-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="52981-113">Inverse sine (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="52981-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="52981-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="52981-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="52981-115">Inverse cosine (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="52981-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="52981-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="52981-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="52981-117">Inverse secant (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="52981-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="52981-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="52981-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="52981-119">Inverse cosecant (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="52981-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="52981-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="52981-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="52981-121">Inverse cotangent (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="52981-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="52981-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="52981-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="52981-123">Hyperbolic sine (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="52981-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="52981-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="52981-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="52981-125">Hyperbolic cosine (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="52981-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="52981-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="52981-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="52981-127">Hyperbolic tangent (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="52981-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="52981-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="52981-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="52981-129">Hyperbolic secant (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="52981-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="52981-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="52981-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="52981-131">Hyperbolic cosecant (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="52981-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="52981-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="52981-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="52981-133">Hyperbolic cotangent (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="52981-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="52981-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="52981-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="52981-135">Inverse hyperbolic sine (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="52981-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="52981-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="52981-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="52981-137">Inverse hyperbolic cosine (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="52981-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="52981-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="52981-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="52981-139">Inverse hyperbolic tangent (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="52981-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="52981-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="52981-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="52981-141">Inverse hyperbolic secant (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="52981-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="52981-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="52981-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="52981-143">Inverse hyperbolic cosecant (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="52981-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="52981-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="52981-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="52981-145">Inverse hyperbolic cotangent (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="52981-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="52981-146">Log((x + 1) / (x – 1)) / 2</span><span class="sxs-lookup"><span data-stu-id="52981-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52981-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="52981-147">See also</span></span>

- [<span data-ttu-id="52981-148">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="52981-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
