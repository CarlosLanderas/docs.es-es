---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: 2d5b07acb9dc374fdd8872ed982a92171da28603
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137229"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a>ICorDebugProcess2::GetDesiredNGENCompilerFlags (Método)
Obtiene la configuración actual del marcador de compilador que el Common Language Runtime (CLR) utiliza para seleccionar la imagen precompilada correcta (es decir, nativa) que se va a cargar en este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pdwFlags`  
 enuncia Un puntero a una combinación bit a bit de los valores de enumeración de [cordebugjitcompilerflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) que se usan para seleccionar la imagen precompilada correcta que se va a cargar.  
  
## <a name="remarks"></a>Comentarios  
 Use el método [ICorDebugProcess2:: SetDesiredNGENCompilerFlags (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) para establecer las marcas que CLR usará para seleccionar la imagen precompilada correcta que se va a cargar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
