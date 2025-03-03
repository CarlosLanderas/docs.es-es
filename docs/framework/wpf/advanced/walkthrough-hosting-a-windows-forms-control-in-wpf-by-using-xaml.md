---
title: 'Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 3b4b743b07876f240366b2d2d19667405941a40b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976541"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona numerosos controles con un conjunto de características enriquecidas. Sin embargo, a veces es posible que desee usar controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en las páginas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Por ejemplo, puede tener una inversión sustancial en los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] existentes o puede tener un control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que proporcione una funcionalidad única.  
  
 En este tutorial se muestra cómo hospedar un control de Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Para obtener una lista de código completa de las tareas que se muestran en este tutorial, vea [hospedar un control de Windows Forms en WPF mediante el ejemplo de XAML](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).
  
## <a name="prerequisites"></a>Requisitos previos  

Necesita Visual Studio para completar este tutorial.  
  
## <a name="hosting-the-windows-forms-control"></a>Hospedar el control de Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Para hospedar el control MaskedTextBox  
  
1. Cree un proyecto de aplicación de WPF denominado `HostingWfInWpfWithXaml`.  
  
2. Agregue referencias a los ensamblados siguientes.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. Abra MainWindow. XAML en el diseñador de WPF.  
  
4. En el elemento <xref:System.Windows.Window>, agregue la siguiente asignación de espacio de nombres. La asignación del espacio de nombres `wf` establece una referencia al ensamblado que contiene el control Windows Forms.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. En el elemento <xref:System.Windows.Controls.Grid>, agregue el siguiente código XAML.  
  
     El control <xref:System.Windows.Forms.MaskedTextBox> se crea como un elemento secundario del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. Presione F5 para compilar y ejecutar la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controles de Windows Forms y controles equivalentes de WPF](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hospedar un control de Windows Forms en WPF mediante el ejemplo de XAML](https://go.microsoft.com/fwlink/?LinkID=160000)
