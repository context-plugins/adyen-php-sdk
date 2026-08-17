
# Authentication Session Request

## Structure

`AuthenticationSessionRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowOrigin` | `string` | Required | The URL where the component will appear. In your live environment, you must protect the URL with an SSL certificate and ensure that it starts with `https://`. | getAllowOrigin(): string | setAllowOrigin(string allowOrigin): void |
| `policy` | [`Policy2`](../../doc/models/policy-2.md) | Required | An object that contains a description of the allowed resources and roles for the requested session. | getPolicy(): Policy2 | setPolicy(Policy2 policy): void |
| `product` | [`string(ProductType2Enum)`](../../doc/models/product-type-2-enum.md) | Required | The type of component.<br><br>For [Onboarding components](https://docs.adyen.com/platforms/onboard-users/components), set this to **onboarding**.<br><br>For [Platform Experience components](https://docs.adyen.com/platforms/build-user-dashboards), set this to **platform**. | getProduct(): string | setProduct(string product): void |

## Example

```php
use AdyenLib\Models\Builders\AuthenticationSessionRequestBuilder;
use AdyenLib\Models\Builders\Policy2Builder;
use AdyenLib\Models\Builders\Resource2Builder;
use AdyenLib\Models\ProductType2Enum;

$authenticationSessionRequest = AuthenticationSessionRequestBuilder::init(
    'allowOrigin0',
    Policy2Builder::init()
        ->resources(
            [
                Resource2Builder::init()
                    ->type('Resource')
                    ->build()
            ]
        )
        ->roles(
            [
                'roles8'
            ]
        )
        ->build(),
    ProductType2Enum::ONBOARDING
)->build();
```

