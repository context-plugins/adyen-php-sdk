
# Opi

## Structure

`Opi`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enablePayAtTable` | `?bool` | Optional | Indicates if Pay at table is enabled. | getEnablePayAtTable(): ?bool | setEnablePayAtTable(?bool enablePayAtTable): void |
| `payAtTableStoreNumber` | `?string` | Optional | The store number to use for Pay at Table. | getPayAtTableStoreNumber(): ?string | setPayAtTableStoreNumber(?string payAtTableStoreNumber): void |
| `payAtTableURL` | `?string` | Optional | The URL and port number used for Pay at Table communication. | getPayAtTableURL(): ?string | setPayAtTableURL(?string payAtTableURL): void |

## Example

```php
use AdyenLib\Models\Builders\OpiBuilder;

$opi = OpiBuilder::init()
    ->enablePayAtTable(false)
    ->payAtTableStoreNumber('payAtTableStoreNumber0')
    ->payAtTableURL('payAtTableURL2')
    ->build();
```

