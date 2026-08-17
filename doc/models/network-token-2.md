
# Network Token 2

The details of the network token.

## Structure

`NetworkToken2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `brandVariant` | `?string` | Optional | The card brand variant of the payment instrument associated with the network token. For example, **mc_prepaid_mrw**. | getBrandVariant(): ?string | setBrandVariant(?string brandVariant): void |
| `creationDate` | `?DateTime` | Optional | Date and time when the network token was created, in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) extended format. For example, **2025-03-19T10:15:30+01:00**.. | getCreationDate(): ?\DateTime | setCreationDate(?\DateTime creationDate): void |
| `device` | [`?DeviceInfo1`](../../doc/models/device-info-1.md) | Optional | Contains information about the device used to provision the network token. | getDevice(): ?DeviceInfo1 | setDevice(?DeviceInfo1 device): void |
| `id` | `?string` | Optional | The unique identifier of the network token. | getId(): ?string | setId(?string id): void |
| `paymentInstrumentId` | `?string` | Optional | The unique identifier of the payment instrument to which this network token belongs to. | getPaymentInstrumentId(): ?string | setPaymentInstrumentId(?string paymentInstrumentId): void |
| `status` | [`?string(Status91Enum)`](../../doc/models/status-91-enum.md) | Optional | The status of the network token. Possible values: **active**, **inactive**, **suspended**, **closed**. | getStatus(): ?string | setStatus(?string status): void |
| `tokenLastFour` | `?string` | Optional | The last four digits of the network token `id`. | getTokenLastFour(): ?string | setTokenLastFour(?string tokenLastFour): void |
| `tokenRequestor` | [`?Item`](../../doc/models/item.md) | Optional | The token requestor is an entity who requested tokenization of the card for secure payments. | getTokenRequestor(): ?Item | setTokenRequestor(?Item tokenRequestor): void |
| `type` | `?string` | Optional | The type of network token. For example, **wallet**, **cof**. | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\NetworkToken2Builder;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\DeviceInfo1Builder;
use AdyenLib\Models\Builders\PhoneInfo2Builder;

$networkToken2 = NetworkToken2Builder::init()
    ->brandVariant('brandVariant4')
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
    ->id('id2')
    ->paymentInstrumentId('paymentInstrumentId4')
    ->build();
```

