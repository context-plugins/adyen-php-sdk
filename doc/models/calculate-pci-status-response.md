
# Calculate Pci Status Response

## Structure

`CalculatePciStatusResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `signingRequired` | `?bool` | Optional | Indicates if the user is required to sign PCI questionnaires. If **false**, they do not need to sign any questionnaires. | getSigningRequired(): ?bool | setSigningRequired(?bool signingRequired): void |

## Example

```php
use AdyenLib\Models\Builders\CalculatePciStatusResponseBuilder;

$calculatePciStatusResponse = CalculatePciStatusResponseBuilder::init()
    ->signingRequired(false)
    ->build();
```

