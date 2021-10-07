---
title: 迁移到新的德国数据中心Office 365服务后将发生哪些变化
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 摘要：了解从德国 Microsoft 云 (德国) 迁移到新的德国数据中心Office 365服务的变化。
ms.openlocfilehash: 6067f993703fce7655c3298b945765dd2f317d60
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211629"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>迁移到新的德国数据中心Office 365服务后将发生哪些变化

租户迁移旨在对管理员和用户产生最小影响。 但是，每个工作负载都有注意事项。 请查看以下部分，以更好地了解工作负载的迁移体验。

以下是德国 Microsoft 云与新的德国数据中心Office 365服务之间的主要区别。

| 类别 | 德国 Microsoft 云 | 新的德国数据中心区域内的 Office 365 服务 |
|:-------|:-----|:-------|
| Microsoft 365 服务适用于只有一个 Office 365 租户的订阅 | 15 个服务 | 29 个服务 <br><br> 有关详细信息，请参阅不同的云服务产品/服务之间Office 365[可用性是什么？。](ms-cloud-germany-transition.md#serv-avail) |
| 新增功能 | 没有可用的新功能。 | 新功能将与服务一Office 365一。 |
| 数据受托人 | 是 | 否 |
| 与全球 Office 365 租户跨租户协作 | 否 | 是 |
| 客户数据驻留 | 客户数据将仅存储在德国数据中心内。 | Microsoft 将专门在德国存储以下客户数据： <ul><li> Exchange Online邮箱 (电子邮件正文、日历条目以及电子邮件附件内容)  </li><li> SharePoint联机网站内容和该网站中存储的文件，以及上载到OneDrive for Business </li></ul> |
| 适用条款 | [此补充的联机](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) 服务 [条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

没有变化：

- 租户初始 (，例如) ID (GUID) 自定义域在迁移后 `contoso.onmicrosoft.de` 仍然保留。 

- 迁移到服务的资源身份验证请求Office 365 Azure 身份验证服务Office 365 Azure 身份验证服务 `login.microsoftonline.com` () 。 在迁移过程中，仍在德国Office 365的资源由现有的德国 Azure 服务 `login.microsoftonline.de` () 。

要注意的注意事项：

- 对于托管域帐户，在复制初始 Azure Active Directory (Azure AD) 租户后 (这是 Azure AD 迁移到 Office 365 服务 Azure AD 服务) 的第一步、密码更改、自助服务密码重置 (SSPR) 更改以及管理员从 Office 365 服务 po 进行密码重置rtals。 此时，从德国服务更新密码的请求不会成功，因为 Azure AD 租户已迁移到 Office 365 服务。 对联合域密码的重置不会受到影响，因为这些重置操作在内部部署目录中完成。

- Azure 登录在用户尝试访问的门户中显示。 转换后，仅 Office 365服务终结点提供审核日志。 在迁移到完成迁移之前，应保存德国 Microsoft 云门户中的登录和审核日志。

- 必须由管理员为未使用 Active Directory 联合身份验证服务 (的托管组织) 执行密码重置、密码更改、密码Office 365重置。 访问德国 Microsoft 云门户的用户重置密码的尝试将失败。

- GDPR (一般数据保护条例) 数据主体请求 (DSR) 从 Office 365 服务 Azure 管理门户执行，供将来请求使用。 位于德国 Microsoft 云的任何旧式或非客户诊断数据在 30 天或之前被删除。

## <a name="subscriptions--licenses"></a>订阅&许可证

- Office 365德国的 Microsoft 云和 Dynamics 订阅通过 Azure AD 重定位转换到德国区域。 然后，更新组织以反映新的 Office 365 服务订阅。 在简短的订阅传输过程中，将阻止对订阅的更改。

- 随着租户过渡到 Office 365 服务，其特定于德国的订阅和许可证通过新的 Office 365 服务产品标准化。 为Office 365德国订阅购买相应的服务订阅。 具有德国许可证的用户将Office 365服务许可证。 完成后，将取消旧式德国订阅，然后从当前 Office 365服务租户中删除。

- 在迁移各个工作负载后，由于新的 Office 365 服务订阅 (Microsoft Planner 和 Power Automate) 等 Office 365 服务应用程序提供了其他Office 365功能。 如果适合贵组织，租户或许可管理员可以在规划变更管理以引入新服务时禁用新服务计划。 有关如何禁用分配给用户许可证的服务计划的指南，请参阅在分配用户许可证时Microsoft 365[服务的访问权限](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

## <a name="exchange-online"></a>Exchange Online

- Exchange后，资源 URL 从旧式 Germany 终结点Office 365 `outlook.office.de` 到 Office 365 `outlook.office365.com` 服务终结点。 在迁移完成之前，您的用户可以使用旧 URL 访问其迁移的邮箱。 在迁移开始后，客户应尽快将Exchange转换到新 URL，以避免影响德国环境的停用。 Office 365迁移开始Outlook，Exchange服务 URL 才可用。

- 邮箱作为后端进程进行迁移。 在转换期间，您组织的用户可能在德国 Microsoft 云或德国区域，并且属于同一全局地址列表 (中的同一 Exchange 组织) 。

- 通过使用其邮箱Outlook Web App URL 访问服务的用户会看到额外的身份验证提示。 例如，如果用户的邮箱位于 Office 365 服务中，并且用户的 Outlook Web App 连接使用旧版终结点，则用户首先会向 进行身份验证，然后对 `outlook.office.de` `login.microsoftonline.de` 进行身份验证 `login.microsoftonline.com` 。 迁移完成后，用户可以访问新的 URL () ，并且他们只能看到一个预期的 `https://outlook.office365.com` 登录请求。 

## <a name="sharepoint-online"></a>SharePoint Online

在 SharePoint Online 和 OneDrive for Business 中，可以通过 Outlook 共享项目。 按"Outlook"按钮后，会创建一个可共享的链接，并推送到 Outlook Web App。

在 SharePoint Online 中OneDrive for Business共享项目Outlook在 SharePoint Online 迁移完成后不再起作用。 我们意识到这是一个已知问题。 但是，由于此Outlook功能位于弃用路径中，因此在推出弃用之前，不会计划解决此问题。

## <a name="office-services"></a>Office服务

Office联机服务可在转换之前 `office.de` 和转换期间访问。 在将用户的邮箱转换为 Office 365 服务后，用户应开始使用Office 365 URL。 随着后续工作负载迁移到 Office 365 服务，它们从 office.com 门户的接口将开始工作。

Office 中最近 (MRU) 服务是一种从德国 Microsoft 云到全球Office 365转换，而不是迁移。 从 Office 365.com 门户迁移后，只有来自 Office 365 全局服务端 Office MRU 链接可见。 来自德国 Microsoft 云的 MRU 链接在全局服务中不可见，Office 365 MRU 链接。 在Office 365全局服务中，MRU 链接仅在租户迁移到达阶段 9 之后才能访问。

## <a name="exchange-online-protection"></a>Exchange Online Protection

- EOP Exchange Online Protection (功能) 复制到新的德国区域。
- Office 365作为迁移的一部分，安全与合规中心用户需要转换为使用全局 `https://protection.office.com` URL。

## <a name="skype-for-business-online"></a>Skype for Business Online

现有 Skype for Business Online 客户将过渡到 Microsoft Teams。 有关详细信息，请参阅 [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) 。

## <a name="office-365-video"></a>Office 365 视频

Office 365视频将于 2021 年 3 月 1 日停用，Office 365将 SharePoint Online 迁移到新的德国数据中心区域后，视频将不受支持。 作为 Office 365 Online 迁移的一部分，将迁移来自视频SharePoint内容。 但是，Office 365迁移后，Office 365视频 UI 中SharePoint播放。 了解有关迁移到 Microsoft Stream Office 365经典视频 ([时间线) 概述](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="next-step"></a>后续步骤

[了解迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到Office 365新的德国数据中心区域部署服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 迁移计划信息](/power-bi/admin/service-admin-migrate-data-germany)
- [开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)
