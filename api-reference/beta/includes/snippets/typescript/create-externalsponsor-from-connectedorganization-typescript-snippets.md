---
description: "Automatically generated file. DO NOT MODIFY"
---

```typescript

//THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
const graphServiceClient = GraphServiceClient.init({authProvider});

const requestBody = new $refRequestBody();
requestBody.additionalData = {
		 "@odata.id" : "https://graph.microsoft.com/beta/users/{id}"
	 }
async () => {
	await graphServiceClient.identityGovernance.entitlementManagement.connectedOrganizationsById("connectedOrganization-id").externalSponsorsById("directoryObject-id").post(requestBody);
}


```