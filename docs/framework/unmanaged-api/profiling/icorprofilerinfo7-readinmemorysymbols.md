---
title: 'ICorProfilerInfo7:: ReadInMemorySymbols'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
ms.openlocfilehash: ae51490be96f3eb6524831c93739c3befbc30b37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132036"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7:: ReadInMemorySymbols
[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Lee bytes de una secuencia de símbolos en memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `moduleId`  
 de Identificador del módulo que contiene la secuencia en memoria.  
  
 `symbolsReadOffset`  
 de Desplazamiento en la secuencia en memoria donde se va a empezar a leer los bytes.  
  
 `pSymbolBytes`  
 enuncia Puntero al búfer en el que se copiarán los datos. El búfer debe tener `countSymbolBytes` de espacio disponible.  
  
 `countSymbolBytes`  
 de Número de bytes que se van a copiar.  
  
 `pCountSymbolBytesRead`  
 enuncia Cuando el método vuelve, contiene el número real de bytes leídos.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK`, si se leyó un número distinto de cero de bytes.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, si el módulo se creó con <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Comentarios  
 El método `ReadInMemorySymbols` intenta leer `countSymbolBytes` de datos a partir de la posición de desplazamiento `symbolsReadOffset` dentro de la secuencia en memoria. Los datos se copian en `pSymbolBytes`, lo que se espera que tenga `countSymbolBytes` de espacio disponible.     `pCountSymbolsBytesRead` contiene el número real de bytes leídos, que puede ser menor que `countSymbolBytes` si se alcanza el final de la secuencia.  
  
> [!NOTE]
> La implementación actual no admite Reflection. Emit. Si el módulo se creó con Reflection. Emit, el método devuelve `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
