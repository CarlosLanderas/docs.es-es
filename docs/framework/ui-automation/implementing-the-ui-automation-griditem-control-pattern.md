---
title: Implementar el patrón de control GridItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: 832a53e072afc5533f2eeb7feb0cc326771cf23d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435256"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a>Implementar el patrón de control GridItem de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>y se incluye información sobre propiedades. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.GridItemPattern> se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IGridProvider>. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar <xref:System.Windows.Automation.Provider.IGridProvider>, tenga en cuenta las directrices y convenciones siguientes:  
  
- Las coordenadas de la cuadrícula son de base, donde la celda superior izquierda tiene las coordenadas (0, 0).  
  
- Las celdas combinadas informarán de sus propiedades <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> y <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> según su celda de anclaje subyacente, como define el proveedor de Automatización de la interfaz de usuario. Normalmente, será la fila o columna superior izquierda.  
  
- <xref:System.Windows.Automation.Provider.IGridItemProvider> no proporciona la manipulación activa de la cuadrícula, como combinar o dividir celdas.  
  
- Los controles que implementan <xref:System.Windows.Automation.Provider.IGridItemProvider> normalmente se pueden atravesar (es decir, un cliente de UI Automation puede moverse a los controles adyacentes) con el teclado.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>Miembros requeridos para IGridItemProvider  
 Para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>, se requieren las siguientes propiedades y métodos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|Propiedad|Ninguno|  
  
 Este patrón de control no tiene métodos o propiedades asociados.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Este patrón de control no tiene excepciones asociadas.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario](support-control-patterns-in-a-ui-automation-provider.md)
- [UI Automation Control Patterns for Clients](ui-automation-control-patterns-for-clients.md)
- [Implementación del patrón de control Grid de Automatización de la interfaz de usuario](implementing-the-ui-automation-grid-control-pattern.md)
- [Información general sobre el árbol de la Automatización de la interfaz de usuario](ui-automation-tree-overview.md)
- [Uso del almacenamiento en caché en la Automatización de la interfaz de usuario](use-caching-in-ui-automation.md)
