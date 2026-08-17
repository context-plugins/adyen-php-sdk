
# Update Company Api Credential Request

## Structure

`UpdateCompanyApiCredentialRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `active` | `?bool` | Optional | Indicates if the API credential is enabled. | getActive(): ?bool | setActive(?bool active): void |
| `allowedOrigins` | `?(string[])` | Optional | The new list of [allowed origins](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins) for the API credential. | getAllowedOrigins(): ?array | setAllowedOrigins(?array allowedOrigins): void |
| `associatedMerchantAccounts` | `?(string[])` | Optional | List of merchant accounts that the API credential has access to. | getAssociatedMerchantAccounts(): ?array | setAssociatedMerchantAccounts(?array associatedMerchantAccounts): void |
| `description` | `?string` | Optional | Description of the API credential. | getDescription(): ?string | setDescription(?string description): void |
| `roles` | `?(string[])` | Optional | List of [roles](https://docs.adyen.com/development-resources/api-credentials#roles-1) for the API credential. Only roles assigned to 'ws@Company.<CompanyName>' can be assigned to other API credentials. | getRoles(): ?array | setRoles(?array roles): void |
| `subjectDN` | `?string` | Optional | The subject DN of the certificate issued by Adyen. | getSubjectDN(): ?string | setSubjectDN(?string subjectDN): void |

## Example

```php
use AdyenLib\Models\Builders\UpdateCompanyApiCredentialRequestBuilder;

$updateCompanyApiCredentialRequest = UpdateCompanyApiCredentialRequestBuilder::init()
    ->active(false)
    ->allowedOrigins(
        [
            'allowedOrigins0',
            'allowedOrigins1'
        ]
    )
    ->associatedMerchantAccounts(
        [
            'associatedMerchantAccounts6'
        ]
    )
    ->description('description6')
    ->roles(
        [
            'roles2',
            'roles1'
        ]
    )
    ->build();
```

