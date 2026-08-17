
# Admin Request

Empty.
Content of the Custom Admin Request message.

## Structure

`AdminRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `serviceIdentification` | `?string` | Optional | Identification of the administrative service to process.<br><br>**Constraints**: *Pattern*: `^.+$` | getServiceIdentification(): ?string | setServiceIdentification(?string serviceIdentification): void |

## Example

```php
use AdyenLib\Models\Builders\AdminRequestBuilder;

$adminRequest = AdminRequestBuilder::init()
    ->serviceIdentification('ServiceIdentification4')
    ->build();
```

