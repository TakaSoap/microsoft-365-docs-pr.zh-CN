---
title: 新德国数据中心区域迁移到 Office 365 服务已更改
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
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
description: 摘要：了解从德国 Microsoft 云 (德国) 迁移到新的德国数据中心地区的 Office 365 服务发生了哪些变化。
ms.openlocfilehash: 0415f7b95cb9a9f2625798311946dac0f1f7c2c0
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688608"
---
# <a name="what-has-changed-for-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>新德国数据中心区域迁移到 Office 365 服务已更改

租户迁移旨在对管理员和用户产生最小影响。 但是，每个工作负载都有注意事项。 请查看以下各节，以更好地了解工作负荷的迁移体验。

以下是德国 Microsoft 云与新的德国数据中心区域的 Office 365 服务之间的主要区别。

| 类别 | 德国 Microsoft 云 (德国 Microsoft 云)  | 新的德国数据中心区域内的 Office 365 服务 |
|:-------|:-----|:-------|
| Microsoft 365 服务适用于只有一个 Office 365 租户的订阅 | 15 个服务 | 29 个服务 <br><br> 有关详细信息，请参阅不同的 [Office 365](ms-cloud-germany-transition.md#serv-avail)云服务产品之间的服务可用性是什么？。 |
| 新增功能 | 不提供任何新功能。 | 新功能将与 Office 365 服务一致。 |
| 数据受托人 | 是 | 否 |
| 与全球 Office 365 租户跨租户协作 | 否 | 是 |
| 客户数据驻留 | 客户数据将仅存储在德国数据中心内。 | Microsoft 将专门在德国存储以下客户数据： <ul><li> Exchange Online 邮箱 (电子邮件正文、日历条目以及电子邮件附件内容)  </li><li> SharePoint Online 网站内容和存储在该网站中的文件，以及上传到 OneDrive for Business 的文件 </li></ul> |
| 适用条款 | [此补充的联机](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) 服务 [条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

没有变化：

- 租户初始 (域，例如) ID (GUID) 迁移后，自定义域将 `contoso.onmicrosoft.de` 保留。 

- 迁移到 Office 365 服务的资源的身份验证请求由 Office 365 服务 Azure 身份验证服务 `login.microsoftonline.com` () 。 在迁移过程中，仍保留在 Office 365 Germany 中的资源由现有德国 Azure 服务 `login.microsoftonline.de` () 。

请注意的注意事项：

- 对于托管域帐户，复制初始 Azure Active Directory (Azure AD) 租户后 (这是 Azure AD 迁移到 Office 365 服务 Azure AD 服务) 的第一步、密码更改、自助服务密码重置 (SSPR) 更改和管理员的密码重置必须从 Office 365 服务门户执行。 此时，从德国服务更新密码的请求不会成功，因为 Azure AD 租户已迁移到 Office 365 服务。 联合域密码重置不受影响，因为这些密码在本地目录中完成。

- Azure 登录在用户尝试访问的门户中显示。 转换后，仅 Office 365 服务终结点提供审核日志。 在迁移到迁移完成之前，应保存 Microsoft 云德国门户中的登录和审核日志。

- 必须由管理员为没有使用 Active Directory 联合身份验证服务 (的托管组织执行密码重置、密码更改和密码) 必须通过 Office 365 服务门户执行。 访问德国 Microsoft 云门户的用户重置密码的尝试将失败。

- GDPR (GDPR) 数据主体请求 (DSR) 从 Office 365 服务 Azure 管理门户执行，供将来请求使用。 位于德国 Microsoft 云的任何旧版或非客户诊断数据在 30 天或之前删除。

## <a name="subscriptions--licenses"></a>订阅&许可证

- Microsoft 云德国的 Office 365 和 Dynamics 订阅通过 Azure AD 重新定位转换到德国区域。 然后更新组织以反映新的 Office 365 服务订阅。 在简短的订阅传输过程中，将阻止对订阅的更改。

- 随着租户过渡到 Office 365 服务，其特定于德国的订阅和许可证通过新的 Office 365 服务产品标准化。 为已转移的德国订阅购买了相应的 Office 365 服务订阅。 拥有德国许可证的用户将被分配 Office 365 服务许可证。 完成后，将取消旧版德国订阅，并删除当前 Office 365 服务租户。

- 在迁移各个工作负载后，由于新的 Office 365 服务订阅，Office 365 服务 (（如 Microsoft Planner 和 Microsoft Flow) ）提供了其他功能。 如果适合贵组织，租户或许可管理员可以在规划变更管理以引入新服务时禁用新的服务计划。 有关如何禁用分配给用户许可证的服务计划的指南，请参阅分配用户许可证时禁用 [对 Microsoft 365 服务的访问权限](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

## <a name="exchange-online"></a>Exchange Online

- 迁移后，Exchange 资源 URL 从旧版德国终结点转换到 `outlook.office.de` Office 365 `outlook.office365.com` 服务终结点。 在迁移完成之前，您的用户可以使用旧 URL 访问其迁移的邮箱。 在 Exchange 迁移开始后，客户应尽快将用户转换到新 URL，以避免影响停用德国环境。 Outlook 服务的 Office 365 服务 URL 仅在 Exchange 迁移开始后可用。

- 邮箱作为后端进程进行迁移。 在转换期间，您组织的用户可能属于德国 Microsoft 云或德国区域，并且属于同一全局地址列表中 (Exchange 组织的一) 。

- 通过使用其Outlook Web App的 URL 访问服务的用户会看到额外的身份验证提示。 例如，如果用户的邮箱位于 Office 365 服务中，并且用户的 Outlook Web App 连接使用旧终结点，则用户首先会进行身份验证，然后再进行身份验证 `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` 。 迁移完成后，用户可以访问新的 URL () ，并且他们只能看到一个预期的 `https://outlook.office365.com` 登录请求。 

## <a name="office-services"></a>Office 服务

可在转换之前和转换期间访问 Office Online `office.de` 服务。 将用户的邮箱转换为 Office 365 服务后，用户应开始使用 Office 365 服务 URL。 随着后续工作负载迁移到 Office 365 服务，它们从 office.com 门户的界面将开始工作。

## <a name="exchange-online-protection"></a>Exchange Online Protection

- 后端 Exchange Online Protection (EOP) 功能复制到新的德国区域。
- 作为迁移的一部分，Office 365 安全与合规中心用户需要转换为使用全局 `https://protection.office.com` URL。

## <a name="skype-for-business-online"></a>Skype for Business Online

现有 Skype for Business Online 客户将过渡到 Microsoft Teams。 有关详细信息，请参阅 [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) 。

## <a name="office-365-video"></a>Office 365 视频

Office 365 视频将于 2021 年 3 月 1 日停用，在将 SharePoint Online 迁移到新的德国数据中心区域后，Office 365 视频将不受支持。 Office 365 视频中的内容将作为 SharePoint Online 迁移的一部分进行迁移。 但是，在 SharePoint 迁移后，Office 365 视频中的视频不会在 Office 365 视频 UI 中播放。 了解有关 Office [365](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)视频到 Microsoft Stream 的迁移时间线 (经典) 概述。

## <a name="next-step"></a>后续步骤

[了解迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
