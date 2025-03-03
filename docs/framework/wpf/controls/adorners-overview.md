---
title: Información general sobre adornos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 22d9b1eddbb6db47fb15deebf94cfc5f8d37a380
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040846"
---
# <a name="adorners-overview"></a>Información general sobre adornos

Los adornos son un tipo especial de <xref:System.Windows.FrameworkElement>, que se usan para proporcionar indicaciones visuales a un usuario. Entre otros usos, los Adorners se pueden utilizar para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.

## <a name="about-adorners"></a>Acerca de Adorners

Un <xref:System.Windows.Documents.Adorner> es un <xref:System.Windows.FrameworkElement> personalizado que está enlazado a un <xref:System.Windows.UIElement>. Los adornos se representan en un <xref:System.Windows.Documents.AdornerLayer>, que es una superficie de representación que siempre está en la parte superior del elemento adornado o en una colección de elementos adornados. La representación de un adorno es independiente de la representación del <xref:System.Windows.UIElement> al que está enlazado el adorno. Un adorno se suele colocar respecto al elemento al que se enlaza, utilizando el origen de coordenadas 2D estándar situado en la parte superior izquierda del elemento adornado.

Algunas aplicaciones comunes de adornos son:

- Agregar manipuladores funcionales a un <xref:System.Windows.UIElement> que permiten a un usuario manipular el elemento de alguna manera (cambiar el tamaño, girar, cambiar de posición, etc.).
- Proporcionar comentarios visuales para indicar diversos estados, o en respuesta a distintos eventos.
- Superponer decoraciones visuales en un <xref:System.Windows.UIElement>.
- Enmascarar o invalidar visualmente una parte o la totalidad de un <xref:System.Windows.UIElement>.

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un marco básico para adornar elementos visuales. En la tabla siguiente se muestra una lista de los tipos principales utilizados al adornar objetos y su finalidad. A continuación se muestran varios ejemplos de uso:

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|Una clase base abstracta de la que heredan todas las implementaciones de adornos contextuales concretas.|
|<xref:System.Windows.Documents.AdornerLayer>|Una clase que representa una capa de representación para los adornos de uno o más elementos adornados.|
|<xref:System.Windows.Documents.AdornerDecorator>|Una clase que permite asociar una capa de adornos a una colección de elementos.|

## <a name="implementing-a-custom-adorner"></a>Implementación de un adorno personalizado

El marco de adornos que proporciona [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está diseñado principalmente para admitir la creación de adornos personalizados. Un adorno personalizado se crea implementando una clase que hereda de la clase <xref:System.Windows.Documents.Adorner> abstracta.

> [!NOTE]
> El objeto primario de una <xref:System.Windows.Documents.Adorner> es el <xref:System.Windows.Documents.AdornerLayer> que representa el <xref:System.Windows.Documents.Adorner>, no el elemento que se va a adornar.

En el ejemplo siguiente se muestra una clase que implementa un adorno simple. El adorno de ejemplo simplemente adorna las esquinas de un <xref:System.Windows.UIElement> con círculos.

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
En la imagen siguiente se muestra el adorno simplecircleadorner aplicado a un <xref:System.Windows.Controls.TextBox>:

![Captura de pantalla que muestra un cuadro de texto adornado.](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a>Comportamiento de representación de los adornos

Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno. Una manera común de implementar el comportamiento de representación es invalidar el método <xref:System.Windows.UIElement.OnRender%2A> y usar uno o varios objetos <xref:System.Windows.Media.DrawingContext> para representar los elementos visuales del adorno según sea necesario (como se muestra en el ejemplo anterior).

> [!NOTE]
> Todo aquello que se coloca en la capa de los adornos se representa encima del resto de estilos que se han establecido. En otras palabras, los adornos siempre están visualmente encima y no pueden invalidar utilizando el orden z.

## <a name="events-and-hit-testing"></a>Eventos y pruebas de posicionamiento

Los adornos reciben eventos de entrada como cualquier otro <xref:System.Windows.FrameworkElement>.  Dado que un adorno siempre tiene un orden z mayor que el elemento que adorna, el adorno recibe eventos de entrada (como <xref:System.Windows.UIElement.Drop> o <xref:System.Windows.UIElement.MouseMove>) que pueden estar destinados al elemento adornado subyacente.  Un adorno puede realizar escuchas para ciertos eventos de entrada y pasárselos al elemento adornado subyacente volviendo a provocar el evento.

Para habilitar la prueba de posicionamiento de paso a través de los elementos de un adorno, establezca la propiedad <xref:System.Windows.UIElement.IsHitTestVisible%2A> de la prueba de posicionamiento en **false** en el adorno.  Para obtener más información sobre las pruebas de posicionamiento, vea [pruebas de posicionamiento en la capa visual](../graphics-multimedia/hit-testing-in-the-visual-layer.md).

## <a name="adorning-a-single-uielement"></a>Adorno de un solo elemento de la interfaz de usuario

Para enlazar un adorno a un <xref:System.Windows.UIElement>determinado, siga estos pasos:

1. Llame al método estático <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para obtener un objeto <xref:System.Windows.Documents.AdornerLayer> para el <xref:System.Windows.UIElement> que se va a adornar. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> recorre el árbol visual, comenzando en el <xref:System.Windows.UIElement>especificado, y devuelve la primera capa de adornos que encuentra. (Si no se encuentra ninguna capa de adornos, el método devuelve null).

2. Llame al método <xref:System.Windows.Documents.AdornerLayer.Add%2A> para enlazar el adorno al <xref:System.Windows.UIElement>de destino.

 En el ejemplo siguiente se enlaza un adorno simplecircleadorner (mostrado anteriormente) a una <xref:System.Windows.Controls.TextBox> denominada *mytextbox*:

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> En la actualidad, no se admite el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para enlazar un adorno a otro elemento.

## <a name="adorning-the-children-of-a-panel"></a>Adornamiento de elementos secundarios de un panel

Para enlazar un adorno a los elementos secundarios de un <xref:System.Windows.Controls.Panel>, siga estos pasos:

1. Llame al método `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> para buscar una capa de adornos para el elemento cuyos elementos secundarios se van a adornar.

2. Enumere los elementos secundarios del elemento primario y llame al método <xref:System.Windows.Documents.AdornerLayer.Add%2A> para enlazar un adorno a cada elemento secundario.

En el ejemplo siguiente se enlaza un adorno simplecircleadorner (mostrado anteriormente) a los elementos secundarios de una <xref:System.Windows.Controls.StackPanel> denominada *myStackPanel*:

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.AdornerHitTestResult>
- [Información general sobre formas y dibujo básico en WPF](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Información general sobre objetos Drawing](../graphics-multimedia/drawing-objects-overview.md)
- [Temas "Cómo..."](adorners-how-to-topics.md)
