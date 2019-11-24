---
title: Obtener atributos de texto mediante UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
ms.openlocfilehash: c338f858f1715d23cad96919db4a21a6ba49710f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446916"
---
# <a name="obtain-text-attributes-using-ui-automation"></a><span data-ttu-id="b2e6e-102">Obtener atributos de texto mediante UI Automation</span><span class="sxs-lookup"><span data-stu-id="b2e6e-102">Obtain Text Attributes Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="b2e6e-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="b2e6e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b2e6e-104">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="b2e6e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b2e6e-105">En este tema se muestra cómo usar [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para obtener atributos de texto de un intervalo de texto.</span><span class="sxs-lookup"><span data-stu-id="b2e6e-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attributes from a text range.</span></span> <span data-ttu-id="b2e6e-106">Un intervalo de texto puede corresponder a la ubicación actual del símbolo de intercalación (o selección degenerada) dentro de un documento, una selección contigua de texto, una colección de selecciones de textos inconexos o todo el contenido textual de un documento.</span><span class="sxs-lookup"><span data-stu-id="b2e6e-106">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2e6e-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2e6e-107">Example</span></span>  
 <span data-ttu-id="b2e6e-108">En el ejemplo de código siguiente se muestra cómo obtener el valor <xref:System.Windows.Automation.TextPattern.FontNameAttribute> de un intervalo de texto.</span><span class="sxs-lookup"><span data-stu-id="b2e6e-108">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 <span data-ttu-id="b2e6e-109">El patrón de control <xref:System.Windows.Automation.TextPattern> , junto con la clase <xref:System.Windows.Automation.Text.TextPatternRange> , admite atributos de texto básicos, propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="b2e6e-109">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="b2e6e-110">Para la funcionalidad específica del control que no es compatible con <xref:System.Windows.Automation.TextPattern> ni <xref:System.Windows.Automation.Text.TextPatternRange> , la clase <xref:System.Windows.Automation.AutomationElement>ofrece métodos para que un cliente de Automatización de la interfaz de usuario acceda al modelo de objeto nativo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b2e6e-110">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange> the <xref:System.Windows.Automation.AutomationElement>, class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e6e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2e6e-111">See also</span></span>

- [<span data-ttu-id="b2e6e-112">Información general sobre TextPattern en Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b2e6e-112">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="b2e6e-113">Adición de contenido a un cuadro de texto mediante Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b2e6e-113">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="b2e6e-114">Búsqueda y resaltado de texto mediante Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b2e6e-114">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="b2e6e-115">Información general sobre los patrones de control de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b2e6e-115">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="b2e6e-116">Patrones de control de Automatización de la interfaz de usuario para clientes</span><span class="sxs-lookup"><span data-stu-id="b2e6e-116">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="b2e6e-117">Obtención de detalles de atributos de texto diversos mediante Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b2e6e-117">Obtain Mixed Text Attribute Details Using UI Automation</span></span>](obtain-mixed-text-attribute-details-using-ui-automation.md)
