
# Pci Signing Response

## Structure

`PciSigningResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `pciQuestionnaireIds` | `?(string[])` | Optional | The unique identifiers of the signed PCI documents. | getPciQuestionnaireIds(): ?array | setPciQuestionnaireIds(?array pciQuestionnaireIds): void |
| `signedBy` | `?string` | Optional | The [legal entity ID](https://docs.adyen.com/api-explorer/#/legalentity/latest/post/legalEntities__resParam_id) of the individual who signed the PCI questionnaire. | getSignedBy(): ?string | setSignedBy(?string signedBy): void |

## Example

```php
use AdyenLib\Models\Builders\PciSigningResponseBuilder;

$pciSigningResponse = PciSigningResponseBuilder::init()
    ->pciQuestionnaireIds(
        [
            'pciQuestionnaireIds7',
            'pciQuestionnaireIds8'
        ]
    )
    ->signedBy('signedBy4')
    ->build();
```

