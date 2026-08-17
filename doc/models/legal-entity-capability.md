
# Legal Entity Capability

## Structure

`LegalEntityCapability`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowed` | `?bool` | Optional, Read-only | Indicates whether the capability is allowed. Adyen sets this to **true** if the verification is successful. | getAllowed(): ?bool | setAllowed(?bool allowed): void |
| `allowedLevel` | [`?string(AllowedLevelEnum)`](../../doc/models/allowed-level-enum.md) | Optional, Read-only | The capability level that is allowed for the legal entity.<br><br>Possible values: **notApplicable**, **low**, **medium**, **high**. | getAllowedLevel(): ?string | setAllowedLevel(?string allowedLevel): void |
| `allowedSettings` | [`?CapabilitySettings11`](../../doc/models/capability-settings-11.md) | Optional | The settings that are allowed for the legal entity. | getAllowedSettings(): ?CapabilitySettings11 | setAllowedSettings(?CapabilitySettings11 allowedSettings): void |
| `requested` | `?bool` | Optional, Read-only | Indicates whether the capability is requested. To check whether the legal entity is permitted to use the capability, refer to the `allowed` field. | getRequested(): ?bool | setRequested(?bool requested): void |
| `requestedLevel` | [`?string(AllowedLevelEnum)`](../../doc/models/allowed-level-enum.md) | Optional, Read-only | The requested level of the capability. Some capabilities, such as those used in [card issuing](https://docs.adyen.com/issuing/add-capabilities#capability-levels), have different levels. Levels increase the capability, but also require additional checks and increased monitoring.<br><br>Possible values: **notApplicable**, **low**, **medium**, **high**. | getRequestedLevel(): ?string | setRequestedLevel(?string requestedLevel): void |
| `requestedSettings` | [`?CapabilitySettings21`](../../doc/models/capability-settings-21.md) | Optional | The settings that are requested for the legal entity. | getRequestedSettings(): ?CapabilitySettings21 | setRequestedSettings(?CapabilitySettings21 requestedSettings): void |
| `transferInstruments` | [`?(SupportingEntityCapability[])`](../../doc/models/supporting-entity-capability.md) | Optional, Read-only | The capability status of transfer instruments associated with the legal entity. | getTransferInstruments(): ?array | setTransferInstruments(?array transferInstruments): void |
| `verificationStatus` | `?string` | Optional, Read-only | The status of the verification checks for the capability.<br><br>Possible values:<br><br>* **pending**: Adyen is running the verification.<br><br>* **invalid**: The verification failed. Check if the `errors` array contains more information.<br><br>* **valid**: The verification has been successfully completed.<br><br>* **rejected**: Adyen has verified the information, but found reasons to not allow the capability. | getVerificationStatus(): ?string | setVerificationStatus(?string verificationStatus): void |

## Example

```php
use AdyenLib\Models\Builders\LegalEntityCapabilityBuilder;
use AdyenLib\Models\Builders\CapabilitySettings11Builder;
use AdyenLib\Models\Builders\PatchableAmountDTOBuilder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\IntervalEnum;

$legalEntityCapability = LegalEntityCapabilityBuilder::init()
    ->allowedSettings(
        CapabilitySettings11Builder::init()
            ->amountPerIndustry(
                [
                    'key0' => PatchableAmountDTOBuilder::init()
                        ->currency('currency8')
                        ->value(56)
                        ->build(),
                    'key1' => PatchableAmountDTOBuilder::init()
                        ->currency('currency8')
                        ->value(56)
                        ->build()
                ]
            )
            ->authorizedCardUsers(false)
            ->fundingSource(
                [
                    FundingSourceEnum::CREDIT,
                    FundingSourceEnum::DEBIT,
                    FundingSourceEnum::PREPAID
                ]
            )
            ->interval(IntervalEnum::DAILY)
            ->maxAmount(
                PatchableAmountDTOBuilder::init()
                    ->currency('currency4')
                    ->value(160)
                    ->build()
            )
            ->build()
    )
    ->build();
```

