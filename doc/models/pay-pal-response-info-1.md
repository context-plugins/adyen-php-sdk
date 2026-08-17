
# Pay Pal Response Info 1

**paypal** details

## Structure

`PayPalResponseInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `directCapture` | `?bool` | Optional | Indicates if direct (immediate) capture for PayPal is enabled. If set to **true**, this setting overrides the [capture](https://docs.adyen.com/online-payments/capture) settings of your merchant account. Default value: **true**. | getDirectCapture(): ?bool | setDirectCapture(?bool directCapture): void |
| `payerId` | `?string` | Optional | PayPal Merchant ID. Character length and limitations: 13 single-byte alphanumeric characters.<br><br>**Constraints**: *Minimum Length*: `13`, *Maximum Length*: `13` | getPayerId(): ?string | setPayerId(?string payerId): void |
| `subject` | `?string` | Optional | Your business email address. | getSubject(): ?string | setSubject(?string subject): void |

## Example

```php
use AdyenLib\Models\Builders\PayPalResponseInfo1Builder;

$payPalResponseInfo1 = PayPalResponseInfo1Builder::init()
    ->directCapture(false)
    ->payerId('payerId0')
    ->subject('subject2')
    ->build();
```

