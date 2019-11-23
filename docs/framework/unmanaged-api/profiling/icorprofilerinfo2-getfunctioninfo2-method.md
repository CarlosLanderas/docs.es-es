---
title: ICorProfilerInfo2::GetFunctionInfo2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type:
- apiref
ms.openlocfilehash: 11f9a186f5ec5e3b9e718a3ccd43b35b66d28078
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433179"
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a><span data-ttu-id="83bec-102">ICorProfilerInfo2::GetFunctionInfo2 (Método)</span><span class="sxs-lookup"><span data-stu-id="83bec-102">ICorProfilerInfo2::GetFunctionInfo2 Method</span></span>
<span data-ttu-id="83bec-103">Obtiene la clase primaria, el token de metadatos y el `ClassID` de cada argumento de tipo, si está presente, de una función.</span><span class="sxs-lookup"><span data-stu-id="83bec-103">Gets the parent class, the metadata token, and the `ClassID` of each type argument, if present, of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83bec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83bec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83bec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83bec-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="83bec-106">[in] Identificador de la función para la que se va a obtener la clase primaria y otra información.</span><span class="sxs-lookup"><span data-stu-id="83bec-106">[in] The ID of the function for which to get the parent class and other information.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="83bec-107">[in] Valor `COR_PRF_FRAME_INFO` que apunta a información acerca de un marco de pila.</span><span class="sxs-lookup"><span data-stu-id="83bec-107">[in] A `COR_PRF_FRAME_INFO` value that points to information about a stack frame.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="83bec-108">[out] Puntero a la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="83bec-108">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="83bec-109">[out] Puntero al módulo en el que se define la clase primaria de la función.</span><span class="sxs-lookup"><span data-stu-id="83bec-109">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="83bec-110">[out] Puntero al token de metadatos para la función.</span><span class="sxs-lookup"><span data-stu-id="83bec-110">[out] A pointer to the metadata token for the function.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="83bec-111">[in] Tamaño de la matriz `typeArgs`.</span><span class="sxs-lookup"><span data-stu-id="83bec-111">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcTypeArgs`  
 <span data-ttu-id="83bec-112">[out] Puntero al número total de valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="83bec-112">[out] A pointer to the total number of `ClassID` values.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="83bec-113">[out] Matriz de valores `ClassID`, cada uno de los cuales es el identificador de un argumento de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="83bec-113">[out] An array of `ClassID` values, each of which is the ID of a type argument of the function.</span></span> <span data-ttu-id="83bec-114">Cuando el método vuelve, `typeArgs` contendrá algunos o todos los valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="83bec-114">When the method returns, `typeArgs` will contain some or all of the `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83bec-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83bec-115">Remarks</span></span>  
 <span data-ttu-id="83bec-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span><span class="sxs-lookup"><span data-stu-id="83bec-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="83bec-117">Después, el token de metadatos que se devuelve a la ubicación a la que `pToken` hace referencia puede usarse para acceder a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="83bec-117">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="83bec-118">El identificador de clase y los argumentos de tipo que se devuelven mediante los parámetros `pClassId` y `typeArgs` dependen del valor que se pasa en el parámetro `frameInfo`, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="83bec-118">The class ID and type arguments that are returned through the `pClassId` and `typeArgs` parameters depend on the value that is passed in the `frameInfo` parameter, as shown in the following table.</span></span>  
  
