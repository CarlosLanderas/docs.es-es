---
title: IMetaDataTables::GetColumnInfo (Método)
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: 854d3ad28cc00c03e903b9e1d2ce3863e3ceef17
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436094"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="c4963-102">IMetaDataTables::GetColumnInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="c4963-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="c4963-103">Gets data about the specified column in the specified table.</span><span class="sxs-lookup"><span data-stu-id="c4963-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4963-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4963-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4963-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4963-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="c4963-106">[in] The index of the desired table.</span><span class="sxs-lookup"><span data-stu-id="c4963-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="c4963-107">[in] The index of the desired column.</span><span class="sxs-lookup"><span data-stu-id="c4963-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="c4963-108">[out] A pointer to the offset of the column in the row.</span><span class="sxs-lookup"><span data-stu-id="c4963-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="c4963-109">[out] A pointer to the size, in bytes, of the column.</span><span class="sxs-lookup"><span data-stu-id="c4963-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="c4963-110">[out] A pointer to the type of the values in the column.</span><span class="sxs-lookup"><span data-stu-id="c4963-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="c4963-111">[out] A pointer to a pointer to the column name.</span><span class="sxs-lookup"><span data-stu-id="c4963-111">[out] A pointer to a pointer to the column name.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="c4963-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4963-112">Remarks</span></span>

<span data-ttu-id="c4963-113">The returned column type falls within a range of values:</span><span class="sxs-lookup"><span data-stu-id="c4963-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="c4963-114">pType</span><span class="sxs-lookup"><span data-stu-id="c4963-114">pType</span></span>                    | <span data-ttu-id="c4963-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4963-115">Description</span></span>   | <span data-ttu-id="c4963-116">Helper function</span><span class="sxs-lookup"><span data-stu-id="c4963-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="c4963-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="c4963-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="c4963-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="c4963-118">(0..63)</span></span>   | <span data-ttu-id="c4963-119">Rid</span><span class="sxs-lookup"><span data-stu-id="c4963-119">Rid</span></span>           | <span data-ttu-id="c4963-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="c4963-120">**IsRidType**</span></span><br><span data-ttu-id="c4963-121">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="c4963-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="c4963-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="c4963-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="c4963-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="c4963-123">(64..95)</span></span> | <span data-ttu-id="c4963-124">Coded token</span><span class="sxs-lookup"><span data-stu-id="c4963-124">Coded token</span></span> | <span data-ttu-id="c4963-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="c4963-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="c4963-126">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="c4963-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="c4963-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="c4963-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="c4963-128">Int16</span><span class="sxs-lookup"><span data-stu-id="c4963-128">Int16</span></span>         | <span data-ttu-id="c4963-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c4963-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c4963-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="c4963-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="c4963-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="c4963-131">UInt16</span></span>        | <span data-ttu-id="c4963-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c4963-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c4963-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="c4963-133">`iLONG` (98)</span></span>             | <span data-ttu-id="c4963-134">Int32</span><span class="sxs-lookup"><span data-stu-id="c4963-134">Int32</span></span>         | <span data-ttu-id="c4963-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c4963-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c4963-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="c4963-136">`iULONG` (99)</span></span>            | <span data-ttu-id="c4963-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="c4963-137">UInt32</span></span>        | <span data-ttu-id="c4963-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c4963-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c4963-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="c4963-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="c4963-140">Byte</span><span class="sxs-lookup"><span data-stu-id="c4963-140">Byte</span></span>          | <span data-ttu-id="c4963-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="c4963-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c4963-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="c4963-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="c4963-143">String</span><span class="sxs-lookup"><span data-stu-id="c4963-143">String</span></span>        | <span data-ttu-id="c4963-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="c4963-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="c4963-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="c4963-145">`iGUID` (102)</span></span>            | <span data-ttu-id="c4963-146">GUID</span><span class="sxs-lookup"><span data-stu-id="c4963-146">Guid</span></span>          | <span data-ttu-id="c4963-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="c4963-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="c4963-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="c4963-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="c4963-149">Blob</span><span class="sxs-lookup"><span data-stu-id="c4963-149">Blob</span></span>          | <span data-ttu-id="c4963-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="c4963-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="c4963-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span><span class="sxs-lookup"><span data-stu-id="c4963-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="c4963-152">`iSTRING`: **IMetadataTables.GetString**</span><span class="sxs-lookup"><span data-stu-id="c4963-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="c4963-153">`iGUID`: **IMetadataTables.GetGUID**</span><span class="sxs-lookup"><span data-stu-id="c4963-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="c4963-154">`iBLOB`: **IMetadataTables.GetBlob**</span><span class="sxs-lookup"><span data-stu-id="c4963-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4963-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span><span class="sxs-lookup"><span data-stu-id="c4963-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4963-156">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4963-156">Requirements</span></span>  
 <span data-ttu-id="c4963-157">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4963-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4963-158">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4963-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4963-159">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4963-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4963-160">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4963-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4963-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4963-161">See also</span></span>

- [<span data-ttu-id="c4963-162">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4963-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c4963-163">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4963-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
