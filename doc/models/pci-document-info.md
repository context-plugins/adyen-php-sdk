
# Pci Document Info

## Structure

`PciDocumentInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?DateTime` | Optional | The date the questionnaire was created, in ISO 8601 extended format. For example, 2022-12-18T10:15:30+01:00 | getCreatedAt(): ?\DateTime | setCreatedAt(?\DateTime createdAt): void |
| `id` | `?string` | Optional | The unique identifier of the signed questionnaire. | getId(): ?string | setId(?string id): void |
| `validUntil` | `?DateTime` | Optional | The expiration date of the questionnaire, in ISO 8601 extended format. For example, 2022-12-18T10:15:30+01:00 | getValidUntil(): ?\DateTime | setValidUntil(?\DateTime validUntil): void |

## Example

```php
use AdyenLib\Models\Builders\PciDocumentInfoBuilder;
use AdyenLib\Utils\DateTimeHelper;

$pciDocumentInfo = PciDocumentInfoBuilder::init()
    ->createdAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->id('id4')
    ->validUntil(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

