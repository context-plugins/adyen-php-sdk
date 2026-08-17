
# Account Holder Capability

## Structure

`AccountHolderCapability`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowed` | `?bool` | Optional, Read-only | Indicates whether the capability is allowed. Adyen sets this to **true** if the verification is successful and the account holder is permitted to use the capability. | getAllowed(): ?bool | setAllowed(?bool allowed): void |
| `allowedLevel` | [`?string(AllowedLevelEnum)`](../../doc/models/allowed-level-enum.md) | Optional, Read-only | The capability level that is allowed for the account holder.<br><br>Possible values: **notApplicable**, **low**, **medium**, **high**. | getAllowedLevel(): ?string | setAllowedLevel(?string allowedLevel): void |
| `allowedSettings` | [`?CapabilitySettings3`](../../doc/models/capability-settings-3.md) | Optional | A JSON object containing the settings that are allowed for the account holder. | getAllowedSettings(): ?CapabilitySettings3 | setAllowedSettings(?CapabilitySettings3 allowedSettings): void |
| `enabled` | `?bool` | Optional | Indicates whether the capability is enabled. If **false**, the capability is temporarily disabled for the account holder. | getEnabled(): ?bool | setEnabled(?bool enabled): void |
| `problems` | [`?(CapabilityProblem[])`](../../doc/models/capability-problem.md) | Optional, Read-only | Contains verification errors and the actions that you can take to resolve them. | getProblems(): ?array | setProblems(?array problems): void |
| `requested` | `?bool` | Optional | Indicates whether the capability is requested. To check whether the account holder is permitted to use the capability, refer to the `allowed` field. | getRequested(): ?bool | setRequested(?bool requested): void |
| `requestedLevel` | [`?string(RequestedLevelEnum)`](../../doc/models/requested-level-enum.md) | Optional | The requested level of the capability. Some capabilities, such as those used in [card issuing](https://docs.adyen.com/issuing/add-capabilities#capability-levels), have different levels. Levels increase the capability, but also require additional checks and increased monitoring.<br><br>Possible values: **notApplicable**, **low**, **medium**, **high**. | getRequestedLevel(): ?string | setRequestedLevel(?string requestedLevel): void |
| `requestedSettings` | [`?CapabilitySettings1`](../../doc/models/capability-settings-1.md) | Optional | A JSON object containing the settings that were requested for the account holder. | getRequestedSettings(): ?CapabilitySettings1 | setRequestedSettings(?CapabilitySettings1 requestedSettings): void |
| `transferInstruments` | [`?(AccountSupportingEntityCapability[])`](../../doc/models/account-supporting-entity-capability.md) | Optional, Read-only | Contains the status of the transfer instruments associated with this capability. | getTransferInstruments(): ?array | setTransferInstruments(?array transferInstruments): void |
| `verificationStatus` | [`?string(VerificationStatusEnum)`](../../doc/models/verification-status-enum.md) | Optional, Read-only | The status of the verification checks for the capability.<br><br>Possible values:<br><br>* **pending**: Adyen is running the verification.<br><br>* **invalid**: The verification failed. Check if the `errors` array contains more information.<br><br>* **valid**: The verification has been successfully completed.<br><br>* **rejected**: Adyen has verified the information, but found reasons to not allow the capability. | getVerificationStatus(): ?string | setVerificationStatus(?string verificationStatus): void |

## Example

```php
use AdyenLib\Models\Builders\AccountHolderCapabilityBuilder;
use AdyenLib\Models\Builders\CapabilitySettings3Builder;
use AdyenLib\Models\Builders\Amount17Builder;
use AdyenLib\Models\FundingSourceEnum;
use AdyenLib\Models\IntervalEnum;

$accountHolderCapability = AccountHolderCapabilityBuilder::init()
    ->allowedSettings(
        CapabilitySettings3Builder::init()
            ->amountPerIndustry(
                [
                    'key0' => Amount17Builder::init(
                        'currency8',
                        56
                    )->build(),
                    'key1' => Amount17Builder::init(
                        'currency8',
                        56
                    )->build()
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
                Amount17Builder::init(
                    'currency4',
                    160
                )->build()
            )->build()
    )
    ->enabled(false)
    ->build();
```

