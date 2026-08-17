
# Store Detail

## Structure

`StoreDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address` | [`ViasAddress7`](../../doc/models/vias-address-7.md) | Required | The address of the physical store where the account holder will process payments from. | getAddress(): ViasAddress7 | setAddress(ViasAddress7 address): void |
| `fullPhoneNumber` | `?string` | Optional | The phone number of the store provided as a single string.  It will be handled as a landline phone.<br><br>Examples: "0031 6 11 22 33 44", "+316/1122-3344", "(0031) 611223344" | getFullPhoneNumber(): ?string | setFullPhoneNumber(?string fullPhoneNumber): void |
| `logo` | `?string` | Optional | Store logo for payment method setup. | getLogo(): ?string | setLogo(?string logo): void |
| `merchantAccount` | `string` | Required | The merchant account to which the store belongs. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `merchantCategoryCode` | `string` | Required | The merchant category code (MCC) that classifies the business of the account holder. | getMerchantCategoryCode(): string | setMerchantCategoryCode(string merchantCategoryCode): void |
| `merchantHouseNumber` | `?string` | Optional | Merchant house number for payment method setup. | getMerchantHouseNumber(): ?string | setMerchantHouseNumber(?string merchantHouseNumber): void |
| `phoneNumber` | [`?ViasPhoneNumber4`](../../doc/models/vias-phone-number-4.md) | Optional | The phone number of the store. | getPhoneNumber(): ?ViasPhoneNumber4 | setPhoneNumber(?ViasPhoneNumber4 phoneNumber): void |
| `shopperInteraction` | [`?string(PaymentFlowEnum)`](../../doc/models/payment-flow-enum.md) | Optional | The sales channel. Possible values: **Ecommerce**, **POS**. | getShopperInteraction(): ?string | setShopperInteraction(?string shopperInteraction): void |
| `splitConfigurationUUID` | `?string` | Optional | The unique reference for the split configuration, returned when you configure splits in your Customer Area. When this is provided, the `virtualAccount` is also required. Adyen uses the configuration and the `virtualAccount` to split funds between accounts in your platform. | getSplitConfigurationUUID(): ?string | setSplitConfigurationUUID(?string splitConfigurationUUID): void |
| `status` | [`?string(Status8Enum)`](../../doc/models/status-8-enum.md) | Optional | The status of the store. Possible values: **Pending**, **Active**, **Inactive**, **InactiveWithModifications**, **Closed**. | getStatus(): ?string | setStatus(?string status): void |
| `store` | `?string` | Optional | Adyen-generated unique alphanumeric identifier (UUID) for the store, returned in the response when you create a store. Required when updating an existing store in an `/updateAccountHolder` request. | getStore(): ?string | setStore(?string store): void |
| `storeName` | `?string` | Optional | The name of the account holder's store. This value is shown in shopper statements.<br><br>* Length: Between 3 to 22 characters<br><br>* The following characters are *not* supported: **:;}{$#@!\|<>%^*+=\\**<br><br>**Note:** storeName does not appear in American Express shopper statements by default. Contact Adyen Support to enable this for American Express. | getStoreName(): ?string | setStoreName(?string storeName): void |
| `storeReference` | `?string` | Optional | Your unique identifier for the store. The Customer Area also uses this value for the store description.<br><br>* Length: Between 3 to 128 characters<br><br>* The following characters are *not* supported: **:;}{$#@!\|<>%^*+=\\** | getStoreReference(): ?string | setStoreReference(?string storeReference): void |
| `virtualAccount` | `?string` | Optional | The account holder's `accountCode` where the split amount will be sent. Required when you provide the `splitConfigurationUUID`. | getVirtualAccount(): ?string | setVirtualAccount(?string virtualAccount): void |
| `webAddress` | `?string` | Optional | URL of the ecommerce store. | getWebAddress(): ?string | setWebAddress(?string webAddress): void |

## Example

```php
use AdyenLib\Models\Builders\StoreDetailBuilder;
use AdyenLib\Models\Builders\ViasAddress7Builder;
use AdyenLib\Models\Builders\ViasPhoneNumber4Builder;
use AdyenLib\Models\PhoneTypeEnum;
use AdyenLib\Models\PaymentFlowEnum;

$storeDetail = StoreDetailBuilder::init(
    ViasAddress7Builder::init(
        'country0'
    )
        ->city('city6')
        ->houseNumberOrName('houseNumberOrName4')
        ->postalCode('postalCode8')
        ->stateOrProvince('stateOrProvince4')
        ->street('street6')
        ->build(),
    'merchantAccount8',
    'merchantCategoryCode4'
)
    ->fullPhoneNumber('fullPhoneNumber0')
    ->logo('logo2')
    ->merchantHouseNumber('merchantHouseNumber4')
    ->phoneNumber(
        ViasPhoneNumber4Builder::init()
            ->phoneCountryCode('phoneCountryCode8')
            ->phoneNumber('phoneNumber0')
            ->phoneType(PhoneTypeEnum::FAX)
            ->build()
    )
    ->shopperInteraction(PaymentFlowEnum::ECOMMERCE)
    ->build();
```

