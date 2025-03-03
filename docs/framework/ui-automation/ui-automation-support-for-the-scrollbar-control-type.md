---
title: Compatibilidad de la automatización de la interfaz de usuario para el tipo de control ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll Bar control type
- control types, Scroll Bar
- Scroll Bar control type
ms.assetid: 329891d7-b609-49e6-920a-09ea8a627d07
ms.openlocfilehash: 97093064fdef3c4a93c08407bc4c7233232ba8c0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801813"
---
# <a name="ui-automation-support-for-the-scrollbar-control-type"></a>Compatibilidad de la automatización de la interfaz de usuario para el tipo de control ScrollBar
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se proporciona información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control ScrollBar. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , valores de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y patrones de control.  
  
 Los controles de la barra de desplazamiento permiten a un usuario desplazarse por el contenido dentro de una ventana o contenedor de elementos. El control se compone de un conjunto de botones y un control thumb.  
  
 En las secciones siguientes se definen la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control ScrollBar. Los requisitos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de lista, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de automatización de interfaz de usuario necesaria  
 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de barra de desplazamiento y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista Contenido|  
|------------------|------------------|  
|ScrollBar<br /><br /> -Button (2 o 4)<br />-Thumb (0 O1)|No disponible. El control de barra de desplazamiento no tiene contenido.|  
  
 El control de barra de desplazamiento siempre tiene de tres a cinco elementos secundarios. Dado que el subárbol tiene más de un control de botón, debe establecer un valor <xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty> específico para cada elemento para que sea reconocibles para herramientas de automatización de prueba.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuyo valor o definición es especialmente relevante para los controles de barra de desplazamiento. Tenga en cuenta que un control de barra de desplazamiento tiene contenido; su funcionalidad se expone mediante el patrón de control Scroll, que se admite en el contenedor que se desplaza.  
  
 Para más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|{2&gt;Value&lt;2}|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el enfoque del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|`Null`|El control de barra de desplazamiento no tiene elementos de contenido y no es necesario establecer `NameProperty` .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|No es un número.|El control de barra de desplazamiento no tiene puntos interactivos.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Las barras de desplazamiento no tienen etiquetas.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ScrollBar|Este valor es el mismo para todos los marcos de trabajo. Las barras de desplazamiento que funcionan como controles deslizantes deben usar el tipo de control Slider.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"barra de desplazamiento"|Cadena localizada que se corresponde con el tipo de control Button.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Falso|El control de barra de desplazamiento nunca es un elemento de contenido. Si la barra de desplazamiento es un control independiente, debe cumplir el tipo de control Slider y devolver `ControlType.Slider` para la propiedad `ControlType` .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Verdadero|La barra de desplazamiento siempre debe ser un control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.OrientationProperty>|Verdadero|El control de barra de desplazamiento siempre debe exponer su orientación horizontal o vertical.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Patrones de control necesarios para la automatización de la interfaz de usuario  
 En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se admiten por los controles de barra de desplazamiento. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md). Tenga en cuenta que cuando se usa una barra de desplazamiento solo como control para manipulación de mouse, no admite patrones de control. Si se usa como control deslizante dentro de una aplicación, se le debe proporcionar el tipo de control Slider.  
  
|Patrón de control|Compatibilidad con|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Never|El patrón de control Scroll nunca se admite directamente en la barra de desplazamiento.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Depende|La compatibilidad de esta funcionalidad solo es necesaria si el patrón de control Scroll no se admite en el contenedor que tenga la barra de desplazamiento.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventos de automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de barra de desplazamiento. Para más información sobre eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico/valor|Notas|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Never|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Never|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Never|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Never|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Never|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Never|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> .|Depende|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Requerido|Ninguno|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.ScrollBar>
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
