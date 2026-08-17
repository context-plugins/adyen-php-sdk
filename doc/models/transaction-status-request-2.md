
# Transaction Status Request 2

Content of the TransactionStatus Request message.

## Structure

`TransactionStatusRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `messageReference` | [`?MessageReference2`](../../doc/models/message-reference-2.md) | Optional | Identification of a previous POI transaction.<br>Present if it contains any data. | getMessageReference(): ?MessageReference2 | setMessageReference(?MessageReference2 messageReference): void |
| `receiptReprintFlag` | `?bool` | Optional | Request to reprint the POI receipt(s). Allows reprinting a receipt with a `TransactionStatus` message<br><br>**Default**: `false` | getReceiptReprintFlag(): ?bool | setReceiptReprintFlag(?bool receiptReprintFlag): void |
| `documentQualifier` | [`?(string(DocumentQualifierEnum)[])`](../../doc/models/document-qualifier-enum.md) | Optional | Qualification of the document to print to the Cashier or the Customer. Allows the manager of the printer, Sale or POI Terminal, to send the information to a particular physical printer or to use the paper type accordingly.<br>Possible values:<br><br>* **CashierReceipt**<br>* **CustomerReceipt**<br>* **Document**<br>* **Journal**<br>* **SaleReceipt**<br>* **Voucher** | getDocumentQualifier(): ?array | setDocumentQualifier(?array documentQualifier): void |

## Example

```php
use AdyenLib\Models\Builders\TransactionStatusRequest2Builder;
use AdyenLib\Models\Builders\MessageReference2Builder;
use AdyenLib\Models\MessageCategory2Enum;
use AdyenLib\Models\DocumentQualifierEnum;

$transactionStatusRequest2 = TransactionStatusRequest2Builder::init()
    ->messageReference(
        MessageReference2Builder::init()
            ->messageCategory(MessageCategory2Enum::PAYMENT)
            ->serviceID('ServiceID0')
            ->deviceID('DeviceID2')
            ->saleID('SaleID8')
            ->pOIID('POIID2')
            ->build()
    )
    ->receiptReprintFlag(false)
    ->documentQualifier(
        [
            DocumentQualifierEnum::CASHIERRECEIPT,
            DocumentQualifierEnum::CUSTOMERRECEIPT,
            DocumentQualifierEnum::DOCUMENT
        ]
    )
    ->build();
```

