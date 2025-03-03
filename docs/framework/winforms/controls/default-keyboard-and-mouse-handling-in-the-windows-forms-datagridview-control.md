---
title: Control de teclado y mouse predeterminado en el control DataGridView Windows Forms
ms.date: 02/13/2018
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
ms.openlocfilehash: 97b8c8c3e418586bbc0053c358a2924484115a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969128"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Control de teclado y mouse predeterminado en el control DataGridView Windows Forms

En las tablas siguientes se describe cómo los usuarios pueden <xref:System.Windows.Forms.DataGridView> interactuar con el control mediante un teclado y un mouse.  
  
> [!NOTE]
> Para personalizar el comportamiento del teclado, puede controlar eventos de teclado estándar <xref:System.Windows.Forms.Control.KeyDown>como. En el modo de edición, sin embargo, el control de edición hospedado recibe la entrada del teclado y los eventos <xref:System.Windows.Forms.DataGridView> de teclado no se producen para el control. Para controlar los eventos de control de edición, adjunte los controladores al control de <xref:System.Windows.Forms.DataGridView.EditingControlShowing> edición en un controlador de eventos. Como alternativa, puede personalizar el comportamiento del teclado en <xref:System.Windows.Forms.DataGridView> una subclase invalidando <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> los <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> métodos y.  
  
## <a name="default-keyboard-handling"></a>Control de teclado predeterminado  
  
### <a name="basic-navigation-and-entry-keys"></a>Teclas de navegación y de entrada básicas  
  
