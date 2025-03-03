---
title: IMetaDataImport::GetPropertyProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 247a2793bf3806f5ee38585d50b4535820dfcb69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437059"
---
# <a name="imetadataimportgetpropertyprops-method"></a>IMetaDataImport::GetPropertyProps (Método)
Obtiene los metadatos de la propiedad representada por el token especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `prop`  
 de Token que representa la propiedad para la que se van a devolver los metadatos.  
  
 `pClass`  
 enuncia Puntero al token de TypeDef que representa el tipo que implementa la propiedad.  
  
 `szProperty`  
 enuncia Búfer que contiene el nombre de la propiedad.  
  
 `cchProperty`  
 de Tamaño en caracteres anchos de `szProperty`.  
  
 `pchProperty`  
 enuncia Número de caracteres anchos devueltos en `szProperty`.  
  
 `pdwPropFlags`  
 enuncia Un puntero a cualquier marcador de atributo aplicado a la propiedad. Este valor es una máscara de máscara de la enumeración [CorPropertyAttr (](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) .  
  
 `ppvSig`  
 enuncia Puntero a la firma de metadatos de la propiedad.  
  
 `pbSig`  
 enuncia Número de bytes devueltos en `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 enuncia Marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad. Este valor procede de la enumeración CorElementType.  
  
 `ppDefaultValue`  
 enuncia Puntero a los bytes que almacenan el valor predeterminado de esta propiedad.  
  
 `pcchDefaultValue`  
 enuncia Tamaño en caracteres anchos de `ppDefaultValue`, si se ELEMENT_TYPE_STRING `pdwCPlusTypeFlag`; de lo contrario, este valor no es relevante. En ese caso, la longitud de `ppDefaultValue` se deduce del tipo especificado por `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 enuncia Puntero al token de MethodDef que representa el método de descriptor de acceso set para la propiedad.  
  
 `pmdGetter`  
 enuncia Puntero al token de MethodDef que representa el método de descriptor de acceso get para la propiedad.  
  
 `rmdOtherMethod`  
 enuncia Matriz de tokens de MethodDef que representan otros métodos asociados a la propiedad.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`. Si no proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin ninguna advertencia.  
  
 `pcOtherMethod`  
 enuncia Número de tokens de MethodDef devueltos en `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
