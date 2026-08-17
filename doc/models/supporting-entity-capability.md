
# Supporting Entity Capability

## Structure

`SupportingEntityCapability`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowed` | `?bool` | Optional, Read-only | Indicates whether the capability is allowed for the supporting entity.<br><br>If a capability is allowed for a supporting entity but not for the parent legal entity, this means the legal entity has other supporting entities that failed verification.<br><br>**You can use the allowed supporting entity** regardless of the verification status of other supporting entities. | getAllowed(): ?bool | setAllowed(?bool allowed): void |
| `id` | `?string` | Optional, Read-only | Supporting entity reference | getId(): ?string | setId(?string id): void |
| `requested` | `?bool` | Optional, Read-only | Indicates whether the supporting entity capability is requested. | getRequested(): ?bool | setRequested(?bool requested): void |
| `verificationStatus` | `?string` | Optional, Read-only | The status of the verification checks for the capability of the supporting entity.<br><br>Possible values:<br><br>* **pending**: Adyen is running the verification.<br><br>* **invalid**: The verification failed. Check if the `errors` array contains more information.<br><br>* **valid**: The verification has been successfully completed.<br><br>* **rejected**: Adyen has verified the information, but found reasons to not allow the capability. | getVerificationStatus(): ?string | setVerificationStatus(?string verificationStatus): void |

## Example

```php
use AdyenLib\Models\Builders\SupportingEntityCapabilityBuilder;

$supportingEntityCapability = SupportingEntityCapabilityBuilder::init()->build();
```

