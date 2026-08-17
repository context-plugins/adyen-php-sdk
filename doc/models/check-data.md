
# Check Data

Information related to the paper check used for the transaction.
Allows the check information to be provided by the Sale System before requesting the payment, or stored by the Sale System after processing of the payment.

## Structure

`CheckData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankID` | `?string` | Optional | Identification of the bank.<br>Mandatory if TrackData absent.<br><br>**Constraints**: *Pattern*: `^.+$` | getBankID(): ?string | setBankID(?string bankID): void |
| `accountNumber` | `?string` | Optional | Identification of the customer account.<br>Mandatory if TrackData absent.<br><br>**Constraints**: *Pattern*: `^.+$` | getAccountNumber(): ?string | setAccountNumber(?string accountNumber): void |
| `checkNumber` | `?string` | Optional | Identification of the bank check.<br>Mandatory if TrackData absent.<br><br>**Constraints**: *Pattern*: `^.+$` | getCheckNumber(): ?string | setCheckNumber(?string checkNumber): void |
| `trackData` | [`?TrackData1`](../../doc/models/track-data-1.md) | Optional | Magnetic track or magnetic ink characters line.<br>Mandatory if CheckNumber absent. | getTrackData(): ?TrackData1 | setTrackData(?TrackData1 trackData): void |
| `checkCardNumber` | `?string` | Optional | Check guarantee card number.<br>If provided by the customer.<br><br>**Constraints**: *Pattern*: `^.+$` | getCheckCardNumber(): ?string | setCheckCardNumber(?string checkCardNumber): void |
| `typeCode` | [`?string(TypeCode1Enum)`](../../doc/models/type-code-1-enum.md) | Optional | Type of bank check.<br>Possible values:<br><br>* **Company**<br>* **Personal** | getTypeCode(): ?string | setTypeCode(?string typeCode): void |
| `country` | `?string` | Optional | Country of the bank check.<br>Absent if country of the Sale system.<br><br>**Constraints**: *Pattern*: `^[A-Z]{3,3}$` | getCountry(): ?string | setCountry(?string country): void |

## Example

```php
use AdyenLib\Models\Builders\CheckDataBuilder;
use AdyenLib\Models\Builders\TrackData1Builder;
use AdyenLib\Models\TrackFormat1Enum;

$checkData = CheckDataBuilder::init()
    ->bankID('BankID0')
    ->accountNumber('AccountNumber6')
    ->checkNumber('CheckNumber2')
    ->trackData(
        TrackData1Builder::init(
            'TrackValue6'
        )
            ->trackNumb(3)
            ->trackFormat(TrackFormat1Enum::JISII)
            ->build()
    )
    ->checkCardNumber('CheckCardNumber6')
    ->build();
```

