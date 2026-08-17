
# Donation Payment Request Payment Method

## Data Type

`ApplePayDonations|CardDonations|GooglePayDonations|IdealDonations|PayWithGoogleDonations|StoredPaymentMethod1`

## Cases

| Type |
|  --- |
| [`ApplePayDonations`](../../../doc/models/apple-pay-donations.md) |
| [`CardDonations`](../../../doc/models/card-donations.md) |
| [`GooglePayDonations`](../../../doc/models/google-pay-donations.md) |
| [`IdealDonations`](../../../doc/models/ideal-donations.md) |
| [`PayWithGoogleDonations`](../../../doc/models/pay-with-google-donations.md) |
| [`StoredPaymentMethod1`](../../../doc/models/stored-payment-method-1.md) |

## ApplePayDonations

### Initialization Code

#### Example

```php
$value = ApplePayDonationsBuilder::init(
    'applePayToken4'
)
    ->type(Type7Enum::APPLEPAY)
    ->build();
```

## CardDonations

### Initialization Code

#### Example

```php
$value = CardDonationsBuilder::init()
    ->type(Type14Enum::SCHEME)
    ->build();
```

## GooglePayDonations

### Initialization Code

#### Example

```php
$value = GooglePayDonationsBuilder::init(
    'googlePayToken0'
)
    ->type(Type24Enum::GOOGLEPAY)
    ->build();
```

## IdealDonations

### Initialization Code

#### Example

```php
$value = IdealDonationsBuilder::init()
    ->type(Type25Enum::IDEAL)
    ->build();
```

## PayWithGoogleDonations

### Initialization Code

#### Example

```php
$value = PayWithGoogleDonationsBuilder::init(
    'googlePayToken2'
)
    ->type(Type26Enum::PAYWITHGOOGLE)
    ->build();
```

## StoredPaymentMethod1

### Initialization Code

#### Example

```php
$value = StoredPaymentMethod1Builder::init()
    ->type(Type27Enum::SEPADIRECTDEBIT)
    ->build();
```

