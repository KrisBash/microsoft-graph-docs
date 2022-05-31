---
description: "Automatically generated file. DO NOT MODIFY"
---

```typescript

//THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
const graphServiceClient = GraphServiceClient.init({authProvider});

const requestBody = new SendActivityNotificationToRecipientsRequestBody();
requestBody.topic = new TeamworkActivityTopic();
requestBody.topic.source = TeamworkActivityTopicSource.EntityUrl;
requestBody.topic.value = "https://graph.microsoft.com/beta/appCatalogs/teamsApps/{teamsAppId}";
requestBody.activityType = "pendingFinanceApprovalRequests";
requestBody.previewText = new ItemBody();
requestBody.previewText.content = "Internal spending team has a pending finance approval requests";
const teamworknotificationrecipient = new TeamworkNotificationRecipient();
teamworknotificationrecipient.additionalData = {
					 "@odata.type" : "microsoft.graph.aadUserNotificationRecipient",
					 "userId" : "569363e2-4e49-4661-87f2-16f245c5d66a"
				 }
const teamworknotificationrecipient1 = new TeamworkNotificationRecipient();
teamworknotificationrecipient1.additionalData = {
					 "@odata.type" : "microsoft.graph.aadUserNotificationRecipient",
					 "userId" : "ab88234e-0874-477c-9638-d144296ed04f"
				 }
const teamworknotificationrecipient2 = new TeamworkNotificationRecipient();
teamworknotificationrecipient2.additionalData = {
					 "@odata.type" : "microsoft.graph.aadUserNotificationRecipient",
					 "userId" : "01c64f53-69aa-42c7-9b7f-9f75195d6bfc"
				 }
requestBody.recipients = [
			teamworknotificationrecipient,
			teamworknotificationrecipient1,
			teamworknotificationrecipient2
		]
const keyvaluepair = new KeyValuePair();
keyvaluepair.additionalData = {
					 "name" : "pendingRequestCount",
					 "value" : "5"
				 }
requestBody.templateParameters = [
			keyvaluepair
		]
async () => {
	await graphServiceClient.teamwork.sendActivityNotificationToRecipients.post(requestBody);
}


```