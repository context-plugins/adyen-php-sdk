
# Permit

## Structure

`Permit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `partnerId` | `?string` | Optional | Partner ID (when using the permit-per-partner token sharing model). | getPartnerId(): ?string | setPartnerId(?string partnerId): void |
| `profileReference` | `?string` | Optional | The profile to apply to this permit (when using the shared permits model). | getProfileReference(): ?string | setProfileReference(?string profileReference): void |
| `restriction` | [`?PermitRestriction2`](../../doc/models/permit-restriction-2.md) | Optional | Permit level restriction overrides. | getRestriction(): ?PermitRestriction2 | setRestriction(?PermitRestriction2 restriction): void |
| `resultKey` | `?string` | Optional | The key to link permit requests to permit results. | getResultKey(): ?string | setResultKey(?string resultKey): void |
| `validTillDate` | `?DateTime` | Optional | The expiry date for this permit. | getValidTillDate(): ?\DateTime | setValidTillDate(?\DateTime validTillDate): void |

## Example

```php
use AdyenLib\Models\Builders\PermitBuilder;
use AdyenLib\Models\Builders\PermitRestriction2Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Utils\DateTimeHelper;

$permit = PermitBuilder::init()
    ->partnerId('partnerId4')
    ->profileReference('profileReference6')
    ->restriction(
        PermitRestriction2Builder::init()
            ->maxAmount(
                AmountBuilder::init(
                    'currency4',
                    160
                )->build()
            )
            ->singleTransactionLimit(
                AmountBuilder::init(
                    'currency8',
                    122
                )->build()
            )
            ->singleUse(false)
            ->build()
    )
    ->resultKey('resultKey0')
    ->validTillDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

