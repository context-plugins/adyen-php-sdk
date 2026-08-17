
# Sca on Approval Enum

Shows the status of the Strong Customer Authentication (SCA) process.

Possible values: **required**, **notApplicable**.

## Enumeration

`ScaOnApprovalEnum`

## Fields

| Name |
|  --- |
| `COMPLETED` |
| `NOTAPPLICABLE` |
| `REQUIRED` |

## Example

```php
use AdyenLib\Models\ScaOnApprovalEnum;

$scaOnApproval = ScaOnApprovalEnum::NOTAPPLICABLE;
```

