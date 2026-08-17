
# Ultimate Parent Company

## Structure

`UltimateParentCompany`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`?ViasAddress1`](../../doc/models/vias-address-1.md) | Optional | Address of the ultimate parent company. | getAddress(): ?ViasAddress1 | setAddress(?ViasAddress1 address): void |
| `businessDetails` | [`?UltimateParentCompanyBusinessDetails2`](../../doc/models/ultimate-parent-company-business-details-2.md) | Optional | Details about the ultimate parent company's business. | getBusinessDetails(): ?UltimateParentCompanyBusinessDetails2 | setBusinessDetails(?UltimateParentCompanyBusinessDetails2 businessDetails): void |
| `ultimateParentCompanyCode` | `?string` | Optional | Adyen-generated unique alphanumeric identifier (UUID) for the entry, returned in the response when you create an ultimate parent company. Required when updating an existing entry in an `/updateAccountHolder` request. | getUltimateParentCompanyCode(): ?string | setUltimateParentCompanyCode(?string ultimateParentCompanyCode): void |

## Example

```php
use AdyenLib\Models\Builders\UltimateParentCompanyBuilder;
use AdyenLib\Models\Builders\ViasAddress1Builder;
use AdyenLib\Models\Builders\UltimateParentCompanyBusinessDetails2Builder;

$ultimateParentCompany = UltimateParentCompanyBuilder::init()
    ->address(
        ViasAddress1Builder::init(
            'country0'
        )
            ->city('city6')
            ->houseNumberOrName('houseNumberOrName4')
            ->postalCode('postalCode8')
            ->stateOrProvince('stateOrProvince4')
            ->street('street6')
            ->build()
    )
    ->businessDetails(
        UltimateParentCompanyBusinessDetails2Builder::init()
            ->legalBusinessName('legalBusinessName8')
            ->registrationNumber('registrationNumber6')
            ->stockExchange('stockExchange4')
            ->stockNumber('stockNumber6')
            ->stockTicker('stockTicker6')
            ->build()
    )
    ->ultimateParentCompanyCode('ultimateParentCompanyCode6')
    ->build();
```

