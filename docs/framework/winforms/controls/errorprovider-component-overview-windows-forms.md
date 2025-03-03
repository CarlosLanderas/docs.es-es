---
title: Información general del componente ErrorProvider (Formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 3cfd3f306d4a18ce8a194b5197060fbca1d157d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965289"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Información general del componente ErrorProvider (Formularios Windows Forms)
El componente Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) se usa para validar los datos proporcionados por el usuario en un formulario o control. Normalmente se utiliza junto con la validación de la entrada del usuario en un formulario o la visualización de errores dentro de un conjunto de datos. Un proveedor de errores es una alternativa mejor que mostrar un mensaje de error en un cuadro de mensaje, ya que una vez que se descarta un cuadro de mensaje, el mensaje de error ya no está visible. El <xref:System.Windows.Forms.ErrorProvider> componente muestra un icono de error![(un signo de exclamación blanco](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)dentro de un círculo rojo) al lado del control correspondiente, como un cuadro de texto; cuando el usuario coloca el puntero del mouse sobre el icono de error, aparece una información sobre herramientas. que muestra la cadena del mensaje de error.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las <xref:System.Windows.Forms.ErrorProvider> propiedades clave del componente son <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>y <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Al usar <xref:System.Windows.Forms.ErrorProvider> un componente con controles enlazados a datos <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> , la propiedad debe establecerse en el contenedor adecuado (normalmente Windows Forms) para que el componente muestre un icono de error en el formulario. Cuando el componente se agrega en el diseñador, la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad se establece en el formulario que lo contiene; si agrega el control en el código, debe establecerlo por sí mismo.  
  
 La <xref:System.Windows.Forms.ErrorProvider.Icon%2A> propiedad se puede establecer en un icono de error personalizado en lugar del valor predeterminado. Cuando se <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> establece la propiedad, el <xref:System.Windows.Forms.ErrorProvider> componente puede mostrar mensajes de error para un conjunto de información. El método clave del <xref:System.Windows.Forms.ErrorProvider> componente es el <xref:System.Windows.Forms.ErrorProvider.SetError%2A> método, que especifica la cadena del mensaje de error y dónde debe aparecer el icono de error.  
  
> [!NOTE]
> El <xref:System.Windows.Forms.ErrorProvider> componente no proporciona compatibilidad integrada para los clientes de accesibilidad. Para que la aplicación sea accesible al usar este componente, debe proporcionar un mecanismo de comentarios adicional y accesible.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ErrorProvider>
- [Procedimientos: Ver los errores dentro de un conjunto de DataSet con el componente ErrorProvider Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Procedimientos: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)
