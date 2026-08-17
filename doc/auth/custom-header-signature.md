
# Custom Header Signature



Documentation for accessing and setting credentials for ApiKeyAuth.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| X-API-Key | `string` | - | `xAPIKey` | `getXAPIKey()` |



**Note:** Auth credentials can be set using `ApiKeyAuthCredentialsBuilder::init()` in `apiKeyAuthCredentials` method in the client builder and accessed through `getApiKeyAuthCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use AdyenLib\Authentication\ApiKeyAuthCredentialsBuilder;
use AdyenLib\AdyenClientBuilder;

$client = AdyenClientBuilder::init()
    ->apiKeyAuthCredentials(
        ApiKeyAuthCredentialsBuilder::init(
            'X-API-Key'
        )
    )
    ->build();
```


