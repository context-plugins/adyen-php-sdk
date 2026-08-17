
# Test Webhook Response

## Structure

`TestWebhookResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | [`?(TestOutput[])`](../../doc/models/test-output.md) | Optional | List with test results. Each test webhook we send has a list element with the result. | getData(): ?array | setData(?array data): void |

## Example

```php
use AdyenLib\Models\Builders\TestWebhookResponseBuilder;
use AdyenLib\Models\Builders\TestOutputBuilder;

$testWebhookResponse = TestWebhookResponseBuilder::init()
    ->data(
        [
            TestOutputBuilder::init(
                'status2'
            )
                ->merchantId('merchantId6')
                ->output('output8')
                ->requestSent('requestSent0')
                ->responseCode('responseCode0')
                ->responseTime('responseTime8')
                ->build(),
            TestOutputBuilder::init(
                'status2'
            )
                ->merchantId('merchantId6')
                ->output('output8')
                ->requestSent('requestSent0')
                ->responseCode('responseCode0')
                ->responseTime('responseTime8')
                ->build(),
            TestOutputBuilder::init(
                'status2'
            )
                ->merchantId('merchantId6')
                ->output('output8')
                ->requestSent('requestSent0')
                ->responseCode('responseCode0')
                ->responseTime('responseTime8')
                ->build()
        ]
    )
    ->build();
```

