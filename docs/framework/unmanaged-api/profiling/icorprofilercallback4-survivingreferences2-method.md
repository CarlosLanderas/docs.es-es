---
title: ICorProfilerCallback4::SurvivingReferences2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
ms.openlocfilehash: 3178d099db96d52f0238cfcf7e055e761687ce30
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430094"
---
# <a name="icorprofilercallback4survivingreferences2-method"></a>ICorProfilerCallback4::SurvivingReferences2 (Método)
Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación. Se llama a este método si el generador de perfiles ha implementado la interfaz [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) . Esta devolución de llamada reemplaza el método [ICorProfilerCallback2:: SurvivingReferences (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) , ya que puede informar de intervalos de objetos mayores cuyas longitudes superen lo que se puede expresar en un ulong.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cSurvivingObjectIDRanges`  
 [in] Número de bloques de objetos contiguos que sobrevivieron como resultado de la recolección de elementos no utilizados sin compactación. Es decir, el valor de `cSurvivingObjectIDRanges` es el tamaño de las matrices `objectIDRangeStart` y `cObjectIDRangeLength`, que almacenan un `ObjectID` y una longitud, respectivamente, para cada bloque de objetos.  
  
 Los dos argumentos siguientes de `SurvivingReferences2` son matrices paralelas. En otras palabras, `objectIDRangeStart` y `cObjectIDRangeLength` hacen referencia al mismo bloque de objetos contiguos.  
  
 `objectIDRangeStart`  
 [in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial de un bloque de objetos activos y contiguos en la memoria.  
  
 `cObjectIDRangeLength`  
 [in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque superviviente de objetos contiguos en la memoria.  
  
 Se especifica un tamaño para cada bloque al que se hace referencia en la matriz `objectIDRangeStart`.  
  
## <a name="remarks"></a>Comentarios  
 Los elementos de las matrices `objectIDRangeStart` y `cObjectIDRangeLength` deben interpretarse del siguiente modo para determinar si un objeto ha sobrevivido a la recolección de elementos no utilizados. Supongamos que un valor `ObjectID` (`ObjectID`) se encuentra dentro del intervalo siguiente:  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 Para cualquier valor `i` que esté en el intervalo siguiente, el objeto sobrevivió a la recolección de elementos no utilizados:  
  
 0 < = `i` < `cSurvivingObjectIDRanges`  
  
 Una recolección de elementos no utilizados sin compactación recupera la memoria ocupada por objetos "inactivos", pero no compacta ese espacio liberado. Como consecuencia, la memoria se devuelve al montón pero no se mueve ningún objeto "activo".  
  
 Common Language Runtime (CLR) llama a `SurvivingReferences2` para las recolecciones de elementos no utilizados sin compactación. Para compactar las recolecciones de elementos no utilizados, se llama a [movedreferences2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) en su lugar. Se puede compactar una única recolección de elementos no utilizados para una generación y no compactar para otra. En el caso de una recolección de elementos no utilizados en una generación determinada, el generador de perfiles recibirá una devolución de llamada de `SurvivingReferences2` o una devolución de llamada [movedreferences2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) , pero no ambos.  
  
 Se podrían recibir varias devoluciones de llamada `SurvivingReferences2` durante una recolección de elementos no utilizados determinada, a causa de un almacenamiento de búfer interno limitado, de varias devoluciones de llamada durante la recolección de elementos no utilizados del servidor o por otras razones. En el caso de varias devoluciones de llamada durante una recolección de elementos no utilizados, la información es acumulativa. Todas las referencias que se notifican en cualquier devolución de llamada `SurvivingReferences2` sobreviven a la recolección de elementos no utilizados.  
  
 Si el generador de perfiles implementa las interfaces [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) y [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) , se llama al método `SurvivingReferences2` antes que al método [ICorProfilerCallback2:: survivingreferences (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) , pero solo si `SurvivingReferences2` devuelve correctamente. Los generadores de perfiles pueden devolver un valor HRESULT que indique un error del método `SurvivingReferences2` para evitar llamar al segundo método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
