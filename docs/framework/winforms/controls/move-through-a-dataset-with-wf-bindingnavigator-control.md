---
title: Procedimiento para desplazarse por un conjunto de datos con el control BindingNavigator de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: d33cad4d0a60aa29d8c9f5e2217532963e8358c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952695"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a>Procedimiento para desplazarse por un conjunto de datos con el control BindingNavigator de Windows Forms
Al crear aplicaciones controladas por datos, a menudo necesitará mostrar colecciones de datos a los usuarios. El control <xref:System.Windows.Forms.BindingNavigator>, junto con el componente <xref:System.Windows.Forms.BindingSource>, proporciona una solución cómoda y extensible para desplazarse por una colección y mostrar sus elementos secuencialmente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, se muestra cómo usar el control <xref:System.Windows.Forms.BindingNavigator> para desplazarse por los datos. El conjunto está contenido en un <xref:System.Data.DataView>, que enlaza a un control <xref:System.Windows.Forms.TextBox> con un componente <xref:System.Windows.Forms.BindingSource>.  
  
> [!NOTE]
> Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación. El uso de la autenticación de Windows (también conocida como seguridad integrada) es un modo más seguro de controlar el acceso a una base de datos. Para más información, consulte [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.Xml.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingNavigator (control)](bindingnavigator-control-windows-forms.md)
- [Componente BindingSource](bindingsource-component.md)
- [Procedimientos: Enlazar un control de Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
