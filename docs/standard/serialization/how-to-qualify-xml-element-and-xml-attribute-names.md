---
title: 'Cómo: Calificar el elemento XML y los nombres del atributo XML'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: 1f79caf6ff295d793c615b17d387cdd165e440e7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353100"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a>Cómo: Calificar el elemento XML y los nombres del atributo XML

Los espacios de nombres XML contenidos en instancias de la clase <xref:System.Xml.Serialization.XmlSerializerNamespaces> deben ajustarse a la especificación de World Wide Web Consortium (W3C) denominada [espacios de nombres en XML](https://www.w3.org/TR/REC-xml-names/).

Los espacios de nombres XML proporcionan una método para calificar los nombres de elementos y atributos XML en documentos XML. Un nombre calificado se compone de un prefijo y un nombre local, separados por dos puntos. El prefijo funciona únicamente como marcador de posición y está asignado a un identificador URI que especifica un espacio de nombres. La combinación del espacio de nombres del URI, universalmente administrado, y el nombre local genera un nombre del que se garantiza que es universalmente único.

Creando una instancia de `XmlSerializerNamespaces` y agregando los pares de espacio de nombres al objeto, puede especificar los prefijos utilizados en un documento XML.

## <a name="to-create-qualified-names-in-an-xml-document"></a>Para crear nombres calificados en un documento XML

1. Cree una instancia de la clase `XmlSerializerNamespaces`.

2. Agregue todos los prefijos y pares de espacio de nombres a `XmlSerializerNamespaces`.

3. Aplique el atributo apropiado `System.Xml.Serialization` a cada método o clase que <xref:System.Xml.Serialization.XmlSerializer> vaya a serializar en un documento XML.

    Los atributos disponibles son: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, y <xref:System.Xml.Serialization.XmlTypeAttribute>.

4. Establezca la propiedad `Namespace` de cada atributo en uno de los valores de espacio de nombres del `XmlSerializerNamespaces`.

5. Pase `XmlSerializerNamespaces` al método `Serialize` de `XmlSerializer`.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo, se crea un `XmlSerializerNamespaces` al que se agregan dos prefijos y pares de espacio de nombres al objeto. El código crea `XmlSerializer` que se utiliza para serializar una instancia de la clase `Books`. El código llama al método `Serialize` con `XmlSerializerNamespaces`, permitiéndole al XML contener los espacios de nombres prefijados.

<!-- TODO: THE FOLLOWING VB SNIPPET ISN'T CORRECT!! -->
```vb
Option Explicit
public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}

Option Strict

Imports System
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Class Run

    Public Shared Sub Main()
        Dim test As New Run()
        test.SerializeObject("XmlNamespaces.xml")
    End Sub 'Main

    Public Sub SerializeObject(filename As String)
        Dim mySerializer As New XmlSerializer(GetType(Books))
        ' Writing a file requires a TextWriter.
        Dim myWriter As New StreamWriter(filename)

        ' Creates an XmlSerializerNamespaces and adds two
        ' prefix-namespace pairs.
        Dim myNamespaces As New XmlSerializerNamespaces()
        myNamespaces.Add("books", "http://www.cpandl.com")
        myNamespaces.Add("money", "http://www.cohowinery.com")

        ' Creates a Book.
        Dim myBook As New Book()
        myBook.TITLE = "A Book Title"
        Dim myPrice As New Price()
        myPrice.price = CDec(9.95)
        myPrice.currency = "US Dollar"
        myBook.PRICE = myPrice
        Dim myBooks As New Books()
        myBooks.Book = myBook
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)
        myWriter.Close()
    End Sub
End Class

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class 'Books

<XmlType([Namespace] := "http://www.cpandl.com")> _
Public Class Book

    <XmlElement([Namespace] := "http://www.cpandl.com")> _
    Public TITLE As String
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public PRICE As Price
End Class

Public Class Price
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _
    Public currency As String
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _
        price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Run
{
    public static void Main()
    {
        Run test = new Run();
        test.SerializeObject("XmlNamespaces.xml");
    }
    public void SerializeObject(string filename)
    {
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        XmlSerializerNamespaces myNamespaces =
        new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        Book myBook = new Book();
        myBook.TITLE = "A Book Title";
        Price myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        Books myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);
        myWriter.Close();
    }
}

public class Books
{
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public Book Book;
}

[XmlType(Namespace ="http://www.cpandl.com")]
public class Book
{
    [XmlElement(Namespace = "http://www.cpandl.com")]
    public string TITLE;
    [XmlElement(Namespace ="http://www.cohowinery.com")]
    public Price PRICE;
}
```

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Serialization.XmlSerializer>
- [Herramienta de definición de esquema XML y serialización XML](the-xml-schema-definition-tool-and-xml-serialization.md)
- [Introducción a la serialización XML](introducing-xml-serialization.md)
- [XmlSerializer (clase)](xref:System.Xml.Serialization.XmlSerializer)
- [Atributos que controlan la serialización XML](attributes-that-control-xml-serialization.md)
- [Cómo: Especificar un nombre de elemento alternativo para una secuencia XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Cómo: Serializar un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserializar un objeto](how-to-deserialize-an-object.md)
