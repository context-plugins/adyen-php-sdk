
# Network Reason 2

Contains information that explains why the transfer was rejected or returned by the network.

## Structure

`NetworkReason2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | The reason code provided by the network. | getCode(): ?string | setCode(?string code): void |
| `description` | `?string` | Optional | The description of the reason code. | getDescription(): ?string | setDescription(?string description): void |
| `namespace` | [`?string(NamespaceEnum)`](../../doc/models/m-namespace-enum.md) | Optional | The namespace that corresponds to the reason code.<br><br>Possible values:<br><br>* **ukFpsRejectionCode**<br>* **ukFpsReturnReasonCode**<br>* **usAchReturnReasonCode**<br>* **iso8583ResponseCode** | getNamespace(): ?string | setNamespace(?string namespace): void |

## Example

```php
use AdyenLib\Models\Builders\NetworkReason2Builder;
use AdyenLib\Models\NamespaceEnum;

$networkReason2 = NetworkReason2Builder::init()
    ->code('code4')
    ->description('description6')
    ->namespace(NamespaceEnum::UKFPSRETURNREASONCODE)
    ->build();
```

