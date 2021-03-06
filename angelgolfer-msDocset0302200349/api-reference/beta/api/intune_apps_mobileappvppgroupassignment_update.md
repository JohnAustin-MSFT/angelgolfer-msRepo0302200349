﻿# Update mobileAppVppGroupAssignment

> **Important:** APIs under the /beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported.

> **Note:** Using the Microsoft Graph APIs to configure Intune controls and policies still requires that the Intune service is [correctly licensed](https://go.microsoft.com/fwlink/?linkid=839381) by the customer.

Update the properties of a [mobileAppVppGroupAssignment](../resources/intune_apps_mobileappvppgroupassignment.md) object.
## Prerequisites
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](../../../concepts/permissions_reference.md).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementApps.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /deviceAppManagement/mobileApps/{mobileAppId}/groupAssignments/{mobileAppGroupAssignmentId}
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
In the request body, supply a JSON representation for the [mobileAppVppGroupAssignment](../resources/intune_apps_mobileappvppgroupassignment.md) object.

The following table shows the properties that are required when you create the [mobileAppVppGroupAssignment](../resources/intune_apps_mobileappvppgroupassignment.md).

|Property|Type|Description|
|:---|:---|:---|
|id|String|Key of the entity. Inherited from [mobileAppGroupAssignment](../resources/intune_apps_mobileappgroupassignment.md)|
|targetGroupId|String|The Id of the AAD group we are targeting the mobile app to. Inherited from [mobileAppGroupAssignment](../resources/intune_apps_mobileappgroupassignment.md)|
|vpnConfigurationId|String|The Id of the Vpn Profile to apply for this app. Inherited from [mobileAppGroupAssignment](../resources/intune_apps_mobileappgroupassignment.md)|
|installIntent|String|The install intent defined by the admin. Inherited from [mobileAppGroupAssignment](../resources/intune_apps_mobileappgroupassignment.md) Possible values are: `available`, `notApplicable`, `required`, `uninstall`, `availableWithoutEnrollment`.|
|useDeviceLicensing|Boolean|Whether or not to use device licensing.|



## Response
If successful, this method returns a `200 OK` response code and an updated [mobileAppVppGroupAssignment](../resources/intune_apps_mobileappvppgroupassignment.md) object in the response body.

## Example
### Request
Here is an example of the request.
``` http
PATCH https://graph.microsoft.com/beta/deviceAppManagement/mobileApps/{mobileAppId}/groupAssignments/{mobileAppGroupAssignmentId}
Content-type: application/json
Content-length: 171

{
  "targetGroupId": "Target Group Id value",
  "vpnConfigurationId": "Vpn Configuration Id value",
  "installIntent": "notApplicable",
  "useDeviceLicensing": true
}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 286

{
  "@odata.type": "#microsoft.graph.mobileAppVppGroupAssignment",
  "id": "89a8674a-674a-89a8-4a67-a8894a67a889",
  "targetGroupId": "Target Group Id value",
  "vpnConfigurationId": "Vpn Configuration Id value",
  "installIntent": "notApplicable",
  "useDeviceLicensing": true
}
```



