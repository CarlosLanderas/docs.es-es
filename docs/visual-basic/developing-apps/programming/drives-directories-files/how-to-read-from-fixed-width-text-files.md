---
title: Procedimiento para leer archivos de texto de ancho fijo
ms.date: 07/20/2015
helpviewer_keywords:
- fixed-width text file
- reading text files [Visual Basic], fixed-width
- files [Visual Basic], parsing
- text files [Visual Basic], tasks
- text files [Visual Basic], reading
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
ms.openlocfilehash: 3cea9bfe2388f0ca510b15cb020f899b81c4603c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74334620"
---
# <a name="how-to-read-from-fixed-width-text-files-in-visual-basic"></a>Cómo: Leer archivos de texto de ancho fijo en Visual Basic

El objeto `TextFieldParser` proporciona una manera fácil y eficaz de analizar archivos de texto estructurados, como registros.  
  
 La propiedad `TextFieldType` define si el archivo analizado se trata de un archivo delimitado o uno que tiene campos de texto de ancho fijo. En un archivo de texto de ancho fijo, el campo puede tener un ancho variable al final. Para especificar que el campo tiene un ancho variable al final, debe definirlo para que tenga un ancho menor o igual que cero.  
  
### <a name="to-parse-a-fixed-width-text-file"></a>Para analizar un archivo de texto de ancho fijo  
  
1. Cree un nuevo objeto `TextFieldParser`. El código siguiente crea el `TextFieldParser` denominado `Reader` y abre el archivo `test.log`.  
  
     [!code-vb[VbFileIORead#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#9)]  
  
2. Defina la propiedad `TextFieldType` como `FixedWidth` definiendo el ancho y el formato. El código siguiente define las columnas de texto; la primera tiene un ancho de 5 caracteres, la segunda de 10, la tercera de 11 y la cuarta es de ancho variable.  
  
     [!code-vb[VbFileIORead#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#10)]  
  
3. Recorra en bucle los campos del archivo. Si alguna línea está dañada, cree un informe de error y continúe el análisis.  
  
     [!code-vb[VbFileIORead#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#11)]  
  
4. Cierre los bloques `While` y `Using` con `End While` y `End Using`.  
  
     [!code-vb[VbFileIORead#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#12)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se lee el archivo `test.log`.  
  
 [!code-vb[VbFileIORead#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIORead/VB/Class1.vb#13)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- No se puede analizar una fila utilizando el formato especificado (<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>). El mensaje de excepción especifica la línea que produce la excepción y la propiedad <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> se asigna al texto contenido en la línea.  
  
- El archivo especificado no existe (<xref:System.IO.FileNotFoundException>).  
  
- Una situación de confianza parcial en la que el usuario no tiene los permisos necesarios para tener acceso al archivo. (<xref:System.Security.SecurityException>).  
  
- La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).  
  
- El usuario no tiene permisos suficientes para acceder al archivo (<xref:System.UnauthorizedAccessException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=nameWithType>
- [Cómo: Leer archivos de texto delimitado por comas](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [Cómo: Leer archivos de texto con varios formatos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [Análisis de archivos de texto con el objeto TextFieldParser](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [Tutorial: Manipulación de archivos y directorios en Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)
- [Solución de problemas: Leer y escribir en archivos de texto](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
