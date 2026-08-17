
# Card Identification 3

Contains the identification details of the card.

## Structure

`CardIdentification3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `expiryMonth` | `?string` | Optional | The expiry month of the card.<br><br>Format: two digits. Add a leading zero for single-digit months. For example:<br><br>* 03 = March<br>* 11 = November<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getExpiryMonth(): ?string | setExpiryMonth(?string expiryMonth): void |
| `expiryYear` | `?string` | Optional | The expiry year of the card.<br><br>Format: four digits. For example: 2020<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `4` | getExpiryYear(): ?string | setExpiryYear(?string expiryYear): void |
| `issueNumber` | `?string` | Optional | The issue number of the card. Applies only to some UK debit cards.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `2` | getIssueNumber(): ?string | setIssueNumber(?string issueNumber): void |
| `number` | `?string` | Optional | The card number without any separators.<br><br>For security, the response only includes the last four digits of the card number.<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `19` | getNumber(): ?string | setNumber(?string number): void |
| `startMonth` | `?string` | Optional | The month when the card was issued. Applies only to some UK debit cards.<br><br>Format: two digits. Add a leading zero for single-digit months. For example:<br><br>* 03 = March<br>* 11 = November<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `2` | getStartMonth(): ?string | setStartMonth(?string startMonth): void |
| `startYear` | `?string` | Optional | The year when the card was issued. Applies only to some UK debit cards.<br><br>Format: four digits. For example: 2020<br><br>**Constraints**: *Minimum Length*: `4`, *Maximum Length*: `4` | getStartYear(): ?string | setStartYear(?string startYear): void |
| `storedPaymentMethodId` | `?string` | Optional | The unique [token](/payouts/payout-service/pay-out-to-cards/manage-card-information#save-card-details) created to identify the counterparty. | getStoredPaymentMethodId(): ?string | setStoredPaymentMethodId(?string storedPaymentMethodId): void |

## Example

```php
use AdyenLib\Models\Builders\CardIdentification3Builder;

$cardIdentification3 = CardIdentification3Builder::init()
    ->expiryMonth('expiryMonth8')
    ->expiryYear('expiryYear2')
    ->issueNumber('issueNumber4')
    ->number('number8')
    ->startMonth('startMonth4')
    ->build();
```

