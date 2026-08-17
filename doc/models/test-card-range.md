
# Test Card Range

## Structure

`TestCardRange`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`?AvsAddress1`](../../doc/models/avs-address-1.md) | Optional | Contains the billing address of the card holder. The address details need to be AVS-compliant, which means that you need to provide at least street address. | getAddress(): ?AvsAddress1 | setAddress(?AvsAddress1 address): void |
| `cardHolderName` | `string` | Required | The name of the card holder, as it appears on the card, for the test card range. | getCardHolderName(): string | setCardHolderName(string cardHolderName): void |
| `cvc` | `?string` | Optional | The test card range security code.<br><br>Example: 123 | getCvc(): ?string | setCvc(?string cvc): void |
| `expiryMonth` | [`string(ExpiryMonthEnum)`](../../doc/models/expiry-month-enum.md) | Required | Expiry month for the test card range.<br><br>Allowed values:<br><br>* JANUARY<br>* FEBRUARY<br>* MARCH<br>* APRIL<br>* MAY<br>* JUNE<br>* JULY<br>* AUGUST<br>* SEPTEMBER<br>* OCTOBER<br>* NOVEMBER<br>* DECEMBER | getExpiryMonth(): string | setExpiryMonth(string expiryMonth): void |
| `expiryYear` | `int` | Required | Expiry year for the test card range.<br><br>Example: 2020 | getExpiryYear(): int | setExpiryYear(int expiryYear): void |
| `rangeEnd` | `string` | Required | The last test card number in the test card range (inclusive):<br><br>* Min 6, max 19 digits<br>* BIN compliant<br>  Example: 5432 1234 1234 4321 | getRangeEnd(): string | setRangeEnd(string rangeEnd): void |
| `rangeStart` | `string` | Required | The first test card number in the test card range (inclusive):<br><br>* Min 6, max 19 digits<br>* BIN compliant<br>  Example: 5432 1234 1234 1234 | getRangeStart(): string | setRangeStart(string rangeStart): void |
| `threeDDirectoryServerResponse` | [`?string(ThreeDDirectoryServerResponseEnum)`](../../doc/models/three-d-directory-server-response-enum.md) | Optional | 3D Secure server response. It notifies whether the specified card holder is enrolled in a 3D Secure service. Possible values:<br><br>* Y (Authentication available)<br>* N (Card holder not enrolled/not participating)<br>* U (Unable to authenticate) | getThreeDDirectoryServerResponse(): ?string | setThreeDDirectoryServerResponse(?string threeDDirectoryServerResponse): void |
| `threeDPassword` | `?string` | Optional | The password used for 3D Secure authentication. | getThreeDPassword(): ?string | setThreeDPassword(?string threeDPassword): void |
| `threeDUsername` | `?string` | Optional | The username used for 3D Secure authentication. | getThreeDUsername(): ?string | setThreeDUsername(?string threeDUsername): void |

## Example

```php
use AdyenLib\Models\Builders\TestCardRangeBuilder;
use AdyenLib\Models\ExpiryMonthEnum;
use AdyenLib\Models\Builders\AvsAddress1Builder;
use AdyenLib\Models\ThreeDDirectoryServerResponseEnum;

$testCardRange = TestCardRangeBuilder::init(
    'cardHolderName0',
    ExpiryMonthEnum::JANUARY,
    144,
    'rangeEnd6',
    'rangeStart4'
)
    ->address(
        AvsAddress1Builder::init(
            'streetAddress6'
        )
            ->zip('zip0')
            ->build()
    )
    ->cvc('cvc0')
    ->threeDDirectoryServerResponse(ThreeDDirectoryServerResponseEnum::Y)
    ->threeDPassword('threeDPassword2')
    ->threeDUsername('threeDUsername8')
    ->build();
```

