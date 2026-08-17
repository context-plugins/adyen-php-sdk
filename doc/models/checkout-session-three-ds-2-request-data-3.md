
# Checkout Session Three DS 2 Request Data 3

The cardholder phone number need to be part of the authentication message for payment data. It is a requirement for Visa Secure Authentication Data Field Mandate effective August 2024.

## Structure

`CheckoutSessionThreeDS2RequestData3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `homePhone` | [`?Phone3`](../../doc/models/phone-3.md) | Optional | The home phone number provided by the cardholder. The phone number must consist of a country code, followed by the number. If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`, and did not send the shopper's phone number in `telephoneNumber`. | getHomePhone(): ?Phone3 | setHomePhone(?Phone3 homePhone): void |
| `mobilePhone` | [`?Phone1`](../../doc/models/phone-1.md) | Optional | The mobile phone number provided by the cardholder. The phone number must consist of a country code, followed by the number. If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`, and did not send the shopper's phone number in `telephoneNumber`. | getMobilePhone(): ?Phone1 | setMobilePhone(?Phone1 mobilePhone): void |
| `threeDSRequestorChallengeInd` | [`?string(ThreeDSRequestorChallengeIndEnum)`](../../doc/models/three-ds-requestor-challenge-ind-enum.md) | Optional | Indicates whether a challenge is requested for this transaction. Possible values:<br><br>* **01** — No preference<br>* **02** — No challenge requested<br>* **03** — Challenge requested (3DS Requestor preference)<br>* **04** — Challenge requested (Mandate)<br>* **05** — No challenge (transactional risk analysis is already performed)<br>* **06** — Data Only | getThreeDSRequestorChallengeInd(): ?string | setThreeDSRequestorChallengeInd(?string threeDSRequestorChallengeInd): void |
| `workPhone` | [`?Phone2`](../../doc/models/phone-2.md) | Optional | The work phone number provided by the cardholder. The phone number must consist of a country code, followed by the number. If the value you provide does not follow the guidelines, we do not submit it for authentication.<br><br>> Required for Visa and JCB transactions that require 3D Secure 2 authentication, if you did not include the `shopperEmail`, and did not send the shopper's phone number in `telephoneNumber`. | getWorkPhone(): ?Phone2 | setWorkPhone(?Phone2 workPhone): void |

## Example

```php
use AdyenLib\Models\Builders\CheckoutSessionThreeDS2RequestData3Builder;
use AdyenLib\Models\Builders\Phone3Builder;
use AdyenLib\Models\Builders\Phone1Builder;
use AdyenLib\Models\ThreeDSRequestorChallengeIndEnum;
use AdyenLib\Models\Builders\Phone2Builder;

$checkoutSessionThreeDS2RequestData3 = CheckoutSessionThreeDS2RequestData3Builder::init()
    ->homePhone(
        Phone3Builder::init()
            ->cc('cc0')
            ->subscriber('subscriber2')
            ->build()
    )
    ->mobilePhone(
        Phone1Builder::init()
            ->cc('cc4')
            ->subscriber('subscriber6')
            ->build()
    )
    ->threeDSRequestorChallengeInd(ThreeDSRequestorChallengeIndEnum::ENUM_03)
    ->workPhone(
        Phone2Builder::init()
            ->cc('cc2')
            ->subscriber('subscriber4')
            ->build()
    )
    ->build();
```

