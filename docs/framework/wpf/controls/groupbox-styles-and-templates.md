---
title: Estilos y plantillas de GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: e5befffc86f26176da4accfc01239a08d4978713
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283762"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="d6abe-102">Estilos y plantillas de GroupBox</span><span class="sxs-lookup"><span data-stu-id="d6abe-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="d6abe-103">En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="d6abe-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="d6abe-104">Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única.</span><span class="sxs-lookup"><span data-stu-id="d6abe-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d6abe-105">Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="d6abe-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="d6abe-106">Elementos GroupBox</span><span class="sxs-lookup"><span data-stu-id="d6abe-106">GroupBox Parts</span></span>  
 <span data-ttu-id="d6abe-107">El control <xref:System.Windows.Controls.GroupBox> no tiene ninguna parte con nombre.</span><span class="sxs-lookup"><span data-stu-id="d6abe-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="d6abe-108">Estados de GroupBox</span><span class="sxs-lookup"><span data-stu-id="d6abe-108">GroupBox States</span></span>  
 <span data-ttu-id="d6abe-109">En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="d6abe-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="d6abe-110">Nombre de VisualState</span><span class="sxs-lookup"><span data-stu-id="d6abe-110">VisualState Name</span></span>|<span data-ttu-id="d6abe-111">Nombre de VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d6abe-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d6abe-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6abe-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d6abe-113">Válido</span><span class="sxs-lookup"><span data-stu-id="d6abe-113">Valid</span></span>|<span data-ttu-id="d6abe-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d6abe-114">ValidationStates</span></span>|<span data-ttu-id="d6abe-115">El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.</span><span class="sxs-lookup"><span data-stu-id="d6abe-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d6abe-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d6abe-116">InvalidFocused</span></span>|<span data-ttu-id="d6abe-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d6abe-117">ValidationStates</span></span>|<span data-ttu-id="d6abe-118">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d6abe-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d6abe-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d6abe-119">InvalidUnfocused</span></span>|<span data-ttu-id="d6abe-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d6abe-120">ValidationStates</span></span>|<span data-ttu-id="d6abe-121">La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="d6abe-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="d6abe-122">Ejemplo de ControlTemplate de GroupBox</span><span class="sxs-lookup"><span data-stu-id="d6abe-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="d6abe-123">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="d6abe-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="d6abe-124">El <xref:System.Windows.Controls.ControlTemplate> usa uno o varios de los siguientes recursos.</span><span class="sxs-lookup"><span data-stu-id="d6abe-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d6abe-125">Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d6abe-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6abe-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6abe-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d6abe-127">Estilos y plantillas de controles</span><span class="sxs-lookup"><span data-stu-id="d6abe-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- <span data-ttu-id="d6abe-128">[Control Customization](control-customization.md) (Personalización de controles)</span><span class="sxs-lookup"><span data-stu-id="d6abe-128">[Control Customization](control-customization.md)</span></span>
- [<span data-ttu-id="d6abe-129">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="d6abe-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d6abe-130">Crear una plantilla para un control</span><span class="sxs-lookup"><span data-stu-id="d6abe-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
