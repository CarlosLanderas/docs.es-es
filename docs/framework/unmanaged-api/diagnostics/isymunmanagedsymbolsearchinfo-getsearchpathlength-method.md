---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 319ba58b5d012cbc0f9ddac0b83e5f3ae2ae062a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446171"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="5dca0-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)</span><span class="sxs-lookup"><span data-stu-id="5dca0-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="5dca0-103">Gets the search path length.</span><span class="sxs-lookup"><span data-stu-id="5dca0-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dca0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5dca0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dca0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5dca0-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="5dca0-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span><span class="sxs-lookup"><span data-stu-id="5dca0-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dca0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5dca0-107">Return Value</span></span>  
 <span data-ttu-id="5dca0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="5dca0-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dca0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dca0-109">Requirements</span></span>  
 <span data-ttu-id="5dca0-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5dca0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dca0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dca0-111">See also</span></span>

- [<span data-ttu-id="5dca0-112">ISymUnmanagedSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dca0-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
