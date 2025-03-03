---
title: 'Cómo: Proyectar un gráfico de objetos'
ms.date: 07/20/2015
ms.assetid: 9451eb47-6a31-49d7-84df-73368c618422
ms.openlocfilehash: 68b58226dbf30f82709a39e96bef0f8cce95d0ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347766"
---
# <a name="how-to-project-an-object-graph-visual-basic"></a>Cómo: proyectar un gráfico de objetos (Visual Basic)
En este tema se ilustra cómo proyectar o rellenar un gráfico de objetos de XML.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código rellena un gráfico de objetos con las clases `Address`, `PurchaseOrder` y `PurchaseOrderItem` del documento XML [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).  
  
```vb  
Class Address  
    Public Enum AddressUse  
        Shipping  
        Billing  
    End Enum  
  
    Private addressTypeVal As AddressUse  
    Private nameVal As String  
    Private streetVal As String  
    Private cityVal As String  
    Private stateVal As String  
    Private zipVal As String  
    Private countryVal As String  
  
    Public Property AddressType() As AddressUse  
        Get  
            Return addressTypeVal  
        End Get  
        Set(ByVal value As AddressUse)  
            addressTypeVal = value  
        End Set  
    End Property  
  
    Public Property Name() As String  
        Get  
            Return nameVal  
        End Get  
        Set(ByVal value As String)  
            nameVal = value  
        End Set  
    End Property  
  
    Public Property Street() As String  
        Get  
            Return streetVal  
        End Get  
        Set(ByVal value As String)  
            streetVal = value  
        End Set  
    End Property  
  
    Public Property City() As String  
        Get  
            Return cityVal  
        End Get  
        Set(ByVal value As String)  
            cityVal = value  
        End Set  
    End Property  
  
    Public Property State() As String  
        Get  
            Return stateVal  
        End Get  
        Set(ByVal value As String)  
            stateVal = value  
        End Set  
    End Property  
  
    Public Property Zip() As String  
        Get  
            Return zipVal  
        End Get  
        Set(ByVal value As String)  
            zipVal = value  
        End Set  
    End Property  
  
    Public Property Country() As String  
        Get  
            Return countryVal  
        End Get  
        Set(ByVal value As String)  
            countryVal = value  
        End Set  
    End Property  
  
    Public Overrides Function ToString() As String  
        Dim sb As StringBuilder = New StringBuilder()  
        sb.Append(String.Format("Type: {0}" + vbNewLine, _  
            IIf(AddressType = AddressUse.Shipping, "Shipping", "Billing")))  
        sb.Append(String.Format("Name: {0}" + vbNewLine, Name))  
        sb.Append(String.Format("Street: {0}" + vbNewLine, Street))  
        sb.Append(String.Format("City: {0}" + vbNewLine, City))  
        sb.Append(String.Format("State: {0}" + vbNewLine, State))  
        sb.Append(String.Format("Zip: {0}" + vbNewLine, Zip))  
        sb.Append(String.Format("Country: {0}" + vbNewLine, Country))  
        Return sb.ToString()  
    End Function  
End Class  
  
Class PurchaseOrderItem  
    Private partNumberVal As String  
    Private productNameVal As String  
    Private quantityVal As Integer  
    Private usPriceVal As Decimal  
    Private commentVal As String  
    Private shipDateVal As DateTime  
  
    Public Property PartNumber() As String  
        Get  
            Return partNumberVal  
        End Get  
        Set(ByVal value As String)  
            partNumberVal = value  
        End Set  
    End Property  
  
    Public Property ProductName() As String  
        Get  
            Return productNameVal  
        End Get  
        Set(ByVal value As String)  
            productNameVal = value  
        End Set  
    End Property  
  
    Public Property Quantity() As Integer  
        Get  
            Return quantityVal  
        End Get  
        Set(ByVal value As Integer)  
            quantityVal = value  
        End Set  
    End Property  
  
    Public Property USPrice() As Decimal  
        Get  
            Return usPriceVal  
        End Get  
        Set(ByVal value As Decimal)  
            usPriceVal = value  
        End Set  
    End Property  
  
    Public Property Comment() As String  
        Get  
            Return commentVal  
        End Get  
        Set(ByVal value As String)  
            commentVal = value  
        End Set  
    End Property  
  
    Public Property ShipDate() As DateTime  
        Get  
            Return shipDateVal  
        End Get  
        Set(ByVal value As DateTime)  
            shipDateVal = value  
        End Set  
    End Property  
  
    Public Overrides Function ToString() As String  
        Dim sb As StringBuilder = New StringBuilder()  
        sb.Append(String.Format("PartNumber: {0}" + vbNewLine, PartNumber))  
        sb.Append(String.Format("ProductName: {0}" + vbNewLine, ProductName))  
        sb.Append(String.Format("Quantity: {0}" + vbNewLine, Quantity))  
        sb.Append(String.Format("USPrice: {0}" + vbNewLine, USPrice))  
        If (Comment <> Nothing) Then  
            sb.Append(String.Format("Comment: {0}" + vbNewLine, Comment))  
        End If  
        If (ShipDate <> DateTime.MinValue) Then  
            sb.Append(String.Format("ShipDate: {0:d}" + vbNewLine, ShipDate))  
        End If  
        Return sb.ToString()  
    End Function  
End Class  
  
Class PurchaseOrder  
    Private purchaseOrderNumberVal As String  
    Private orderDateVal As DateTime  
    Private commentVal As String  
    Private addressesVal As List(Of Address)  
    Private itemsVal As List(Of PurchaseOrderItem)  
  
    Public Property PurchaseOrderNumber() As String  
        Get  
            Return purchaseOrderNumberVal  
        End Get  
        Set(ByVal value As String)  
            purchaseOrderNumberVal = value  
        End Set  
    End Property  
  
    Public Property OrderDate() As DateTime  
        Get  
            Return orderDateVal  
        End Get  
        Set(ByVal value As DateTime)  
            orderDateVal = value  
        End Set  
    End Property  
  
    Public Property Comment() As String  
        Get  
            Return commentVal  
        End Get  
        Set(ByVal value As String)  
            commentVal = value  
        End Set  
    End Property  
  
    Public Property Addresses() As List(Of Address)  
        Get  
            Return addressesVal  
        End Get  
        Set(ByVal value As List(Of Address))  
            addressesVal = value  
        End Set  
    End Property  
  
    Public Property Items() As List(Of PurchaseOrderItem)  
        Get  
            Return itemsVal  
        End Get  
        Set(ByVal value As List(Of PurchaseOrderItem))  
            itemsVal = value  
        End Set  
    End Property  
  
    Public Overrides Function ToString() As String  
        Dim sb As StringBuilder = New StringBuilder()  
        sb.Append(String.Format("PurchaseOrderNumber: {0}" _  
                    + vbNewLine, PurchaseOrderNumber))  
        sb.Append(String.Format("OrderDate: {0:d}" + vbNewLine, OrderDate))  
        sb.Append(vbNewLine)  
        sb.Append("Addresses" + vbNewLine)  
        sb.Append("=====" + vbNewLine)  
        For Each address As Address In Addresses  
            sb.Append(address)  
            sb.Append(vbNewLine)  
        Next  
        sb.Append("Items" + vbNewLine)  
        sb.Append("=====" + vbNewLine)  
        For Each item As PurchaseOrderItem In Items  
            sb.Append(item)  
            sb.Append(vbNewLine)  
        Next  
        Return sb.ToString()  
    End Function  
End Class  
  
Sub Main()  
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
    Dim purchOrder = New PurchaseOrder With { _  
        .PurchaseOrderNumber = po.@<PurchaseOrderNumber>, _  
        .OrderDate = Convert.ToDateTime(po.@<OrderDate>), _  
        .Addresses = ( _  
            From a In po.<Address> _  
            Select New Address With { _  
                .AddressType = IIf(a.@<Type> = "Shipping", _  
                                   Address.AddressUse.Shipping, _  
                                   Address.AddressUse.Billing), _  
                .Name = a.<Name>.Value, _  
                .Street = a.<Street>.Value, _  
                .City = a.<City>.Value, _  
                .State = a.<State>.Value, _  
                .Zip = a.<Zip>.Value, _  
                .Country = a.<Country>.Value _  
                } _  
            ).ToList(), _  
        .Items = ( _  
            From i In po.<Items>.<Item> _  
            Select New PurchaseOrderItem With { _  
                .PartNumber = i.@<PartNumber>, _  
                .ProductName = i.<ProductName>.Value, _  
                .Quantity = i.<Quantity>.Value, _  
                .USPrice = i.<USPrice>.Value, _  
                .Comment = i.<Comment>.Value, _  
                .ShipDate = IIf(i.<ShipDate>.Value <> Nothing, _  
                            Convert.ToDateTime(i.<ShipDate>.Value), _  
                            DateTime.MinValue) _  
                } _  
            ).ToList() _  
    }  
    Console.WriteLine(purchOrder)  
End Sub  
```  
  
 En este ejemplo, el resultado de la consulta de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] se devuelve como un <xref:System.Collections.Generic.IEnumerable%601> de `PurchaseOrderItem`. Los elementos de la clase `PurchaseOrder` son del tipo <xref:System.Collections.Generic.IEnumerable%601> de `PurchaseOrderItem`. El código usa el método de extensión <xref:System.Linq.Enumerable.ToList%2A> para crear una colección <xref:System.Collections.Generic.List%601> de los resultados de la consulta.  
  
 El ejemplo genera el siguiente resultado:  
  
```console  
PurchaseOrderNumber: 99503  
OrderDate: 10/20/1999  
  
Addresses  
=====  
Type: Shipping  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 10999  
Country: USA  
  
Type: Billing  
Name: Tai Yee  
Street: 8 Oak Avenue  
City: Old Town  
State: PA  
Zip: 95819  
Country: USA  
  
Items  
=====  
PartNumber: 872-AA  
ProductName: Lawnmower  
Quantity: 1  
USPrice: 148.95  
Comment: Confirm this is electric  
  
PartNumber: 926-AA  
ProductName: Baby Monitor  
Quantity: 2  
USPrice: 39.98  
ShipDate: 5/21/1999  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.Enumerable.Select%2A>
- <xref:System.Linq.Enumerable.ToList%2A>
- [Proyecciones y transformaciones (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
