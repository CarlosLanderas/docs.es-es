---
title: Procedimiento para leer texto de archivos con StreamReader
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 572463d1f03d768fb133f2dac59b012051f053bb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74334563"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>Procedimiento para leer texto de archivos con StreamReader (Visual Basic)

El objeto `My.Computer.FileSystem` proporciona métodos para abrir un <xref:System.IO.TextReader> y un <xref:System.IO.TextWriter>. Estos métodos, `OpenTextFileWriter` y `OpenTextFileReader`, son métodos avanzados que no aparecen en IntelliSense a menos que seleccione la pestaña **Todos**.  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>Para leer una línea de un archivo con un lector de texto  
  
- Use el método `OpenTextFileReader` para abrir el <xref:System.IO.TextReader>, especificando el archivo. En este ejemplo se abre el archivo denominado `testfile.txt`, lee una línea del mismo y la muestra en un cuadro de mensajes.  
  
     [!code-vb[VbFileIORead#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  

 El archivo que se lee debe ser un archivo de texto.  
  
 No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.  
  
 Compruebe todas las entradas antes de utilizar los datos en la aplicación. Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Para leer un archivo, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.FileIOPermission>. Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código). El usuario también necesita acceso al archivo. Para obtener más información, vea [Información general sobre la tecnología ACL](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [SaveFileDialog (componente)](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [Leer archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
