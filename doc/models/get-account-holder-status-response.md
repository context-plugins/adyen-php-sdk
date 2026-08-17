
# Get Account Holder Status Response

## Structure

`GetAccountHolderStatusResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderCode` | `?string` | Optional | The code of the Account Holder. | getAccountHolderCode(): ?string | setAccountHolderCode(?string accountHolderCode): void |
| `accountHolderStatus` | [`?AccountHolderStatus4`](../../doc/models/account-holder-status-4.md) | Optional | The status of the Account Holder. | getAccountHolderStatus(): ?AccountHolderStatus4 | setAccountHolderStatus(?AccountHolderStatus4 accountHolderStatus): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\GetAccountHolderStatusResponseBuilder;
use AdyenLib\Models\Builders\AccountHolderStatus4Builder;
use AdyenLib\Models\Status12Enum;
use AdyenLib\Models\Builders\AccountEventBuilder;
use AdyenLib\Models\EventEnum;
use AdyenLib\Utils\DateTimeHelper;
use AdyenLib\Models\Builders\AccountPayoutState2Builder;
use AdyenLib\Models\Builders\AmountBuilder;
use AdyenLib\Models\Builders\AccountProcessingState2Builder;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;

$getAccountHolderStatusResponse = GetAccountHolderStatusResponseBuilder::init()
    ->accountHolderCode('accountHolderCode2')
    ->accountHolderStatus(
        AccountHolderStatus4Builder::init(
            Status12Enum::INACTIVE
        )
            ->events(
                [
                    AccountEventBuilder::init()
                        ->event(EventEnum::INACTIVATEACCOUNT)
                        ->executionDate(DateTimeHelper::fromRfc3339DateTime('2016-03-13T12:52:32.123Z'))
                        ->reason('reason6')
                        ->build()
                ]
            )
            ->payoutState(
                AccountPayoutState2Builder::init()
                    ->allowPayout(false)
                    ->disableReason('disableReason2')
                    ->disabled(false)
                    ->notAllowedReason('notAllowedReason4')
                    ->payoutLimit(
                        AmountBuilder::init(
                            'currency8',
                            88
                        )->build()
                    )->build()
            )
            ->processingState(
                AccountProcessingState2Builder::init()
                    ->disableReason('disableReason2')
                    ->disabled(false)
                    ->processedFrom(
                        AmountBuilder::init(
                            'currency4',
                            148
                        )->build()
                    )
                    ->processedTo(
                        AmountBuilder::init(
                            'currency2',
                            54
                        )->build()
                    )
                    ->tierNumber(156)
                    ->build()
            )
            ->statusReason('statusReason8')
            ->build()
    )
    ->invalidFields(
        [
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build(),
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build(),
            ErrorFieldTypeBuilder::init()
                ->errorCode(78)
                ->errorDescription('errorDescription6')
                ->fieldType(
                    FieldTypeBuilder::init()
                        ->field('field6')
                        ->fieldName(FieldNameEnum::DRIVINGLICENCEFRONT)
                        ->shareholderCode('shareholderCode0')
                        ->build()
                )
                ->build()
        ]
    )
    ->pspReference('pspReference6')
    ->resultCode('resultCode2')
    ->build();
```

