
# Apple Pay Response Info

## Structure

`ApplePayResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `domains` | `?(string[])` | Optional | The list of merchant domains.<br><br>For more information, see [Apple Pay documentation](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in?tab=adyen-certificate-live_1#going-live). | getDomains(): ?array | setDomains(?array domains): void |

## Example

```php
use AdyenLib\Models\Builders\ApplePayResponseInfoBuilder;

$applePayResponseInfo = ApplePayResponseInfoBuilder::init()
    ->domains(
        [
            'domains4'
        ]
    )
    ->build();
```

