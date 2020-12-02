---
title: 在迁移到新的德国数据中心区域内的 Office 365 服务期间的客户体验
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 摘要：了解从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务时，从 Microsoft 云 (德国) 的体验。
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551691"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>在迁移到新的德国数据中心区域内的 Office 365 服务期间的客户体验

租户迁移旨在对管理员和用户造成最小影响。 但是，每个工作负载都有注意事项。 若要更好地了解工作负荷的迁移体验，请查看以下各节。

以下是新的德国数据中心区域中的 Microsoft 云德国和 Office 365 服务之间的主要差异。

| 类别 | Microsoft 云德国 (Microsoft 云德国)  | 新的德国数据中心区域内的 Office 365 服务 |
|:-------|:-----|:-------|
| Microsoft 365 服务适用于只有一个 Office 365 租户的订阅 | 15个服务 | 29个服务 <br><br> 有关详细信息，请参阅 [不同 Office 365 云服务产品之间的服务可用性是什么？](ms-cloud-germany-transition.md#serv-avail)。 |
| 新增功能 | 不提供任何新功能。 | 新功能将可与 Office 365 服务保持一致。 |
| 数据受托人 | 是 | 否 |
| 与全球 Office 365 租户跨租户协作 | 否 | 是 |
| 客户数据驻留 | 客户数据将仅存储在德国数据中心内。 | Microsoft 会在德国以独占方式将以下客户数据存储在 rest 上： <ul><li> Exchange Online 邮箱内容 (电子邮件正文、日历条目和电子邮件附件的内容)  </li><li> SharePoint Online 网站内容和存储在该网站中的文件，以及上传到 OneDrive for Business 的文件 </li></ul> |
| 适用条款 | 包含此[补充](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64)的[在线服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) | [联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

不会更改的内容：

- 租户初始域 (例如 `contoso.onmicrosoft.de` 租户 ID () GUID 的) ，并且自定义域将在迁移后保持。 

- 迁移到 Office 365 服务的资源的身份验证请求由 Office 365 服务 Azure 身份验证服务 () 授予 `login.microsoftonline.com` 。 在迁移期间，仍在 Office 365 德国的资源由现有的德国 Azure 服务 () 进行身份验证 `login.microsoftonline.de` 。

需要注意的注意事项：

- 对于托管域帐户，在将初始 Azure Active Directory 复制 (Azure AD) 租户完成之后 (第一步是将 Azure AD 迁移到 Office 365 服务 Azure AD 服务) 、密码更改、自助密码重置 (SSPR) 更改和管理员重置的密码必须从 Office 365 服务门户完成。 从德国服务更新密码的请求将不会成功，因为 Azure AD 租户已迁移到 Office 365 服务。 联合域密码的重置不会受到影响，因为这些密码在本地目录中完成。

- Azure 登录将显示在用户尝试访问的门户中。 审核日志仅在转换后的 Office 365 服务终结点中可用。 在迁移完成之前，应从 Microsoft 云德国门户保存登录和审核日志。

- 密码重置、密码更改、管理员 (未使用 Active Directory 联合身份验证服务的托管组织的密码重置) 必须通过 Office 365 服务门户执行。 访问 Microsoft 云德国门户以重置密码的用户尝试将失败。

- 常规数据保护法规 (GDPR) 数据主体请求 (Dsr) 从 Office 365 服务 Azure 管理门户执行，以供将来的请求使用。 驻留在 Microsoft 云德国中的任何旧版或非客户诊断数据将在30天内被删除。

## <a name="subscriptions--licenses"></a>订阅 & 许可证

- Microsoft 云德国中的 Office 365 和 Dynamics 订阅将通过 Azure AD 重定位转换为德语区域。 然后更新组织以反映新的 Office 365 服务订阅。 在简短订阅传输过程中，将阻止对订阅所做的更改。

- 在将租户转换为 Office 365 服务时，其特定于德国的订阅和许可证是通过新的 Office 365 服务提供的标准化。 为传输的德国订阅购买对应的 Office 365 服务订阅。 拥有德国许可证的用户将被分配到 Office 365 服务许可证。 完成后，旧版德国订阅将被取消，并从当前的 Office 365 服务租户中删除。

- 迁移各个工作负荷后，通过 Office 365 服务 (如 Microsoft Planner 和 Microsoft Flow) （因为新的 Office 365 服务订阅），可提供其他功能。 如果适合您的组织，租户或许可管理员可以在规划更改管理以引入新服务时禁用新服务计划。 有关如何禁用分配给用户许可证的服务计划的指南，请参阅在 [分配用户许可证时禁用对 Microsoft 365 服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

## <a name="exchange-online"></a>Exchange Online

- 迁移后，Exchange 资源 Url 从旧版德国终结点转换 `outlook.office.de` 为 Office 365 服务终结点 `outlook.office365.com` 。 在迁移完成之前，您的用户可以使用旧版 URL 访问其迁移的邮箱。 客户应在 Exchange 迁移开始后尽快将用户转换到新 URL，以避免影响德国环境的停用状态。 只有在 Exchange 迁移开始后，Outlook services 的 Office 365 服务 Url 才可用。

- 将邮箱迁移为后端进程。 组织中的用户可能在转换过程中处于 Microsoft 云德国或德国地区，并且是同一全局地址列表中 (同一 Exchange 组织的一部分) 。

- 通过使用其邮箱未驻留的 URL 访问服务的 Outlook Web App 用户将看到额外的身份验证提示。 例如，如果用户的邮箱位于 Office 365 服务中，并且用户的 Outlook Web App 连接使用旧版终结点 `outlook.office.de` ，则用户将首先对进行身份验证 `login.microsoftonline.de` ，然后再对进行身份验证 `login.microsoftonline.com` 。 迁移完成后，用户可以访问 () 的新 URL `https://outlook.office365.com` ，并且他们将仅看到单个的预期登录请求。 

## <a name="office-services"></a>Office 服务

可以 `office.de` 在转换之前和过程中访问 Office Online services。 用户的邮箱转换为 Office 365 服务后，用户应开始使用 Office 365 服务 Url。 当后续工作负载迁移到 Office 365 服务时，其从 office.com 门户的接口将开始工作。

## <a name="exchange-online-protection"></a>Exchange Online Protection

- 后端 Exchange Online Protection (EOP) 功能将复制到新的德国地区。
- 在迁移过程中，Office 365 安全与合规中心用户需要转换为使用全局 Url `https://protection.office.com` 。

## <a name="skype-for-business-online"></a>Skype for Business Online

现有 Skype for Business Online 客户将过渡到 Microsoft Teams。 有关详细信息，请参阅 [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) 。

## <a name="office-365-video"></a>Office 365 视频

Office 365 视频即将在 SharePoint Online 迁移到新的德国数据中心区域后，在3月1日、2021和 Office 365 视频上被停用。 Office 365 视频中的内容将作为迁移 SharePoint Online 的一部分进行迁移。 但是，在 SharePoint 迁移后，Office 365 视频中的视频不会在 Office 365 视频 UI 中播放。 有关详细信息，请参阅 [Office 365 视频转换到 Microsoft Stream (经典) 概述](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)中的迁移日程表。

## <a name="next-step"></a>后续步骤

[了解迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>详细信息

入门：

- [从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)

在转换中移动：

- [迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预备工作](ms-cloud-germany-transition-add-pre-work.md)
- [服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
