
# Close Account Holder Response

## Structure

`CloseAccountHolderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountHolderStatus` | [`?AccountHolderStatus1`](../../doc/models/account-holder-status-1.md) | Optional | The new status of the Account Holder. | getAccountHolderStatus(): ?AccountHolderStatus1 | setAccountHolderStatus(?AccountHolderStatus1 accountHolderStatus): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\CloseAccountHolderResponseBuilder;
use AdyenLib\Models\Builders\AccountHolderStatus1Builder;
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

$closeAccountHolderResponse = CloseAccountHolderResponseBuilder::init()
    ->accountHolderStatus(
        AccountHolderStatus1Builder::init(
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
                ->build()
        ]
    )
    ->pspReference('pspReference8')
    ->resultCode('resultCode8')
    ->build();
```

