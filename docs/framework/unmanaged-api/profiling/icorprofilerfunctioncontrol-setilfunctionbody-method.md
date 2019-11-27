---
title: ICorProfilerFunctionControl::SetILFunctionBody (método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: f6e2cfe47bdd212e39549544b06bf5b11033a956
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429888"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="45974-102">ICorProfilerFunctionControl::SetILFunctionBody (método)</span><span class="sxs-lookup"><span data-stu-id="45974-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="45974-103">Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.</span><span class="sxs-lookup"><span data-stu-id="45974-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45974-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45974-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45974-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45974-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="45974-106">[in] El tamaño total del nuevo CIL, incluido el encabezado y cualquier estructura que venga después del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="45974-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="45974-107">[in] Puntero al nuevo encabezado de CIL.</span><span class="sxs-lookup"><span data-stu-id="45974-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45974-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="45974-108">Return Value</span></span>  
 <span data-ttu-id="45974-109">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="45974-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="45974-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45974-110">HRESULT</span></span>|<span data-ttu-id="45974-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="45974-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45974-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="45974-112">S_OK</span></span>|<span data-ttu-id="45974-113">El reemplazo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="45974-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45974-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45974-114">Remarks</span></span>  
 <span data-ttu-id="45974-115">A diferencia del método [ICorProfilerInfo:: SetILFunctionBody (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) , el método `SetILFunctionBody` administra la memoria necesaria para el nuevo cuerpo de CIL.</span><span class="sxs-lookup"><span data-stu-id="45974-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="45974-116">Esto significa que no es necesario asignar el cuerpo de CIL proporcionado por el generador de perfiles utilizando la interfaz [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) o asignada dentro de un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="45974-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="45974-117">sino que se puede asignar en cualquier montón.</span><span class="sxs-lookup"><span data-stu-id="45974-117">It can be allocated on any heap.</span></span> <span data-ttu-id="45974-118">El generador de perfiles puede liberar la memoria usada para su cuerpo de CIL después de que `SetILFunctionBody` devuelve.</span><span class="sxs-lookup"><span data-stu-id="45974-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45974-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45974-119">Requirements</span></span>  
 <span data-ttu-id="45974-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45974-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45974-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45974-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45974-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45974-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45974-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45974-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45974-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="45974-124">See also</span></span>

- [<span data-ttu-id="45974-125">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45974-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
