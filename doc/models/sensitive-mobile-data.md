
# Sensitive Mobile Data

## Structure

`SensitiveMobileData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mSISDN` | `int` | Required | Mobile Subscriber Integrated Service Digital Network (i.e. mobile phone number of the SIM card). Country, National Destination Code, and Subscriber Number. | getMSISDN(): int | setMSISDN(int mSISDN): void |
| `iMSI` | `?int` | Optional | International Mobile Subscriber Identity. Unique number associated with the mobile phone user, containing the Mobile Country Code (MCC), the Mobile Network Code (MNC), and the Mobile Identification Number (MSIN) | getIMSI(): ?int | setIMSI(?int iMSI): void |
| `iMEI` | `?int` | Optional | International Mobile Equipment Identity. Unique number associated with the mobile phone device. | getIMEI(): ?int | setIMEI(?int iMEI): void |

## Example

```php
use AdyenLib\Models\Builders\SensitiveMobileDataBuilder;

$sensitiveMobileData = SensitiveMobileDataBuilder::init(
    66
)
    ->iMSI(42)
    ->iMEI(206)
    ->build();
```

