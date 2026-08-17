
# Checkout Network Token Option

## Structure

`CheckoutNetworkTokenOption`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `includeCryptogram` | `?bool` | Optional | Set to **true** to enable forwarding network token cryptograms. | getIncludeCryptogram(): ?bool | setIncludeCryptogram(?bool includeCryptogram): void |
| `useNetworkToken` | `?bool` | Optional | Set to **true** to forward the network token for a card. | getUseNetworkToken(): ?bool | setUseNetworkToken(?bool useNetworkToken): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutNetworkTokenOptionBuilder;

$checkoutNetworkTokenOption = CheckoutNetworkTokenOptionBuilder::init()
    ->includeCryptogram(false)
    ->useNetworkToken(false)
    ->build();
```

