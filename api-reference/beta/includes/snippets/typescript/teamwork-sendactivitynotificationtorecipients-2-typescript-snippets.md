---
description: "Automatically generated file. DO NOT MODIFY"
---

```typescript

//THIS SNIPPET IS A PREVIEW FOR THE KIOTA BASED SDK. NON-PRODUCTION USE ONLY
const graphServiceClient = GraphServiceClient.init({authProvider});

const requestBody = new SendActivityNotificationToRecipientsRequestBody();
requestBody.topic = new TeamworkActivityTopic();
requestBody.topic.source = TeamworkActivityTopicSource.Text;
requestBody.topic.value = "Deployment Approvals Channel";
requestBody.topic.webUrl = "https://teams.microsoft.com/l/message/19:448cfd2ac2a7490a9084a9ed14cttr78c@thread.skype/1605223780000?tenantId=c8b1bf45-3834-4ecf-971a-b4c755ee677d&groupId=d4c2a937-f097-435a-bc91-5c1683ca7245&parentMessageId=1605223771864&teamName=Approvals&channelName=Azure%20DevOps&createdTime=1605223780000";
requestBody.activityType = "deploymentApprovalRequired";
requestBody.previewText = new ItemBody();
requestBody.previewText.content = "New deployment requires your approval";
const keyvaluepair = new KeyValuePair();
keyvaluepair.additionalData = {
					 "name" : "deploymentId",
					 "value" : "6788662"
				 }
requestBody.templateParameters = [
			keyvaluepair
		]
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
async () => {
	await graphServiceClient.teamwork.sendActivityNotificationToRecipients.post(requestBody);
}


```