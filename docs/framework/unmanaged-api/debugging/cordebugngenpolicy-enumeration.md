---
title: CorDebugNGenPolicy (enumeración)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
ms.openlocfilehash: 2f8337f96239948189ffd58923d87fd05c79b0c3
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204862"
---
# <a name="cordebugngenpolicy-enumeration"></a>CorDebugNGenPolicy (enumeración)
Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>Miembros  
  
|Nombre de miembro|Descripción|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|En una aplicación de la tienda Windows 8. x, el uso de imágenes de la memoria caché de imágenes nativas local está deshabilitado. En una aplicación de escritorio, este valor no tiene ningún efecto.|  
  
## <a name="remarks"></a>Comentarios  
 El método [ICorDebugProcess5:: enablengenpolicy (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) usa la enumeración `CorDebugNGENPolicy`. Deshabilitar el uso de imágenes de la memoria caché de imágenes nativas local proporciona una experiencia de depuración coherente asegurándose de que el depurador carga imágenes compiladas por JIT depurables en lugar de imágenes nativas optimizadas.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
