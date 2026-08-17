
# List Network Tokens Response

## Structure

`ListNetworkTokensResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `networkTokens` | [`?(NetworkToken[])`](../../doc/models/network-token.md) | Optional | List of network tokens. | getNetworkTokens(): ?array | setNetworkTokens(?array networkTokens): void |

## Example

```php
use AdyenLib\Models\Builders\ListNetworkTokensResponseBuilder;
use AdyenLib\Models\Builders\NetworkTokenBuilder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\DeviceInfo1Builder;
use AdyenLib\Models\Builders\PhoneInfo2Builder;

$listNetworkTokensResponse = ListNetworkTokensResponseBuilder::init()
    ->networkTokens(
        [
            NetworkTokenBuilder::init()
                ->brandVariant('brandVariant8')
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->device(
                    DeviceInfo1Builder::init()
                        ->formFactor('formFactor4')
                        ->osName('osName6')
                        ->phone(
                            PhoneInfo2Builder::init()
                                ->hashedNumber('hashedNumber2')
                                ->lastFourDigits('lastFourDigits8')
                                ->number('number8')
                                ->build()
                        )
                        ->build()
                )
                ->id('id6')
                ->paymentInstrumentId('paymentInstrumentId8')
                ->build(),
            NetworkTokenBuilder::init()
                ->brandVariant('brandVariant8')
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->device(
                    DeviceInfo1Builder::init()
                        ->formFactor('formFactor4')
                        ->osName('osName6')
                        ->phone(
                            PhoneInfo2Builder::init()
                                ->hashedNumber('hashedNumber2')
                                ->lastFourDigits('lastFourDigits8')
                                ->number('number8')
                                ->build()
                        )
                        ->build()
                )
                ->id('id6')
                ->paymentInstrumentId('paymentInstrumentId8')
                ->build(),
            NetworkTokenBuilder::init()
                ->brandVariant('brandVariant8')
                ->creationDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->device(
                    DeviceInfo1Builder::init()
                        ->formFactor('formFactor4')
                        ->osName('osName6')
                        ->phone(
                            PhoneInfo2Builder::init()
                                ->hashedNumber('hashedNumber2')
                                ->lastFourDigits('lastFourDigits8')
                                ->number('number8')
                                ->build()
                        )
                        ->build()
                )
                ->id('id6')
                ->paymentInstrumentId('paymentInstrumentId8')
                ->build()
        ]
    )
    ->build();
```

