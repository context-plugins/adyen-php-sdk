
# Get Totals Response

Content of the Reconciliation Response message.
It conveys Information related to the Reconciliation transaction processed by the POI System.

## Structure

`GetTotalsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `response` | [`Response11`](../../doc/models/response-11.md) | Required | Result of a message request processing. | getResponse(): Response11 | setResponse(Response11 response): void |
| `pOIReconciliationID` | `int` | Required | Identification of the reconciliation period between Sale and POI. | getPOIReconciliationID(): int | setPOIReconciliationID(int pOIReconciliationID): void |
| `transactionTotals` | [`?(TransactionTotals[])`](../../doc/models/transaction-totals.md) | Optional | Result of the Sale to POI Reconciliation processing.<br>If `Response.Result` is Success. | getTransactionTotals(): ?array | setTransactionTotals(?array transactionTotals): void |

## Example

```php
use AdyenLib\Models\Builders\GetTotalsResponseBuilder;
use AdyenLib\Models\Builders\Response11Builder;
use AdyenLib\Models\Result11Enum;
use AdyenLib\Models\ErrorCondition1Enum;
use AdyenLib\Models\Builders\TransactionTotalsBuilder;
use AdyenLib\Models\PaymentInstrumentType11Enum;

$getTotalsResponse = GetTotalsResponseBuilder::init(
    Response11Builder::init(
        Result11Enum::PARTIAL
    )
        ->errorCondition(ErrorCondition1Enum::PAYMENTRESTRICTION)
        ->additionalResponse('AdditionalResponse8')
        ->build(),
    232
)
    ->transactionTotals(
        [
            TransactionTotalsBuilder::init(
                PaymentInstrumentType11Enum::MOBILE
            )
                ->acquirerID(138)
                ->hostReconciliationID('HostReconciliationID4')
                ->cardBrand('CardBrand8')
                ->pOIID('POIID6')
                ->saleID('SaleID2')
                ->build(),
            TransactionTotalsBuilder::init(
                PaymentInstrumentType11Enum::MOBILE
            )
                ->acquirerID(138)
                ->hostReconciliationID('HostReconciliationID4')
                ->cardBrand('CardBrand8')
                ->pOIID('POIID6')
                ->saleID('SaleID2')
                ->build()
        ]
    )
    ->build();
```

