
# Output Barcode

## Structure

`OutputBarcode`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `barcodeValue` | `string` | Required | Value with a Barcode coding. The barcode value to display or print.<br><br>**Constraints**: *Pattern*: `^.+$` | getBarcodeValue(): string | setBarcodeValue(string barcodeValue): void |

## Example

```php
use AdyenLib\Models\Builders\OutputBarcodeBuilder;

$outputBarcode = OutputBarcodeBuilder::init(
    'BarcodeValue2'
)->build();
```

