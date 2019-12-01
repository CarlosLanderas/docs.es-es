---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643848"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a><span data-ttu-id="66578-101">Cambio de `Control.DefaultFont` a `Segoe UI 9pt`</span><span class="sxs-lookup"><span data-stu-id="66578-101">`Control.DefaultFont` changed to `Segoe UI 9pt`</span></span>

#### <a name="change-description"></a><span data-ttu-id="66578-102">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="66578-102">Change description</span></span>

<span data-ttu-id="66578-103">En .NET Framework, la propiedad <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> se estableció en `Microsoft Sans Serif 8pt`.</span><span class="sxs-lookup"><span data-stu-id="66578-103">In the .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="66578-104">En la figura siguiente se muestra una ventana en la que se usa la fuente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="66578-104">The following figure shows a window that uses the default font.</span></span>

![fuente de control predeterminada en .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="66578-106">En .NET Core, a partir de .NET Core 3.0, se establece en `Segoe UI 9pt` (la misma fuente que <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="66578-106">In .NET Core starting with .NET Core 3.0, it is set to `Segoe UI 9pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="66578-107">Como resultado de este cambio, los formularios y controles tendrán un tamaño predeterminado aproximadamente un 27 % más grande para tener en cuenta el mayor tamaño de la nueva fuente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="66578-107">As a result of this change, forms and controls will be sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="66578-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="66578-108">For example:</span></span>

![fuente de control predeterminada en .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="66578-110">Este cambio se realizó para alinearse con las [directrices para la experiencia de usuario de Windows](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span><span class="sxs-lookup"><span data-stu-id="66578-110">This change was made to align with [Windows UX guidelines](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="66578-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="66578-111">Version introduced</span></span>

<span data-ttu-id="66578-112">3.0</span><span class="sxs-lookup"><span data-stu-id="66578-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="66578-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="66578-113">Recommended action</span></span>

<span data-ttu-id="66578-114">Debido al cambio en el tamaño de los formularios y controles, asegúrese de que la aplicación se representa correctamente.</span><span class="sxs-lookup"><span data-stu-id="66578-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="66578-115">Para conservar la fuente original, establezca la fuente predeterminada del formulario en `Microsoft Sans Serif 8pt`.</span><span class="sxs-lookup"><span data-stu-id="66578-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="66578-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="66578-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="66578-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="66578-117">Category</span></span>

- <span data-ttu-id="66578-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66578-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="66578-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="66578-119">Affected APIs</span></span>

<span data-ttu-id="66578-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="66578-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
