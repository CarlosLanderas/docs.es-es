---
title: COR_PRF_STATIC_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 40efe81f72a2043503bf521e3e47dad1a7f4530c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448454"
---
# <a name="cor_prf_static_type-enumeration"></a>COR_PRF_STATIC_TYPE (Enumeración)
Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo. Estos valores se pueden combinar mediante la operación OR bit a bit para indicar que el campo tiene varias cualidades estáticas diferentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|El campo no es estático.|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|El campo es dominio de aplicación-estático.|  
|`COR_PRF_FIELD_THREAD_STATIC`|El campo es estático de subproceso.|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|El campo es de contexto estático.|  
|`COR_PRF_FIELD_RVA_STATIC`|El campo es la dirección virtual relativa (RVA)-static.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
