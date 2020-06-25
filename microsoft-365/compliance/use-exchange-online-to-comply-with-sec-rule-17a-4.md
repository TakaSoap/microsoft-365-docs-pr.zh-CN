---
title: 使用 Exchange Online 和安全与合规中心来遵守 SEC 规则 17a-4
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 配置 Exchange Online 与合规中心，帮助满足 CFTC Rule 1.31(c)-(d)、 FINRA Rule 4511 和 SEC Rule 17a-4 的法规要求。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6dc53ec9dd016a2423ca96886bba400e2f17e17a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819072"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>使用 Exchange Online 和安全与合规中心来遵守 SEC 规则 17a-4

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.

However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.

为了帮助这些组织更好地了解如何利用安全与合规中心来履行其对 Exchange Online 的监管义务，特别是与规则 17a-4 要求相关的监管义务，我们已与 Cohasset Associates 合作发布了一份评估报告。

Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.

## <a name="download-the-cohasset-assessment"></a>下载 Cohasset 评估报告

可[在此处下载 Cohasset 评估报告](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)。

![Cohasset Associates 可下载评估的标题页](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>此评估专门针对 Exchange Online

Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.

It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>使用保留锁定是推荐配置的关键

Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:

- 在规定的保留期内保留，不能缩短，只能增加。
- 不可变，即在要求的保留期间，不能覆盖、删除或更改记录。

In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.

By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:

- 策略的保留期限只能增加，不能缩短。
- 可以将用户添加到策略，但不能删除用户。
- 管理员无法删除保留策略。

保留锁定可有助于满足 SEC 17a-4 法规要求。

## <a name="how-to-set-up-preservation-lock"></a>如何设置保留锁定

你可以使用 PowerShell 来锁定保留策略。 有关详细信息，请参阅[使用保留锁定遵从合规性要求](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)。

## <a name="known-limitations"></a>已知限制

目前，Exchange Online 有一些限制：

- 线程通信不适用于 Teams 聊天和频道消息。
- 不会为 Teams 聊天和频道消息保留赞。

> [!NOTE]
> 项目级审核现已在 Microsoft 365 组邮箱中可用。 有关详细信息，请参阅[管理邮箱审核](enable-mailbox-auditing.md)。
