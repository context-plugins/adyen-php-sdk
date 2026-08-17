
# Cellulant

## Structure

`Cellulant`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkoutAttemptId` | `?string` | Optional | The checkout attempt identifier. | getCheckoutAttemptId(): ?string | setCheckoutAttemptId(?string checkoutAttemptId): void |
| `issuer` | `?string` | Optional | The Cellulant issuer. | getIssuer(): ?string | setIssuer(?string issuer): void |
| `sdkData` | `?string` | Optional | Base64-encoded JSON object containing SDK related parameters required by the SDK<br><br>**Constraints**: *Maximum Length*: `50000` | getSdkData(): ?string | setSdkData(?string sdkData): void |
| `type` | [`?string(Type17Enum)`](../../doc/models/type-17-enum.md) | Optional | **Cellulant**<br><br>**Default**: `Type17Enum::CELLULANT` | getType(): ?string | setType(?string type): void |

## Example

```php
use AdyenLib\Models\Builders\CellulantBuilder;
use AdyenLib\Models\Type17Enum;

$cellulant = CellulantBuilder::init()
    ->checkoutAttemptId('checkoutAttemptId6')
    ->issuer('issuer0')
    ->sdkData('sdkData0')
    ->type(Type17Enum::CELLULANT)
    ->build();
```

