
# Admin Request 2

Content of the Admin Request message.

## Structure

`AdminRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `serviceIdentification` | `?string` | Optional | Identification of the administrative service to process.<br><br>**Constraints**: *Pattern*: `^.+$` | getServiceIdentification(): ?string | setServiceIdentification(?string serviceIdentification): void |

## Example

```php
use AdyenLib\Models\Builders\AdminRequest2Builder;

$adminRequest2 = AdminRequest2Builder::init()
    ->serviceIdentification('ServiceIdentification0')
    ->build();
```

