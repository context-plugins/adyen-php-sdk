
# Service Enum

The service for which you are creating the business line.

Possible values:

* **paymentProcessing**
* **issuing**
* **banking**

## Enumeration

`ServiceEnum`

## Fields

| Name |
|  --- |
| `PAYMENTPROCESSING` |
| `ISSUING` |
| `BANKING` |

## Example

```php
use AdyenLib\Models\ServiceEnum;

$service = ServiceEnum::ISSUING;
```

