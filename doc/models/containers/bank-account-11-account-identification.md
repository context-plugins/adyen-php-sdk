
# Bank Account 11 Account Identification

## Data Type

`AULocalAccountIdentification|BRLocalAccountIdentification|CALocalAccountIdentification|CZLocalAccountIdentification|DKLocalAccountIdentification|HKLocalAccountIdentification|HULocalAccountIdentification|IbanAccountIdentification|NOLocalAccountIdentification|NZLocalAccountIdentification|NumberAndBicAccountIdentification|PLLocalAccountIdentification|SELocalAccountIdentification|SGLocalAccountIdentification|UKLocalAccountIdentification|USLocalAccountIdentification`

## Cases

| Type |
|  --- |
| [`AULocalAccountIdentification`](../../../doc/models/au-local-account-identification.md) |
| [`BRLocalAccountIdentification`](../../../doc/models/br-local-account-identification.md) |
| [`CALocalAccountIdentification`](../../../doc/models/ca-local-account-identification.md) |
| [`CZLocalAccountIdentification`](../../../doc/models/cz-local-account-identification.md) |
| [`DKLocalAccountIdentification`](../../../doc/models/dk-local-account-identification.md) |
| [`HKLocalAccountIdentification`](../../../doc/models/hk-local-account-identification.md) |
| [`HULocalAccountIdentification`](../../../doc/models/hu-local-account-identification.md) |
| [`IbanAccountIdentification`](../../../doc/models/iban-account-identification.md) |
| [`NOLocalAccountIdentification`](../../../doc/models/no-local-account-identification.md) |
| [`NZLocalAccountIdentification`](../../../doc/models/nz-local-account-identification.md) |
| [`NumberAndBicAccountIdentification`](../../../doc/models/number-and-bic-account-identification.md) |
| [`PLLocalAccountIdentification`](../../../doc/models/pl-local-account-identification.md) |
| [`SELocalAccountIdentification`](../../../doc/models/se-local-account-identification.md) |
| [`SGLocalAccountIdentification`](../../../doc/models/sg-local-account-identification.md) |
| [`UKLocalAccountIdentification`](../../../doc/models/uk-local-account-identification.md) |
| [`USLocalAccountIdentification`](../../../doc/models/us-local-account-identification.md) |

## AULocalAccountIdentification

### Initialization Code

#### Example

```php
$value = AULocalAccountIdentificationBuilder::init(
    'accountNumber4',
    'bsbCode8'
)->build();
```

## BRLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = BRLocalAccountIdentificationBuilder::init(
    'accountNumber0',
    'bankCode2',
    'branchNumber2'
)->build();
```

## CALocalAccountIdentification

### Initialization Code

#### Example

```php
$value = CALocalAccountIdentificationBuilder::init(
    'accountNumber8',
    'institutionNumber2',
    'transitNumber8'
)
    ->accountType(AccountType2Enum::CHECKING)
    ->build();
```

## CZLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = CZLocalAccountIdentificationBuilder::init(
    'accountNumber4',
    'bankCode8'
)->build();
```

## DKLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = DKLocalAccountIdentificationBuilder::init(
    'accountNumber6',
    'bankCode6'
)->build();
```

## HKLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = HKLocalAccountIdentificationBuilder::init(
    'accountNumber8',
    'clearingCode2'
)->build();
```

## HULocalAccountIdentification

### Initialization Code

#### Example

```php
$value = HULocalAccountIdentificationBuilder::init(
    'accountNumber8'
)->build();
```

## IbanAccountIdentification

### Initialization Code

#### Example

```php
$value = IbanAccountIdentificationBuilder::init(
    'iban6'
)->build();
```

## NOLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = NOLocalAccountIdentificationBuilder::init(
    'accountNumber6'
)->build();
```

## NZLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = NZLocalAccountIdentificationBuilder::init(
    'accountNumber6'
)->build();
```

## NumberAndBicAccountIdentification

### Initialization Code

#### Example

```php
$value = NumberAndBicAccountIdentificationBuilder::init(
    'accountNumber0',
    'bic4'
)->build();
```

## PLLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = PLLocalAccountIdentificationBuilder::init(
    'accountNumber4'
)->build();
```

## SELocalAccountIdentification

### Initialization Code

#### Example

```php
$value = SELocalAccountIdentificationBuilder::init(
    'accountNumber0',
    'clearingNumber2'
)->build();
```

## SGLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = SGLocalAccountIdentificationBuilder::init(
    'accountNumber2',
    'bic2'
)
    ->type(Type82Enum::SGLOCAL)
    ->build();
```

## UKLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = UKLocalAccountIdentificationBuilder::init(
    'accountNumber8',
    'sortCode8'
)->build();
```

## USLocalAccountIdentification

### Initialization Code

#### Example

```php
$value = USLocalAccountIdentificationBuilder::init(
    'accountNumber2',
    'routingNumber2'
)
    ->accountType(AccountType2Enum::CHECKING)
    ->build();
```

