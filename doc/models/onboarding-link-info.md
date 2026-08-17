
# Onboarding Link Info

## Structure

`OnboardingLinkInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locale` | `?string` | Optional | The language that will be used for the page, specified by a combination of two letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language and [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country codes. See possible valuesfor [marketplaces](https://docs.adyen.com/marketplaces/onboard-users/hosted#supported-languages) or [platforms](https://docs.adyen.com/platforms/onboard-users/hosted#supported-languages).<br><br>If not specified in the request or if the language is not supported, the page uses the browser language. If the browser language is not supported, the page uses **en-US** by default. | getLocale(): ?string | setLocale(?string locale): void |
| `redirectUrl` | `?string` | Optional | The URL where the user is redirected after they complete hosted onboarding. | getRedirectUrl(): ?string | setRedirectUrl(?string redirectUrl): void |
| `settings` | [`?OnboardingLinkSettings2`](../../doc/models/onboarding-link-settings-2.md) | Optional | Key-value pairs indicating the settings for the hosted onboarding page. The key represents a specific setting. | getSettings(): ?OnboardingLinkSettings2 | setSettings(?OnboardingLinkSettings2 settings): void |
| `themeId` | `?string` | Optional | The unique identifier of the hosted onboarding theme. | getThemeId(): ?string | setThemeId(?string themeId): void |

## Example

```php
use AdyenLib\Models\Builders\OnboardingLinkInfoBuilder;
use AdyenLib\Models\Builders\OnboardingLinkSettings2Builder;

$onboardingLinkInfo = OnboardingLinkInfoBuilder::init()
    ->locale('locale8')
    ->redirectUrl('redirectUrl6')
    ->settings(
        OnboardingLinkSettings2Builder::init()
            ->acceptedCountries(
                [
                    'acceptedCountries9',
                    'acceptedCountries0'
                ]
            )
            ->allowBankAccountFormatSelection(false)
            ->allowDebugUi(false)
            ->allowIntraRegionCrossBorderPayout(false)
            ->changeLegalEntityType(false)
            ->build()
    )
    ->themeId('themeId4')
    ->build();
```

