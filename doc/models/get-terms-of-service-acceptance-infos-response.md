
# Get Terms of Service Acceptance Infos Response

## Structure

`GetTermsOfServiceAcceptanceInfosResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(TermsOfServiceAcceptanceInfo[])`](../../doc/models/terms-of-service-acceptance-info.md) | Optional | The Terms of Service acceptance information. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\GetTermsOfServiceAcceptanceInfosResponseBuilder;
use AdyenLib\Models\Builders\TermsOfServiceAcceptanceInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Type64Enum;

$getTermsOfServiceAcceptanceInfosResponse = GetTermsOfServiceAcceptanceInfosResponseBuilder::init()
    ->data(
        [
            TermsOfServiceAcceptanceInfoBuilder::init()
                ->acceptedBy('acceptedBy8')
                ->acceptedFor('acceptedFor0')
                ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id0')
                ->type(Type64Enum::ADYENACCOUNT)
                ->build()
        ]
    )
    ->build();
```

