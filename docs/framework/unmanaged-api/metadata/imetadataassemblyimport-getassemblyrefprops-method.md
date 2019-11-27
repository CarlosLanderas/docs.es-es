---
title: IMetaDataAssemblyImport::GetAssemblyRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 4149db74adfa26df221eed5c590766a023bb105e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448226"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="2ef8a-102">IMetaDataAssemblyImport::GetAssemblyRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="2ef8a-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="2ef8a-103">Obtiene el conjunto de propiedades para la referencia de ensamblado con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ef8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ef8a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ef8a-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="2ef8a-106">de Símbolo (token) de metadatos de `mdAssemblyRef` que representa la referencia de ensamblado para la que se van a obtener las propiedades.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="2ef8a-107">enuncia Puntero a la clave pública o al token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="2ef8a-108">enuncia Número de bytes de la clave pública o el token devueltos.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="2ef8a-109">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2ef8a-110">de Tamaño, en caracteres anchos, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2ef8a-111">enuncia Puntero al número de caracteres anchos que se devuelven realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="2ef8a-112">enuncia Puntero a una estructura ASSEMBLYMETADATA (que contiene los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="2ef8a-113">enuncia Puntero al valor hash.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="2ef8a-114">Este es el hash, mediante el algoritmo SHA-1, de la `PublicKey` propiedad del ensamblado al que se hace referencia, a menos que se establezca la marca arfFullOriginator de la enumeración [AssemblyRefFlags (](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2ef8a-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="2ef8a-115">enuncia Número de caracteres anchos en el valor hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="2ef8a-116">enuncia Puntero a las marcas que describen los metadatos aplicados a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="2ef8a-117">El valor de flags es una combinación de uno o más valores de [corassemblyflags (](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2ef8a-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ef8a-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2ef8a-118">Return Value</span></span>  
 <span data-ttu-id="2ef8a-119">Este método devuelve S_OK si se realiza correctamente; de lo contrario, devuelve uno de los códigos de error definidos en el archivo de encabezado Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="2ef8a-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ef8a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ef8a-120">Requirements</span></span>  
 <span data-ttu-id="2ef8a-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ef8a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ef8a-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2ef8a-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ef8a-123">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2ef8a-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ef8a-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ef8a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef8a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ef8a-125">See also</span></span>

- [<span data-ttu-id="2ef8a-126">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ef8a-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
