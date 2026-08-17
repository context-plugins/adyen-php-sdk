# Dispute Attachments

```php
$disputeAttachmentsApi = $client->getDisputeAttachmentsApi();
```

## Class Name

`DisputeAttachmentsApi`

## Methods

* [Get-Disputes-Dispute Id-Attachments](../../doc/controllers/dispute-attachments.md#get-disputes-dispute-id-attachments)
* [Post-Disputes-Dispute Id-Attachments](../../doc/controllers/dispute-attachments.md#post-disputes-dispute-id-attachments)
* [Delete-Disputes-Dispute Id-Attachments-Attachment Id](../../doc/controllers/dispute-attachments.md#delete-disputes-dispute-id-attachments-attachment-id)
* [Get-Disputes-Dispute Id-Attachments-Attachment Id](../../doc/controllers/dispute-attachments.md#get-disputes-dispute-id-attachments-attachment-id)


# Get-Disputes-Dispute Id-Attachments

Get a list of attachments associated with a dispute ID.

:information_source: **Note** This endpoint does not require authentication.

```php
function getDisputesDisputeIdAttachments(string $disputeId): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The unique identifier of the raised dispute. |

## Response Type

**200**: OK - the request has succeeded.

[`DisputeAttachment[]`](../../doc/models/dispute-attachment.md)

## Example Usage

```php
$disputeId = 'disputeId4';

$disputeAttachmentsApi = $client->getDisputeAttachmentsApi();

try {
    $result = $disputeAttachmentsApi->getDisputesDisputeIdAttachments($disputeId);
    echo 'DisputeAttachment[]:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Disputes-Dispute Id-Attachments

Add supporting information as an attachment for the raised dispute. Upload receipts, communication, or any other documentation to support the dispute.

:information_source: **Note** This endpoint does not require authentication.

```php
function postDisputesDisputeIdAttachments(string $disputeId, DisputeAttachment $body): AttachDocumentResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The unique identifier of the raised dispute. |
| `body` | [`DisputeAttachment`](../../doc/models/dispute-attachment.md) | Body, Required | - |

## Response Type

**200**: OK - the request has succeeded.

[`AttachDocumentResponse`](../../doc/models/attach-document-response.md)

## Example Usage

```php
$disputeId = 'disputeId4';

$body = DisputeAttachmentBuilder::init(
    AttachmentType1Enum::CORRESPONDENCE,
    'content0',
    'fileName0'
)->build();

$disputeAttachmentsApi = $client->getDisputeAttachmentsApi();

try {
    $result = $disputeAttachmentsApi->postDisputesDisputeIdAttachments(
        $disputeId,
        $body
    );
    echo 'AttachDocumentResponse:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Disputes-Dispute Id-Attachments-Attachment Id

Removes the attachment from the raised dispute. Adyen may keep this file for compliance purposes.

:information_source: **Note** This endpoint does not require authentication.

```php
function deleteDisputesDisputeIdAttachmentsAttachmentId(string $disputeId, string $attachmentId): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The unique identifier of the raised dispute. |
| `attachmentId` | `string` | Template, Required | The unique identifier of the attachment. |

## Response Type

**204**: The attachment was successfully removed

`void`

## Example Usage

```php
$disputeId = 'disputeId4';

$attachmentId = 'attachmentId8';

$disputeAttachmentsApi = $client->getDisputeAttachmentsApi();

try {
    $disputeAttachmentsApi->deleteDisputesDisputeIdAttachmentsAttachmentId(
        $disputeId,
        $attachmentId
    );
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Disputes-Dispute Id-Attachments-Attachment Id

Search for a single attachment, providing the specific dispute ID and attachment ID.

:information_source: **Note** This endpoint does not require authentication.

```php
function getDisputesDisputeIdAttachmentsAttachmentId(string $disputeId, string $attachmentId): DisputeAttachment
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `disputeId` | `string` | Template, Required | The unique identifier of the raised dispute. |
| `attachmentId` | `string` | Template, Required | The unique identifier of the attachment. |

## Response Type

**200**: OK - the request has succeeded.

[`DisputeAttachment`](../../doc/models/dispute-attachment.md)

## Example Usage

```php
$disputeId = 'disputeId4';

$attachmentId = 'attachmentId8';

$disputeAttachmentsApi = $client->getDisputeAttachmentsApi();

try {
    $result = $disputeAttachmentsApi->getDisputesDisputeIdAttachmentsAttachmentId(
        $disputeId,
        $attachmentId
    );
    echo 'DisputeAttachment:';
    var_dump($result);
} catch (DefaultErrorResponseEntityException $exp) {
    echo 'Caught DefaultErrorResponseEntityException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | A request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

