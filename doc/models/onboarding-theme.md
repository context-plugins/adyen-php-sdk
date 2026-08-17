
# Onboarding Theme

## Structure

`OnboardingTheme`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `DateTime` | Required | The creation date of the theme. | getCreatedAt(): \DateTime | setCreatedAt(\DateTime createdAt): void |
| `description` | `?string` | Optional | The description of the theme. | getDescription(): ?string | setDescription(?string description): void |
| `id` | `string` | Required | The unique identifier of the theme. | getId(): string | setId(string id): void |
| `properties` | `array<string,string>` | Required | The properties of the theme. | getProperties(): array | setProperties(array properties): void |
| `updatedAt` | `?DateTime` | Optional | The date when the theme was last updated. | getUpdatedAt(): ?\DateTime | setUpdatedAt(?\DateTime updatedAt): void |

## Example

```php
use AdyenLib\Models\Builders\OnboardingThemeBuilder;
use AdyenLib\Utils\DateTimeHelper;

$onboardingTheme = OnboardingThemeBuilder::init(
    DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
    'id6',
    [
        'key0' => 'properties4',
        'key1' => 'properties5',
        'key2' => 'properties6'
    ]
)
    ->description('description4')
    ->updatedAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
    ->build();
```

