---
title: IMetaDataDispenserEx::SetOption (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
ms.openlocfilehash: bc30f9fb120db92ccfc1e7dd0560b3fe18c54b29
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432733"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption (Método)
Establece la opción especificada en un valor determinado para el ámbito de metadatos actual. La opción controla cómo se controlan las llamadas al ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `optionId`  
 de Un puntero a un GUID que especifica la opción que se va a establecer.  
  
 `pValue`  
 de Valor que se va a usar para establecer la opción. El tipo de este valor debe ser una variante del tipo de la opción especificada.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se enumeran los GUID disponibles a los que puede apuntar el parámetro `optionId` y los valores válidos correspondientes para el parámetro `pValue`.  
  
|GUID|Descripción|`pValue` parámetro|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Controla qué elementos están comprobados en busca de duplicados. Cada vez que se llama a un método [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) que crea un nuevo elemento, puede pedir al método que compruebe si el elemento ya existe en el ámbito actual. Por ejemplo, puede comprobar la existencia de elementos `mdMethodDef`dos; en este caso, al llamar a [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), comprobará que el método no existe aún en el ámbito actual. Esta comprobación utiliza la clave que identifica de forma única un método dado: tipo primario, nombre y firma.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración [CorCheckDuplicatesFor (](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) .|  
|MetaDataRefToDefCheck|Controla los elementos a los que se hace referencia que se convierten en definiciones. De forma predeterminada, el motor de metadatos optimizará el código convirtiendo un elemento al que se hace referencia en su definición si el elemento al que se hace referencia se define realmente en el ámbito actual.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración [correftodefcheck (](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) .|  
|MetaDataNotificationForTokenMovement|Controla qué reasignaciones de token se producen durante una combinación de metadatos genera devoluciones de llamada. Use el método [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) para establecer la interfaz [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) .|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración [cornotificationfortokenmovement (](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) .|  
|MetaDataSetENC|Controla el comportamiento de editar y continuar (ENC). Solo se puede establecer un modo de comportamiento a la vez.|Debe ser una variante de tipo UI4 y debe contener un valor de la enumeración [corsetenc (](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) . El valor no es una máscara de máscara.|  
|MetaDataErrorIfEmitOutOfOrder|Controla los errores de emisión desordenados que generan devoluciones de llamada. La emisión de metadatos fuera de orden no es grave; sin embargo, si se emiten metadatos en un orden que se favorece mediante el motor de metadatos, los metadatos son más compactos y, por lo tanto, se pueden buscar de forma más eficaz. Use el método `IMetaDataEmit::SetHandler` para establecer la interfaz de [imetadataerror (](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) .|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración [corerrorifemitoutoforder (](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) .|  
|MetaDataImportOption|Controla qué tipos de elementos que se eliminaron durante un ENC se recuperan mediante un enumerador.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración de [enumeración corimportoptions (](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) .|  
|MetaDataThreadSafetyOptions|Controla si el motor de metadatos obtiene bloqueos de lectura/escritura, lo que garantiza la seguridad para subprocesos. De forma predeterminada, el motor supone que el acceso es de subproceso único por parte del llamador, por lo que no se obtiene ningún bloqueo. Los clientes son responsables de mantener la sincronización de subprocesos adecuada cuando se usa la API de metadatos.|Debe ser una variante de tipo UI4 y debe contener un valor de la enumeración [corthreadsafetyoptions (](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) . El valor no es una máscara de máscara.|  
|MetaDataGenerateTCEAdapters|Controla si el importador de la biblioteca de tipos debe generar los adaptadores de eventos estrechamente acoplados (TCE) para los contenedores de puntos de conexión COM.|Debe ser una variante de tipo BOOL. Si `pValue` se establece en `true`, el importador de la biblioteca de tipos genera los adaptadores de TCE.|  
|MetaDataTypeLibImportNamespace|Especifica un espacio de nombres no predeterminado para la biblioteca de tipos que se va a importar.|Debe ser un valor null o una variante de tipo BSTR. Si `pValue` es un valor null, el espacio de nombres actual se establece en null; de lo contrario, el espacio de nombres actual se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataLinkerOptions|Controla si el vinculador debe generar un ensamblado o un archivo de módulo de .NET Framework.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración [corlinkeroptions (](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) .|  
|MetaDataRuntimeVersion|Especifica la versión de la Common Language Runtime en la que se compiló esta imagen. La versión se almacena como una cadena, como "v 1.0.3705".|Debe ser un valor null, un valor de VT_EMPTY o una variante de tipo BSTR. Si `pValue` es null, la versión del tiempo de ejecución se establece en NULL. Si `pValue` es VT_EMPTY, la versión se establece en un valor predeterminado, que se extrae de la versión de mscorwks. dll en la que se está ejecutando el código de metadatos. De lo contrario, la versión en tiempo de ejecución se establece en la cadena que se mantiene en el tipo BSTR de la variante.|  
|MetaDataMergerOptions|Especifica las opciones para combinar los metadatos.|Debe ser una variante de tipo UI4 y debe contener una combinación de los valores de la enumeración `MergeFlags`, que se describe en el archivo CorHdr. h.|  
|MetaDataPreserveLocalRefs|Deshabilita la optimización de referencias locales en definiciones.|Debe contener una combinación de los valores de la enumeración [corlocalrefpreservation (](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) .|  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se utiliza como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
