
# Output Barcode 1

Barcode content to display or print.
Mandatory if `OutputFormat` is Barcode, not allowed otherwise.

## Structure

`OutputBarcode1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `barcodeValue` | `string` | Required | Value with a Barcode coding. The barcode value to display or print.<br><br>**Constraints**: *Pattern*: `^.+$` | getBarcodeValue(): string | setBarcodeValue(string barcodeValue): void |

## Example

```php
use AdyenLib\Models\Builders\OutputBarcode1Builder;

$outputBarcode1 = OutputBarcode1Builder::init(
    'BarcodeValue0'
)->build();
```

