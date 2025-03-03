---
title: Me, My, MyBase y MyClass
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347338"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase y MyClass en Visual Basic
`Me`, `My`, `MyBase`y `MyClass` en Visual Basic tienen nombres similares, pero con fines diferentes. En este tema se describe cada una de estas entidades con el fin de distinguirlas.  
  
## <a name="me"></a>Me  
 La palabra clave `Me` proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que se está ejecutando el código. `Me` se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual. El uso de `Me` es especialmente útil para pasar información sobre la instancia que se está ejecutando actualmente de una clase o estructura a un procedimiento de otra clase, estructura o módulo.  
  
 Por ejemplo, supongamos que tiene el siguiente procedimiento en un módulo.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Puede llamar a este procedimiento y pasar la instancia actual de la clase <xref:System.Windows.Forms.Form> como argumento mediante la siguiente instrucción.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 La característica `My` proporciona acceso sencillo e intuitivo a una serie de clases de .NET Framework, lo que permite al usuario de Visual Basic interactuar con el equipo, la aplicación, la configuración, los recursos, etc.  
  
## <a name="mybase"></a>MyBase  
 La palabra clave `MyBase` se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase` se usa normalmente para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada. `MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
## <a name="myclass"></a>MyClass  
 La palabra clave `MyClass` se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementó originalmente. `MyClass` es similar a `Me`, pero todas las llamadas al método en él se tratan como si se `NotOverridable`el método.  
  
## <a name="see-also"></a>Vea también

- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
