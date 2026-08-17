
# Account Holder Resource

## Structure

`AccountHolderResource`

## Inherits From

[`Resource2`](../../doc/models/resource-2.md)

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the resource connected to the component. For [Platform Experience components](https://docs.adyen.com/platforms/build-user-dashboards), this is the account holder linked to the balance account shown in the component.<br><br>**Constraints**: *Minimum Length*: `1` | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolderResourceBuilder;

$accountHolderResource = AccountHolderResourceBuilder::init(
    'accountHolderId8'
)
    ->type('accountHolder')
    ->build();
```

