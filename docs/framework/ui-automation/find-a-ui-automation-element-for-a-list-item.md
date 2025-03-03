---
title: Buscar un elemento de UI Automation para un elemento de lista
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 63181de26f7d8efda99d5b5d71b006cde44823a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433546"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Buscar un elemento de UI Automation para un elemento de lista
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se muestra cómo recuperar un <xref:System.Windows.Automation.AutomationElement> para un elemento de una lista cuando se conoce el índice del elemento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran dos maneras de recuperar un elemento especificado de una lista, uno que usa <xref:System.Windows.Automation.TreeWalker> y el otro mediante <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 La primera técnica tiende a ser más rápida para los controles de [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], pero la segunda es más rápida para los controles de Windows Presentation Foundation (WPF).  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>Vea también

- [Obtaining UI Automation Elements](obtaining-ui-automation-elements.md)
