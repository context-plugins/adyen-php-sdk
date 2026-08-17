
# Ideal Auth Link Request

## Structure

`IdealAuthLinkRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the account holder.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `150` | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |

## Example

```php
use AdyenLib\Models\Builders\IdealAuthLinkRequestBuilder;

$idealAuthLinkRequest = IdealAuthLinkRequestBuilder::init(
    'AH00000000000000000000000'
)->build();
```

