---
title: My.Response (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 522814ad48fb7548032b8a37779bb3ff6ca62413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350656"
---
# <a name="myresponse-object"></a><span data-ttu-id="e7bbd-102">My.Response (Objeto)</span><span class="sxs-lookup"><span data-stu-id="e7bbd-102">My.Response Object</span></span>
<span data-ttu-id="e7bbd-103">Obtiene el objeto de <xref:System.Web.HttpResponse> asociado al <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="e7bbd-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="e7bbd-104">Este objeto permite enviar datos de respuesta HTTP a un cliente y contiene información sobre esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="e7bbd-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7bbd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7bbd-105">Remarks</span></span>  
 <span data-ttu-id="e7bbd-106">El objeto `My.Response` contiene el objeto <xref:System.Web.HttpResponse> actual asociado a la página.</span><span class="sxs-lookup"><span data-stu-id="e7bbd-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="e7bbd-107">El objeto `My.Response` solo está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e7bbd-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7bbd-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7bbd-108">Example</span></span>  
 <span data-ttu-id="e7bbd-109">En el ejemplo siguiente se obtiene la colección de encabezados del objeto `My.Request` y se usa el objeto `My.Response` para escribirlo en la página ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e7bbd-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e7bbd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7bbd-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="e7bbd-111">My.Request (objeto)</span><span class="sxs-lookup"><span data-stu-id="e7bbd-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
