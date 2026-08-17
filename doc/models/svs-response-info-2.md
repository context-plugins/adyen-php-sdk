
# Svs Response Info 2

**svs** details

## Structure

`SvsResponseInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorisationMid` | `?string` | Optional | The merchant ID (MID) that the acquirer recognizes you by. | getAuthorisationMid(): ?string | setAuthorisationMid(?string authorisationMid): void |
| `currencyCode` | `?string` | Optional | The three-character ISO currency code, example **USD** | getCurrencyCode(): ?string | setCurrencyCode(?string currencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\SvsResponseInfo2Builder;

$svsResponseInfo2 = SvsResponseInfo2Builder::init()
    ->authorisationMid('authorisationMid8')
    ->currencyCode('currencyCode2')
    ->build();
```

