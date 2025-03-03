---
title: Procedimiento Dibujar texto en un elemento visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963841"
---
# <a name="how-to-draw-text-to-a-visual"></a>Procedimiento Dibujar texto en un elemento visual
En el ejemplo siguiente se muestra cómo dibujar texto en <xref:System.Windows.Media.DrawingVisual> mediante un <xref:System.Windows.Media.DrawingContext> objeto. Un contexto de dibujo se devuelve mediante una <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> llamada al método <xref:System.Windows.Media.DrawingVisual> de un objeto. Puede dibujar gráficos y texto en un contexto de dibujo.  
  
 Para dibujar texto en el contexto del dibujo, use <xref:System.Windows.Media.DrawingContext.DrawText%2A> el método de <xref:System.Windows.Media.DrawingContext> un objeto. Cuando haya terminado de dibujar el contenido en el contexto del dibujo, <xref:System.Windows.Media.DrawingContext.Close%2A> llame al método para cerrar el contexto del dibujo y conservar el contenido.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> Para obtener el código completo del que se ha extraído el ejemplo de código anterior, vea [Ejemplo Hit Test Using DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).
