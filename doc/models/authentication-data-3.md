
# Authentication Data 3

Data for 3DS authentication.

## Structure

`AuthenticationData3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attemptAuthentication` | [`?string(AttemptAuthenticationEnum)`](../../doc/models/attempt-authentication-enum.md) | Optional | Indicates when 3D Secure authentication should be attempted. This overrides all other rules, including [Dynamic 3D Secure settings](https://docs.adyen.com/risk-management/dynamic-3d-secure).<br><br>Possible values:<br><br>* **always**: Perform 3D Secure authentication.<br>* **never**: Don't perform 3D Secure authentication. If PSD2 SCA or other national regulations require authentication, the transaction gets declined. | getAttemptAuthentication(): ?string | setAttemptAuthentication(?string attemptAuthentication): void |
| `authenticationOnly` | `?bool` | Optional | Required to trigger the [authentication-only flow](https://docs.adyen.com/online-payments/3d-secure/authentication-only/). If set to **true**, you will only perform the 3D Secure 2 authentication, and will not proceed to the payment authorization.<br>Default: **false**.<br><br>**Default**: `false` | getAuthenticationOnly(): ?bool | setAuthenticationOnly(?bool authenticationOnly): void |
| `threeDSRequestData` | [`?ThreeDSRequestData2`](../../doc/models/three-ds-request-data-2.md) | Optional | Object with additional parameters for the 3D Secure authentication flow. | getThreeDSRequestData(): ?ThreeDSRequestData2 | setThreeDSRequestData(?ThreeDSRequestData2 threeDSRequestData): void |

## Example

```php
use AdyenLib\Models\Builders\AuthenticationData3Builder;
use AdyenLib\Models\AttemptAuthenticationEnum;
use AdyenLib\Models\Builders\ThreeDSRequestData2Builder;
use AdyenLib\Models\ChallengeWindowSizeEnum;
use AdyenLib\Models\DataOnlyEnum;
use AdyenLib\Models\NativeThreeDSEnum;
use AdyenLib\Models\ThreeDSVersionEnum;

$authenticationData3 = AuthenticationData3Builder::init()
    ->attemptAuthentication(AttemptAuthenticationEnum::ALWAYS)
    ->authenticationOnly(false)
    ->threeDSRequestData(
        ThreeDSRequestData2Builder::init()
            ->challengeWindowSize(ChallengeWindowSizeEnum::ENUM_03)
            ->dataOnly(DataOnlyEnum::FALSE)
            ->nativeThreeDS(NativeThreeDSEnum::PREFERRED)
            ->threeDSVersion(ThreeDSVersionEnum::ENUM_210)
            ->build()
    )
    ->build();
```

