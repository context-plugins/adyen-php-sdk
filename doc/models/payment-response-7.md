
# Payment Response 7

## Structure

`PaymentResponse7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | [`?PaymentValidationsNameResponse2`](../../doc/models/payment-validations-name-response-2.md) | Optional | Object that contains the status and outcomes of the [name validation](https://docs.adyen.com/payment-methods/cards/name-validation). | getName(): ?PaymentValidationsNameResponse2 | setName(?PaymentValidationsNameResponse2 name): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentResponse7Builder;
use AdyenLib\Models\Builders\PaymentValidationsNameResponse2Builder;
use AdyenLib\Models\Builders\PaymentValidationsNameResultRawResponse2Builder;
use AdyenLib\Models\Builders\PaymentValidationsNameResultResponse2Builder;
use AdyenLib\Models\StatusEnum;

$paymentResponse7 = PaymentResponse7Builder::init()
    ->name(
        PaymentValidationsNameResponse2Builder::init()
            ->rawResponse(
                PaymentValidationsNameResultRawResponse2Builder::init()
                    ->firstName('firstName0')
                    ->fullName('fullName4')
                    ->lastName('lastName8')
                    ->middleName('middleName2')
                    ->status('status6')
                    ->build()
            )
            ->result(
                PaymentValidationsNameResultResponse2Builder::init()
                    ->firstName('firstName8')
                    ->fullName('fullName6')
                    ->lastName('lastName0')
                    ->middleName('middleName4')
                    ->build()
            )
            ->status(StatusEnum::NOTPERFORMED)
            ->build()
    )
    ->build();
```

