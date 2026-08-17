
# Generate Pci Description Response

## Structure

`GeneratePciDescriptionResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `content` | `?string` | Optional | The generated questionnaires in a base64 encoded format. | getContent(): ?string | setContent(?string content): void |
| `language` | `?string` | Optional | The two-letter [ISO-639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code for the questionnaire. For example, **en**. | getLanguage(): ?string | setLanguage(?string language): void |
| `pciTemplateReferences` | `?(string[])` | Optional | The array of Adyen-generated unique identifiers for the questionnaires. If empty, the user is not required to sign questionnaires. | getPciTemplateReferences(): ?array | setPciTemplateReferences(?array pciTemplateReferences): void |

## Example

```php
use AdyenLib\Models\Builders\GeneratePciDescriptionResponseBuilder;

$generatePciDescriptionResponse = GeneratePciDescriptionResponseBuilder::init()
    ->content('content0')
    ->language('language8')
    ->pciTemplateReferences(
        [
            'pciTemplateReferences6',
            'pciTemplateReferences7'
        ]
    )
    ->build();
```

