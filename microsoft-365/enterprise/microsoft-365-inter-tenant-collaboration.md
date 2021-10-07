---
title: Microsoft 365租户间协作
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: 了解Microsoft 365组织之间的协作如何工作，从而允许不同组织安全地协同工作。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cb91b6bcaac212eeaf0ef4051f466751d8dbbd9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163332"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365租户间协作

假设 Fabrikam 和 Contoso 这两个组织都有一Microsoft 365租户，并且他们希望一起处理多个项目;其中一些运行的时间有限，某些运行正在进行。 Fabrikam 和 Contoso 如何允许其员工和团队以安全的方式跨不同租户Microsoft 365更有效地协作？ Microsoft 365 Azure AD Azure Active Directory (B2B) 结合使用，提供了多个选项。 本文介绍 Fabrikam 和 Contoso 可以考虑的几个关键方案。

Microsoft 365租户间协作选项包括使用文件和对话的中心位置、共享日历、使用 IM、用于通信的音频/视频呼叫，以及保护对资源和应用程序的访问。 使用下表选择解决方案并了解更多信息。

## <a name="exchange-online-collaboration-options"></a>Exchange Online协作选项

| 共享目标 | 管理操作 | 使用说明信息 |
|:-----|:-----|:-----|
|与其他组织共享Microsoft 365日历 |管理员可以在 Exchange Online 中设置不同级别的日历访问，以允许企业与其他企业协作，并允许用户与他人共享 (忙/闲) 日程安排。 | <ul><li>[共享](/exchange/sharing/sharing) </li><li> [组织关系](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [创建组织关系](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [修改组织关系](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [删除组织关系](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [与外部用户共享日历](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|控制用户如何与组织外部人员共享日历 | 管理员将共享策略应用于用户邮箱，以控制可以与谁共享该策略以及授予的访问权限级别 |  <ul><li> [共享策略](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [创建共享策略](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [将共享策略应用于邮箱](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [修改、禁用或删除共享策略](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|配置安全电子邮件通道并控制与合作伙伴组织之间的邮件流 | 管理员创建连接器以将安全性应用于与合作伙伴组织或服务提供商的邮件交换。 连接器通过传输层安全性 (TLS) ，并允许对合作伙伴发送电子邮件的域名或 IP 地址范围进行限制。 |  <ul><li> [Exchange Online 如何使用 TLS 保护电子邮件连接](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [使用连接器配置邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [远程域](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [设置连接器以确保与合作伙伴组织的安全邮件流](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [邮件流最佳实践 (概述) ](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |

## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint联机OneDrive for Business协作选项

| 共享目标 | 管理操作 | 使用说明信息 |
|:-----|:-----|:-----|
|与外部用户共享网站和文档 | 管理员在租户或网站集级别为经过身份验证的 Microsoft 帐户、经过身份验证的工作或学校帐户或来宾帐户配置共享 |  <ul><li> [管理 SharePoint Online 环境的外部共享](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [按域限制 SharePoint 和 OneDrive 内容的共享](/sharepoint/restricted-domains-sharing) </li><li> [使用 SharePoint Online 作为企业到企业 (B2B) Extranet 解决方案](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|跟踪和控制最终用户的外部共享 | OneDrive for Business文件所有者和 SharePoint Online 最终用户配置网站和文档共享并建立跟踪共享的通知 |  <ul><li> [配置外部共享通知以用于OneDrive for Business](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [共享 SharePoint 文件或文件夹](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |

## <a name="skype-for-business-collaboration-options"></a>Skype for Business协作选项

| 共享目标 | 管理操作 | 使用说明信息 |
|:-----|:-----|:-----|
|Skype for Business联机 - 即时消息、呼叫和与其他Skype for Business状态 | 管理员可以允许其 Skype for Business Online 用户进行 IM、进行音频/视频呼叫以及查看其他租户中用户Microsoft 365状态。 | [允许用户连接外部 Skype for Business 用户](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)|
|Skype for Business联机 - 与消费者用户Skype (即时消息、) 状态 | 管理员可以允许其 Skype for Business Online 用户通过即时消息、拨打电话和查看状态Skype (使用者) 用户。 | [允许 Skype for Business 用户添加 Skype 联系人](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)|

## <a name="azure-ad-b2b-collaboration-options"></a>Azure AD B2B 协作选项

| 共享目标 | 管理操作 | 使用说明信息 |
|:-----|:-----|:-----|
|Azure AD B2B 协作 - 通过将外部用户添加到组织目录中的组来共享内容 | 一个 Microsoft 365 租户的 **Azure AD** DC 管理员、安全管理员、用户管理员、云应用程序管理员或 **全局** 管理员可以邀请另一个 Microsoft 365 租户中的人员加入他们的目录，将那些外部用户添加到组，并授予对内容（如组的 SharePoint 网站和库）的访问权限。  |  <ul><li> [什么是 Azure AD B2B 协作预览？](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B：新更新使跨业务排序规则变得简单](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [外部共享和Azure Active Directory B2B 协作](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active DirectoryB2B 协作 API 和自定义](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD 和标识显示：Azure AD B2B 协作 (企业到企业](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |

## <a name="microsoft-365-collaboration-options"></a>Microsoft 365协作选项

| 共享目标 | 管理操作 | 使用说明信息 |
|:-----|:-----|:-----|
|Microsoft 365组 - 集中位置OneNote、日历、日历和共享文件 | 组在商业基础版、商业高级版、教育版Enterprise E1、E3 和 E5 计划中受支持。 一个租户中的Microsoft 365可以创建组，并邀请另一个租户Microsoft 365作为来宾用户。 也适用于 Dynamics CRM。 |  <ul><li> [了解 Microsoft 365 组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [来宾组中来宾Microsoft 365访问](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [部署Microsoft 365组](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |

## <a name="yammer-collaboration-options"></a>Yammer协作选项

| 共享目标 | 管理操作 | 使用说明信息 |
|:-----|:-----|:-----|
|Yammer - 通过企业社交媒体进行协作 | 除非 Yammer 管理员禁用了创建外部组的能力，否则用户可以创建外部组以通过对话、喜欢和关注帖子、共享文件和在线聊天等方式在 Yammer 中协作。 | [在 Yammer 中创建和管理外部组](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)|

## <a name="teams-collaboration-options"></a>Teams协作选项

|共享目标|管理操作|使用说明信息|
|:-----|:-----|:-----|
|与Teams外部的用户进行协作 | 邀请 **用户** 租户的用户管理员或全局管理员Microsoft 365需要在租户中启用外部Teams。 全局管理员和团队所有者现在能够邀请具有电子邮件地址的任何人在 Teams。  <br/> 管理员还可以管理和编辑租户中已有的来宾。 |  <ul><li> [授权来宾访问](/microsoftteams/teams-dependencies) </li><li> [打开或关闭来宾访问Teams](/microsoftteams/set-up-guests) </li><li> [使用 PowerShell 控制来宾访问](/microsoftteams/guest-access-powershell) </li><li> [来宾访问清单](/microsoftteams/guest-access-checklist) </li><li> [查看来宾用户](/microsoftteams/view-guests) </li><li> [编辑来宾用户信息](/microsoftteams/edit-guests-information) </li></ul> |
|团队所有者可以邀请并管理来宾在团队中的协作方式。  |团队所有者对来宾可以在团队中执行哪些操作有其他控制。 |  <ul><li> [添加来宾](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [向团队添加来宾](/microsoftteams/add-guests) </li><li> [管理来宾访问Teams](/microsoftteams/manage-guests) </li><li> [查看谁在团队或频道中](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|来自其他租户的来宾可以查看 Teams中的内容并与其他成员协作 | 无。 | [来宾访问体验](/microsoftteams/guest-experience)|

## <a name="power-bi-collaboration-options"></a>Power BI协作选项

| 共享目标 | 管理操作 | 使用说明信息 |
|:-----|:-----|:-----|
|Power BI允许外部来宾用户使用通过链接共享的内容。 这使组织的用户能够安全地在组织中分发内容。<br/> | 管理员Power BI可以控制用户是否可以邀请外部用户查看组织内部的内容。| [使用 Power BI AD B2B 将内容分发给外部来宾用户](/power-bi/service-admin-azure-ad-b2b) |

## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>请注意有关租户Microsoft 365协作的要点

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>共享用户帐户、许可证、订阅和存储

每个组织都维护自己的用户帐户、标识、安全组、订阅、许可证和存储。 人们使用 Microsoft 365 中的协作功能以及共享策略和安全设置，以提供对所需信息的访问权限，同时维持对公司资产的控制。

- **用户帐户：** 在本地 Active Directory 域服务中的租户或分区之间不能共享或复制帐户。

- **许可证 &amp;** 订阅：在 Microsoft 365 中，许可计划 (中的许可证也称为 SKUS 或 Microsoft 365 计划) 可让用户访问为这些计划定义的 Microsoft 365 服务。

- **存储：** 在Microsoft 365计划中，SharePoint Online 的软件边界和限制独立于邮箱存储限制进行管理。 邮箱存储限制是通过使用邮箱存储Exchange Online。 在这两种方案中，无法跨租户共享存储。

### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>我们能否跨多个租户Microsoft 365命名空间？

不需要。 组织域名（如 fabrikam.com 或 tailspintoys.com）只能与单个租户关联Microsoft 365使用。 每个租户都必须有自己的命名空间。 无法在租户之间共享 UPN、SMTP 和 SIP 命名空间。

### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>混合组件和租户Microsoft 365协作呢？

本地混合组件（如 Exchange 和 Azure AD 连接）不能跨多个租户进行拆分。
