
# Calculate Terms of Service Status Response

## Structure

`CalculateTermsOfServiceStatusResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `termsOfServiceTypes` | [`?(string(TermsOfServiceTypeEnum)[])`](../../doc/models/terms-of-service-type-enum.md) | Optional | The type of Terms of Service that the legal entity needs to accept. If empty, no Terms of Service needs to be accepted. | getTermsOfServiceTypes(): ?array | setTermsOfServiceTypes(?array termsOfServiceTypes): void |

## Example

```php
use AdyenLib\Models\Builders\CalculateTermsOfServiceStatusResponseBuilder;
use AdyenLib\Models\TermsOfServiceTypeEnum;

$calculateTermsOfServiceStatusResponse = CalculateTermsOfServiceStatusResponseBuilder::init()
    ->termsOfServiceTypes(
        [
            TermsOfServiceTypeEnum::ADYENACCOUNT,
            TermsOfServiceTypeEnum::ADYENCAPITAL,
            TermsOfServiceTypeEnum::ADYENCARD
        ]
    )
    ->build();
```

