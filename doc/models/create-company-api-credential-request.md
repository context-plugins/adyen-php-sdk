
# Create Company Api Credential Request

## Structure

`CreateCompanyApiCredentialRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowedOrigins` | `?(string[])` | Optional | List of [allowed origins](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins) for the new API credential. | getAllowedOrigins(): ?array | setAllowedOrigins(?array allowedOrigins): void |
| `associatedMerchantAccounts` | `?(string[])` | Optional | List of merchant accounts that the API credential has access to. | getAssociatedMerchantAccounts(): ?array | setAssociatedMerchantAccounts(?array associatedMerchantAccounts): void |
| `description` | `?string` | Optional | Description of the API credential. | getDescription(): ?string | setDescription(?string description): void |
| `roles` | `?(string[])` | Optional | List of [roles](https://docs.adyen.com/development-resources/api-credentials#roles-1) for the API credential. Only roles assigned to 'ws@Company.<CompanyName>' can be assigned to other API credentials. | getRoles(): ?array | setRoles(?array roles): void |

## Example

```php
use AdyenLib\Models\Builders\CreateCompanyApiCredentialRequestBuilder;

$createCompanyApiCredentialRequest = CreateCompanyApiCredentialRequestBuilder::init()
    ->allowedOrigins(
        [
            'allowedOrigins8',
            'allowedOrigins7'
        ]
    )
    ->associatedMerchantAccounts(
        [
            'associatedMerchantAccounts8'
        ]
    )
    ->description('description8')
    ->roles(
        [
            'roles2',
            'roles1',
            'roles0'
        ]
    )
    ->build();
```

