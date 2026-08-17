
# Passcodes

## Structure

`Passcodes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `adminMenuPin` | `?string` | Optional | The passcode for the Admin menu and the Settings menu.<br><br>**Constraints**: *Maximum Length*: `6` | getAdminMenuPin(): ?string | setAdminMenuPin(?string adminMenuPin): void |
| `refundPin` | `?string` | Optional | The passcode for referenced and unreferenced refunds on standalone terminals.<br><br>**Constraints**: *Maximum Length*: `6` | getRefundPin(): ?string | setRefundPin(?string refundPin): void |
| `screenLockPin` | `?string` | Optional | The passcode to unlock the terminal screen after a timeout.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `6` | getScreenLockPin(): ?string | setScreenLockPin(?string screenLockPin): void |
| `txMenuPin` | `?string` | Optional | The passcode for the Transactions menu.<br><br>**Constraints**: *Maximum Length*: `6` | getTxMenuPin(): ?string | setTxMenuPin(?string txMenuPin): void |

## Example

```php
use AdyenLib\Models\Builders\PasscodesBuilder;

$passcodes = PasscodesBuilder::init()
    ->adminMenuPin('adminMenuPin0')
    ->refundPin('refundPin4')
    ->screenLockPin('screenLockPin4')
    ->txMenuPin('txMenuPin4')
    ->build();
```

