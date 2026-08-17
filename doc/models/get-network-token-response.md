
# Get Network Token Response

## Structure

`GetNetworkTokenResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `token` | [`NetworkToken2`](../../doc/models/network-token-2.md) | Required | The details of the network token. | getToken(): NetworkToken2 | setToken(NetworkToken2 token): void |

## Example

```php
use AdyenLib\Models\Builders\GetNetworkTokenResponseBuilder;
use AdyenLib\Models\Builders\NetworkToken2Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\DeviceInfo1Builder;
use AdyenLib\Models\Builders\PhoneInfo2Builder;

$getNetworkTokenResponse = GetNetworkTokenResponseBuilder::init(
    NetworkToken2Builder::init()
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
)->build();
```

