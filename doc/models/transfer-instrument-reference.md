
# Transfer Instrument Reference

## Structure

`TransferInstrumentReference`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountIdentifier` | `string` | Required | The masked IBAN or bank account number. | getAccountIdentifier(): string | setAccountIdentifier(string accountIdentifier): void |
| `id` | `string` | Required | The unique identifier of the resource. | getId(): string | setId(string id): void |
| `realLastFour` | `?string` | Optional | Four last digits of the bank account number. If the transfer instrument is created using [instant bank account verification](https://docs.adyen.com/release-notes/platforms-and-financial-products#releaseNote=2023-05-08-hosted-onboarding), and it is a virtual bank account, these digits may be different from the last four digits of the masked account number. | getRealLastFour(): ?string | setRealLastFour(?string realLastFour): void |
| `trustedSource` | `?bool` | Optional, Read-only | Identifies if the bank account was created through [instant bank verification](https://docs.adyen.com/release-notes/platforms-and-financial-products#releaseNote=2023-05-08-hosted-onboarding). | getTrustedSource(): ?bool | setTrustedSource(?bool trustedSource): void |

## Example

```php
use AdyenLib\Models\Builders\TransferInstrumentReferenceBuilder;

$transferInstrumentReference = TransferInstrumentReferenceBuilder::init(
    'accountIdentifier8',
    'id6'
)
    ->realLastFour('realLastFour4')
    ->build();
```

