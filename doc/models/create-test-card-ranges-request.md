
# Create Test Card Ranges Request

## Structure

`CreateTestCardRangesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountCode` | `string` | Required | The code of the account, for which the test card ranges should be created. | getAccountCode(): string | setAccountCode(string accountCode): void |
| `accountTypeCode` | `string` | Required | The type of the account, for which the test card ranges should be created.<br><br>Permitted values:<br><br>* Company<br>* MerchantAccount<br><br>> These values are case-sensitive. | getAccountTypeCode(): string | setAccountTypeCode(string accountTypeCode): void |
| `testCardRanges` | [`TestCardRange[]`](../../doc/models/test-card-range.md) | Required | A list of test card ranges to create. | getTestCardRanges(): array | setTestCardRanges(array testCardRanges): void |

## Example

```php
use AdyenLib\Models\Builders\CreateTestCardRangesRequestBuilder;
use AdyenLib\Models\Builders\TestCardRangeBuilder;
use AdyenLib\Models\ExpiryMonthEnum;
use AdyenLib\Models\Builders\AvsAddress1Builder;
use AdyenLib\Models\ThreeDDirectoryServerResponseEnum;

$createTestCardRangesRequest = CreateTestCardRangesRequestBuilder::init(
    'accountCode6',
    'accountTypeCode0',
    [
        TestCardRangeBuilder::init(
            'cardHolderName0',
            ExpiryMonthEnum::DECEMBER,
            138,
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
            ->threeDDirectoryServerResponse(ThreeDDirectoryServerResponseEnum::N)
            ->threeDPassword('threeDPassword2')
            ->threeDUsername('threeDUsername8')
            ->build()
    ]
)->build();
```

