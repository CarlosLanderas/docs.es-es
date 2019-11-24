---
title: ISymUnmanagedBinder::GetReaderFromStream (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
ms.openlocfilehash: b1cb2bf3aa021ed738f7fad93fc4b86d97baf1e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449382"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="0419f-102">ISymUnmanagedBinder::GetReaderFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="0419f-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="0419f-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span><span class="sxs-lookup"><span data-stu-id="0419f-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0419f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0419f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0419f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0419f-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="0419f-106">[in] A pointer to the metadata import interface.</span><span class="sxs-lookup"><span data-stu-id="0419f-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="0419f-107">[in] A pointer to the stream that contains the symbol store.</span><span class="sxs-lookup"><span data-stu-id="0419f-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0419f-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="0419f-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0419f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0419f-109">Return Value</span></span>  
 <span data-ttu-id="0419f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="0419f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0419f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0419f-111">Requirements</span></span>  
 <span data-ttu-id="0419f-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0419f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0419f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0419f-113">See also</span></span>

- [<span data-ttu-id="0419f-114">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0419f-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
