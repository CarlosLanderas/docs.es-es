---
title: IMetaDataInfo::GetFileMapping (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436175"
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping (Método)
Obtiene la región de memoria del archivo asignado y el tipo de asignación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppvData`  
 enuncia Puntero al principio del archivo asignado.  
  
 `pcbData`  
 enuncia Tamaño de la región asignada. Si `pdwMappingType` es `fmFlat`, es el tamaño del archivo.  
  
 `pdwMappingType`  
 enuncia Valor de [corfilemapping (](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) que indica el tipo de asignación. La implementación actual del Common Language Runtime (CLR) siempre devuelve `fmFlat`. Otros valores se reservan para un uso futuro. Sin embargo, siempre debe comprobar el valor devuelto, ya que otros valores pueden estar habilitados en versiones futuras o versiones de servicio.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|`S_OK`|Se rellenan todas las salidas.|  
|`E_INVALIDARG`|Se pasó NULL como un valor de argumento.|  
|`COR_E_NOTSUPPORTED`|La implementación de CLR no puede proporcionar información sobre la región de memoria. Esto puede deberse a los siguientes motivos:<br /><br /> -El ámbito de metadatos se abrió con la marca `ofWrite` o `ofCopyMemory`.<br />-El ámbito de metadatos se abrió sin la marca `ofReadOnly`.<br />-El método [IMetaDataDispenser:: openscopeonmemory (](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) se usó para abrir solo la parte de metadatos del archivo.<br />-El archivo no es un archivo ejecutable portable (PE). **Nota:**  Estas condiciones dependen de la implementación de CLR y es probable que se debiliten en versiones futuras de CLR.|  
  
## <a name="remarks"></a>Comentarios  
 La memoria a la que apunta `ppvData` solo es válida siempre y cuando el ámbito de los metadatos subyacentes sea abierto.  
  
 Para que este método funcione, cuando asigne los metadatos de un archivo en disco a la memoria mediante una llamada al método [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) , debe especificar la marca `ofReadOnly` y no debe especificar la marca `ofWrite` o `ofCopyMemory`.  
  
 La elección del tipo de asignación de archivos para cada ámbito es específica de una implementación determinada de CLR. El usuario no puede establecerlo. La implementación actual de CLR siempre devuelve `fmFlat` en `pdwMappingType`, pero esto puede cambiar en versiones futuras de CLR o en futuras versiones de servicio de una versión determinada. Siempre debe comprobar el valor devuelto en `pdwMappingType`, ya que los distintos tipos tendrán distintos diseños y desplazamientos.  
  
 No se admite pasar NULL para ninguno de los tres parámetros. El método devuelve `E_INVALIDARG`y no se rellena ninguna de las salidas. Si se omite el tipo de asignación o el tamaño de la región, se puede producir una terminación anómala del programa.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataInfo (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [CorFileMapping (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
