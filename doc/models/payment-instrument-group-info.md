
# Payment Instrument Group Info

## Structure

`PaymentInstrumentGroupInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balancePlatform` | `string` | Required | The unique identifier of the [balance platform](https://docs.adyen.com/api-explorer/#/balanceplatform/latest/get/balancePlatforms/{id}__queryParam_id) to which the payment instrument group belongs. | getBalancePlatform(): string | setBalancePlatform(string balancePlatform): void |
| `description` | `?string` | Optional | Your description for the payment instrument group.<br><br>**Constraints**: *Maximum Length*: `300` | getDescription(): ?string | setDescription(?string description): void |
| `properties` | `?array<string,string>` | Optional | Properties of the payment instrument group. | getProperties(): ?array | setProperties(?array properties): void |
| `reference` | `?string` | Optional | Your reference for the payment instrument group.<br><br>**Constraints**: *Maximum Length*: `150` | getReference(): ?string | setReference(?string reference): void |
| `txVariant` | `string` | Required | The tx variant of the payment instrument group. | getTxVariant(): string | setTxVariant(string txVariant): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentInstrumentGroupInfoBuilder;

$paymentInstrumentGroupInfo = PaymentInstrumentGroupInfoBuilder::init(
    'balancePlatform0',
    'txVariant6'
)
    ->description('description8')
    ->properties(
        [
            'key0' => 'properties6',
            'key1' => 'properties7',
            'key2' => 'properties8'
        ]
    )
    ->reference('reference4')
    ->build();
```

