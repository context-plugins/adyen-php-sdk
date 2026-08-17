
# Me Api Credential

## Structure

`MeApiCredential`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?ApiCredentialLinks2`](../../doc/models/api-credential-links-2.md) | Optional | References to resources linked to the API credential. | getLinks(): ?ApiCredentialLinks2 | setLinks(?ApiCredentialLinks2 links): void |
| `active` | `bool` | Required | Indicates if the API credential is enabled. Must be set to **true** to use the credential in your integration. | getActive(): bool | setActive(bool active): void |
| `allowedIpAddresses` | `string[]` | Required | List of IP addresses from which your client can make requests.<br><br>If the list is empty, we allow requests from any IP.<br>If the list is not empty and we get a request from an IP which is not on the list, you get a security error. | getAllowedIpAddresses(): array | setAllowedIpAddresses(array allowedIpAddresses): void |
| `allowedOrigins` | [`?(AllowedOrigin[])`](../../doc/models/allowed-origin.md) | Optional | List containing the [allowed origins](https://docs.adyen.com/development-resources/client-side-authentication#allowed-origins) linked to the API credential. | getAllowedOrigins(): ?array | setAllowedOrigins(?array allowedOrigins): void |
| `clientKey` | `string` | Required | Public key used for [client-side authentication](https://docs.adyen.com/development-resources/client-side-authentication). The client key is required for Drop-in and Components integrations. | getClientKey(): string | setClientKey(string clientKey): void |
| `companyName` | `?string` | Optional | Name of the company linked to the API credential. | getCompanyName(): ?string | setCompanyName(?string companyName): void |
| `description` | `?string` | Optional | Description of the API credential.<br><br>**Constraints**: *Maximum Length*: `50` | getDescription(): ?string | setDescription(?string description): void |
| `id` | `string` | Required | Unique identifier of the API credential. | getId(): string | setId(string id): void |
| `roles` | `string[]` | Required | List of [roles](https://docs.adyen.com/development-resources/api-credentials#roles-1) for the API credential. | getRoles(): array | setRoles(array roles): void |
| `subjectDN` | `?string` | Optional | The subject DN of the certificate issued by Adyen. | getSubjectDN(): ?string | setSubjectDN(?string subjectDN): void |
| `username` | `string` | Required | The name of the [API credential](https://docs.adyen.com/development-resources/api-credentials), for example **ws@Company.TestCompany**. | getUsername(): string | setUsername(string username): void |

## Example

```php
use AdyenLib\Models\Builders\MeApiCredentialBuilder;
use AdyenLib\Models\Builders\ApiCredentialLinks2Builder;
use AdyenLib\Models\Builders\LinksElement6Builder;
use AdyenLib\Models\Builders\LinksElement1Builder;
use AdyenLib\Models\Builders\LinksElement2Builder;
use AdyenLib\Models\Builders\LinksElement3Builder;
use AdyenLib\Models\Builders\LinksElement4Builder;
use AdyenLib\Models\Builders\LinksElement5Builder;
use AdyenLib\Models\Builders\AllowedOriginBuilder;
use AdyenLib\Models\Builders\Links2Builder;

$meApiCredential = MeApiCredentialBuilder::init(
    false,
    [
        'allowedIpAddresses7',
        'allowedIpAddresses8'
    ],
    'clientKey8',
    'id8',
    [
        'roles8',
        'roles9'
    ],
    'username2'
)
    ->links(
        ApiCredentialLinks2Builder::init(
            LinksElement6Builder::init()
                ->href('href0')
                ->build()
        )
            ->allowedOrigins(
                LinksElement1Builder::init()
                    ->href('href6')
                    ->build()
            )
            ->company(
                LinksElement2Builder::init()
                    ->href('href2')
                    ->build()
            )
            ->generateApiKey(
                LinksElement3Builder::init()
                    ->href('href6')
                    ->build()
            )
            ->generateClientKey(
                LinksElement4Builder::init()
                    ->href('href4')
                    ->build()
            )
            ->merchant(
                LinksElement5Builder::init()
                    ->href('href6')
                    ->build()
            )
            ->build()
    )
    ->allowedOrigins(
        [
            AllowedOriginBuilder::init(
                'domain0'
            )
                ->links(
                    Links2Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )->build()
                )
                ->id('id4')
                ->build(),
            AllowedOriginBuilder::init(
                'domain0'
            )
                ->links(
                    Links2Builder::init(
                        LinksElement6Builder::init()
                            ->href('href0')
                            ->build()
                    )->build()
                )
                ->id('id4')
                ->build()
        ]
    )
    ->companyName('companyName0')
    ->description('description2')
    ->subjectDN('subjectDN8')
    ->build();
```

