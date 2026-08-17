
# Bin Detail 1

Bin Group Details

## Structure

`BinDetail1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `issuerCountry` | `?string` | Optional | The country where the card was issued. | getIssuerCountry(): ?string | setIssuerCountry(?string issuerCountry): void |

## Example

```php
use AdyenLib\Models\Builders\BinDetail1Builder;

$binDetail1 = BinDetail1Builder::init()
    ->issuerCountry('issuerCountry0')
    ->build();
```

