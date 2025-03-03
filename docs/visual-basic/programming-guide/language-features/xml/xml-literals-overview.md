---
title: Información general sobre literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: e5d2465d145f4059600121c6cef30bb2c74a8c1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346200"
---
# <a name="xml-literals-overview-visual-basic"></a>Información general sobre literales XML (Visual Basic)
Un *literal XML* permite incorporar XML directamente en el código de Visual Basic. La sintaxis de los literales XML representa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos y es similar a la sintaxis de XML 1,0. De este modo, resulta más fácil crear elementos y documentos XML mediante programación, ya que el código tiene la misma estructura que el XML final.  
  
 Visual Basic compila literales XML en objetos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona un modelo de objetos simple para crear y manipular XML, y este modelo se integra bien con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.  
  
 Puede incrustar una expresión de Visual Basic en un literal XML. En tiempo de ejecución, la aplicación crea un objeto [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para cada literal, incorporando los valores de las expresiones incrustadas. Esto le permite especificar contenido dinámico dentro de un literal XML. Para obtener más información, vea [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Para obtener más información sobre las diferencias entre la sintaxis de literales XML y la sintaxis de XML 1,0, vea [literales XML y la especificación xml 1,0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Literales simples  
 Puede crear un objeto de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] en el código Visual Basic escribiendo o pegando XML válido. Un literal de elemento XML devuelve un objeto <xref:System.Xml.Linq.XElement>. Para obtener más información, vea [literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [literales XML y la especificación XML 1,0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). En el ejemplo siguiente se crea un elemento XML que tiene varios elementos secundarios.  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 Puede crear un documento XML iniciando un literal XML con `<?xml version="1.0"?>`, como se muestra en el ejemplo siguiente. Un literal de documento XML devuelve un objeto <xref:System.Xml.Linq.XDocument>. Para obtener más información, vea [literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
> La sintaxis de los literales XML de Visual Basic no es idéntica a la sintaxis de la especificación XML 1,0. Para obtener más información, vea [literales XML y la especificación xml 1,0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Continuación de línea  
 Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea (la secuencia Space-subrayado-entrar). Esto facilita la comparación de los literales XML en el código con documentos XML.  
  
 El compilador trata los caracteres de continuación de línea como parte de un literal XML. Por lo tanto, debe usar la secuencia Space-subrayate-Enter solo cuando pertenezca al objeto [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Sin embargo, se necesitan caracteres de continuación de línea si tiene una expresión de varias líneas en una expresión incrustada. Para obtener más información, vea [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Incrustar consultas en literales XML  
 Puede utilizar una consulta en una expresión incrustada. Al hacerlo, los elementos devueltos por la consulta se agregan al elemento XML. Esto le permite agregar contenido dinámico, como el resultado de la consulta de un usuario, a un literal XML.  
  
 Por ejemplo, el código siguiente utiliza una consulta incrustada para crear elementos XML a partir de los miembros de la matriz de `phoneNumbers2` y, a continuación, agregar esos elementos como elementos secundarios de `contact2`.  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Cómo el compilador crea objetos a partir de literales XML  
 El compilador de Visual Basic traduce los literales XML en llamadas a los constructores de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalentes para generar el objeto [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Por ejemplo, el compilador Visual Basic traducirá el siguiente ejemplo de código en una llamada al constructor <xref:System.Xml.Linq.XProcessingInstruction> para la instrucción de versión XML, llama al constructor <xref:System.Xml.Linq.XElement> para los elementos `<contact>`, `<name>`y `<phone>`, y llama al constructor <xref:System.Xml.Linq.XAttribute> para el atributo `type`. En concreto, dados los atributos en el ejemplo siguiente, el compilador Visual Basic llamará dos veces al constructor <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29>. El primero pasará el valor `type` para el parámetro `name` y el valor `home` para el parámetro `value`. La segunda también pasará el valor `type` del parámetro `name`, pero el valor `work` para el parámetro `value`.  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement>
- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)
