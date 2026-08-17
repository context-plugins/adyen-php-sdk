
# Forex Quote 11

The forex quote as returned in the response of the forex service.

## Structure

`ForexQuote11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | `?string` | Optional | The account name. | getAccount(): ?string | setAccount(?string account): void |
| `accountType` | `?string` | Optional | The account type. | getAccountType(): ?string | setAccountType(?string accountType): void |
| `baseAmount` | [`?Amount`](../../doc/models/amount.md) | Optional | The base amount. | getBaseAmount(): ?Amount | setBaseAmount(?Amount baseAmount): void |
| `basePoints` | `int` | Required | The base points. | getBasePoints(): int | setBasePoints(int basePoints): void |
| `buy` | [`?Amount`](../../doc/models/amount.md) | Optional | The buy rate. | getBuy(): ?Amount | setBuy(?Amount buy): void |
| `interbank` | [`?Amount`](../../doc/models/amount.md) | Optional | The interbank amount. | getInterbank(): ?Amount | setInterbank(?Amount interbank): void |
| `reference` | `?string` | Optional | The reference assigned to the forex quote request. | getReference(): ?string | setReference(?string reference): void |
| `sell` | [`?Amount`](../../doc/models/amount.md) | Optional | The sell rate. | getSell(): ?Amount | setSell(?Amount sell): void |
| `signature` | `?string` | Optional | The signature to validate the integrity. | getSignature(): ?string | setSignature(?string signature): void |
| `source` | `?string` | Optional | The source of the forex quote. | getSource(): ?string | setSource(?string source): void |
| `type` | `?string` | Optional | The type of forex. | getType(): ?string | setType(?string type): void |
| `validTill` | `DateTime` | Required | The date until which the forex quote is valid. | getValidTill(): \DateTime | setValidTill(\DateTime validTill): void |

## Example

```php
use AdyenLib\Models\Builders\ForexQuote11Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\AmountBuilder;

$forexQuote11 = ForexQuote11Builder::init(
    184,
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)
    ->account('account4')
    ->accountType('accountType4')
    ->baseAmount(
        AmountBuilder::init(
            'currency8',
            202
        )->build()
    )
    ->buy(
        AmountBuilder::init(
            'currency2',
            72
        )->build()
    )
    ->interbank(
        AmountBuilder::init(
            'currency4',
            244
        )->build()
    )->build();
```

