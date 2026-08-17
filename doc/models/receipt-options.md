
# Receipt Options

## Structure

`ReceiptOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `headerLine1` | `?string` | Optional | The text of the first header line to be shown on the receipt.<br><br>**Constraints**: *Maximum Length*: `100` | getHeaderLine1(): ?string | setHeaderLine1(?string headerLine1): void |
| `headerLine2` | `?string` | Optional | The text of the second header line to be shown on the receipt.<br><br>**Constraints**: *Maximum Length*: `100` | getHeaderLine2(): ?string | setHeaderLine2(?string headerLine2): void |
| `logo` | `?string` | Optional | The receipt logo converted to a Base64-encoded string. The image must be a .bmp file of < 256 KB, dimensions 240 (H) x 384 (W) px.<br><br>**Constraints**: *Maximum Length*: `350000` | getLogo(): ?string | setLogo(?string logo): void |
| `promptBeforePrinting` | `?bool` | Optional | Indicates whether a screen appears asking if you want to print the shopper receipt. | getPromptBeforePrinting(): ?bool | setPromptBeforePrinting(?bool promptBeforePrinting): void |
| `qrCodeData` | `?string` | Optional | Data to print on the receipt as a QR code. This can include static text and the following variables:<br><br>- `${merchantreference}`: the merchant reference of the transaction.<br>- `${pspreference}`: the PSP reference of the transaction.<br><br>For example, **http://www.example.com/order/${pspreference}/${merchantreference}**. | getQrCodeData(): ?string | setQrCodeData(?string qrCodeData): void |

## Example

```php
use AdyenLib\Models\Builders\ReceiptOptionsBuilder;

$receiptOptions = ReceiptOptionsBuilder::init()
    ->headerLine1('headerLine16')
    ->headerLine2('headerLine24')
    ->logo('logo0')
    ->promptBeforePrinting(false)
    ->qrCodeData('qrCodeData6')
    ->build();
```

