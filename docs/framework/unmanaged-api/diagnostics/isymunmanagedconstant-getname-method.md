---
title: ISymUnmanagedConstant::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 924feaeb91b42404461ad5d276c0cb77279d4dc4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449282"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="05c1d-102">ISymUnmanagedConstant::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="05c1d-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="05c1d-103">Gets the name of the constant.</span><span class="sxs-lookup"><span data-stu-id="05c1d-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05c1d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05c1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05c1d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="05c1d-106">[in] The length of the buffer that the `szName` parameter points to.</span><span class="sxs-lookup"><span data-stu-id="05c1d-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="05c1d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span><span class="sxs-lookup"><span data-stu-id="05c1d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="05c1d-108">[out] The buffer that stores the name.</span><span class="sxs-lookup"><span data-stu-id="05c1d-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05c1d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="05c1d-109">Return Value</span></span>  
 <span data-ttu-id="05c1d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="05c1d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05c1d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05c1d-111">Requirements</span></span>  
 <span data-ttu-id="05c1d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="05c1d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c1d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="05c1d-113">See also</span></span>

- [<span data-ttu-id="05c1d-114">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="05c1d-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="05c1d-115">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="05c1d-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="05c1d-116">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="05c1d-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
