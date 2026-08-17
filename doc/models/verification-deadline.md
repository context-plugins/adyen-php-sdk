
# Verification Deadline

## Structure

`VerificationDeadline`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capabilities` | [`string(CapabilityEnum)[]`](../../doc/models/capability-enum.md) | Required, Read-only | The names of the capabilities to be disallowed. | getCapabilities(): array | setCapabilities(array capabilities): void |
| `entityIds` | `?(string[])` | Optional, Read-only | The unique identifiers of the bank account(s) that the deadline applies to | getEntityIds(): ?array | setEntityIds(?array entityIds): void |
| `expiresAt` | `DateTime` | Required, Read-only | The date that verification is due by before capabilities are disallowed. | getExpiresAt(): \DateTime | setExpiresAt(\DateTime expiresAt): void |

## Example

```php
use AdyenLib\Models\Builders\VerificationDeadlineBuilder;

$verificationDeadline = VerificationDeadlineBuilder::init(
    [],
    new \DateTime()
)->build();
```

