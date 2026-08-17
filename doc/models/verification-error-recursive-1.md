
# Verification Error Recursive 1

## Structure

`VerificationErrorRecursive1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capabilities` | [`?(string(CapabilityEnum)[])`](../../doc/models/capability-enum.md) | Optional | Contains key-value pairs that specify the actions that the legal entity can do in your platform. The key is a capability required for your integration. For example, **issueCard** for Issuing.The value is an object containing the settings for the capability. | getCapabilities(): ?array | setCapabilities(?array capabilities): void |
| `code` | `?string` | Optional | The general error code. | getCode(): ?string | setCode(?string code): void |
| `message` | `?string` | Optional | The general error message. | getMessage(): ?string | setMessage(?string message): void |
| `type` | [`?string(Type512Enum)`](../../doc/models/type-512-enum.md) | Optional | The type of error.<br><br>Possible values:<br><br>* **invalidInput**<br>* **dataMissing**<br>* **pendingStatus**<br>* **rejected**<br>* **dataReview** | getType(): ?string | setType(?string type): void |
| `remediatingActions` | [`?(RemediatingAction[])`](../../doc/models/remediating-action.md) | Optional | An object containing possible solutions to fix a verification error. | getRemediatingActions(): ?array | setRemediatingActions(?array remediatingActions): void |

## Example

```php
use AdyenLib\Models\Builders\VerificationErrorRecursive1Builder;
use AdyenLib\Models\CapabilityEnum;
use AdyenLib\Models\Type512Enum;
use AdyenLib\Models\Builders\RemediatingActionBuilder;

$verificationErrorRecursive1 = VerificationErrorRecursive1Builder::init()
    ->capabilities(
        [
            CapabilityEnum::RECEIVEFROMTRANSFERINSTRUMENT
        ]
    )
    ->code('code6')
    ->message('message8')
    ->type(Type512Enum::INVALIDINPUT)
    ->remediatingActions(
        [
            RemediatingActionBuilder::init()
                ->code('code4')
                ->message('message6')
                ->build(),
            RemediatingActionBuilder::init()
                ->code('code4')
                ->message('message6')
                ->build()
        ]
    )
    ->build();
```

