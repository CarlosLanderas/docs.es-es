---
title: ICorProfilerInfo3::GetThreadStaticAddress2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
ms.openlocfilehash: ee44c89ec30edcb6233081f0757fa0f7b7191178
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449645"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a>ICorProfilerInfo3::GetThreadStaticAddress2 (Método)
Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso y del dominio de aplicación especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parámetros  
 `classId`  
 de IDENTIFICADOR de la clase que contiene el campo estático de subproceso solicitado.  
  
 `fieldToken`  
 de Símbolo (token) de metadatos del campo estático de subproceso solicitado.  
  
 `appDomainId`  
 [in] Identificador de dominio de la aplicación.  
  
 `threadId`  
 de IDENTIFICADOR del subproceso que es el ámbito del campo estático solicitado.  
  
 `ppAddress`  
 enuncia Puntero a la dirección del campo estático que está dentro del subproceso especificado.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetThreadStaticAddress2` puede devolver uno de los siguientes:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT si no se ha asignado una dirección al campo estático dado en el contexto especificado.  
  
- Direcciones de los objetos que pueden estar en el montón de recolección de elementos no utilizados. Estas direcciones pueden dejar de ser válidas después de la recolección de elementos no utilizados, por lo que después de la recolección de elementos no utilizados, los perfiles no deben suponer que son válidas.  
  
 Antes de que se complete el constructor de clase de una clase, `GetThreadStaticAddress2` devolverá CORPROF_E_DATAINCOMPLETE para todos sus campos estáticos, aunque es posible que algunos de los campos estáticos ya estén inicializados y contengan objetos de recolección de elementos no utilizados de raíz.  
  
 El método [ICorProfilerInfo2:: getthreadstaticaddress (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) es similar al método `GetThreadStaticAddress2`, pero no acepta un argumento dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
