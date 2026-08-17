
# Response Additional Data Domestic Error

## Structure

`ResponseAdditionalDataDomesticError`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `domesticRefusalReasonRaw` | `?string` | Optional | The reason the transaction was declined, given by the local issuer.<br>Currently available for merchants in Japan. | getDomesticRefusalReasonRaw(): ?string | setDomesticRefusalReasonRaw(?string domesticRefusalReasonRaw): void |
| `domesticShopperAdvice` | `?string` | Optional | The action the shopper should take, in a local language.<br>Currently available in Japanese, for merchants in Japan. | getDomesticShopperAdvice(): ?string | setDomesticShopperAdvice(?string domesticShopperAdvice): void |

## Example

```php
use AdyenLib\Models\Builders\ResponseAdditionalDataDomesticErrorBuilder;

$responseAdditionalDataDomesticError = ResponseAdditionalDataDomesticErrorBuilder::init()
    ->domesticRefusalReasonRaw('domesticRefusalReasonRaw6')
    ->domesticShopperAdvice('domesticShopperAdvice8')
    ->build();
```

