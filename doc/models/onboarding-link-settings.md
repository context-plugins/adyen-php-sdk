
# Onboarding Link Settings

## Structure

`OnboardingLinkSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acceptedCountries` | `?(string[])` | Optional | The list of countries the user can choose from in hosted onboarding when `editPrefilledCountry` is allowed.<br><br>The value must be in the two-character [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code format.<br><br>The array is empty by default, allowing all [countries and regions supported by hosted onboarding](https://docs.adyen.com/platforms/onboard-users/#hosted-onboarding). | getAcceptedCountries(): ?array | setAcceptedCountries(?array acceptedCountries): void |
| `allowBankAccountFormatSelection` | `?bool` | Optional | Default value: **false**<br><br>Indicates if the user can select the format for their payout account (if applicable). | getAllowBankAccountFormatSelection(): ?bool | setAllowBankAccountFormatSelection(?bool allowBankAccountFormatSelection): void |
| `allowDebugUi` | `?bool` | Optional | Default value: **true**<br><br>Indicates whether the debug user interface (UI) is enabled. The debug UI provides information for your support staff to diagnose and resolve user issues during onboarding. It can be accessed using a keyboard shortcut. | getAllowDebugUi(): ?bool | setAllowDebugUi(?bool allowDebugUi): void |
| `allowIntraRegionCrossBorderPayout` | `?bool` | Optional | Default value: **false**<br><br>Indicates if the user can select a payout account in a different EU/EEA location (including Switzerland and the UK) than the location of their legal entity. | getAllowIntraRegionCrossBorderPayout(): ?bool | setAllowIntraRegionCrossBorderPayout(?bool allowIntraRegionCrossBorderPayout): void |
| `changeLegalEntityType` | `?bool` | Optional | Default value: **true**<br><br>Indicates if the user can change their legal entity type. | getChangeLegalEntityType(): ?bool | setChangeLegalEntityType(?bool changeLegalEntityType): void |
| `editPrefilledCountry` | `?bool` | Optional | Default value: **true**<br><br>Indicates if the user can change the country of their legal entity's address, for example the registered address of an organization. | getEditPrefilledCountry(): ?bool | setEditPrefilledCountry(?bool editPrefilledCountry): void |
| `enforceLegalAge` | `?bool` | Optional | Default value: **false**<br><br>Indicates if only users above the age of 18 can be onboarded. | getEnforceLegalAge(): ?bool | setEnforceLegalAge(?bool enforceLegalAge): void |
| `hideOnboardingIntroductionIndividual` | `?bool` | Optional | Default value: **true**<br><br>Indicates whether the introduction screen is hidden for the user of the individual legal entity type.<br>The introduction screen provides brief instructions for the subsequent steps in the hosted onboarding process. | getHideOnboardingIntroductionIndividual(): ?bool | setHideOnboardingIntroductionIndividual(?bool hideOnboardingIntroductionIndividual): void |
| `hideOnboardingIntroductionOrganization` | `?bool` | Optional | Default value: **true**<br><br>Indicates whether the introduction screen is hidden for the user of the organization legal entity type.<br>The introduction screen provides brief instructions for the subsequent steps in the hosted onboarding process. | getHideOnboardingIntroductionOrganization(): ?bool | setHideOnboardingIntroductionOrganization(?bool hideOnboardingIntroductionOrganization): void |
| `hideOnboardingIntroductionSoleProprietor` | `?bool` | Optional | Default value: **true**<br><br>Indicates whether the introduction screen is hidden for the user of the sole proprietorship legal entity type.<br>The introduction screen provides brief instructions for the subsequent steps in the hosted onboarding process. | getHideOnboardingIntroductionSoleProprietor(): ?bool | setHideOnboardingIntroductionSoleProprietor(?bool hideOnboardingIntroductionSoleProprietor): void |
| `hideOnboardingIntroductionTrust` | `?bool` | Optional | Default value: **true**<br><br>Indicates whether the introduction screen is hidden for the user of the trust legal entity type.<br>The introduction screen provides brief instructions for the subsequent steps in the hosted onboarding process. | getHideOnboardingIntroductionTrust(): ?bool | setHideOnboardingIntroductionTrust(?bool hideOnboardingIntroductionTrust): void |
| `instantBankVerification` | `?bool` | Optional | Default value: **true**<br><br>Indicates if the user can initiate the verification process through open banking providers, like Plaid or Tink. | getInstantBankVerification(): ?bool | setInstantBankVerification(?bool instantBankVerification): void |
| `requirePciSignEcomMoto` | `?bool` | Optional | Default value: **false**<br><br>Indicates if the user is required to sign a PCI questionnaires for the **ecomMoto** sales channel type. | getRequirePciSignEcomMoto(): ?bool | setRequirePciSignEcomMoto(?bool requirePciSignEcomMoto): void |
| `requirePciSignEcommerce` | `?bool` | Optional | Default value: **false**<br><br>Indicates if the user is required to sign a PCI questionnaires for the **eCommerce** sales channel type. | getRequirePciSignEcommerce(): ?bool | setRequirePciSignEcommerce(?bool requirePciSignEcommerce): void |
| `requirePciSignPos` | `?bool` | Optional | Default value: **false**<br><br>Indicates if the user is required to sign a PCI questionnaires for the **pos** sales channel type. | getRequirePciSignPos(): ?bool | setRequirePciSignPos(?bool requirePciSignPos): void |
| `requirePciSignPosMoto` | `?bool` | Optional | Default value: **false**<br><br>Indicates if the user is required to sign a PCI questionnaires for the **posMoto** sales channel type. | getRequirePciSignPosMoto(): ?bool | setRequirePciSignPosMoto(?bool requirePciSignPosMoto): void |
| `transferInstrumentLimit` | `?int` | Optional | The maximum number of transfer instruments the user can create. | getTransferInstrumentLimit(): ?int | setTransferInstrumentLimit(?int transferInstrumentLimit): void |

## Example

```php
use AdyenLib\Models\Builders\OnboardingLinkSettingsBuilder;

$onboardingLinkSettings = OnboardingLinkSettingsBuilder::init()
    ->acceptedCountries(
        [
            'acceptedCountries9'
        ]
    )
    ->allowBankAccountFormatSelection(false)
    ->allowDebugUi(false)
    ->allowIntraRegionCrossBorderPayout(false)
    ->changeLegalEntityType(false)
    ->build();
```

