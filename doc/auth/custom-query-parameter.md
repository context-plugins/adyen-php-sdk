
# Custom Query Parameter



Documentation for accessing and setting credentials for clientKey.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| clientKey | `string` | - | `clientKey` | `getClientKey()` |



**Note:** Auth credentials can be set using `ClientKeyCredentialsBuilder::init()` in `clientKeyCredentials` method in the client builder and accessed through `getClientKeyCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```php
use AdyenLib\Authentication\ClientKeyCredentialsBuilder;
use AdyenLib\AdyenClientBuilder;

$client = AdyenClientBuilder::init()
    ->clientKeyCredentials(
        ClientKeyCredentialsBuilder::init(
            'clientKey'
        )
    )
    ->build();
```


