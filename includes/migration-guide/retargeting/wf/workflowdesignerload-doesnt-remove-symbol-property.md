---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804639"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>El método WorkflowDesigner.Load no elimina una propiedad de símbolo

|   |   |
|---|---|
|Detalles|Al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo y cargar un flujo de trabajo de la versión 3.5 rehospedado con el método <xref:System.Activities.Presentation.WorkflowDesigner.Load>, se inicia una excepción <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> mientras se guarda el flujo de trabajo.|
|Sugerencia|Este error solo se manifiesta al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo, por lo que una solución alternativa consiste en establecer <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> en la versión 4.0 de .NET Framework. Como alternativa, el problema se puede solucionar si se usa el método <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> para cargar el flujo de trabajo, en lugar de <xref:System.Activities.Presentation.WorkflowDesigner.Load>.|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

