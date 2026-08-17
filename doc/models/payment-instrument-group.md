
# Payment Instrument Group

## Structure

`PaymentInstrumentGroup`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balancePlatform` | `string` | Required | The unique identifier of the [balance platform](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/get/balancePlatforms/{id}__queryParam_id) to which the payment instrument group belongs. | getBalancePlatform(): string | setBalancePlatform(string balancePlatform): void |
| `description` | `?string` | Optional | Your description for the payment instrument group.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | The unique identifier of the payment instrument group. | getId(): ?string | setId(?string id): void |
| `properties` | `?array<string,string>` | Optional | Properties of the payment instrument group. | getProperties(): ?array | setProperties(?array properties): void |
| `reference` | `?string` | Optional | Your reference for the payment instrument group.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `txVariant` | `string` | Required | The tx variant of the payment instrument group. | getTxVariant(): string | setTxVariant(string txVariant): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentGroupBuilder;

$paymentInstrumentGroup = PaymentInstrumentGroupBuilder::init(
    'balancePlatform2',
    'txVariant8'
)
    ->description('description0')
    ->id('id0')
    ->properties(
        [
            'key0' => 'properties8'
        ]
    )
    ->reference('reference4')
    ->build();
```

