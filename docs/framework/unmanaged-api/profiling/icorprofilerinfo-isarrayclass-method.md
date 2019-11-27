---
title: ICorProfilerInfo::IsArrayClass (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 57515ac4670b9b7e25bb496851347a62e1b246df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438709"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="ee5b3-102">ICorProfilerInfo::IsArrayClass (Método)</span><span class="sxs-lookup"><span data-stu-id="ee5b3-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="ee5b3-103">Determina si la clase especificada es una clase de matriz.</span><span class="sxs-lookup"><span data-stu-id="ee5b3-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee5b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee5b3-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee5b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee5b3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="ee5b3-106">de IDENTIFICADOR de la clase que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="ee5b3-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="ee5b3-107">enuncia Un puntero a un valor de la enumeración CorElementType que indica el tipo de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ee5b3-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="ee5b3-108">enuncia Puntero al identificador de clase de los elementos de la matriz, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="ee5b3-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="ee5b3-109">enuncia Un puntero a un entero que indica el rango (es decir, el número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ee5b3-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee5b3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee5b3-110">Remarks</span></span>  
 <span data-ttu-id="ee5b3-111">Si la clase especificada es una clase de matriz, el método `IsArrayClass` devuelve un S_OK HRESULT y valores para cualquier parámetro de salida que no sea NULL.</span><span class="sxs-lookup"><span data-stu-id="ee5b3-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="ee5b3-112">De lo contrario, devuelve S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="ee5b3-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee5b3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee5b3-113">Requirements</span></span>  
 <span data-ttu-id="ee5b3-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee5b3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee5b3-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee5b3-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee5b3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee5b3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee5b3-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee5b3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5b3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee5b3-118">See also</span></span>

- [<span data-ttu-id="ee5b3-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee5b3-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
