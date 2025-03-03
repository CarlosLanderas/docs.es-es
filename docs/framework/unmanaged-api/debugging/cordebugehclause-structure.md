---
title: CorDebugEHClause (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: f35e979a5107064d2987a385a989075ef71283ff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098858"
---
# <a name="cordebugehclause-structure"></a>CorDebugEHClause (Estructura)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Representa una cláusula de control de excepciones (EH) para una parte determinada de código de lenguaje intermedio (IL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`Flags`|Campo de bits que describe la información de la excepción en la cláusula EH. Para obtener más información, vea la sección Comentarios.|  
|`TryOffset`|Desplazamiento, en bytes, del bloque `try` desde el comienzo del cuerpo del método.|  
|`TryLength`|Longitud, en bytes, del bloque `try`.|  
|`HandlerOffset`|Ubicación del controlador para este bloque `try`.|  
|`HandlerLength`|Tamaño del código de controlador, en bytes.|  
|`ClassToken`|Token de metadatos para un controlador de excepciones basado en tipos.|  
|`FilterOffset`|Desplazamiento, en bytes, desde el principio del cuerpo del método para un controlador de excepciones basado en filtros.|  
  
## <a name="remarks"></a>Comentarios  
 El método [getehclauses (](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) devuelve una matriz de valores `CoreDebugEHClause`.  
  
 La información de la cláusula EH se define mediante la especificación de CLI. Para obtener más información, consulte [el estándar ECMA-355: Common Language Infrastructure (CLI), 6ª edición](https://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
 El campo `flags` puede contener las siguientes marcas. Tenga en cuenta que no están definidas en CorDebug.idl ni en CorDebug.h.  
  
|Marcar|Valor|Descripción|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|0x00000000|Cláusula de excepción tipada.|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|0x00000001|Filtro de excepción y cláusula de controlador.|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|0x00000002|Cláusula `finally`.|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|0x00000004|Cláusula fault (cláusula `finally` a la que se llama solo cuando se inicia una excepción).|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetEHClauses (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)
- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
