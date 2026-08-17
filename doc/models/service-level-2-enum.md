
# Service Level 2 Enum

Specifies the service level (settlement type) of this payment method. Required for merchants operating in Japan.
Possible values:

* **noContract**: Adyen holds the contract with JCB for merchants operating in Japan or American Express for merchants operating in Canada, Australia and New Zealand.
* **gatewayContract**: JCB or American Express receives the settlement and handles disputes, then pays out to you or your sub-merchant directly.
* **paymentDesignatorContract**: Available only for merchants operating in Canada, Australia and New Zealand. Adyen receives the settlement, and handles disputes and payouts.

## Enumeration

`ServiceLevel2Enum`

## Fields

| Name |
|  --- |
| `NOCONTRACT` |
| `GATEWAYCONTRACT` |
| `PAYMENTDESIGNATORCONTRACT` |

## Example

```php
use AdyenLib\Models\ServiceLevel2Enum;

$serviceLevel2 = ServiceLevel2Enum::PAYMENTDESIGNATORCONTRACT;
```