|Tecla o combinación de teclas|DESCRIPCIÓN|  
|----------------------------|-----------------|  
|FLECHA ABAJO|Mueve el foco a la celda que se encuentra justo debajo de la celda actual. Si el foco está en la última fila, no hace nada.|  
|FLECHA IZQUIERDA|Mueve el foco a la celda anterior de la fila. Si el foco está en la primera celda de la fila, no hace nada.|  
|FLECHA DERECHA|Mueve el foco a la siguiente celda de la fila. Si el foco está en la última celda de la fila, no hace nada.|  
|FLECHA ARRIBA|Mueve el foco a la celda directamente encima de la celda actual. Si el foco está en la primera fila, no hace nada.|  
|INICIO|Mueve el foco a la primera celda de la fila actual.|  
|FIN|Mueve el foco a la última celda de la fila actual.|  
|AV PÁG|Desplaza el control hacia abajo por el número de filas que se muestran por completo. Mueve el foco a la última fila que se muestra completamente sin cambiar las columnas.|  
|RE PÁG|Desplaza el control hacia arriba el número de filas que se muestran completamente. Mueve el foco a la primera fila mostrada sin cambiar las columnas.|  
|TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `false`propiedad es, mueve el foco a la siguiente celda de la fila actual. Si el foco ya está en la última celda de la fila, mueve el foco a la primera celda de la fila siguiente. Si el foco está en la última celda del control, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `true`propiedad es, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.|  
|MAYÚS+TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `false`propiedad es, mueve el foco a la celda anterior de la fila actual. Si el foco ya está en la primera celda de la fila, mueve el foco a la última celda de la fila anterior. Si el foco está en la primera celda del control, mueve el foco al control anterior en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `true`propiedad es, mueve el foco al control anterior en el orden de tabulación del contenedor primario.|  
|CTRL+TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `false`propiedad es, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `true`propiedad es, mueve el foco a la siguiente celda de la fila actual. Si el foco ya está en la última celda de la fila, mueve el foco a la primera celda de la fila siguiente. Si el foco está en la última celda del control, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.|  
|CTRL+MAYÚS+TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `false`propiedad es, mueve el foco al control anterior en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valor de la `true`propiedad es, mueve el foco a la celda anterior de la fila actual. Si el foco ya está en la primera celda de la fila, mueve el foco a la última celda de la fila anterior. Si el foco está en la primera celda del control, mueve el foco al control anterior en el orden de tabulación del contenedor primario.|  
|CTRL + FLECHA|Mueve el foco a la celda más alejada en la dirección de la flecha.|  
|CTRL + INICIO|Mueve el foco a la primera celda del control.|  
|CTRL + FIN|Mueve el foco a la última celda del control.|  
|CTRL + AV PÁG/ARRIBA|Igual que Re Pág o re pág.|  
|F2|Pone la celda actual en modo de edición de celda <xref:System.Windows.Forms.DataGridView.EditMode%2A> si el valor <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> de <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>la propiedad es o.|
|F3|Ordena la columna actual si el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> valor de la <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>propiedad es. Es lo mismo que hacer clic en el encabezado de columna actual. Disponible desde .NET Framework 4.7.2. Para habilitar esta característica, las aplicaciones deben tener como destino .NET Framework 4.7.2 o versiones posteriores, o bien participar explícitamente en las mejoras de accesibilidad con los modificadores de AppContext.|  
|F4|Si la celda actual es un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, coloca la celda en modo de edición y muestra la lista desplegable.|  
|ALT + FLECHA ARRIBA/FLECHA ABAJO|Si la celda actual es un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, coloca la celda en modo de edición y muestra la lista desplegable.|  
|Barra espaciadora|Si la celda actual es <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>o <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, genera los <xref:System.Windows.Forms.DataGridView.CellClick> eventos y <xref:System.Windows.Forms.DataGridView.CellContentClick> . Si la celda actual es un <xref:System.Windows.Forms.DataGridViewButtonCell>, también presiona el botón. Si la celda actual es un <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, cambia también el estado de activación.|  
|ENTRAR|Confirma los cambios realizados en la celda y la fila actuales, y mueve el foco a la celda directamente debajo de la celda actual. Si el foco está en la última fila, confirma cualquier cambio sin mover el foco.|  
|ESC|Si el control está en modo de edición, cancela la edición. Si el control no está en modo de edición, revierte los cambios realizados en la fila actual si el control está enlazado a un origen de datos que admite la edición o el modo virtual se ha implementado con el ámbito de confirmación de nivel de fila.|  
|RETROCESO|Elimina el carácter situado delante del punto de inserción al editar una celda.|  
|SUPRIMIR|Elimina el carácter situado después del punto de inserción al editar una celda.|  
|CTRL+ENTRAR|Confirma los cambios realizados en la celda actual sin mover el foco. También confirma los cambios realizados en la fila actual si el control está enlazado a un origen de datos que admite la edición o el modo virtual se ha implementado con el ámbito de confirmación de nivel de fila.|  
|CTRL+0|Escribe un <xref:System.DBNull.Value?displayProperty=nameWithType> valor en la celda actual si se puede editar la celda. De forma predeterminada, el valor de presentación <xref:System.DBNull> de un valor de celda es el <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> valor de la <xref:System.Windows.Forms.DataGridViewCellStyle> propiedad del efecto para la celda actual.|  
  
### <a name="selection-keys"></a>Teclas de selección

 Si la <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad se establece en `false` y la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, el cambio de la celda actual mediante las teclas de navegación cambia la selección a la nueva celda. Las teclas Mayús, CTRL y ALT no afectan a este comportamiento.  
  
 Si se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, se produce el mismo comportamiento, pero con las siguientes adiciones. <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
  
