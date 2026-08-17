
# Update Company Webhook Request

## Structure

`UpdateCompanyWebhookRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acceptsExpiredCertificate` | `?bool` | Optional | Indicates if expired SSL certificates are accepted. Default value: **false**. | getAcceptsExpiredCertificate(): ?bool | setAcceptsExpiredCertificate(?bool acceptsExpiredCertificate): void |
| `acceptsSelfSignedCertificate` | `?bool` | Optional | Indicates if self-signed SSL certificates are accepted. Default value: **false**. | getAcceptsSelfSignedCertificate(): ?bool | setAcceptsSelfSignedCertificate(?bool acceptsSelfSignedCertificate): void |
| `acceptsUntrustedRootCertificate` | `?bool` | Optional | Indicates if untrusted SSL certificates are accepted. Default value: **false**. | getAcceptsUntrustedRootCertificate(): ?bool | setAcceptsUntrustedRootCertificate(?bool acceptsUntrustedRootCertificate): void |
| `active` | `?bool` | Optional | Indicates if the webhook configuration is active. The field must be **true** for us to send webhooks about events related an account. | getActive(): ?bool | setActive(?bool active): void |
| `additionalSettings` | [`?AdditionalSettings1`](../../doc/models/additional-settings-1.md) | Optional | Additional shopper and transaction information to be included in your [standard webhooks](https://docs.adyen.com/development-resources/webhooks/webhook-types/#event-codes). Find out more about the available [additional settings](https://docs.adyen.com/development-resources/webhooks/additional-settings). | getAdditionalSettings(): ?AdditionalSettings1 | setAdditionalSettings(?AdditionalSettings1 additionalSettings): void |
| `communicationFormat` | [`?string(CommunicationFormatEnum)`](../../doc/models/communication-format-enum.md) | Optional | Format or protocol for receiving webhooks. Possible values:<br><br>* **soap**<br>* **http**<br>* **json** | getCommunicationFormat(): ?string | setCommunicationFormat(?string communicationFormat): void |
| `description` | `?string` | Optional | Your description for this webhook configuration. | getDescription(): ?string | setDescription(?string description): void |
| `encryptionProtocol` | [`?string(EncryptionProtocolEnum)`](../../doc/models/encryption-protocol-enum.md) | Optional | SSL version to access the public webhook URL specified in the `url` field. Possible values:<br><br>* **TLSv1.3**<br>* **TLSv1.2**<br>* **HTTP** - Only allowed on Test environment.<br><br>If not specified, the webhook will use `sslVersion`: **TLSv1.2**. | getEncryptionProtocol(): ?string | setEncryptionProtocol(?string encryptionProtocol): void |
| `filterMerchantAccountType` | [`?string(FilterMerchantAccountType2Enum)`](../../doc/models/filter-merchant-account-type-2-enum.md) | Optional | Shows how merchant accounts are filtered when configuring the webhook. Possible values:<br><br>* **includeAccounts**: The webhook is configured for the merchant accounts listed in `filterMerchantAccounts`.<br>* **excludeAccounts**: The webhook is not configured for the merchant accounts listed in `filterMerchantAccounts`.<br>* **allAccounts**: Includes all merchant accounts, and does not require specifying `filterMerchantAccounts`. | getFilterMerchantAccountType(): ?string | setFilterMerchantAccountType(?string filterMerchantAccountType): void |
| `filterMerchantAccounts` | `?(string[])` | Optional | A list of merchant account names that are included or excluded from receiving the webhook. Inclusion or exclusion is based on the value defined for `filterMerchantAccountType`.<br><br>Required if `filterMerchantAccountType` is either:<br><br>* **includeAccounts**<br>* **excludeAccounts**<br><br>Not needed for `filterMerchantAccountType`: **allAccounts**. | getFilterMerchantAccounts(): ?array | setFilterMerchantAccounts(?array filterMerchantAccounts): void |
| `networkType` | [`?string(NetworkTypeEnum)`](../../doc/models/network-type-enum.md) | Optional | Network type for Terminal API notification webhooks. Possible values:<br><br>* **public**<br>* **local**<br><br>Default Value: **public**. | getNetworkType(): ?string | setNetworkType(?string networkType): void |
| `password` | `?string` | Optional | Password to access the webhook URL. | getPassword(): ?string | setPassword(?string password): void |
| `populateSoapActionHeader` | `?bool` | Optional | Indicates if the SOAP action header needs to be populated. Default value: **false**.<br><br>Only applies if `communicationFormat`: **soap**. | getPopulateSoapActionHeader(): ?bool | setPopulateSoapActionHeader(?bool populateSoapActionHeader): void |
| `url` | `?string` | Optional | Public URL where webhooks will be sent, for example **https://www.domain.com/webhook-endpoint**. | getUrl(): ?string | setUrl(?string url): void |
| `username` | `?string` | Optional | Username to access the webhook URL.<br><br>**Constraints**: *Maximum Length*: `255` | getUsername(): ?string | setUsername(?string username): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateCompanyWebhookRequestBuilder;
use AdyenLib\Models\Builders\AdditionalSettings1Builder;
use AdyenLib\Models\CommunicationFormatEnum;
use AdyenLib\Models\EncryptionProtocolEnum;

$updateCompanyWebhookRequest = UpdateCompanyWebhookRequestBuilder::init()
    ->acceptsExpiredCertificate(false)
    ->acceptsSelfSignedCertificate(false)
    ->acceptsUntrustedRootCertificate(false)
    ->active(false)
    ->additionalSettings(
        AdditionalSettings1Builder::init()
            ->includeEventCodes(
                [
                    'includeEventCodes8'
                ]
            )
            ->properties(
                [
                    'key0' => false,
                    'key1' => true
                ]
            )
            ->build()
    )
    ->communicationFormat(CommunicationFormatEnum::SOAP)
    ->encryptionProtocol(EncryptionProtocolEnum::ENUM_TLSV12)
    ->url('http://www.adyen.com')
    ->build();
```

