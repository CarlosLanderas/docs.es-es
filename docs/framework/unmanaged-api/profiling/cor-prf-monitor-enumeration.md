---
title: COR_PRF_MONITOR (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
ms.openlocfilehash: 321ad53ca5f773191c5b5d1084b36caa6aeae4dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137046"
---
# <a name="cor_prf_monitor-enumeration"></a>COR_PRF_MONITOR (Enumeración)
Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a>Miembros  
 En las secciones siguientes se enumeran `COR_PRF_MONITOR` miembros de enumeración por categoría. Las categorías son:  
  
- [No se ha establecido ninguna marca](#None)  
  
- [Marcas de devolución de llamada](#Callback)  
  
- [Marcas de habilitación de características](#Feature)  
  
- [Marcas de configuración](#Config)  
  
- [Marcas compuestas](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a>No se ha establecido ninguna marca  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|No se establecen marcas.|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a>Marcas de devolución de llamada  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Habilita todos los eventos de devolución de llamada.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|Controla las devoluciones de llamada `AppDomainCreation*` y `AppDomainShutdown*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|Controla las devoluciones de llamada `AssemblyLoad*` y `AssemblyUnload*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|Controla las devoluciones de llamada `JITCachedFunctionSearch*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).<br /><br /> El comportamiento de esta marca se cambió en .NET Framework versión 2.0.|  
|`COR_PRF_MONITOR_CCW`|Controla las devoluciones de llamada `COMClassicVTable*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CLASS_LOADS`|Controla las devoluciones de llamada `ClassLoad*` y `ClassUnload*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|Controla las devoluciones de llamada `ExceptionCLRCatcher*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|Controla las devoluciones de llamada [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) y [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_ENTERLEAVE`|Controla las `FunctionEnter*`funciones estáticas globales de generación de perfiles`FunctionLeave*``FunctionTailCall*`, [ y ](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md).|  
|`COR_PRF_MONITOR_EXCEPTIONS`|Controla la devolución de llamada [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) y las devoluciones de llamada `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*` y `ExceptionCatcher*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Controla la devolución de llamada [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_GC`|Controla las devoluciones de llamada [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md), [RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md) y [FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) en las interfaces `ICorProfilerCallback*`. Cuando se asigna `COR_PRF_MONITOR_GC`, se desactiva la recolección de elementos no utilizados simultánea.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|Controla las devoluciones de llamada `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md) y [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_MODULE_LOADS`|Controla las devoluciones de llamada `ModuleLoad*`, `ModuleUnload*` y [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Controla la devolución de llamada [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_REMOTING`|Controla las devoluciones de llamada `Remoting*` en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Controla si las devoluciones de llamada `Remoting*` supervisarán eventos asincrónicos.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Controla si se pasa una cookie a las devoluciones de llamada `Remoting*`.|  
|`COR_PRF_MONITOR_SUSPENDS`|Controla las devoluciones de llamada `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md) y [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) en la interfaz [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md).|  
|`COR_PRF_MONITOR_THREADS`|Controla las devoluciones de llamada [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md) y [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) en las interfaces [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) e [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md).|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a>Marcas para habilitar características  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Habilita la recuperación de un `ClassID` exacto para una función genérica llamando al método [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) con un valor `COR_PRF_FRAME_INFO` devuelto por la devolución de llamada [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md).|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Habilita el seguimiento de argumentos usando las devoluciones de llamada [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) o [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) y el método [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md).|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Permite realizar el seguimiento de valores devueltos usando las devoluciones de llamada [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) o [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) y el método [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md).|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|Desusado.<br /><br /> No se admite la depuración en proceso. Esta marca no tiene efecto.|  
|`COR_PRF_ENABLE_JIT_MAPS`|Desusado.<br /><br /> Permite al generador de perfiles obtener asignaciones de IL a nativo usando [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md). A partir de .NET Framework 2.0, el tiempo de ejecución siempre realiza el seguimiento de las asignaciones de IL a nativo; por lo tanto, se considera que esta marca está siempre establecida.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Informa al tiempo de ejecución que puede que el generador de perfiles quiera notificaciones de asignación de objetos. Esta marca se debe establecer durante la inicialización. Permite al generador de perfiles seguir usando la marca `COR_PRF_MONITOR_OBJECT_ALLOCATED` para recibir devoluciones de llamada [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).|  
|`COR_PRF_ENABLE_REJIT`|Habilita las llamadas a los métodos [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) y [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md). El generador de perfiles debe establecer esta marca en el inicio.  Si el generador de perfiles especifica esta marca, también debe especificar `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Habilita las llamadas al método [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md).|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a>Marcas de configuración  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Impide que se carguen todas las imágenes nativas (incluidas imágenes mejoradas por el generador de perfiles).  Si se especifican esta marca y la marca `COR_PRF_USE_PROFILE_IMAGES`, se usa `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_DISABLE_INLINING`|Deshabilita todas las inserciones.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Deshabilita todas las optimizaciones de código.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Deshabilita las comprobaciones de transparencia de seguridad que normalmente se realizan durante la compilación Just-In-Time (JIT) y la carga de las clases para ensamblados de confianza total. Esto puede hacer que la instrumentación sea más fácil de realizar.|  
|`COR_PRF_USE_PROFILE_IMAGES`|Hace que la búsqueda de imágenes nativas busque imágenes mejoradas por el generador de perfiles. Si no se encuentra ninguna imagen mejorada por el generador de perfiles para un ensamblado determinado, Common Language Runtime vuelve a JIT para ese ensamblado. Si se especifican esta marca y la marca `COR_PRF_DISABLE_ALL_NGEN_IMAGES`, se usa `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a>Marcas compuestas  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_ALL`|Representa todos los valores de la marca `COR_PRF_MONITOR`.|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|Representa todas las marcas `COR_PRF_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución. En la sección sobre la sintaxis se indica cada una de las marcas presentes en esta máscara de bits.|  
|`COR_PRF_MONITOR_ALL`|Habilita todos los eventos de devolución de llamada.|  
|`COR_PRF_MONITOR_IMMUTABLE`|Representa todas las marcas `COR_PRF_MONITOR` que se pueden establecer solo durante la inicialización. Al intentar cambiar cualquiera de estas marcas después de la inicialización se genera un valor `HRESULT` que indica error.|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|Representa todas las marcas `COR_PRF_MONITOR` que requieren imágenes mejoradas para el perfil.|  
  
## <a name="remarks"></a>Comentarios  
 Se usa un valor `COR_PRF_MONITOR` con los métodos [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para definir las notificaciones de eventos que Common Language Runtime envía al generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [GetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)
- [SetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)
