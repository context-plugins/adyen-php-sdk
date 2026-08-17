
# Svs Info 2

Details to provide if `type` is **svs**.

## Structure

`SvsInfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorisationMid` | `string` | Required | The merchant ID (MID) that the acquirer recognizes you by. | getAuthorisationMid(): string | setAuthorisationMid(string authorisationMid): void |
| `currencyCode` | `string` | Required | The three-character ISO currency code, example **USD** | getCurrencyCode(): string | setCurrencyCode(string currencyCode): void |

## Example

```php
use AdyenLib\Models\Builders\SvsInfo2Builder;

$svsInfo2 = SvsInfo2Builder::init(
    'authorisationMid6',
    'currencyCode0'
)->build();
```

