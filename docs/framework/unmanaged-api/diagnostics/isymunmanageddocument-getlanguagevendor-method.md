---
title: ISymUnmanagedDocument::GetLanguageVendor (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
ms.openlocfilehash: cea2c161211dd74a46818c9b3c641852ea9999cd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449158"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="1a706-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="1a706-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="1a706-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="1a706-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a706-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a706-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a706-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a706-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1a706-106">enuncia Puntero a una variable que recibe el proveedor de idioma.</span><span class="sxs-lookup"><span data-stu-id="1a706-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a706-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1a706-107">Return Value</span></span>  
 <span data-ttu-id="1a706-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a706-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a706-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a706-109">See also</span></span>

- [<span data-ttu-id="1a706-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a706-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
