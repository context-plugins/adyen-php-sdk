
# Routing Details

## Structure

`RoutingDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | A human-readable explanation specific to this occurrence of the problem. | getDetail(): ?string | setDetail(?string detail): void |
| `errorCode` | `?string` | Optional | A code that identifies the problem type. | getErrorCode(): ?string | setErrorCode(?string errorCode): void |
| `priority` | [`?string(Priority1Enum)`](../../doc/models/priority-1-enum.md) | Optional | The priority for the bank transfer. This sets the speed at which the transfer is sent and the fees that you have to pay. Required for transfers with `category` **bank**.<br><br>Possible values:<br><br>* **regular**: For normal, low-value transactions.<br><br>* **fast**: A faster way to transfer funds, but the fees are higher. Recommended for high-priority, low-value transactions.<br><br>* **wire**: The fastest way to transfer funds, but this has the highest fees. Recommended for high-priority, high-value transactions.<br><br>* **instant**: For instant funds transfers within the United States and in [SEPA locations](https://www.ecb.europa.eu/paym/integration/retail/sepa/html/index.en.html).<br><br>* **crossBorder**: For high-value transfers to a recipient in a different country.<br><br>* **internal**: For transfers to an Adyen-issued business bank account (by bank account number/IBAN). | getPriority(): ?string | setPriority(?string priority): void |
| `title` | `?string` | Optional | A short, human-readable summary of the problem type. | getTitle(): ?string | setTitle(?string title): void |

## Example

```php
use AdyenLib\Models\Builders\RoutingDetailsBuilder;
use AdyenLib\Models\Priority1Enum;

$routingDetails = RoutingDetailsBuilder::init()
    ->detail('detail4')
    ->errorCode('errorCode4')
    ->priority(Priority1Enum::CROSSBORDER)
    ->title('title4')
    ->build();
```

