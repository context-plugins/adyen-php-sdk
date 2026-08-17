
# KYC Check Summary

## Structure

`KYCCheckSummary`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kycCheckCode` | `?int` | Optional | The code of the check. For possible values, refer to [Verification codes](https://docs.adyen.com/classic-platforms/verification-process/verification-codes). | getKycCheckCode(): ?int | setKycCheckCode(?int kycCheckCode): void |
| `kycCheckDescription` | `?string` | Optional | A description of the check. | getKycCheckDescription(): ?string | setKycCheckDescription(?string kycCheckDescription): void |

## Example

```php
use AdyenLib\Models\Builders\KYCCheckSummaryBuilder;

$kYCCheckSummary = KYCCheckSummaryBuilder::init()
    ->kycCheckCode(70)
    ->kycCheckDescription('kycCheckDescription8')
    ->build();
```

