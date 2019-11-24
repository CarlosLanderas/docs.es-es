---
title: ISymUnmanagedReader::GetUserEntryPoint (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: 50f41bb55b7c3dc45646a465032074ce90be0abf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444510"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="823b7-102">ISymUnmanagedReader::GetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="823b7-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="823b7-103">Returns the method that was specified as the user entry point for the module, if any.</span><span class="sxs-lookup"><span data-stu-id="823b7-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="823b7-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span><span class="sxs-lookup"><span data-stu-id="823b7-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="823b7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="823b7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="823b7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="823b7-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="823b7-107">[out] A pointer to a variable that receives the entry point.</span><span class="sxs-lookup"><span data-stu-id="823b7-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="823b7-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="823b7-108">Return Value</span></span>  
 <span data-ttu-id="823b7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="823b7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="823b7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="823b7-110">Requirements</span></span>  
 <span data-ttu-id="823b7-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="823b7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="823b7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="823b7-112">See also</span></span>

- [<span data-ttu-id="823b7-113">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="823b7-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
