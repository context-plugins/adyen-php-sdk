
# Instalment Type Enum

Type of instalment transaction. For requesting an instalment payment transaction.
Possible values:

* **DeferredInstalments**
* **EqualInstalments**
* **InequalInstalments**

## Enumeration

`InstalmentTypeEnum`

## Fields

| Name |
|  --- |
| `DEFERREDINSTALMENTS` |
| `EQUALINSTALMENTS` |
| `INEQUALINSTALMENTS` |

## Example

```php
use AdyenLib\Models\InstalmentTypeEnum;

$instalmentType = InstalmentTypeEnum::EQUALINSTALMENTS;
```

