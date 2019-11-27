---
title: ICeeGen::GetSectionCreate (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 2c3c3a0168216902e5982b7d0193e72acc2bdf47
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448099"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="565c7-102">ICeeGen::GetSectionCreate (Método)</span><span class="sxs-lookup"><span data-stu-id="565c7-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="565c7-103">Genera y obtiene una sección de código usando el nombre y los valores de marca especificados.</span><span class="sxs-lookup"><span data-stu-id="565c7-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="565c7-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="565c7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="565c7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="565c7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="565c7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="565c7-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="565c7-107">de Puntero a una cadena que especifica el nombre de la sección que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="565c7-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="565c7-108">de Marcas que especifican las opciones.</span><span class="sxs-lookup"><span data-stu-id="565c7-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="565c7-109">enuncia Un puntero a la sección de código que se acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="565c7-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="565c7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="565c7-110">Remarks</span></span>  
 <span data-ttu-id="565c7-111">Llame solo a `GetSectionCreate` si tiene requisitos de sección especiales que no se controlan mediante otros métodos.</span><span class="sxs-lookup"><span data-stu-id="565c7-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="565c7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="565c7-112">Requirements</span></span>  
 <span data-ttu-id="565c7-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="565c7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="565c7-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="565c7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="565c7-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="565c7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="565c7-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="565c7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565c7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="565c7-117">See also</span></span>

- [<span data-ttu-id="565c7-118">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="565c7-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
