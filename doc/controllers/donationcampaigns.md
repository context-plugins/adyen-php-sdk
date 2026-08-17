# Donationcampaigns

```php
$donationcampaignsApi = $client->getDonationcampaignsApi();
```

## Class Name

`DonationcampaignsApi`

## Methods

* [Post-Companies-Company Id-Campaign Management](../../doc/controllers/donationcampaigns.md#post-companies-company-id-campaign-management)
* [Get-Companies-Company Id-Campaign Management-Account Holders-Account Holder Id](../../doc/controllers/donationcampaigns.md#get-companies-company-id-campaign-management-account-holders-account-holder-id)
* [Delete-Companies-Company Id-Campaign Management-Donation Campaign Id](../../doc/controllers/donationcampaigns.md#delete-companies-company-id-campaign-management-donation-campaign-id)
* [Patch-Companies-Company Id-Campaign Management-Donation Campaign Id](../../doc/controllers/donationcampaigns.md#patch-companies-company-id-campaign-management-donation-campaign-id)
* [Post-Companies-Company Id-Campaign Management-Donation Campaign Id-Status-Status](../../doc/controllers/donationcampaigns.md#post-companies-company-id-campaign-management-donation-campaign-id-status-status)
* [Post-Companies-Company Id-Nonprofits](../../doc/controllers/donationcampaigns.md#post-companies-company-id-nonprofits)


# Post-Companies-Company Id-Campaign Management

Creates a new donation campaign, to give shoppers the option to donate to a nonprofit organization when making a payment. A campaign can be for online payments, in-person payments, or both online and in-person payments.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Campaign Management read and write

```php
function postCompaniesCompanyIdCampaignManagement(
    string $companyId,
    ?DonationCampaignRequest $body = null
): DonationCampaign1
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `body` | [`?DonationCampaignRequest`](../../doc/models/donation-campaign-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DonationCampaign1`](../../doc/models/donation-campaign-1.md)

## Example Usage

```php
$companyId = 'companyId0';

$donationCampaignsApi = $client->getDonationCampaignsApi();

try {
    $result = $donationCampaignsApi->postCompaniesCompanyIdCampaignManagement($companyId);
    echo 'DonationCampaign1:';
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
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Get-Companies-Company Id-Campaign Management-Account Holders-Account Holder Id

Returns a paginated list of donation campaigns associated with the account holder specified in the path. You can filter the list by campaign status.

To make this request, your API credential must have one of the following [roles](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Campaign Management read
* Management API—Campaign Management read and write

```php
function getCompaniesCompanyIdCampaignManagementAccountHoldersAccountHolderId(
    string $companyId,
    string $accountHolderId,
    ?string $status = null,
    ?int $pageNumber = 1,
    ?int $pageSize = 10
): ListDonationCampaignsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `accountHolderId` | `string` | Template, Required | The unique identifier of the account holder. |
| `status` | `?string` | Query, Optional | The campaign status to return campaigns that match. Allowed values: **inactive**, **active**, or **ended**. |
| `pageNumber` | `?int` | Query, Optional | The number of the page to fetch.<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1` |
| `pageSize` | `?int` | Query, Optional | The number of items to have on a page, maximum 100. The default is 10 items on a page.<br><br>**Default**: `10`<br><br>**Constraints**: `>= 1`, `<= 100` |

## Response Type

**200**: OK - the request has succeeded.

[`ListDonationCampaignsResponse`](../../doc/models/list-donation-campaigns-response.md)

## Example Usage

```php
$companyId = 'companyId0';

$accountHolderId = 'accountHolderId8';

$pageNumber = 1;

$pageSize = 10;

$donationCampaignsApi = $client->getDonationCampaignsApi();

try {
    $result = $donationCampaignsApi->getCompaniesCompanyIdCampaignManagementAccountHoldersAccountHolderId(
        $companyId,
        $accountHolderId,
        null,
        $pageNumber,
        $pageSize
    );
    echo 'ListDonationCampaignsResponse:';
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
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Delete-Companies-Company Id-Campaign Management-Donation Campaign Id

Removes the donation campaign specified in the path. This request is only allowed if the campaign has the status **inactive**.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Campaign Management read and write

```php
function deleteCompaniesCompanyIdCampaignManagementDonationCampaignId(
    string $companyId,
    string $donationCampaignId
): void
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `donationCampaignId` | `string` | Template, Required | The unique identifier of the donation campaign to be deleted. |

## Response Type

**204**: No Content - the request has been successfully processed, but there is no additional content.

`void`

## Example Usage

```php
$companyId = 'companyId0';

$donationCampaignId = 'donationCampaignId0';

$donationCampaignsApi = $client->getDonationCampaignsApi();

try {
    $donationCampaignsApi->deleteCompaniesCompanyIdCampaignManagementDonationCampaignId(
        $companyId,
        $donationCampaignId
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
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Patch-Companies-Company Id-Campaign Management-Donation Campaign Id

Updates the properties of the donation campaign specified in the path. Note the following restrictions:

* You cannot use a PATCH request to update the campaign status. To activate or end a campaign, make a POST request to the `/campaignManagement/{campaignId}/status/{status}` endpoint.
* You get a validation error if you add account holders that are not compatible with the nonprofit.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Campaign Management read and write

```php
function patchCompaniesCompanyIdCampaignManagementDonationCampaignId(
    string $companyId,
    string $donationCampaignId,
    ?DonationCampaignUpdate $body = null
): DonationCampaign1
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `donationCampaignId` | `string` | Template, Required | The unique identifier of the donation campaign to be updated. |
| `body` | [`?DonationCampaignUpdate`](../../doc/models/donation-campaign-update.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`DonationCampaign1`](../../doc/models/donation-campaign-1.md)

## Example Usage

```php
$companyId = 'companyId0';

$donationCampaignId = 'donationCampaignId0';

$donationCampaignsApi = $client->getDonationCampaignsApi();

try {
    $result = $donationCampaignsApi->patchCompaniesCompanyIdCampaignManagementDonationCampaignId(
        $companyId,
        $donationCampaignId
    );
    echo 'DonationCampaign1:';
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
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Companies-Company Id-Campaign Management-Donation Campaign Id-Status-Status

Starts or stops the donation campaign specified in the path, by providing a path parameter.
Use the path parameter **activate** to start an inactive campaign, or **end** to stop an active campaign. Other status transitions are not allowed.

To make this request, your API credential must have the following [role](https://docs.adyen.com/development-resources/api-credentials#api-permissions):

* Management API—Campaign Management read and write

```php
function postCompaniesCompanyIdCampaignManagementDonationCampaignIdStatusStatus(
    string $companyId,
    string $donationCampaignId,
    string $status
): DonationCampaign1
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `donationCampaignId` | `string` | Template, Required | The unique identifier of the donation campaign to activate or end. |
| `status` | [`string(CampaignStatusTransitionEnum)`](../../doc/models/campaign-status-transition-enum.md) | Template, Required | The desired status change. Possible values: **activate** or **end**. |

## Response Type

**200**: OK - the request has succeeded.

[`DonationCampaign1`](../../doc/models/donation-campaign-1.md)

## Example Usage

```php
$companyId = 'companyId0';

$donationCampaignId = 'donationCampaignId0';

$status = CampaignStatusTransitionEnum::ACTIVATE;

$donationCampaignsApi = $client->getDonationCampaignsApi();

try {
    $result = $donationCampaignsApi->postCompaniesCompanyIdCampaignManagementDonationCampaignIdStatusStatus(
        $companyId,
        $donationCampaignId,
        $status
    );
    echo 'DonationCampaign1:';
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
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |


# Post-Companies-Company Id-Nonprofits

Returns a list of supported nonprofit organizations to choose from when creating a donation campaign. The list only contains nonprofits that are compatible with all the account holders specified in the request.

```php
function postCompaniesCompanyIdNonprofits(
    string $companyId,
    ?string $searchTerm = null,
    ?int $pageNumber = null,
    ?int $pageSize = 10,
    ?array $goal = null,
    ?ListNonprofitsRequest $body = null
): ListNonprofitsResponse
```

## Authentication

This endpoint requires [BasicAuth](../../doc/auth/basic-authentication.md) **OR** [ApiKeyAuth](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `companyId` | `string` | Template, Required | The unique identifier of the company account. |
| `searchTerm` | `?string` | Query, Optional | A query to return nonprofit organizations for, maximum 100 characters. For example, `&searchTerm=clean%20water`.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `100` |
| `pageNumber` | `?int` | Query, Optional | The number of the page to fetch.<br><br>**Constraints**: `>= 1` |
| `pageSize` | `?int` | Query, Optional | The number of items to have on a page, maximum 100. The default is 10 items on a page.<br><br>**Default**: `10`<br><br>**Constraints**: `>= 1`, `<= 100` |
| `goal` | `?(string[])` | Query, Optional | One or more United Nations Sustainable Development Goals to return nonprofit organizations for. Format: `unsdg_<number>`, for example, `&goal=unsdg_6&goal=unsdg_2`. |
| `body` | [`?ListNonprofitsRequest`](../../doc/models/list-nonprofits-request.md) | Body, Optional | - |

## Response Type

**200**: OK - the request has succeeded.

[`ListNonprofitsResponse`](../../doc/models/list-nonprofits-response.md)

## Example Usage

```php
$companyId = 'companyId0';

$pageSize = 10;

$donationCampaignsApi = $client->getDonationCampaignsApi();

try {
    $result = $donationCampaignsApi->postCompaniesCompanyIdNonprofits(
        $companyId,
        null,
        null,
        $pageSize
    );
    echo 'ListNonprofitsResponse:';
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
| 400 | Bad Request - a problem reading or understanding the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 401 | Unauthorized - authentication required. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 403 | Forbidden - insufficient permissions to process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 422 | Unprocessable Entity - a request validation error. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |
| 500 | Internal Server Error - the server could not process the request. | [`DefaultErrorResponseEntityException`](../../doc/models/default-error-response-entity-exception.md) |

