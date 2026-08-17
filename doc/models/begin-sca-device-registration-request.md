
# Begin Sca Device Registration Request

## Structure

`BeginScaDeviceRegistrationRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `string` | Required | The name of the SCA device that you are registering. You can use it to help your users identify the device.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `64` | getName(): string | setName(string name): void |
| `sdkOutput` | `string` | Required | A base64-encoded block with the data required to register the SCA device. You obtain this information by using Adyen's authentication SDK.<br><br>**Constraints**: *Minimum Length*: `0`, *Maximum Length*: `20000` | getSdkOutput(): string | setSdkOutput(string sdkOutput): void |

## Example

```php
use AdyenLib\Models\Builders\BeginScaDeviceRegistrationRequestBuilder;

$beginScaDeviceRegistrationRequest = BeginScaDeviceRegistrationRequestBuilder::init(
    'name0',
    'sdkOutput8'
)->build();
```

