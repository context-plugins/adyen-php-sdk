
# Forex Quote 2

The forex quote as returned in the response of the forex service.

## Structure

`ForexQuote2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | `?string` | Optional | The account name. | getAccount(): ?string | setAccount(?string account): void |
| `accountType` | `?string` | Optional | The account type. | getAccountType(): ?string | setAccountType(?string accountType): void |
| `baseAmount` | [`?Amount3`](../../doc/models/amount-3.md) | Optional | The base amount. | getBaseAmount(): ?Amount3 | setBaseAmount(?Amount3 baseAmount): void |
| `basePoints` | `int` | Required | The base points. | getBasePoints(): int | setBasePoints(int basePoints): void |
| `buy` | [`?Amount4`](../../doc/models/amount-4.md) | Optional | The buy rate. | getBuy(): ?Amount4 | setBuy(?Amount4 buy): void |
| `interbank` | [`?Amount5`](../../doc/models/amount-5.md) | Optional | The interbank amount. | getInterbank(): ?Amount5 | setInterbank(?Amount5 interbank): void |
| `reference` | `?string` | Optional | The reference assigned to the forex quote request. | getReference(): ?string | setReference(?string reference): void |
| `sell` | [`?Amount6`](../../doc/models/amount-6.md) | Optional | The sell rate. | getSell(): ?Amount6 | setSell(?Amount6 sell): void |
| `signature` | `?string` | Optional | The signature to validate the integrity. | getSignature(): ?string | setSignature(?string signature): void |
| `source` | `?string` | Optional | The source of the forex quote. | getSource(): ?string | setSource(?string source): void |
| `type` | `?string` | Optional | The type of forex. | getType(): ?string | setType(?string type): void |
| `validTill` | `DateTime` | Required | The date until which the forex quote is valid. | getValidTill(): \DateTime | setValidTill(\DateTime validTill): void |

## Example

```php
use AdyenLib\Models\Builders\ForexQuote2Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\Amount3Builder;
use AdyenLib\Models\Builders\Amount4Builder;
use AdyenLib\Models\Builders\Amount5Builder;

$forexQuote2 = ForexQuote2Builder::init(
    8,
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z')
)
    ->account('account0')
    ->accountType('accountType0')
    ->baseAmount(
        Amount3Builder::init(
            'currency8',
            202
        )->build()
    )
    ->buy(
        Amount4Builder::init(
            'currency2',
            72
        )->build()
    )
    ->interbank(
        Amount5Builder::init(
            'currency4',
            244
        )->build()
    )->build();
```

