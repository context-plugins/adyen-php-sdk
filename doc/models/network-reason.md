
# Network Reason

## Structure

`NetworkReason`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The reason code provided by the network. | getCode(): ?string | setCode(?string code): void |
| `description` | `?string` | Optional | The description of the reason code. | getDescription(): ?string | setDescription(?string description): void |
| `namespace` | [`?string(NamespaceEnum)`](../../doc/models/m-namespace-enum.md) | Optional | The namespace that corresponds to the reason code.<br><br>Possible values:<br><br>* **ukFpsRejectionCode**<br>* **ukFpsReturnReasonCode**<br>* **usAchReturnReasonCode**<br>* **iso8583ResponseCode** | getNamespace(): ?string | setNamespace(?string namespace): void |

## Example

```php
use AdyenLib\Models\Builders\NetworkReasonBuilder;
use AdyenLib\Models\NamespaceEnum;

$networkReason = NetworkReasonBuilder::init()
    ->code('code0')
    ->description('description2')
    ->namespace(NamespaceEnum::UKFPSRETURNREASONCODE)
    ->build();
```

