---
title: CorDebugGuidToTypeMapping (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
ms.openlocfilehash: 313f6649448653ad630d616c7dbf739653e352dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132838"
---
# <a name="cordebugguidtotypemapping-structure"></a>CorDebugGuidToTypeMapping (Estructura)
Asigna un GUID de Windows Runtime a su objeto ICorDebugType correspondiente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`iid`|GUID del tipo de Windows Runtime almacenado en memoria caché.|  
|`pType`|Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en memoria caché.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Windows Runtime.  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
