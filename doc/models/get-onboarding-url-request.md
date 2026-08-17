
# Get Onboarding Url Request

## Structure

`GetOnboardingUrlRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `string` | Required | The account holder code you provided when you created the account holder. | getAccountHolderCode(): string | setAccountHolderCode(string accountHolderCode): void |
| `collectInformation` | [`?CollectInformation1`](../../doc/models/collect-information-1.md) | Optional | Contains indicators whether the page should only collect information for specific [KYC checks](https://docs.adyen.com/classic-platforms/verification-checks). By default, the page collects information for all KYC checks that apply to the [legal entity type](https://docs.adyen.com/classic-platforms/account-holders-and-accounts#legal-entity-types). | getCollectInformation(): ?CollectInformation1 | setCollectInformation(?CollectInformation1 collectInformation): void |
| `editMode` | `?bool` | Optional | Indicates if editing checks is allowed even if all the checks have passed. | getEditMode(): ?bool | setEditMode(?bool editMode): void |
| `mobileOAuthCallbackUrl` | `?string` | Optional | The URL to which the account holder is redirected after completing an OAuth authentication with a bank through Trustly/PayMyBank. | getMobileOAuthCallbackUrl(): ?string | setMobileOAuthCallbackUrl(?string mobileOAuthCallbackUrl): void |
| `platformName` | `?string` | Optional | The platform name which will show up in the welcome page. | getPlatformName(): ?string | setPlatformName(?string platformName): void |
| `returnUrl` | `?string` | Optional | The URL where the account holder will be redirected back to after they complete the onboarding, or if their session times out. Maximum length of 500 characters. If you don't provide this, the account holder will be redirected back to the default return URL configured in your platform account. | getReturnUrl(): ?string | setReturnUrl(?string returnUrl): void |
| `shopperLocale` | `?string` | Optional | The language to be used in the page, specified by a combination of a language and country code. For example, **pt-BR**.<br><br>If not specified in the request or if the language is not supported, the page uses the browser language. If the browser language is not supported, the page uses **en-US** by default.<br><br>For a list of supported languages, refer to [Change the page language](https://docs.adyen.com/classic-platforms/hosted-onboarding-page/customize-experience#change-page-language). | getShopperLocale(): ?string | setShopperLocale(?string shopperLocale): void |
| `showPages` | [`?ShowPages2`](../../doc/models/show-pages-2.md) | Optional | Contains indicators whether specific pages must be shown to the account holder. | getShowPages(): ?ShowPages2 | setShowPages(?ShowPages2 showPages): void |

## Example

```php
use AdyenLib\Models\Builders\GetOnboardingUrlRequestBuilder;
use AdyenLib\Models\Builders\CollectInformation1Builder;

$getOnboardingUrlRequest = GetOnboardingUrlRequestBuilder::init(
    'accountHolderCode4'
)
    ->collectInformation(
        CollectInformation1Builder::init()
            ->bankDetails(false)
            ->businessDetails(false)
            ->individualDetails(false)
            ->legalArrangementDetails(false)
            ->pciQuestionnaire(false)
            ->build()
    )
    ->editMode(false)
    ->mobileOAuthCallbackUrl('mobileOAuthCallbackUrl2')
    ->platformName('platformName6')
    ->returnUrl('returnUrl2')
    ->build();
```

