
# Card 12

Contains information about the counterparty card.

## Structure

`Card12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardHolder` | [`PartyIdentification1`](../../doc/models/party-identification-1.md) | Required | Contains information about the cardholder. | getCardHolder(): PartyIdentification1 | setCardHolder(PartyIdentification1 cardHolder): void |
| `cardIdentification` | [`CardIdentification3`](../../doc/models/card-identification-3.md) | Required | Contains the identification details of the card. | getCardIdentification(): CardIdentification3 | setCardIdentification(CardIdentification3 cardIdentification): void |

## Example

```php
use AdyenLib\Models\Builders\Card12Builder;
use AdyenLib\Models\Builders\PartyIdentification1Builder;
use AdyenLib\Models\Builders\Address12Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Type112Enum;
use AdyenLib\Models\Builders\CardIdentification3Builder;

$card12 = Card12Builder::init(
    PartyIdentification1Builder::init()
        ->address(
            Address12Builder::init(
                'country0'
            )
                ->city('city6')
                ->line1('line18')
                ->line2('line20')
                ->postalCode('postalCode8')
                ->stateOrProvince('stateOrProvince4')
                ->build()
        )
        ->dateOfBirth(DateTimeHelper::fromSimpleDate('2016-03-13'))
        ->email('email0')
        ->firstName('firstName8')
        ->fullName('fullName6')
        ->type(Type112Enum::UNKNOWN)
        ->build(),
    CardIdentification3Builder::init()
        ->expiryMonth('expiryMonth2')
        ->expiryYear('expiryYear2')
        ->issueNumber('issueNumber0')
        ->number('number6')
        ->startMonth('startMonth8')
        ->build()
)->build();
```

