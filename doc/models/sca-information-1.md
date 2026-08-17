
# Sca Information 1

Information for the Strong Customer Authentication (SCA)

## Structure

`ScaInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `exemption` | [`?string(ScaExemptionEnum)`](../../doc/models/sca-exemption-enum.md) | Optional | The type of exemption for Strong Customer Authentication (SCA). Possible values:<br><br>* **lowerLimit**: the newly created limit is lower than the existing limit.<br>* **notRegulated**: the limit is created in a country, region, or industry where it is not mandated by law to use SCA.<br>* **setByPlatform**: you set a limit for one of your user's balance accounts, or for your balance platform.<br>* **initialLimit**: there are no existing transfer limits set on the balance account or balance platform.<br>* **alreadyPerformed**: you are confident about your user's identity and do not need to verify this using SCA. | getExemption(): ?string | setExemption(?string exemption): void |
| `status` | [`string(ScaStatusEnum)`](../../doc/models/sca-status-enum.md) | Required | The status of Strong Customer Authentication (SCA). Possible values:<br><br>* **notPerformed**: the requester was unable to successfully authenticate the request using SCA, or has an SCA exemption.<br>* **pending**: the request is pending SCA authentication.<br>* **performed**: the request is successfully authenticated using SCA. | getStatus(): string | setStatus(string status): void |

## Example

```php
use AdyenLib\Models\Builders\ScaInformation1Builder;
use AdyenLib\Models\ScaStatusEnum;
use AdyenLib\Models\ScaExemptionEnum;

$scaInformation1 = ScaInformation1Builder::init(
    ScaStatusEnum::PERFORMED
)
    ->exemption(ScaExemptionEnum::SETBYPLATFORM)
    ->build();
```

