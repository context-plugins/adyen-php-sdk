
# Webhook

## Structure

`Webhook`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?WebhookLinks2`](../../doc/models/webhook-links-2.md) | Optional | References to resources connected with this webhook. | getLinks(): ?WebhookLinks2 | setLinks(?WebhookLinks2 links): void |
| `acceptsExpiredCertificate` | `?bool` | Optional | Indicates if expired SSL certificates are accepted. Default value: **false**. | getAcceptsExpiredCertificate(): ?bool | setAcceptsExpiredCertificate(?bool acceptsExpiredCertificate): void |
| `acceptsSelfSignedCertificate` | `?bool` | Optional | Indicates if self-signed SSL certificates are accepted. Default value: **false**. | getAcceptsSelfSignedCertificate(): ?bool | setAcceptsSelfSignedCertificate(?bool acceptsSelfSignedCertificate): void |
| `acceptsUntrustedRootCertificate` | `?bool` | Optional | Indicates if untrusted SSL certificates are accepted. Default value: **false**. | getAcceptsUntrustedRootCertificate(): ?bool | setAcceptsUntrustedRootCertificate(?bool acceptsUntrustedRootCertificate): void |
| `accountReference` | `?string` | Optional | Reference to the account the webook is set on. | getAccountReference(): ?string | setAccountReference(?string accountReference): void |
| `active` | `bool` | Required | Indicates if the webhook configuration is active. The field must be **true** for you to receive webhooks about events related an account. | getActive(): bool | setActive(bool active): void |
| `additionalSettings` | [`?AdditionalSettingsResponse1`](../../doc/models/additional-settings-response-1.md) | Optional | Additional shopper and transaction information to be included in your [standard webhooks](https://docs.adyen.com/development-resources/webhooks/webhook-types/#event-codes). Find out more about the available [additional settings](https://docs.adyen.com/development-resources/webhooks/additional-settings). | getAdditionalSettings(): ?AdditionalSettingsResponse1 | setAdditionalSettings(?AdditionalSettingsResponse1 additionalSettings): void |
| `certificateAlias` | `?string` | Optional | The alias of our SSL certificate. When you receive a notification from us, the alias from the HMAC signature will match this alias. | getCertificateAlias(): ?string | setCertificateAlias(?string certificateAlias): void |
| `communicationFormat` | [`string(CommunicationFormatEnum)`](../../doc/models/communication-format-enum.md) | Required | Format or protocol for receiving webhooks. Possible values:<br><br>* **soap**<br>* **http**<br>* **json** | getCommunicationFormat(): string | setCommunicationFormat(string communicationFormat): void |
| `description` | `?string` | Optional | Your description for this webhook configuration. | getDescription(): ?string | setDescription(?string description): void |
| `encryptionProtocol` | [`?string(EncryptionProtocolEnum)`](../../doc/models/encryption-protocol-enum.md) | Optional | SSL version to access the public webhook URL specified in the `url` field. Possible values:<br><br>* **TLSv1.3**<br>* **TLSv1.2**<br>* **HTTP** - Only allowed on Test environment.<br><br>If not specified, the webhook will use `sslVersion`: **TLSv1.2**. | getEncryptionProtocol(): ?string | setEncryptionProtocol(?string encryptionProtocol): void |
| `filterMerchantAccountType` | [`?string(FilterMerchantAccountType1Enum)`](../../doc/models/filter-merchant-account-type-1-enum.md) | Optional | Shows how merchant accounts are included in company-level webhooks. Possible values:<br><br>* **includeAccounts**<br>* **excludeAccounts**<br>* **allAccounts**: Includes all merchant accounts, and does not require specifying `filterMerchantAccounts`. | getFilterMerchantAccountType(): ?string | setFilterMerchantAccountType(?string filterMerchantAccountType): void |
| `filterMerchantAccounts` | `?(string[])` | Optional | A list of merchant account names that are included or excluded from receiving the webhook. Inclusion or exclusion is based on the value defined for `filterMerchantAccountType`.<br><br>Required if `filterMerchantAccountType` is either:<br><br>* **includeAccounts**<br>* **excludeAccounts**<br><br>Not needed for `filterMerchantAccountType`: **allAccounts**. | getFilterMerchantAccounts(): ?array | setFilterMerchantAccounts(?array filterMerchantAccounts): void |
| `hasError` | `?bool` | Optional | Indicates if the webhook configuration has errors that need troubleshooting. If the value is **true**, troubleshoot the configuration using the [testing endpoint](https://docs.adyen.com/api-explorer/#/ManagementService/v1/post/companies/{companyId}/webhooks/{webhookid}/test). | getHasError(): ?bool | setHasError(?bool hasError): void |
| `hasPassword` | `?bool` | Optional | Indicates if the webhook is password protected. | getHasPassword(): ?bool | setHasPassword(?bool hasPassword): void |
| `hmacKeyCheckValue` | `?string` | Optional | The [checksum](https://en.wikipedia.org/wiki/Key_checksum_value) of the HMAC key generated for this webhook. You can use this value to uniquely identify the HMAC key configured for this webhook. | getHmacKeyCheckValue(): ?string | setHmacKeyCheckValue(?string hmacKeyCheckValue): void |
| `id` | `?string` | Optional | Unique identifier for this webhook. | getId(): ?string | setId(?string id): void |
| `networkType` | [`?string(NetworkType2Enum)`](../../doc/models/network-type-2-enum.md) | Optional | Network type for Terminal API details webhooks. | getNetworkType(): ?string | setNetworkType(?string networkType): void |
| `populateSoapActionHeader` | `?bool` | Optional | Indicates if the SOAP action header needs to be populated. Default value: **false**.<br><br>Only applies if `communicationFormat`: **soap**. | getPopulateSoapActionHeader(): ?bool | setPopulateSoapActionHeader(?bool populateSoapActionHeader): void |
| `type` | `string` | Required | The type of webhook. Possible values are:<br><br>- **standard**<br>- **account-settings-notification**<br>- **banktransfer-notification**<br>- **boletobancario-notification**<br>- **directdebit-notification**<br>- **ach-notification-of-change-notification**<br>- **direct-debit-notice-of-change-notification**<br>- **pending-notification**<br>- **ideal-notification**<br>- **ideal-pending-notification**<br>- **report-notification**<br>- **terminal-api-notification**<br>- **terminal-settings**<br>- **terminal-boarding**<br><br>Find out more about [standard webhooks](https://docs.adyen.com/development-resources/webhooks/webhook-types/#event-codes) and [other types of webhooks](https://docs.adyen.com/development-resources/webhooks/webhook-types/#other-webhooks). | getType(): string | setType(string type): void |
| `url` | `string` | Required | Public URL where webhooks will be sent, for example **https://www.domain.com/webhook-endpoint**. | getUrl(): string | setUrl(string url): void |
| `username` | `?string` | Optional | Username to access the webhook URL. | getUsername(): ?string | setUsername(?string username): void |

## Example

```php
use AdyenLib\Models\Builders\WebhookBuilder;
use AdyenLib\Models\CommunicationFormatEnum;
use AdyenLib\Models\Builders\WebhookLinks2Builder;
use AdyenLib\Models\Builders\LinksElement16Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElement19Builder;
use AdyenLib\Models\Builders\LinksElement15Builder;
use AdyenLib\Models\Builders\LinksElement17Builder;
use AdyenLib\Models\EncryptionProtocolEnum;

$webhook = WebhookBuilder::init(
    false,
    CommunicationFormatEnum::SOAP,
    'type8',
    'http://www.adyen.com'
)
    ->links(
        WebhookLinks2Builder::init(
            LinksElement16Builder::init()
                ->href('href6')
                ->build(),
            LinksElement6Builder::init()
                ->href('href0')
                ->build(),
            LinksElement19Builder::init()
                ->href('href6')
                ->build()
        )
            ->company(
                LinksElement15Builder::init()
                    ->href('href2')
                    ->build()
            )
            ->merchant(
                LinksElement17Builder::init()
                    ->href('href6')
                    ->build()
            )
            ->build()
    )
    ->acceptsExpiredCertificate(false)
    ->acceptsSelfSignedCertificate(false)
    ->acceptsUntrustedRootCertificate(false)
    ->accountReference('accountReference0')
    ->encryptionProtocol(EncryptionProtocolEnum::ENUM_TLSV12)
    ->build();
```

