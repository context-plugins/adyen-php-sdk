
# Pci Signing Request

## Structure

`PciSigningRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pciTemplateReferences` | `string[]` | Required | The array of Adyen-generated unique identifiers for the questionnaires. | getPciTemplateReferences(): array | setPciTemplateReferences(array pciTemplateReferences): void |
| `signedBy` | `string` | Required | The [legal entity ID](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/legalEntities__resParam_id) of the individual who signs the PCI questionnaire. | getSignedBy(): string | setSignedBy(string signedBy): void |

## Example

```php
use AdyenLib\Models\Builders\PciSigningRequestBuilder;

$pciSigningRequest = PciSigningRequestBuilder::init(
    [
        'pciTemplateReferences8',
        'pciTemplateReferences9',
        'pciTemplateReferences0'
    ],
    'signedBy2'
)->build();
```

