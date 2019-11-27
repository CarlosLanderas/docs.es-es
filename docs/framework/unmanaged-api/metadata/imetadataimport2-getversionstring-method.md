---
title: IMetaDataImport2::GetVersionString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 0c9f667edf30feb23e1cdaa28950503283fce42e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445225"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="aae38-102">IMetaDataImport2::GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="aae38-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="aae38-103">Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aae38-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aae38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aae38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aae38-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="aae38-106">enuncia Matriz para almacenar la cadena que especifica la versión.</span><span class="sxs-lookup"><span data-stu-id="aae38-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="aae38-107">de Tamaño, en caracteres anchos, de la matriz de `pwzBuf`.</span><span class="sxs-lookup"><span data-stu-id="aae38-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="aae38-108">enuncia El número de caracteres anchos, incluido un terminador nulo, devuelto en la matriz `pwzBuf`.</span><span class="sxs-lookup"><span data-stu-id="aae38-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aae38-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aae38-109">Remarks</span></span>  
 <span data-ttu-id="aae38-110">El método `GetVersionString` obtiene la versión integrada del ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="aae38-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="aae38-111">Si el ámbito no se ha guardado nunca, no tendrá una versión integrada y se devolverá una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="aae38-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae38-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aae38-112">Requirements</span></span>  
 <span data-ttu-id="aae38-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aae38-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae38-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aae38-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aae38-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aae38-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aae38-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aae38-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae38-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="aae38-117">See also</span></span>

- [<span data-ttu-id="aae38-118">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aae38-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="aae38-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aae38-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
