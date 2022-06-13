---
title: "Versioning, support, and breaking change policies for Microsoft Graph "
description: "This article describes the support and breaking change policies for Microsoft Graph and the versions of the Microsoft Graph API that are currently available."
ms.localizationpriority: high
---

# Versioning, support, and breaking change policies for Microsoft Graph

This article describes the support and breaking change policies for Microsoft Graph and the versions of the Microsoft Graph API that are currently available.

## Support policy and deprecation information

Microsoft Graph follows the [Microsoft Lifecycle Policy](https://support.microsoft.com/lifecycle). Microsoft Graph uses a combination of major API versions and _within version_ deprecation to minimize potential disruption to client applications as APIs evolve. 
### New major versions
Major versions for Microsoft Graph APIs are referenced in the request URL (e.g. '/v1.0'). In some cases, a new major version may be released, and the prior version(s) deprecated. As this can have substantial impact on clients, we reserve major version increments for substantial changes that impact many or all Microsoft Graph resource types. 

### API changes within a major version
The majority of changes to Microsoft Graph APIs will occur within a major API version. The expectations for these changes are different for 1) backward compatible and 2) non-backward compatible changes. 

The following are examples of non-backward compatible changes:

- Changes to the URL or fundamental request/response associated with a resource
- Removal, rename, or change to the type of a declared property
- Removal or rename of APIs or API parameters
- Addition of a required request header

The following are examples of backward compatible changes:

- Addition of properties that are nullable or have a default value
- Addition of a member to an enumeration
- Removal, rename, or change to the type of an open extension
- Removal, rename, or change to the type of an annotation
- Introduction of paging to existing collections
- Changes to error codes
- Changes to the order of properties
- Changes to the length or format of opaque strings, such as resource IDs

#### 1) Backward compatible changes within a major version
For changes to a published Microsoft Graph API that are backward compatible, the change may be published at any time. These changes typically debut in the /beta version for a period of public validation before publishing to a Generally Availble version (e.g. v1.0). These changes are listed in the [Microsoft Graph Changelog](changelog.md)

#### 2) Non-backward compatible changes within a major version
Occasionally, a non-backward compatible change may need to be published to a Microsoft Graph API within a major version. These changes will follow the Microsoft Graph deprecation process and the change to the API will take effect only after the deprecation notice period is complete. 

**Examples**
- If a resource type or property of a resource type is to be removed, the type or property will be deprecated and retired after the minimum deprecation notice period
- If a resource type or property is to be renamed, a new type name or property will be added (a backward compatible change) and the old type or property will be deprecated. The old type or property name will only be retired after the minimum deprecation notice period. 
- If a resource property data type is to be changed, a new property will be added with the new data type (a backward compatible change), typically with a numerical suffix, such as '_1'. The old property will be deprecated and only retired after the minimum deprecation notice period. 

### Microsoft Graph API deprecation process
For both major version updates and for non-backward compatible changes within a Generally Available (GA) version, deprecation will occur at least 24 months in advance of removal (sunset). 

When an API (or URI path or property) is marked as deprecated, we strongly recommend that you migrate to the latest version or recommended alternative as soon as possible. In some cases, we will announce that new applications will have to start using the new APIs a short time after the original APIs are deprecated. In those cases, only active applications that currently use the deprecated APIs can continue to use them.

#### How to learn of deprecation of a major version
When we increment the *major version* of the API (for example, from v1.0 to v2.0), we are announcing that the current version (in this example, v1.0) is immediately deprecated and we will no longer support it 24 months after the announcement. We might make exceptions to this policy for service security or health reliability issues.

