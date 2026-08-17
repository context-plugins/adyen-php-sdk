
# Payment Method Response

## Structure

`PaymentMethodResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?PaginationLinks1`](../../doc/models/pagination-links-1.md) | Optional | Pagination references. | getLinks(): ?PaginationLinks1 | setLinks(?PaginationLinks1 links): void |
| `data` | [`?(ManagementPaymentMethod[])`](../../doc/models/management-payment-method.md) | Optional | The list of supported payment methods and their details. | getData(): ?array | setData(?array data): void |
| `itemsTotal` | `int` | Required | Total number of items. | getItemsTotal(): int | setItemsTotal(int itemsTotal): void |
| `pagesTotal` | `int` | Required | Total number of pages. | getPagesTotal(): int | setPagesTotal(int pagesTotal): void |
| `typesWithErrors` | [`?(string(TypesWithErrorEnum)[])`](../../doc/models/types-with-error-enum.md) | Optional | The payment method types that were not successfully requested and their corresponding errors. | getTypesWithErrors(): ?array | setTypesWithErrors(?array typesWithErrors): void |

## Example

```php
use AdyenLib\Models\Builders\PaymentMethodResponseBuilder;
use AdyenLib\Models\Builders\PaginationLinks1Builder;
use AdyenLib\Models\Builders\LinksElement9Builder;
use AdyenLib\Models\Builders\LinksElement10Builder;
use AdyenLib\Models\Builders\LinksElement13Builder;
use AdyenLib\Models\Builders\LinksElement11Builder;
use AdyenLib\Models\Builders\LinksElement12Builder;
use AdyenLib\Models\Builders\ManagementPaymentMethodBuilder;
use AdyenLib\Models\Builders\AccelResponseInfo1Builder;
use AdyenLib\Models\ProcessingTypeEnum;
use AdyenLib\Models\Builders\TransactionDescriptionResponseInfo1Builder;
use AdyenLib\Models\Type8Enum;
use AdyenLib\Models\Builders\AffirmResponseInfo1Builder;
use AdyenLib\Models\Builders\AfterpayTouchResponseInfo1Builder;
use AdyenLib\Models\Builders\AlipayPlusResponseInfo1Builder;
use AdyenLib\Models\TypesWithErrorEnum;

$paymentMethodResponse = PaymentMethodResponseBuilder::init(
    208,
    86
)
    ->links(
        PaginationLinks1Builder::init(
            LinksElement9Builder::init()
                ->href('href2')
                ->build(),
            LinksElement10Builder::init()
                ->href('href2')
                ->build(),
            LinksElement13Builder::init()
                ->href('href0')
                ->build()
        )
            ->next(
                LinksElement11Builder::init()
                    ->href('href4')
                    ->build()
            )
            ->prev(
                LinksElement12Builder::init()
                    ->href('href8')
                    ->build()
            )
            ->build()
    )
    ->data(
        [
            ManagementPaymentMethodBuilder::init(
                'id0'
            )
                ->accel(
                    AccelResponseInfo1Builder::init()
                        ->processingType(ProcessingTypeEnum::BILLPAY)
                        ->transactionDescription(
                            TransactionDescriptionResponseInfo1Builder::init()
                                ->doingBusinessAsName('doingBusinessAsName0')
                                ->type(Type8Enum::FIXED)
                                ->build()
                        )
                        ->build()
                )
                ->affirm(
                    AffirmResponseInfo1Builder::init()
                        ->publicApiKey('publicApiKey4')
                        ->build()
                )
                ->afterpayTouch(
                    AfterpayTouchResponseInfo1Builder::init()
                        ->supportEmail('supportEmail8')
                        ->supportUrl('supportUrl4')
                        ->build()
                )
                ->alipayPlus(
                    AlipayPlusResponseInfo1Builder::init()
                        ->settlementCurrencyCode('settlementCurrencyCode0')
                        ->build()
                )
                ->allowed(false)
                ->build(),
            ManagementPaymentMethodBuilder::init(
                'id0'
            )
                ->accel(
                    AccelResponseInfo1Builder::init()
                        ->processingType(ProcessingTypeEnum::BILLPAY)
                        ->transactionDescription(
                            TransactionDescriptionResponseInfo1Builder::init()
                                ->doingBusinessAsName('doingBusinessAsName0')
                                ->type(Type8Enum::FIXED)
                                ->build()
                        )
                        ->build()
                )
                ->affirm(
                    AffirmResponseInfo1Builder::init()
                        ->publicApiKey('publicApiKey4')
                        ->build()
                )
                ->afterpayTouch(
                    AfterpayTouchResponseInfo1Builder::init()
                        ->supportEmail('supportEmail8')
                        ->supportUrl('supportUrl4')
                        ->build()
                )
                ->alipayPlus(
                    AlipayPlusResponseInfo1Builder::init()
                        ->settlementCurrencyCode('settlementCurrencyCode0')
                        ->build()
                )
                ->allowed(false)
                ->build()
        ]
    )
    ->typesWithErrors(
        [
            TypesWithErrorEnum::ALIPAY_PLUS_TRUEMONEY,
            TypesWithErrorEnum::ALIPAY_WAP,
            TypesWithErrorEnum::AMEX
        ]
    )
    ->build();
```

