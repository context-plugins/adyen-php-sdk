
# Svs Response Info

## Structure

`SvsResponseInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorisationMid` | `?string` | Optional | The merchant ID (MID) that the acquirer recognizes you by. | getAuthorisationMid(): ?string | setAuthorisationMid(?string authorisationMid): void |
| `currencyCode` | `?string` | Optional | The three-character ISO currency code, example **USD** | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\SvsResponseInfoBuilder;

$svsResponseInfo = SvsResponseInfoBuilder::init()
    ->authorisationMid('authorisationMid4')
    ->currencyCode('currencyCode8')
    ->build();
```

