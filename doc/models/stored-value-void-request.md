
# Stored Value Void Request

## Structure

`StoredValueVoidRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantAccount` | `string` | Required | The merchant account identifier, with which you want to process the transaction. | getMerchantAccount(): string | setMerchantAccount(string merchantAccount): void |
| `originalReference` | `string` | Required | The original pspReference of the payment to modify. | getOriginalReference(): string | setOriginalReference(string originalReference): void |
| `reference` | `?string` | Optional | Your reference for the payment modification. This reference is visible in Customer Area and in reports.<br>Maximum length: 80 characters. | getReference(): ?string | setReference(?string reference): void |
| `store` | `?string` | Optional | The physical store, for which this payment is processed.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `16` | getStore(): ?string | setStore(?string store): void |
| `tenderReference` | `?string` | Optional | The reference of the tender. | getTenderReference(): ?string | setTenderReference(?string tenderReference): void |
| `uniqueTerminalId` | `?string` | Optional | The unique ID of a POS terminal. | getUniqueTerminalId(): ?string | setUniqueTerminalId(?string uniqueTerminalId): void |

## Example

```php
use AdyenLib\Models\Builders\StoredValueVoidRequestBuilder;

$storedValueVoidRequest = StoredValueVoidRequestBuilder::init(
    'merchantAccount2',
    'originalReference6'
)
    ->reference('reference4')
    ->store('store0')
    ->tenderReference('tenderReference2')
    ->uniqueTerminalId('uniqueTerminalId0')
    ->build();
```

