---
title: 'Comentarios de documentación XML: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: 6405b094ccc50499bfeb4db4522f0ec9b01f68ad
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523485"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Comentarios de documentación XML (Guía de programación de C#)
En Visual C# puede crear documentación para el código incluyendo elementos XML en campos de comentario especiales (se indica con barras diagonales triples) en el código fuente directamente delante del bloque de código al que hacen referencia los comentarios, por ejemplo:  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 Cuando se compila con la opción [-doc](../../language-reference/compiler-options/doc-compiler-option.md), el compilador buscará todas las etiquetas XML en el código fuente y creará un archivo de documentación XML. Para crear la documentación final basada en el archivo generado por el compilador, puede crear una herramienta personalizada o usar una herramienta como [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).  
  
 Para hacer referencia a elementos XML (por ejemplo, la función procesa los elementos XML concretos que desea describir en un comentario de documentación XML), puede usar el mecanismo de entrecomillado estándar (`<` y `>`).  Para hacer referencia a identificadores genéricos en elementos de referencia de código (`cref`), puede usar los caracteres de escape (por ejemplo, `cref="List&lt;T&gt;"`) o llaves (`cref="List{T}"`).  Como caso especial, el compilador analiza las llaves como corchetes angulares para que la creación del comentario de documentación resulte menos complicada al hacer referencia a identificadores genéricos.  
  
> [!NOTE]
> Los comentarios de documentación XML no son metadatos; no se incluyen en el ensamblado compilado y, por tanto, no se puede obtener acceso a ellos mediante reflexión.  
  
## <a name="in-this-section"></a>En esta sección  
  
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)  
  
- [Procesamiento del archivo XML](./processing-the-xml-file.md)  
  
- [Delimitadores para etiquetas de documentación](./delimiters-for-documentation-tags.md)  
  
- [Cómo: Usar las características de documentación XML](./how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información, consulte:  
  
- [-doc (Procesamiento de comentarios de documentación)](../../language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
