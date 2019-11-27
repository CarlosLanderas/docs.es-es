---
title: IMetaDataTables::GetNextBlob (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
ms.openlocfilehash: 145fdde302e7e942ea77049b3faeabf60894dd94
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448413"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="891eb-102">IMetaDataTables::GetNextBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="891eb-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="891eb-103">Obtiene el índice del siguiente objeto binario grande (BLOB) de la tabla.</span><span class="sxs-lookup"><span data-stu-id="891eb-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="891eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="891eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="891eb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="891eb-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="891eb-106">de Índice, tal y como se devuelve de una columna de blobs.</span><span class="sxs-lookup"><span data-stu-id="891eb-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="891eb-107">enuncia Puntero al índice del siguiente BLOB.</span><span class="sxs-lookup"><span data-stu-id="891eb-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="891eb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="891eb-108">Requirements</span></span>  
 <span data-ttu-id="891eb-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="891eb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="891eb-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="891eb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="891eb-111">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="891eb-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="891eb-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="891eb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891eb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="891eb-113">See also</span></span>

- [<span data-ttu-id="891eb-114">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="891eb-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="891eb-115">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="891eb-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
