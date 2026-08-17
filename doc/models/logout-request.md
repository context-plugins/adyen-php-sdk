
# Logout Request

Empty.
Content of the Logout Request message.

## Structure

`LogoutRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maintenanceAllowed` | `?bool` | Optional | Indicates that the POI terminal is able to or has to go to maintenance. Sent in the Logout Request to express that after closing the session, the POI may go to maintenance.<br><br>**Default**: `false` | getMaintenanceAllowed(): ?bool | setMaintenanceAllowed(?bool maintenanceAllowed): void |

## Example

```php
use AdyenLib\Models\Builders\LogoutRequestBuilder;

$logoutRequest = LogoutRequestBuilder::init()
    ->maintenanceAllowed(false)
    ->build();
```

