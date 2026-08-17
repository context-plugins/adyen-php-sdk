
# Opi 1

Settings for an Oracle Payment Interface (OPI) integration.

## Structure

`Opi1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enablePayAtTable` | `?bool` | Optional | Indicates if Pay at table is enabled. | getEnablePayAtTable(): ?bool | setEnablePayAtTable(?bool enablePayAtTable): void |
| `payAtTableStoreNumber` | `?string` | Optional | The store number to use for Pay at Table. | getPayAtTableStoreNumber(): ?string | setPayAtTableStoreNumber(?string payAtTableStoreNumber): void |
| `payAtTableURL` | `?string` | Optional | The URL and port number used for Pay at Table communication. | getPayAtTableURL(): ?string | setPayAtTableURL(?string payAtTableURL): void |

## Example

```php
use AdyenLib\Models\Builders\Opi1Builder;

$opi1 = Opi1Builder::init()
    ->enablePayAtTable(false)
    ->payAtTableStoreNumber('payAtTableStoreNumber4')
    ->payAtTableURL('payAtTableURL8')
    ->build();
```

