---
title: Compatibilidad de la automatización de la interfaz de usuario para el tipo de control RadioButton
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Radio Button
- UI Automation, Radio Button control type
- RadioButton control type
ms.assetid: 87170464-7857-41f1-bcf7-bb41be31cb53
ms.openlocfilehash: b5a64c987fd8d7816e2327e048b90ce20fa61c53
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800316"
---
# <a name="ui-automation-support-for-the-radiobutton-control-type"></a>Compatibilidad de la automatización de la interfaz de usuario para el tipo de control RadioButton
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control RadioButton. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , valores de propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] y patrones de control.  
  
 Un botón de opción consta de un botón redondo y de texto definido por la aplicación (una etiqueta), un icono o un mapa de bits que indica una opción que el usuario puede realizar seleccionando el botón. Normalmente, una aplicación usa botones de radio en un cuadro de grupo para permitir al usuario elegir entre un conjunto de opciones relacionadas, aunque mutuamente excluyentes. Por ejemplo, la aplicación puede presentar un grupo de botones de radio desde el que el usuario puede seleccionar una preferencia de formato para el texto seleccionado en el área del cliente. El usuario podría seleccionar un formato alineado a la izquierda, alineado a la derecha o centrado seleccionando el botón de radio correspondiente. Normalmente, el usuario solo puede seleccionar una opción cada vez a partir de un conjunto de botones de radio.  
  
 En las secciones siguientes se definen la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control RadioButton. Los requisitos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de lista, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de automatización de interfaz de usuario necesaria  
 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de botón de radio y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista Contenido|  
|------------------|------------------|  
|RadioButton|RadioButton|  
  
 No hay ningún elemento secundario en la vista de control o la vista de contenido.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuyo valor o definición es especialmente relevante para el tipo de control RadioButton. Para obtener más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [UI Automation Properties for clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|{2&gt;Value&lt;2}|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el enfoque del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El nombre del control del botón de radio es el texto que aparece junto al botón que mantiene el estado de la selección.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|El punto en el que se puede hacer clic del botón de radio DEBE ser un punto que establezca la selección en el botón de opción si se hace clic con el puntero del mouse.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Los botones de radio son controles con etiquetas propias.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|RadioButton|Este valor es el mismo para todos los marcos de trabajo [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"botón de radio"|Cadena localizada que corresponde al tipo de control RadioButton.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Verdadero|El control de botón de radio siempre se incluye en la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Verdadero|El control de botón de radio siempre se incluye en la vista de control del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Patrones de control necesarios para la automatización de la interfaz de usuario  
 En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de botón de radio. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control/propiedad de patrón de control|Soporte técnico/valor|Notas|  
|-----------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Sí|Todos los controles de botón de radio deben admitir el patrón Selection Item para permitir que se seleccionen.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider.SelectionContainer%2A>|Vea las notas.|Siempre debe completarse la `SelectionContainerProperty` para que un cliente de la automatización de la interfaz de usuario pueda determinar qué otros botones de radio dentro de un contexto específico están relacionados entre sí.  Para la versión [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] del botón de radio, no se admitirá esta propiedad porque no es posible obtener esta información de ese marco de trabajo heredado.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Never|El botón de radio no puede recorrer cíclicamente su estado una vez que se ha establecido.  Este patrón nunca se debe admitir en el botón de radio.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventos de automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de botón de radio. Para más información sobre eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Compatibilidad con|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Requerido|Ninguno|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Never|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Requerido|Ninguno|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.RadioButton>
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
