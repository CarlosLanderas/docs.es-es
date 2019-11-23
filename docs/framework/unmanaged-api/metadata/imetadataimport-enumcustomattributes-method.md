---
title: IMetaDataImport::EnumCustomAttributes (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: a43c1883038e41cac1b58c78bc26f20d436ebbd1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440242"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="ba9a8-102">IMetaDataImport::EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="ba9a8-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="ba9a8-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba9a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba9a8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba9a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba9a8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ba9a8-106">[in, out] A pointer to the returned enumerator.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="ba9a8-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ba9a8-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="ba9a8-109">[out] An array of custom attribute tokens.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ba9a8-110">[in] Tamaño máximo de la matriz `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="ba9a8-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba9a8-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba9a8-112">Return Value</span></span>  
  
|<span data-ttu-id="ba9a8-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba9a8-113">HRESULT</span></span>|<span data-ttu-id="ba9a8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba9a8-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba9a8-115">`EnumCustomAttributes` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ba9a8-116">There are no custom attributes to enumerate.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="ba9a8-117">In that case, `pcCustomAttributes` is zero.</span><span class="sxs-lookup"><span data-stu-id="ba9a8-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba9a8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba9a8-118">Requirements</span></span>  
 <span data-ttu-id="ba9a8-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba9a8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba9a8-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ba9a8-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba9a8-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba9a8-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba9a8-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba9a8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba9a8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba9a8-123">See also</span></span>

- [<span data-ttu-id="ba9a8-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba9a8-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ba9a8-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba9a8-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
