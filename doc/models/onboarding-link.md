
# Onboarding Link

## Structure

`OnboardingLink`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `url` | `?string` | Optional | The URL of the hosted onboarding page where you need to redirect your user. This URL:<br><br>- Expires after 4 minutes.<br><br>- Can only be used once.<br><br>- Can only be clicked once by the user.<br><br>If the link expires, you need to create a new link. | getUrl(): ?string | setUrl(?string url): void |

## Example

```php
use AdyenLib\Models\Builders\OnboardingLinkBuilder;

$onboardingLink = OnboardingLinkBuilder::init()
    ->url('url2')
    ->build();
```

