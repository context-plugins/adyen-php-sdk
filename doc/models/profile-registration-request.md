
# Profile Registration Request

## Structure

`ProfileRegistrationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderId` | `string` | Required | The unique identifier of the account holder.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `150` | getAccountHolderId(): string | setAccountHolderId(string accountHolderId): void |
| `paymentInstrumentIds` | `string[]` | Required | The unique identifiers of the payment instruments to be associated with the iDEAL profile.<br><br>**Constraints**: *Minimum Items*: `1`, *Maximum Items*: `100`, *Minimum Length*: `1`, *Maximum Length*: `150` | getPaymentInstrumentIds(): array | setPaymentInstrumentIds(array paymentInstrumentIds): void |

## Example

```php
use AdyenLib\Models\Builders\ProfileRegistrationRequestBuilder;

$profileRegistrationRequest = ProfileRegistrationRequestBuilder::init(
    'AH00000000000000000000000',
    [
        'PI00000000000000000000000',
        'PI11111111111111111111111'
    ]
)->build();
```

