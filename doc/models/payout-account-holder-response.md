
# Payout Account Holder Response

## Structure

`PayoutAccountHolderResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bankAccountUUID` | `?string` | Optional | The unique ID of the Bank Account to which the payout was made. | getBankAccountUUID(): ?string | setBankAccountUUID(?string bankAccountUUID): void |
| `invalidFields` | [`?(ErrorFieldType[])`](../../doc/models/error-field-type.md) | Optional | Contains field validation errors that would prevent requests from being processed. | getInvalidFields(): ?array | setInvalidFields(?array invalidFields): void |
| `merchantReference` | `?string` | Optional | The value supplied by the executing user when initiating the transfer; may be used to link multiple transactions. | getMerchantReference(): ?string | setMerchantReference(?string merchantReference): void |
| `payoutSpeed` | [`?string(PayoutSpeedEnum)`](../../doc/models/payout-speed-enum.md) | Optional | Speed with which payouts for this account are processed. Permitted values: `STANDARD`, `SAME_DAY`.<br><br>**Default**: `PayoutSpeedEnum::STANDARD` | getPayoutSpeed(): ?string | setPayoutSpeed(?string payoutSpeed): void |
| `pspReference` | `?string` | Optional | The reference of a request. Can be used to uniquely identify the request. | getPspReference(): ?string | setPspReference(?string pspReference): void |
| `resultCode` | `?string` | Optional | The result code. | getResultCode(): ?string | setResultCode(?string resultCode): void |

## Example

```php
use AdyenLib\Models\Builders\PayoutAccountHolderResponseBuilder;
use AdyenLib\Models\Builders\ErrorFieldTypeBuilder;
use AdyenLib\Models\Builders\FieldTypeBuilder;
use AdyenLib\Models\FieldNameEnum;
use AdyenLib\Models\PayoutSpeedEnum;

$payoutAccountHolderResponse = PayoutAccountHolderResponseBuilder::init()
    ->bankAccountUUID('bankAccountUUID6')
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
    ->merchantReference('merchantReference4')
    ->payoutSpeed(PayoutSpeedEnum::STANDARD)
    ->pspReference('pspReference2')
    ->build();
```

