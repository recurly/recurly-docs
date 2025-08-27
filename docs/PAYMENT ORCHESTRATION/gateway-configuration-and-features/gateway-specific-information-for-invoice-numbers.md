---
title: Gateway specific information for invoice numbers
excerpt: >-
  Gateways each have their own specific attributes that are used for
  transactions.  Invoice numbers are often sent but can be used differently per
  gateway.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Prerequisites

* Access to one or more supported payment gateways or;

### Limitations

* Gateways each have their own character limit for gateway attributes

# Invoice numbers character limits

Invoice numbers that exceed the character limit for a gateway will be left truncated to meet the maximum character requirement for that gateway.

The following table displays the gateway and the maximum character requirement for that gateway:

| Gateway        | Max Number of Characters |
| -------------- | ------------------------ |
| Freedom Pay    | 17                       |
| Chase Orbital  | 22                       |
| Card Connect   | 36                       |
| Check Commerce | 40                       |
| WorldPay       | 100                      |

Invoice numbers that exceed the character limit for a gateway will be left truncated to meet the maximum character requirement for that gateway.  Some gateways have additional attributes that are set that may use invoice numbers.

The following table displays the gateway and the maximum character requirement for that gateway and the special considerations for gateway attributes:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Gateway
      </th>

      <th>
        Max Number of Characters
      </th>

      <th>
        Special Considerations
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Vantiv
      </td>

      <td>
        17/25
      </td>

      <td>
        Purchases and refunds use invoice number, it will be truncated if over 25 characters.
        Other transactions use transaction uuid, this will be left truncated if over 25 characters.
        invoiceNumberReference set to invoiceNumber
        Customer reference set to invoice number, will be left truncated if over 17 characters.
      </td>
    </tr>

    <tr>
      <td>
        TSYS
      </td>

      <td>
        15
      </td>

      <td>
        If the invoice number is empty, falls back to PO Number.
      </td>
    </tr>

    <tr>
      <td>
        PayPal
      </td>

      <td>
        127
      </td>

      <td>
        PayPal Business, PayPal UK, PayPal Complete:
        Greater than 127 characters, INVNUM is left truncated to 127 characters.
      </td>
    </tr>

    <tr>
      <td>
        Stripe
      </td>

      <td>
        25
      </td>

      <td>
        Long invoice numbers of 500 characters:
        Level 3 merchant reference, left truncated at 25 characters.
        Level 3 customer reference, left truncated at 17 characters.
        Invoice numbers of 17 characters or less:
        Full invoice number for metadata.invoiceNumber, Level 3 merchant reference, Level 3 customer reference.
      </td>
    </tr>

    <tr>
      <td>
        Authorize.net
      </td>

      <td>
        20
      </td>

      <td>
        PO Number left truncated to 25 characters.
        Order.InvoiceNumber left truncated to 20 characters.
      </td>
    </tr>

    <tr>
      <td>
        Adyen
      </td>

      <td>
        25
      </td>

      <td>
        merchantOrderReference full invoice number up to 1000 characters.
        enhancedSchemeData.customerReference left truncated to 25 characters.
      </td>
    </tr>

    <tr>
      <td>
        AmazonPay V1
      </td>

      <td>
        128
      </td>

      <td>
        Left truncated if over 128 characters.
        OrderReferenceAttributes.SellerOrderAttributes.SellerOrderID, SellerOrderAttributes.SellerOrderId
      </td>
    </tr>

    <tr>
      <td>
        Braintree
      </td>

      <td>
        127
      </td>

      <td>
        Invoice number left truncated if over 128 characters for OrderId.
        purchaseOrderNumber is left truncated if over 12 characters.
      </td>
    </tr>

    <tr>
      <td>
        Cybersource
      </td>

      <td>
        Varies by processor
      </td>

      <td>
        Asia, Middle East, and Africa gateways: 40 characters.
        China UnionPay: 40 characters.
        Elavon Americas: 39 characters.
        FDC Nashville Global: 8 characters.
        All other processors: 8 characters.
      </td>
    </tr>
  </tbody>
</Table>

<br />
