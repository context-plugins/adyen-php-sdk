
# Terms of Service Acceptance Info

## Structure

`TermsOfServiceAcceptanceInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acceptedBy` | `?string` | Optional | The unique identifier of the user that accepted the Terms of Service. | getAcceptedBy(): ?string | setAcceptedBy(?string acceptedBy): void |
| `acceptedFor` | `?string` | Optional | The unique identifier of the legal entity for which the Terms of Service are accepted. | getAcceptedFor(): ?string | setAcceptedFor(?string acceptedFor): void |
| `createdAt` | `?DateTime` | Optional | The date when the Terms of Service were accepted, in ISO 8601 extended format. For example, 2022-12-18T10:15:30+01:00. | getCreatedAt(): ?\DateTime | setCreatedAt(?\DateTime createdAt): void |
| `id` | `?string` | Optional | An Adyen-generated reference for the accepted Terms of Service. | getId(): ?string | setId(?string id): void |
| `type` | [`?string(Type64Enum)`](../../doc/models/type-64-enum.md) | Optional | The type of Terms of Service.<br><br>Possible values:<br><br>* **adyenForPlatformsManage**<br>* **adyenIssuing**<br>* **adyenForPlatformsAdvanced**<br>* **adyenCapital**<br>* **adyenAccount**<br>* **adyenCard**<br>* **adyenFranchisee**<br>* **adyenPccr**<br>* **adyenChargeCard**<br>* **kycOnInvite** | getType(): ?string | setType(?string type): void |
| `validTo` | `?DateTime` | Optional | The expiration date for the Terms of Service acceptance, in ISO 8601 extended format. For example, 2022-12-18T00:00:00+01:00. | getValidTo(): ?\DateTime | setValidTo(?\DateTime validTo): void |

## Example

```php
use AdyenLib\Models\Builders\TermsOfServiceAcceptanceInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Type64Enum;

$termsOfServiceAcceptanceInfo = TermsOfServiceAcceptanceInfoBuilder::init()
    ->acceptedBy('acceptedBy2')
    ->acceptedFor('acceptedFor4')
    ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->id('id4')
    ->type(Type64Enum::ADYENFORPLATFORMSADVANCED)
    ->build();
```

