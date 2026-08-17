
# Get Pci Questionnaire Infos Response

## Structure

`GetPciQuestionnaireInfosResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(PciDocumentInfo[])`](../../doc/models/pci-document-info.md) | Optional | Information about the signed PCI questionnaires. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\GetPciQuestionnaireInfosResponseBuilder;
use AdyenLib\Models\Builders\PciDocumentInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;

$getPciQuestionnaireInfosResponse = GetPciQuestionnaireInfosResponseBuilder::init()
    ->data(
        [
            PciDocumentInfoBuilder::init()
                ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id0')
                ->validUntil(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->build(),
            PciDocumentInfoBuilder::init()
                ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->id('id0')
                ->validUntil(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                ->build()
        ]
    )
    ->build();
```

