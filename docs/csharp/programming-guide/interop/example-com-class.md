---
title: 'Clase COM de ejemplo: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: 461d5a2afb197596c1c52daeeca0583b7b5e9693
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589141"
---
# <a name="example-com-class-c-programming-guide"></a>Clases COM de ejemplo (Guía de programación de C#)
El siguiente es un ejemplo de una clase que se expondría como un objeto COM. Una vez insertado este código de ejemplo en un archivo .cs y agregado al proyecto, establezca la propiedad **Registrar para interoperabilidad COM** en **True**. Para obtener más información, vea [Cómo: Registrar un componente para interoperabilidad COM](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).
  
 Exponer objetos de Visual C# para COM requiere declarar una interfaz de clase, una interfaz de eventos si es necesario y la propia clase. Los miembros de clase deben seguir estas reglas para que sean visibles en COM:  
  
- La clase debe ser pública.  
  
- Las propiedades, métodos y eventos deben ser públicos.  
  
- Las propiedades y métodos deben declararse en la interfaz de clase.  
  
- Los eventos deben declararse en la interfaz de eventos.  
  
 Los demás miembros públicos de la clase que no se declaren en estas interfaces no serán visibles para COM, pero lo serán para el resto de objetos de .NET Framework.  
  
 Para exponer propiedades y métodos en COM, se deben declarar en la interfaz de clase y marcar con el atributo `DispId`, e implementarlos en la clase. El orden en que se declaran los miembros en la interfaz es el orden usado para la tabla virtual de COM.  
  
 Para exponer los eventos de la clase, se deben declarar en la interfaz de eventos y marcarlos con un atributo `DispId`. La clase no debe implementar esta interfaz.  
  
 La clase implementa la interfaz de clase y puede implementar más de una interfaz, pero la primera implementación debe ser la interfaz de clase predeterminada. Implemente los métodos y propiedades expuestos para COM aquí. Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de clase. Asimismo, declare los eventos iniciados por la clase aquí. Deben marcarse como públicos y coincidir con las declaraciones de la interfaz de eventos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideInterop#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/ExampleCOM.cs#8)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Interoperabilidad](./index.md)
- [Página Compilar (Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)