The availability of new Microsoft Graph versions will be announced in the [Microsoft Graph Changelog](changelog.md), and deprecation of prior major versions will be described under [Deprecated and unsupported versions](#deprecated-and-unsupported-versions) on this page.

#### How to learn of deprecation within major version
There are multiple methods to learn of deprecation for resource types, properties, or URI paths within a major version. These include: 
- Deprecation announcements for these changes are listed in the [Microsoft Graph Changelog](changelog.md) with the change type 'Deprecation.'
- Any requests to Microsoft Graph that use a deprecated API element will receive HTTP Headers in the response with details of the deprecation. These headers are:

|Header Key|Format|Description|
--- | --- | ---|
|Deprecation|DateTime|The date that the deprecation was announced|
|Link|String|A URL for the corresponding Changelog entry|
|Sunset|DateTime|The date of the expected retirement for the deprecated element|
### API contract and non-backward compatible changes

Microsoft Graph has a log of changes across versions. These changes are listed in the [Microsoft Graph Changelog](changelog.md). As new functionality and data is added to Microsoft Graph, we will increment the API version number for any non-backward compatible changes to the API.

The following are examples of non-backward compatible changes:

- Changes to the URL or fundamental request/response associated with a resource
- Removal, rename, or change to the type of a declared property
- Removal or rename of APIs or API parameters
- Addition of a required request header

The following are examples of backward compatible changes:

- Addition of properties that are nullable or have a default value
- Addition of a member to an enumeration
- Removal, rename, or change to the type of an open extension
- Removal, rename, or change to the type of an annotation
- Introduction of paging to existing collections
- Changes to error codes
- Changes to the order of properties
- Changes to the length or format of opaque strings, such as resource IDs

>**Note:** Over time, we will update the list of backward compatible changes. If you generate your own client proxies (like WCF clients), our guidance is that your client applications should be prepared to receive properties and derived types not previously defined by the Microsoft Graph API service. Microsoft Graph API follows the guidance described in the [Model Versioning](https://github.com/Microsoft/api-guidelines/blob/master/Guidelines.md#12-versioning) section in the [Microsoft REST API guidelines](https://github.com/microsoft/api-guidelines/).

## Versions

The following major versions of the Microsoft Graph API are currently available.

### Beta version
In general, APIs debut in the beta version and are accessible in the `https://graph.microsoft.com/beta` endpoint. For beta API documentation, see [Microsoft Graph beta endpoint reference](/graph/api/overview?view=graph-rest-beta&preserve-view=true). Expect breaking changes and deprecation of APIs in the beta version from time to time. Do not take a production dependency on beta APIs.

We make no guarantees that a beta feature will be promoted to the current version. When the Microsoft Graph API team believes that a beta feature is ready for general availability, we will add that feature to the latest current version. 

Our developer community can post feature requests on the [Microsoft 365 Developer Platform ideas forum](https://techcommunity.microsoft.com/t5/microsoft-365-developer-platform/idb-p/Microsoft365DeveloperPlatform/label-name/Microsoft%20Graph), including requests for new features as well as requests to promote existing beta APIs to the current version.

### Current version

The current version of Microsoft Graph is v1.0. Exposed under `https://graph.microsoft.com/v1.0`, the Microsoft Graph API v1.0 version contains features that are generally available and ready for production use. Browse the [documentation for the v1.0 APIs](/graph/api/overview?view=graph-rest-1.0&preserve-view=true).

## Preview status
An API or feature in Microsoft Graph is labelled as "(preview)" to indicate its behavior is _unique_ in the beta endpoint. 

The behavior of most APIs and features in the v1.0 version is in parity with the beta version. "preview" qualifies a minority of APIs and features in one of the following two cases: 
- Available in only beta
- Available in beta differently than in v1.0

Like any other API in the beta endpoint, APIs marked in the documentation as "(preview)" may experience breaking changes without notice. Do not access APIs from the beta endpoint in production apps. The "(preview)" label applies to the REST API and its documentation in Microsoft Graph, even if the service itself is generally available.

### Deprecated and unsupported versions

There are currently no deprecated versions of Microsoft Graph.

## Terms of use

By using the Microsoft Graph APIs, you agree to the [Microsoft APIs Terms of Use](/legal/microsoft-apis/terms-of-use?context=/graph/context).

Your feedback is important to us. Connect with us on [Microsoft Q&A](/answers/products/m365#microsoft-graph). Tag your questions with [microsoft-graph-*].
