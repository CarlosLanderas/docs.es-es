---
title: IMetaDataEmit::Save (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: afd60cdf566bea459816ee890d44cc09258de516
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435944"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="d956c-102">IMetaDataEmit::Save (Método)</span><span class="sxs-lookup"><span data-stu-id="d956c-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="d956c-103">Saves all metadata in the current scope to the file at the specified address.</span><span class="sxs-lookup"><span data-stu-id="d956c-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d956c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d956c-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d956c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d956c-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="d956c-106">[in] The name of the file to save to.</span><span class="sxs-lookup"><span data-stu-id="d956c-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="d956c-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span><span class="sxs-lookup"><span data-stu-id="d956c-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="d956c-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="d956c-108">[in] Reserved.</span></span> <span data-ttu-id="d956c-109">Must be zero.</span><span class="sxs-lookup"><span data-stu-id="d956c-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d956c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d956c-110">Requirements</span></span>  
 <span data-ttu-id="d956c-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d956c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d956c-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d956c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d956c-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d956c-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d956c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d956c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d956c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d956c-115">See also</span></span>

- [<span data-ttu-id="d956c-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d956c-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d956c-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d956c-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
