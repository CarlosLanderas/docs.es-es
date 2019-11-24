---
title: IMetaDataImport::EnumEvents (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
ms.openlocfilehash: 4faf8646b81f92ddf65eff15fdc610d275b37864
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440008"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="fad53-102">IMetaDataImport::EnumEvents (Método)</span><span class="sxs-lookup"><span data-stu-id="fad53-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="fad53-103">Enumera los tokens de definición de eventos del token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="fad53-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fad53-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fad53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fad53-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fad53-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="fad53-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="fad53-107">[in] The TypeDef token whose event definitions are to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="fad53-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="fad53-108">[out] The array of returned events.</span><span class="sxs-lookup"><span data-stu-id="fad53-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fad53-109">[in] Tamaño máximo de la matriz `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="fad53-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="fad53-110">[out] The actual number of events returned in `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="fad53-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fad53-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fad53-111">Return Value</span></span>  
  
|<span data-ttu-id="fad53-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fad53-112">HRESULT</span></span>|<span data-ttu-id="fad53-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fad53-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fad53-114">`EnumEvents` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="fad53-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fad53-115">There are no events to enumerate.</span><span class="sxs-lookup"><span data-stu-id="fad53-115">There are no events to enumerate.</span></span> <span data-ttu-id="fad53-116">In that case, `pcEvents` is zero.</span><span class="sxs-lookup"><span data-stu-id="fad53-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fad53-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fad53-117">Requirements</span></span>  
 <span data-ttu-id="fad53-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fad53-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad53-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fad53-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fad53-120">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fad53-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fad53-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad53-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad53-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fad53-122">See also</span></span>

- [<span data-ttu-id="fad53-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fad53-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fad53-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fad53-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
