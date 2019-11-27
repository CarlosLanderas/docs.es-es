---
title: IMetaDataEmit2::SaveDeltaToMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: d0718ff9a7e288ffc6a856032aa47949fda443f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447891"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="03c1e-102">IMetaDataEmit2::SaveDeltaToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="03c1e-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="03c1e-103">Guarda los cambios de la sesión de edición y continuación actual en la memoria.</span><span class="sxs-lookup"><span data-stu-id="03c1e-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03c1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03c1e-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03c1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03c1e-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="03c1e-106">enuncia Dirección en la que se va a comenzar a escribir la diferencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="03c1e-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="03c1e-107">de Tamaño de los cambios.</span><span class="sxs-lookup"><span data-stu-id="03c1e-107">[in] The size of the changes.</span></span> <span data-ttu-id="03c1e-108">Use [IMetaDataEmit2:: GetDeltaSaveSize (](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="03c1e-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03c1e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03c1e-109">Requirements</span></span>  
 <span data-ttu-id="03c1e-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03c1e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03c1e-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="03c1e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03c1e-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="03c1e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03c1e-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03c1e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c1e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="03c1e-114">See also</span></span>

- [<span data-ttu-id="03c1e-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03c1e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="03c1e-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03c1e-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
