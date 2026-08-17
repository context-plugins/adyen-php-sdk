
# Surcharge 21

Settings for payment [surcharge](https://docs.adyen.com/point-of-sale/surcharge) features.

## Structure

`Surcharge21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `askConfirmation` | `?bool` | Optional | Show the surcharge details on the terminal, so the shopper can confirm. | getAskConfirmation(): ?bool | setAskConfirmation(?bool askConfirmation): void |
| `configurations` | [`?(Configuration[])`](../../doc/models/configuration.md) | Optional | Surcharge fees or percentages for specific cards, funding sources (credit or debit), and currencies. | getConfigurations(): ?array | setConfigurations(?array configurations): void |
| `disclosureOnPresentCard` | `?bool` | Optional | Show the maximum surcharge rate to the shopper on the present card screen before they tap. | getDisclosureOnPresentCard(): ?bool | setDisclosureOnPresentCard(?bool disclosureOnPresentCard): void |
| `excludeGratuityFromSurcharge` | `?bool` | Optional | Exclude the tip amount from the surcharge calculation. | getExcludeGratuityFromSurcharge(): ?bool | setExcludeGratuityFromSurcharge(?bool excludeGratuityFromSurcharge): void |

## Example

```php
use AdyenLib\Models\Builders\Surcharge21Builder;
use AdyenLib\Models\Builders\ConfigurationBuilder;
use AdyenLib\Models\Builders\CurrencyBuilder;

$surcharge21 = Surcharge21Builder::init()
    ->askConfirmation(false)
    ->configurations(
        [
            ConfigurationBuilder::init(
                'brand4',
                [
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build(),
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build(),
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build()
                ]
            )
                ->commercial(false)
                ->country(
                    [
                        'country1',
                        'country2'
                    ]
                )
                ->sources(
                    [
                        'sources8',
                        'sources9'
                    ]
                )
                ->build(),
            ConfigurationBuilder::init(
                'brand4',
                [
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build(),
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build(),
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build()
                ]
            )
                ->commercial(false)
                ->country(
                    [
                        'country1',
                        'country2'
                    ]
                )
                ->sources(
                    [
                        'sources8',
                        'sources9'
                    ]
                )
                ->build(),
            ConfigurationBuilder::init(
                'brand4',
                [
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build(),
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build(),
                    CurrencyBuilder::init(
                        'currencyCode6'
                    )
                        ->amount(208)
                        ->maxAmount(98)
                        ->percentage(191.04)
                        ->build()
                ]
            )
                ->commercial(false)
                ->country(
                    [
                        'country1',
                        'country2'
                    ]
                )
                ->sources(
                    [
                        'sources8',
                        'sources9'
                    ]
                )
                ->build()
        ]
    )
    ->disclosureOnPresentCard(false)
    ->excludeGratuityFromSurcharge(false)
    ->build();
```

