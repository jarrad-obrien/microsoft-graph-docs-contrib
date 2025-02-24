---
title: "Get virtualEventPresenter"
description: "Read the properties and relationships of a virtualEventPresenter object."
author: "frankpeng7"
ms.localizationpriority: medium
ms.subservice: "cloud-communications"
doc_type: apiPageType
---

# Get virtualEventPresenter
Namespace: microsoft.graph

Read the properties and relationships of a [virtualEventPresenter](../resources/virtualeventpresenter.md) object.

Currently the supported virtual event types are: 
- [virtualEventTownhall](../resources/virtualeventtownhall.md)
- [virtualEventWebinar](../resources/virtualeventwebinar.md)

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "virtualeventsession_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/virtualeventpresenter-get-permissions.md)]

> [!NOTE]
>
> To use application permissions for this API, tenant administrators must create an [application access policy](/graph/cloud-communication-online-meeting-application-access-policy) and assign it to a user. This allows the authorized application to access registrants' information from virtual events created by that specific user.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
GET /solutions/virtualEvents/townhalls/{townhallId}/presenters/{presenterId}
GET /solutions/virtualEvents/webinars/{webinarId}/presenters/{presenterId}
```

## Optional query parameters

This method doesn't support the OData query parameters. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [virtualEventPresenter](../resources/virtualeventpresenter.md) object in the response body.

## Examples

### Request

The following example shows how to get a presenter on a **virtualEventTownhall**.

<!-- {
  "blockType": "request",
  "name": "get_virtualeventpresenter",
  "sampleKeys": ["88b245ac-b0b2-f1aa-e34a-c81c27abdac2@f9448ec4-804b-46af-b810-62085248da33", "831affc2-4c8a-9929-50e7-02964563b6e4"]
}
-->
``` http
GET https://graph.microsoft.com/v1.0/solutions/virtualEvents/townhalls/88b245ac-b0b2-f1aa-e34a-c81c27abdac2@f9448ec4-804b-46af-b810-62085248da33/presenters/831affc2-4c8a-9929-50e7-02964563b6e4
```

---

### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.virtualEventPresenter"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
      "@odata.type": "#microsoft.graph.virtualEventPresenter",
      "id": "831affc2-4c8a-9929-50e7-02964563b6e4",
      "identity": {
        "@odata.type": "microsoft.graph.communicationsUserIdentity",
        "displayName": "Diane Demoss",
        "id": "831affc2-4c8a-9929-50e7-02964563b6e4",
        "tenantId": "77229959-e479-4a73-b6e0-ddac27be315c"
      },
      "email": "DianeDemoss@contoso.com"
    }
}
```
