
# Transfer View Category Data

## Data Type

`BankCategoryData|InternalCategoryData|IssuedCard|PlatformPayment`

## Cases

| Type |
|  --- |
| [`BankCategoryData`](../../../doc/models/bank-category-data.md) |
| [`InternalCategoryData`](../../../doc/models/internal-category-data.md) |
| [`IssuedCard`](../../../doc/models/issued-card.md) |
| [`PlatformPayment`](../../../doc/models/platform-payment.md) |

## BankCategoryData

### Initialization Code

#### Example

```php
$value = BankCategoryDataBuilder::init()
    ->type(Type310Enum::BANK)
    ->build();
```

## InternalCategoryData

### Initialization Code

#### Example

```php
$value = InternalCategoryDataBuilder::init()
    ->type(Type411Enum::INTERNAL)
    ->build();
```

## IssuedCard

### Initialization Code

#### Example

```php
$value = IssuedCardBuilder::init()
    ->type(Type511Enum::ISSUEDCARD)
    ->build();
```

## PlatformPayment

### Initialization Code

#### Example

```php
$value = PlatformPaymentBuilder::init()
    ->type(Type63Enum::PLATFORMPAYMENT)
    ->build();
```