|Tecla o combinación de teclas|DESCRIPCIÓN|  
|----------------------------|-----------------|  
|MAYÚS + BARRA ESPACIADORA|Selecciona la fila o columna completa (lo mismo que hacer clic en el encabezado de fila o de columna).|  
|tecla de navegación (tecla de dirección, RE PÁG/AV PÁG, Inicio, fin)|Si se selecciona una fila o columna completa, al cambiar la celda actual a una nueva fila o columna, la selección se mueve a la nueva fila o columna completa (según el modo de selección).|  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecido en `false` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, al cambiar la celda actual a una nueva fila o columna mediante el teclado, la selección se mueve a la nueva fila o columna completa. Las teclas Mayús, CTRL y ALT no afectan a este comportamiento.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true`, el comportamiento de navegación no cambia, pero la navegación con el teclado mientras se presiona la tecla Mayús (incluido Ctrl + Mayús) modificará una selección de varias celdas. Antes de que comience la navegación, el control marca la celda actual como una celda de delimitador. Al navegar mientras se presiona la tecla Mayús, la selección incluye todas las celdas entre la celda delimitadora y la celda actual. Otras celdas del control permanecerán seleccionadas si ya estaban seleccionadas, pero se pueden anular la selección si la navegación del teclado las coloca temporalmente entre la celda del delimitador y la celda actual.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecido en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, el comportamiento de la celda del delimitador y la celda actual es el mismo, pero solo se seleccionan o anulan la selección de las filas o columnas completas.  
  
## <a name="default-mouse-handling"></a>Control del mouse predeterminado
  
### <a name="basic-mouse-handling"></a>Control básico del mouse
  
> [!NOTE]
> Al hacer clic en una celda con el botón primario del mouse, siempre cambia la celda actual. Al hacer clic en una celda con el botón secundario del mouse, se abre un menú contextual, cuando está disponible.  
  
|Acción del mouse|DESCRIPCIÓN|  
|------------------|-----------------|  
|Botón primario del mouse hacia abajo|Convierte la celda en la que se hace clic en la celda <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> actual y genera el evento.|  
|Botón primario del mouse hacia arriba|Genera el evento <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Clic con el botón primario del mouse|Genera los <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> eventos <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> y.|  
|Presionar el botón primario del mouse y arrastrar en una celda de encabezado de columna|Si la <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> propiedad es `true`, mueve la columna para que se pueda colocar en una nueva posición.|  
  
### <a name="mouse-selection"></a>Selección del mouse

 No se asocia ningún comportamiento de selección con el botón central del mouse o la rueda del mouse.  
  
 Si la <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad se establece en `false` y la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, se produce el comportamiento siguiente.  
  
|Acción del mouse|DESCRIPCIÓN|  
|------------------|-----------------|  
|Hacer clic con el botón primario del mouse|Selecciona solo la celda actual si el usuario hace clic en una celda. No hay ningún comportamiento de selección si el usuario hace clic en un encabezado de fila o de columna.|  
|Hacer clic con el botón secundario del mouse|Muestra un menú contextual si hay uno disponible.|  
  
 El mismo comportamiento se produce cuando <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, salvo que, en función del modo de selección, al hacer clic en un encabezado de fila o de columna, se selecciona la fila o columna completa y se establece la celda actual en la primera celda de la fila o columna.  
  
 Si <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, al hacer clic en cualquier celda de una fila o columna, se seleccionará la fila o columna completa.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true`, al hacer clic en una celda mientras se presiona Ctrl o Mayús se modificará una selección de varias celdas.  
  
 Al hacer clic en una celda mientras se presiona CTRL, la celda cambiará su estado de selección mientras todas las demás celdas conservan su estado de selección actual.  
  
 Al hacer clic en una celda o en una serie de celdas mientras se presiona la tecla Mayús, la selección incluye todas las celdas entre la celda actual y una celda de delimitación situada en la posición de la celda actual antes del primer clic. Al hacer clic y arrastrar el puntero por varias celdas, la celda del delimitador es la celda en la que se hace clic al principio de la operación de arrastre. Los clics posteriores mientras presiona Mayús cambian la celda actual, pero no la celda del delimitador. Otras celdas del control permanecerán seleccionadas si ya estaban seleccionadas, pero se pueden anular la selección si la navegación del mouse las coloca temporalmente entre la celda del delimitador y la celda actual.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecido en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, al hacer clic en un encabezado de fila o de columna (dependiendo del modo de selección) mientras se presiona Mayús, se modificará una selección existente de filas o columnas completas si tal la selección existe. De lo contrario, se borrará la selección y se iniciará una nueva selección de filas o columnas completas. Sin embargo, al hacer clic en un encabezado de fila o de columna, se agregará o quitará la fila o columna en la selección actual sin modificar de otra forma la selección actual.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, al hacer clic en una celda mientras se presiona Mayús o Ctrl se comporta de la misma manera, salvo que solo se ven afectadas las filas y columnas completas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView (control)](datagridview-control-windows-forms.md)