|<span data-ttu-id="83bec-119">Valor del parámetro `frameInfo`</span><span class="sxs-lookup"><span data-stu-id="83bec-119">Value of the `frameInfo` parameter</span></span>|<span data-ttu-id="83bec-120">Resultado</span><span class="sxs-lookup"><span data-stu-id="83bec-120">Result</span></span>|  
|----------------------------------------|------------|  
|<span data-ttu-id="83bec-121">Un valor `COR_PRF_FRAME_INFO` que se obtiene de una devolución de llamada `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="83bec-121">A `COR_PRF_FRAME_INFO` value that was obtained from a `FunctionEnter2` callback</span></span>|<span data-ttu-id="83bec-122">El `ClassID` que se devuelve en la ubicación a la que `pClassId` hace referencia y todos los argumentos de tipo que se devuelven en la matriz `typeArgs` serán exactos.</span><span class="sxs-lookup"><span data-stu-id="83bec-122">The `ClassID`, returned in the location referenced by `pClassId`, and all type arguments, returned in the `typeArgs` array, will be exact.</span></span>|  
|<span data-ttu-id="83bec-123">Un valor `COR_PRF_FRAME_INFO` que se obtiene de un origen que no es una devolución de llamada `FunctionEnter2`</span><span class="sxs-lookup"><span data-stu-id="83bec-123">A `COR_PRF_FRAME_INFO` that was obtained from a source other than a `FunctionEnter2` callback</span></span>|<span data-ttu-id="83bec-124">El `ClassID` y los argumentos de tipo no se puede determinar exactamente.</span><span class="sxs-lookup"><span data-stu-id="83bec-124">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="83bec-125">Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="83bec-125">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
|<span data-ttu-id="83bec-126">Cero</span><span class="sxs-lookup"><span data-stu-id="83bec-126">Zero</span></span>|<span data-ttu-id="83bec-127">El `ClassID` y los argumentos de tipo no se puede determinar exactamente.</span><span class="sxs-lookup"><span data-stu-id="83bec-127">The exact `ClassID` and type arguments cannot be determined.</span></span> <span data-ttu-id="83bec-128">Es decir, `ClassID` podría ser NULL y algunos argumentos de tipo podrían volver como <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="83bec-128">That is, the `ClassID` might be null and some type arguments might come back as <xref:System.Object>.</span></span>|  
  
 <span data-ttu-id="83bec-129">Después de que `GetFunctionInfo2` vuelva, debe comprobar que el búfer `typeArgs` era lo suficientemente grande como para contener todos los valores `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="83bec-129">After `GetFunctionInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="83bec-130">Para ello, compare el valor al que `pcTypeArgs` apunta con el valor del parámetro `cTypeArgs`.</span><span class="sxs-lookup"><span data-stu-id="83bec-130">To do this, compare the value that `pcTypeArgs` points to with the value of the `cTypeArgs` parameter.</span></span> <span data-ttu-id="83bec-131">Si `pcTypeArgs` apunta a un valor mayor que `cTypeArgs` dividido por el tamaño de un valor `ClassID`, asigne un búfer `pcTypeArgs` mayor, actualice `cTypeArgs` con el nuevo tamaño y vuelva a llamar a `GetFunctionInfo2`.</span><span class="sxs-lookup"><span data-stu-id="83bec-131">If `pcTypeArgs` points to a value that is larger than `cTypeArgs` divided by the size of a `ClassID` value, allocate a larger `pcTypeArgs` buffer, update `cTypeArgs` with the new, larger size, and call `GetFunctionInfo2` again.</span></span>  
  
 <span data-ttu-id="83bec-132">También tiene la opción de llamar primero a `GetFunctionInfo2` con un búfer `pcTypeArgs` de longitud de cero para obtener el tamaño de búfer correcto.</span><span class="sxs-lookup"><span data-stu-id="83bec-132">Alternatively, you can first call `GetFunctionInfo2` with a zero-length `pcTypeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="83bec-133">Después, establezca el tamaño del búfer en el valor devuelto en `pcTypeArgs`, dividido por el tamaño de un valor `ClassID` y vuelva a llamar a `GetFunctionInfo2`.</span><span class="sxs-lookup"><span data-stu-id="83bec-133">You can then set the buffer size to the value returned in `pcTypeArgs` divided by the size of a `ClassID` value, and call `GetFunctionInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83bec-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83bec-134">Requirements</span></span>  
 <span data-ttu-id="83bec-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83bec-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83bec-136">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83bec-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83bec-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83bec-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83bec-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83bec-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bec-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="83bec-139">See also</span></span>

- [<span data-ttu-id="83bec-140">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83bec-140">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="83bec-141">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83bec-141">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="83bec-142">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="83bec-142">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="83bec-143">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="83bec-143">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
