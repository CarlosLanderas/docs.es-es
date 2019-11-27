---
title: ICorProfilerCallback::ClassUnloadStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadStarted
helpviewer_keywords:
- ClassUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ClassUnloadStarted method [.NET Framework profiling]
ms.assetid: bc93bead-f3a9-415c-b919-ddd3ca80facc
topic_type:
- apiref
ms.openlocfilehash: 3b729d3be84571a48cc9a770d7f06b99723c0d1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445069"
---
# <a name="icorprofilercallbackclassunloadstarted-method"></a><span data-ttu-id="07859-102">ICorProfilerCallback::ClassUnloadStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="07859-102">ICorProfilerCallback::ClassUnloadStarted Method</span></span>
<span data-ttu-id="07859-103">Notifica al generador de perfiles que se está descargando una clase.</span><span class="sxs-lookup"><span data-stu-id="07859-103">Notifies the profiler that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07859-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07859-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07859-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07859-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="07859-106">de Identifica la clase que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="07859-106">[in] Identifies the class that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07859-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07859-107">Remarks</span></span>  
 <span data-ttu-id="07859-108">El valor de `classId` no es válido para una solicitud de información después de que se devuelva el método `ClassUnloadStarted`; esta es la última oportunidad del generador de perfiles para obtener información sobre esta clase.</span><span class="sxs-lookup"><span data-stu-id="07859-108">The value of `classId` is not valid for an information request after the `ClassUnloadStarted` method returns — this is the profiler's last chance to obtain information about this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07859-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07859-109">Requirements</span></span>  
 <span data-ttu-id="07859-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07859-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07859-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="07859-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07859-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07859-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07859-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07859-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07859-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="07859-114">See also</span></span>

- [<span data-ttu-id="07859-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="07859-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="07859-116">ClassUnloadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="07859-116">ClassUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)
