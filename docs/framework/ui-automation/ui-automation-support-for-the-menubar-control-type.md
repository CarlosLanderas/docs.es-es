---
title: Compatibilidad de la automatización de la interfaz de usuario para el tipo de control MenuBar
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Menu Bar control type
- control types, Menu Bar
- Menu Bar control type
ms.assetid: c1202b21-c1f0-4560-853c-7b99bd73ad97
ms.openlocfilehash: 233fdb088d31718650696d56c035cdb1a97687fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446694"
---
# <a name="ui-automation-support-for-the-menubar-control-type"></a>Compatibilidad de la automatización de la interfaz de usuario para el tipo de control MenuBar
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control <xref:System.Windows.Automation.ControlType.MenuBar> . En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que debe cumplir un control para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . En las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Los controles de contenedor de barra de menús son un ejemplo de controles que implementan el tipo de control MenuBar. Las barras de menús proporcionan un medio para que los usuarios activen los comandos y las opciones contenidos en una aplicación.  
  
 En las secciones siguientes se definen la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control MenuBar. Los requisitos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de la lista, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  
 En la tabla siguiente se describen la vista de control y la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de barra de menús y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista Contenido|  
|------------------|------------------|  
|MenuBar<br /><br /> -MenuItem (1 o más)<br />-Otros controles (0 o muchos)|MenuBar<br /><br /> -MenuItem (1 o más)<br />-Otros controles (0 o muchos)|  
  
 Los controles de barra de menús pueden contener otros controles como controles de edición y cuadros combinados dentro de su estructura. Estos controles adicionales corresponden a la categoría "otros controles" que se indica anteriormente en las vistas de control y de contenido.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Propiedades necesarias para la automatización de la interfaz de usuario  
 En la tabla siguiente se muestran las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que tienen un valor o una definición que es especialmente relevante para los controles de barra de menús. Para obtener más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [UI Automation Properties for clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valor|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El valor que expone esta propiedad debe incluir todos los controles que se contienen dentro de ella.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El control de barra de menús no necesita un nombre a menos que una aplicación tenga más de una barra de menús. Si hay más de una barra de menús en una aplicación, esta propiedad debe utilizarse para exponer los nombres distintivos, como "Formatting" o "Outlining".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Los controles de barra de menús nunca tienen una etiqueta.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|MenuBar|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"barra de menús"|Cadena localizada que corresponde al tipo de control MenuBar.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de barra de menús siempre se incluye en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de barra de menús siempre se incluye en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Vea las notas.|El valor de esta propiedad depende de si el control es visible en la pantalla.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.OrientationProperty>|Depende|Esta propiedad expone si el control de barra de menús es horizontal o vertical.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Los controles de barra de menús pueden recibir el foco del teclado porque los controles que contienen pueden recibir el foco de teclado.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vea las notas.|No hay escenarios en los que sea necesario texto de ayuda para un control de barra de menús.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>|`Null`|Las barras de menús nunca tienen teclas de aceleración.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>|"Alt"|Al presionar la tecla Alt, el foco siempre debe pasar a la barra de menús de dentro de la aplicación.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los patrones de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir los controles de barra de menús. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Compatibilidad|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Depende|Si el control se puede expandir o contraer, implemente <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.|  
|<xref:System.Windows.Automation.Provider.IDockProvider>|Depende|Si el control se puede acoplar a diferentes partes de la pantalla, implemente <xref:System.Windows.Automation.Provider.IDockProvider>.|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|Depende|Si el control puede cambiar de tamaño, girarse o moverse, debe implementar <xref:System.Windows.Automation.Provider.ITransformProvider>.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir todos los controles de barra de menús. Para más información sobre eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico/valor|Notas|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Obligatorio|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Obligatorio|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Obligatorio|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Depende|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obligatorio|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|Ninguno|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.MenuBar>
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
