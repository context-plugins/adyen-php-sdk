
# Onboarding Themes

## Structure

`OnboardingThemes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `next` | `?string` | Optional | The next page. Only present if there is a next page. | getNext(): ?string | setNext(?string next): void |
| `previous` | `?string` | Optional | The previous page. Only present if there is a previous page. | getPrevious(): ?string | setPrevious(?string previous): void |
| `themes` | [`OnboardingTheme[]`](../../doc/models/onboarding-theme.md) | Required | List of onboarding themes. | getThemes(): array | setThemes(array themes): void |

## Example

```php
use AdyenLib\Models\Builders\OnboardingThemesBuilder;
use AdyenLib\Models\Builders\OnboardingThemeBuilder;
use AdyenLib\Utils\DateTimeHelper;

$onboardingThemes = OnboardingThemesBuilder::init(
    [
        OnboardingThemeBuilder::init(
            DateTimeHelper::fromRfc3339DateTimeRequired('2016-03-13T12:52:32.123Z'),
            'id2',
            [
                'key0' => 'properties0'
            ]
        )
            ->description('description8')
            ->updatedAt(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
            ->build()
    ]
)
    ->next('next2')
    ->previous('previous2')
    ->build();
```

