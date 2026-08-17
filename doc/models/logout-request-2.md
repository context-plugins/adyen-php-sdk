
# Logout Request 2

Content of the Logout Request message.

## Structure

`LogoutRequest2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maintenanceAllowed` | `?bool` | Optional | Indicates that the POI terminal is able to or has to go to maintenance. Sent in the Logout Request to express that after closing the session, the POI may go to maintenance.<br><br>**Default**: `false` | getMaintenanceAllowed(): ?bool | setMaintenanceAllowed(?bool maintenanceAllowed): void |

## Example

```php
use AdyenLib\Models\Builders\LogoutRequest2Builder;

$logoutRequest2 = LogoutRequest2Builder::init()
    ->maintenanceAllowed(false)
    ->build();
```

