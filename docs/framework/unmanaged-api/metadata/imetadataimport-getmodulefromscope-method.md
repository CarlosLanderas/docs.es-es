---
title: IMetaDataImport::GetModuleFromScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 026a952e14cda2ef4ebc32ca91006026e920e3c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437361"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="c4171-102">IMetaDataImport::GetModuleFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="c4171-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="c4171-103">Obtiene un símbolo (token) de metadatos para el módulo al que se hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="c4171-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4171-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4171-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4171-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4171-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="c4171-106">enuncia Puntero al token que representa el módulo al que se hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="c4171-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4171-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4171-107">Requirements</span></span>  
 <span data-ttu-id="c4171-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4171-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4171-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c4171-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4171-110">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c4171-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4171-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4171-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4171-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4171-112">See also</span></span>

- [<span data-ttu-id="c4171-113">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4171-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c4171-114">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4171-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
