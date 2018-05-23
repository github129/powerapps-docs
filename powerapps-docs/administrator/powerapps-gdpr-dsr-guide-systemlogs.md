---
title: Responding to DSR requests for system-generated logs in PowerApps, Microsoft Flow, and Common Data Service (CDS) for Apps  | Microsoft Docs
description: Walkthrough of how to respond to DSR requests for system-generated logs in PowerApps, Microsoft Flow, and Common Data Service (CDS) for Apps
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: jamesol
---

# Responding to DSR requests for system-generated logs in PowerApps, Microsoft Flow, and Common Data Service for Apps
Microsoft gives you the ability to access, export, and delete system-generated logs that may be deemed personal under the European Union (EU) General Data Protection Regulation (GDPR) broad definition of *personal data*. Examples of system-generated logs that may be deemed personal under GDPR include:
* Product and service usage data, such as user activity logs
* User search requests and query data
* Data generated by product and services as a product of system functionality and interaction by users or other systems

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud, and diagnostic data&mdash;including modifications to such data&mdash;would compromise the historical record of actions and increase fraud and security risks.

## Accessing and exporting system-generated logs
Administrators can access system-generated logs associated with a user’s use of PowerApps, Microsoft Flow, and Common Data Service (CDS) for Apps services and applications.

To access and export system-generated logs, do the following:

1. Go to the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) and sign in using Office 365 Global Administrator credentials.

2. From the **Privacy** drop-down list at the top of the page, select **Data Subject Request**.

3. On the **Data Subject Request** page, under **System Generated Logs**, select **Data Log Export**. The Data Log Export displays and shows a list of export data requests submitted by your organization.

4. To create a new request for a user, click **Create Export Data Request**.

    After you create a new request, the request is listed on the **Data Log Export** page, where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization’s Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as XML, CSV, or JSON. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs. For more information, see [Introduction to Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction).

The following table summarizes accessing and exporting system-generated logs:

| Question | Answer |
| --- | --- |
| How long does the Microsoft Data Log Export tool take to complete a request? |	This depends on several factors. In most cases it should complete in one or two days, but it can take up to 30 days.
| What format will the output be in? | The output will be in the form of structured, machine-readable files such as XML, CSV, or JSON.
| Who has access to the Data Log Export tool to submit access requests for system-generated logs? |	Office 365 Global Administrators will have access to the GDPR Log Manager tool.
| What data does the Data Log Export tool return? |	The Data Log Export tool returns system-generated logs that Microsoft stores. Exported data spans across various Microsoft services including Office 365, Azure, Dynamics, PowerApps, Microsoft Flow, and CDS for Apps.
| How is data returned to the user? |	Data will be exported to your organization's Azure storage location; it will be up to administrators in your organization to determine how they will show/return this data to users.
| What will data in system-generated logs look like? |	Example of a system-generated log record in JSON format: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  For security and audit purposes, some features do not allow you to export or delete system-generated logs in order to maintain the integrity of personal information.
>
>

## Deleting system-generated logs
To delete system-generated logs retrieved through an access request, you must remove the user from the service and permanently delete his or her Azure Active Directory account. For instructions on how to permanently delete a user, see the **Deleting a user** section in the *Azure Data Subject Request GDPR documentation* that can be found on the [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR). It's important to note that permanently deleting a user account is irreversible once initiated.

Permanently deleting a user account removes the user’s data from system-generated logs for PowerApps, Microsoft Flow, and CDS for Apps services within 30 days.