---
description: "Automatically generated file. DO NOT MODIFY"
---

```typescript

//THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
const graphServiceClient = GraphServiceClient.init({authProvider});

let requestParameters = {
	id : "https://graph.microsoft.com/beta/users/%7Bid%7D",
};
async () => {
	await graphServiceClient.groupsById("group-id").rejectedSendersById("directoryObject-id").delete(requestParameters);
}


```