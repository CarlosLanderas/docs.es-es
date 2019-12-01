---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643902"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="d362f-101">No se admite el modificador de compatibilidad Switch.System.Windows.Forms.EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="d362f-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="d362f-102">No se admite el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` en Windows Forms en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d362f-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d362f-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d362f-103">Change description</span></span>

<span data-ttu-id="d362f-104">En .NET Framework, el modificador de compatibilidad `Switch.System.Windows.Forms.EnableVisualStyleValidation` permitía que una aplicación rechazara la validación de los estilos visuales proporcionados en un formato numérico.</span><span class="sxs-lookup"><span data-stu-id="d362f-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="d362f-105">En .NET Core, no se admite el modificador `Switch.System.Windows.Forms.EnableVisualStyleValidation`.</span><span class="sxs-lookup"><span data-stu-id="d362f-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d362f-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d362f-106">Version introduced</span></span>

<span data-ttu-id="d362f-107">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="d362f-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d362f-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d362f-108">Recommended action</span></span>

<span data-ttu-id="d362f-109">Quite el modificador.</span><span class="sxs-lookup"><span data-stu-id="d362f-109">Remove the switch.</span></span> <span data-ttu-id="d362f-110">No se admite el modificador y no hay ninguna funcionalidad alternativa disponible.</span><span class="sxs-lookup"><span data-stu-id="d362f-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d362f-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="d362f-111">Category</span></span>

<span data-ttu-id="d362f-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d362f-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d362f-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d362f-113">Affected APIs</span></span>

- <span data-ttu-id="d362f-114">None</span><span class="sxs-lookup"><span data-stu-id="d362f-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
