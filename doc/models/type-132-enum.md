
# Type 132 Enum

Type of identity data. For individuals, the following types are supported. See our [onboarding guide](https://docs.adyen.com/platforms/onboard-users/onboarding-steps/?onboarding_type=custom) for other supported countries.

- Australia: **driversLicense**, **passport**

- Hong Kong: **driversLicense**, **nationalIdNumber**, **passport**

- New Zealand: **driversLicense**, **passport**

- Singapore: **driversLicense**, **nationalIdNumber**, **passport**

- All other supported countries: **nationalIdNumber**

## Enumeration

`Type132Enum`

## Fields

| Name |
|  --- |
| `NATIONALIDNUMBER` |
| `PASSPORT` |
| `DRIVERSLICENSE` |
| `IDENTITYCARD` |

## Example

```php
use AdyenLib\Models\Type132Enum;

$type132 = Type132Enum::DRIVERSLICENSE;
```

