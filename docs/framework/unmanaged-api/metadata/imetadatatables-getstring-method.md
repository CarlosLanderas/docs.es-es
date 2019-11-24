---
title: IMetaDataTables::GetString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 055499230f500cb7249746e1acbf46b4548d25bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426802"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="fdf4a-102">IMetaDataTables::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="fdf4a-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="fdf4a-103">Gets the string at the specified index from the table column in the current reference scope.</span><span class="sxs-lookup"><span data-stu-id="fdf4a-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf4a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdf4a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdf4a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdf4a-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="fdf4a-106">[in] The index at which to start to search for the next value.</span><span class="sxs-lookup"><span data-stu-id="fdf4a-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="fdf4a-107">[out] A pointer to a pointer to the returned string value.</span><span class="sxs-lookup"><span data-stu-id="fdf4a-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdf4a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdf4a-108">Requirements</span></span>  
 <span data-ttu-id="fdf4a-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdf4a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdf4a-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fdf4a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fdf4a-111">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fdf4a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fdf4a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdf4a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf4a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdf4a-113">See also</span></span>

- [<span data-ttu-id="fdf4a-114">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdf4a-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="fdf4a-115">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdf4a-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
