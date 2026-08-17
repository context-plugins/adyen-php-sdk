
# Bin Detail

## Structure

`BinDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `issuerCountry` | `?string` | Optional | The country where the card was issued. | getIssuerCountry(): ?string | setIssuerCountry(?string issuerCountry): void |

## Example

```php
use AdyenLib\Models\Builders\BinDetailBuilder;

$binDetail = BinDetailBuilder::init()
    ->issuerCountry('issuerCountry0')
    ->build();
```

