---
title: 从德国 Microsoft 云迁移到Office 365新的德国数据中心区域提供服务
ms.author: andyber
author: andybergen
manager: laurawi
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
description: 摘要：了解如何从德国 Microsoft 云迁移到新的德国数据中心区域内的 Office 365 服务
ms.openlocfilehash: e301f58c3a194c6af8989f4081e733c50a4c104e
ms.sourcegitcommit: 9469d16c6bbd29442a6787beaf7d84fb7699c5e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58400327"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>从德国 Microsoft 云迁移到Office 365新的德国数据中心区域提供服务

> [!NOTE]
> 本文仅适用于符合条件的德国 Microsoft 云客户。

2018 年 8 月，Microsoft 宣布我们计划从德国的新云区域交付完整的 Microsoft 云（Azure、Office 365、Dynamics 365 和 Power Platform）以更好地实现客户的数字化转型。 2019 年 8 月，我们宣布已启动在德国开放新的云区域的流程。 我们已宣布提供 Azure、Office 365、Dynamics 365 和 Power Platform。

新区域旨在通过更灵活、最新的智能云服务、与 Microsoft 365 服务云服务网络的完整连接以及德国的客户数据驻留满足德国客户不断变化的需求。

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>如何迁移到新的德国数据中心区域

现有的德国 Microsoft 云客户现在可以开始迁移其Office 365 Dynamics 365 客户参与度和 Power Platform 客户。 首先要[选择采用 Microsoft 引导的迁移](./ms-cloud-germany-migration-opt-in.md)方法，迁移到新的德国数据中心区域。

对于选择采用 Microsoft 驱动的方法的组织，迁移预计于 2021 年初开始，并将于 2021 年 10 月 29 日完成。 迁移后，核心客户数据和订阅会迁移到新的德国区域。

本文概述了 Microsoft 推动的迁移方法、迁移期间和迁移后的用户和管理员体验的清晰性，以及客户可能需要基于你利用哪些工作负载的操作。

下列服务将采用 Microsoft 提出的方法进行迁移：

- Azure Active Directory (Azure AD) 
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business
- Skype for Business联机\*\*
- Office 365 组
- Dynamics 365 / Power Platform\*\*\*

\*\*在从德国 Microsoft 云迁移到德国数据中心区域期间，现有 Skype for Business Online 客户将过渡到Microsoft Teams。 有关详细信息，请参阅[开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)。

\*\*\*Dynamics 365 Customer engagement一文介绍了 [这些服务迁移的先决条件和](/dynamics365/get-started/migrate-data-german-region) 影响。

Office 365 视频将于 2021年 3 月 1 日停用。 如果选择将 Office 365 租户迁移到新德国数据中心区域，则 SharePoint Online 迁移完成后，将不支持 Office 365 视频。 有关详细信息，请参阅 [Microsoft Cloud Deutschland timeline](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)。

## <a name="how-is-the-migration-organized"></a>如何组织迁移？

此图显示了迁移到新的德国数据中心的十个阶段。

:::image type="content" alt-text="迁移到新德国数据中心的十个阶段" source="../media/ms-cloud-germany-migration-opt-in/migration-organization.png" lightbox="../media/ms-cloud-germany-migration-opt-in/migration-organization.png":::

当你选择加入迁移 [时，这些阶段将开始](./ms-cloud-germany-migration-opt-in.md)。 大多数迁移阶段都是作为后端服务操作执行的，所需的客户交互最少，并且执行后一个阶段。 其他客户引导任务的开始和整体迁移状态将在迁移过程中通过 Microsoft 365 管理中心消息中心进行通信。 任务示例可能包括客户管理的 DNS 更新、针对混合客户的混合Exchange重新配置或 Azure 迁移。

选择加入时迁移不会立即开始。 你的组织将添加到计划稍后迁移的租户列表中。 现在可以开始工作前阶段，这些阶段对于确保在完成时成功迁移和使用至关重要：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)

在租户迁移开始的一周之前，你将在消息中心服务中收到通知，作为最终警告，提醒必须完成所有先决条件。

迁移将 Azure AD 租户从德国 Azure AD 服务迁移到欧盟Office 365 Azure AD 的 Azure AD 服务实例。

下一个阶段是，将租户订阅&#39;许可证从德国特定产品迁移到全球产品。

完成所有步骤（包括客户 Azure 迁移）后，租户将在 Office 365 服务中完成，迁移将标记为完成。 此时，将提供给您消息中心的最终更新。 租户现在是一个完全全局Office 365组织。

你将收到邮件中心帖子的迁移进度通知。 这些帖子将在特定的里程碑上发生，并提供步骤进度的指导，以及客户根据流程要求采取行动的重要信息。 消息中心通知以下列里程碑提供：

- 在 Azure AD (迁移开始前 5 个工作日开始迁移) 
- Azure AD 迁移完成
- 订阅和许可证迁移完成
- SharePoint迁移完成
- Exchange迁移完成
- Skype for Business完成
- Dynamics complete
- Power BI完成
- 服务的最终转换已完成

Azure AD 最终转换到全球服务后，预计所有客户端和应用程序都完全转换为使用正确的终结点。 最终转换后有 30 天窗口，可以继续从德国 Microsoft 云服务获取 Azure AD 令牌。 30 天窗口到期后，客户端和应用程序将无法再访问德国 Microsoft 云的 Azure AD 终结点。 此时，应用程序或用户访问将失败。 在此时间窗口关闭之前，必须确保所有用户和应用程序都迁移到正确的终结点。 

## <a name="moving-to-the-new-german-datacenter-regions"></a>移动到新的德国数据中心区域

现有的德国 Microsoft 云客户现在可以开始迁移其Office 365 Dynamics 365 客户参与度和 Power Platform 服务。 首先要[选择采用 Microsoft 引导的迁移](./ms-cloud-germany-migration-opt-in.md)方法，迁移到新的德国数据中心区域。 续订订阅时，将自动选择加入 Microsoft 协助的迁移。 发生此情况时，Microsoft 会向客户租户管理员发送电子邮件，Microsoft 365 管理中心消息中心通知客户租户管理员。 但是，如果你希望立即开始此过程，则现在可以直接选择加入Microsoft 365 管理中心。 [](./ms-cloud-germany-migration-opt-in.md) 迁移预计于 2021 年初开始，并将于 2021 年 10 月 29 日完成。 

迁移后，核心客户数据和订阅将移动到新的德国数据中心区域。

> [!NOTE]
> 本文包含有关迁移服务Office 365指南。 如果你正在德国 Microsoft 云中运行其他 Azure 工作负载，请参阅德国 [Azure 的迁移指南](/azure/germany/germany-migration-main)。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>如何做好准备以迁移到新的德国数据中心区域内的 Office 365 服务

第一步是通知 Microsoft，以便我们有权将你的订阅和数据从德国 Microsoft 云迁移到新的德国数据中心Office 365服务。 有关说明 [，请参阅选择加入](./ms-cloud-germany-migration-opt-in.md) 流程，请注意：

- 所有迁移客户都需要验证与 Office 365 Services Office 365 URL 和[IP](urls-and-ip-address-ranges.md)地址的连接，其中包括新的德国数据中心区域。 不操作可能会导致服务和客户端故障。
- 查看工作 [前活动列表](ms-cloud-germany-transition-add-pre-work.md) ，确保组织已了解并针对更改做好准备。
- 应查看 Office 365 平台服务说明，了解迁移到德国区域后，贵组织可以使用哪些功能和服务。
- 试用版订阅将不会迁移，并且将阻止迁移所有付费订阅。 在迁移开始之前，必须取消任何试用版或转换为付费订阅。

## <a name="where-do-i-go-from-here"></a>从此处转到何处？

查看以下常见问题部分。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="is-migration-required"></a>是否需要迁移？

Microsoft Office 365从德国 Microsoft 云迁移到德国Office 365德国数据中心区域，无需额外付费。 所有符合条件的德国 Microsoft 云 (德国 Microsoft 云) 客户现已迁移。 不会通过自动化过程迁移其他客户。 作为服务关闭活动的一部分，任何剩余的德国 Microsoft 云订阅和租户将在 2021 年 9 月停用和取消预配。

我们将继续向德国 Microsoft 云区域提供必要的安全更新，直到服务关闭。 

Office 365新的德国数据中心区域提供以下服务：

- 为 [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) 和 [Power BI](https://powerbi.microsoft.com/pricing/) 提供具有市场竞争力的定价。
- 连接到 Microsoft&#39;全球网络，提供数百个网络边缘站点、对等位置和出口点，在全球任何地方提供可靠的用户体验。
- 帮助你满足德国境内的当地客户数据驻留要求。
- 通过我们服务的最新版本和新功能（包括 Microsoft Teams 和 Office 365 中的多地理位置）提供我们功能齐全的全球云产品。 按 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、、[Office 365](o365-data-locations.md) 和 [Dynamics 365](/dynamics365/get-started/availability) 的区域比较产品。
- 提供完备功能、企业级安全性和全面的功能，帮助客户满足合规性和法规要求。
- 可通过现有在线服务合同访问。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>不同 Office 365 云服务方案中的服务可用性是什么？
<h2 id="serv-avail"></h2>

Microsoft 云德国云服务提供以下 15 种服务。 我们不会向德国 Microsoft 云添加新服务。

1. Exchange Online
2. 客户密码箱 (Exchange Online)
3. 组（新式组）
4. Delve 配置文件
5. Exchange Online Protection
6. Defender for Office 365
7. 高级电子数据展示
8. 高级数据管理
9. SharePoint Online
10. 客户密码箱 (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online、Excel Online、PowerPoint, OneNote、Visio Online
14. Office 365 专业增强版
15. Outlook Mobile

目前，有 39 个服务作为新的德国数据中心Office 365服务一部分提供。 新功能和服务的可用性将持续与全球 Office 365 服务的保持一致。

1. Exchange Online
2. 客户密码箱Exchange Online
3. Microsoft 365 组
4. Delve 配置文件
5. MyAnalytics
6. 工作区分析
7. Exchange Online Protection
8. Defender for Office 365
9. 高级电子数据展示
10. 高级安全管理
11. Information Protection for Office 365 
12. 高级数据管理
13. SharePoint Online
14. SharePoint Online 的客户密码箱
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (迁移期间Microsoft Teams迁移到) 
18. 云 PBX
19. PSTN 会议
20. PSTN 呼叫
21. Microsoft Teams
22. 管理员报告/使用率报告
23. Office 网页版
24. Planner
25. Sway
26. Microsoft 365 应用版
27. Outlook Mobile
28. 企业移动性 + 安全性 (EMS) E3 (Azure AD Premium P1、Intune 和 Rights Management Service) 
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate Office 365
32. Power Virtual Agents Office 365
33. Power Apps Office 365
34. Microsoft Bookings
35. 微软待办
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. 列表

### <a name="when-will-migration-happen"></a>何时将进行迁移？

**Azure**

如果你只是 Azure 客户，你现在可以开始 [将](/azure/germany/germany-migration-main) Azure 资源迁移到另一区域。 

如果你有带 Office 365、Dynamics 365 或 Power BI 的 Azure，则必须首先遵循 Office 365 服务的迁移过程，以确保 Azure AD 迁移成功，然后才能开始自动定向 Azure 迁移。 完成租户迁移之前，必须完成 Azure 迁移，才能使用 Azure AD 和 azure Office 365维护 Azure 工作负载。 有关 [其他详细信息，](ms-cloud-germany-transition-phases.md) 请参阅德国 Microsoft 云迁移的迁移阶段操作和影响。

**Office 365、Dynamics 365 和 Power BI**

所有符合条件的德国 Microsoft 云 (德国 Microsoft 云) 客户现已迁移。 不会通过自动化过程迁移其他客户。 作为服务关闭活动的一部分，任何剩余的德国 Microsoft 云订阅和租户将在 2021 年 9 月停用和取消预配。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>我使用的服务Office 365价格会发生变化吗？

是。 Microsoft 全球&#39;区域的定价 (包括新的数据中心区域) 通常较低。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>在订阅迁移过程中，哪些 SKUS 和许可证将应用于我的组织和用户？

在从德国 Microsoft 云迁移到 Office 365 服务期间，德国特定于服务的 SKU 将替换为相同或类似 SKU 的全局版本。 在大多数情况下，Office 365 服务中的 SKU 是相同的，但是，在德国的 SKU 在 Office 365 服务中不再可用， 如果您希望在迁移完成后更新分配给您的组织的 SKU，请与卖家联系，以添加或修改分配的服务。

| 德国 Microsoft 云 - DE (产品 SKU)  | Microsoft Cloud Global - WW (产品 SKU)  |
| --- | --- |
| 客户密码箱 \_ DE (密码箱 \_ DE)  | 客户密码箱 (密码箱)  |
| Dynamics 365 Enterprise Edition - 其他数据库 存储 \_ DE (CRMSTORAGE \_ DE)  | Dynamics 365 Enterprise Edition - CRMSTORAGE 存储 (数据库)  |
| Dynamics 365 Enterprise Edition - \_ CRMTESTINSTANCE DE (其他非生产 \_)  | Dynamics 365 Enterprise Edition - CRMTESTINSTANCE (其他非生产)  |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE DE \_ \_ \_)  | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER SERVICE \_)  |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE SALES DE \_ \_)  | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES)  |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS DE \_ \_ \_)  | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM MEMBERS \_)  |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 DE \_)  | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1)  |
| \_ECAL 服务 (EOA, EOP, DLP) DE (ECAL \_ SERVICES \_ DE)  | ECAL 服务 (EOA, EOP, DLP)  (ECAL \_ SERVICES)  |
| \_企业移动性 + 安全性 E3DE (EMS \_ DE)  | 企业移动性 + 安全性 E3 (EMS)  |
| \_Exchange Online（计划 1）DE (EXCHANGESTANDARD \_ DE)  | Exchange Online（计划 1） (EXCHANGESTANDARD)  |
| \_Exchange Online（计划 2）DE (EXCHANGEENTERPRISE \_ DE)  | Exchange Online（计划 2） (EXCHANGEENTERPRISE)  |
| \_Exchange Online 适用的 Exchange Online ArchivingDE (EXCHANGEARCHIVE \_ \_ ADDON DE)  | Exchange Online 适用的 Exchange Online Archiving (EXCHANGEARCHIVE \_ ADDON)  |
| \_Exchange Server 适用的 Exchange Online ArchivingDE (EXCHANGEARCHIVE \_ DE)  | Exchange Server 适用的 Exchange Online Archiving (EXCHANGEARCHIVE)  |
| \_Exchange Online EssentialsDE (EXCHANGE \_ S \_ ESSENTIALS \_ DE)  | Exchange Online Essentials (EXCHANGE \_ \_ ESSENTIALS)  |
| \_Exchange Online KioskDE (EXCHANGEDESKLESS \_ DE)  | Exchange Online Kiosk (EXCHANGEDESKLESS)  |
| \_Exchange Online ProtectionDE (EOP \_ ENTERPRISE \_ DE)  | Exchange Online Protection (EOP \_ ENTERPRISE)  |
| Microsoft 365 商业标准版 (O365 \_ 商业 \_ 高级版)  | Microsoft 365 商业标准版 (O365 \_ 商业 \_ 高级版)  |
| Microsoft Dynamics CRM OnlineCRMINSTANCE DE (\_ \_ 实例 DE)  | Microsoft Dynamics CRM OnlineCRMINSTANCE (实例)  |
| Office 365 A1 DE 教职员工 \_ (STANDARDWOFFPACK \_ FACULTY \_ DE)  | Office 365 A1 STANDARDWOFFPACK 教职 (教职 \_ 员工)  |
| Office 365 A1针对学生 DE \_ (STANDARDWOFFPACK STUDENT \_ \_ DE)  | Office 365 A1 STANDARDWOFFPACK 学生 (\_ 中学生)  |
| \_Office 365 高级合规版DE (EQUIVIO \_ ANALYTICS \_ DE)  | Microsoft 365 E5 合规 (信息 \_ 保护 \_ 合规性)  |
|MICROSOFT Defender for Office 365 (Plan 1) \_ DE (ATP ENTERPRISE DE \_ \_)  |Microsoft Defender for Office 365 (Plan 1)  (ATP \_ ENTERPRISE)  |
| \_Office 365 商业协作版DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE)  | Microsoft 365 商业基础版 (O365 \_ 商业 \_ 基本)  |
| \_Office 365 商业高级版DE (O365 \_ 商业 \_ 高级 \_ 版 DE)  | Microsoft 365 商业标准版 (O365 \_ 商业 \_ 高级版)  |
| \_Office 365 商业版DE (O365 \_ BUSINESS \_ DE)  | Microsoft 365 商业应用版 (O365 \_ BUSINESS)  |
| \_Office 365 E1DE (STANDARDPACK \_ DE)  | Office 365 E1 (STANDARDPACK)  |
| Office 365 E3 PROPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE)  | Office 365 E3 ENTERPRISEPACKWITHOUTPROPLUS (没有 ProPlus)  |
| \_Office 365 E3DE (ENTERPRISEPACK \_ DE)  | Office 365 E3 (ENTERPRISEPACK)  |
| Office 365 企业版E1 \_ DE (STANDARDPACK DE \_)  | Office 365 企业版E1 (STANDARDPACK)  |
| Office 365 企业版E3 \_ DE (ENTERPRISEPACK DE \_)  | Office 365 企业版E3 (ENTERPRISEPACK)  |
| \_Office 365 额外文件存储空间DE (SHAREPOINTSTORAGE \_ DE)  | Office 365 额外文件存储空间 (SHAREPOINTSTORAGE)  |
| \_Office 365 F1DE (DESKLESSPACK \_ DE)  | Office 365 F1 (DESKLESSPACK)  |
| Office 365 专业增强版教职员工 DE \_ (OFFICESUBSCRIPTION \_ FACULTY \_ DE)  | Office 365 专业增强版教职员工 (OFFICESUBSCRIPTION \_ FACULTY)  |
| Office 365 专业增强版学生 \_ 教育 (注册学生 \_ \_ DE)  | Office 365 专业增强版学生 (OFFICES 订阅 \_ 学生)  |
| \_Office 365 专业增强版DE (OFFICESUBSCRIPTION \_ DE)  | Office 365 专业增强版 (OFFICESUBSCRIPTION)  |
| \_OneDrive for Business（计划 1）DE (WACONEDRIVESTANDARD \_ DE)  | OneDrive for Business（计划 1） (WACONEDRIVESTANDARD)  |
| \_OneDrive for Business（计划 2）DE (WACONEDRIVEENTERPRISE \_ DE)  | OneDrive for Business（计划 2） (WACONEDRIVEENTERPRISE)  |
| Power BI Pro DE 教职员工 \_ (POWER BI \_ \_ PRO \_ FACULTY \_ DE)  | Power BI Pro POWER BI 专业 (\_ 教 \_ \_ 职员工)  |
| \_Power BI ProDE (POWER \_ BI \_ PRO DE \_)  | Power BI Pro (POWER \_ BI \_ PRO)  |
| \_Project Online 协作版DE (PROJECTESSENTIALS \_ DE)  | Project Online 协作版 (PROJECTESSENTIALS)  |
| \_Project Online 高级版DE (PROJECTPREMIUM \_ DE)  | Project Online 高级版 (PROJECTPREMIUM)  |
| \_Project Online ProfessionalDE (PROJECTPROFESSIONAL \_ DE)  | Project Online Professional (PROJECTPROFESSIONAL)  |
| \_Project 计划 3DE (PROJECTPROFESSIONAL \_ DE)  | Project 计划 3 (PROJECTPROFESSIONAL)  |
| Office 365E4 \_ DE (ENTERPRISEWITHSCAL \_ DE)  | Office 365 E3 (ENTERPRISEPACK)  |
| \_SharePoint Online（计划 1）DE (SHAREPOINTSTANDARD \_ DE)  | SharePoint Online（计划 1） (SHAREPOINTSTANDARD)  |
| \_SharePoint Online（计划 2）DE (SHAREPOINTENTERPRISE \_ DE)  | SharePoint Online（计划 2） (SHAREPOINTENTERPRISE)  |
| Skype for Business联机 (计划 1) \_ DE (MCOIMP \_ DE)  | Office 365 E1 (STANDARDPACK)  |
| Skype for Business联机 (计划 1) \_ DE (MCOIMP \_ DE)  | Skype for Business联机 (MCOIMP)  (计划 1)  |
| Skype for Business联机 (计划 2) DE \_ (MCOSTANDARD \_ DE)  | Skype for BusinessMCOSTANDARD (2)  (Online)  |
| Skype for Business加上 CAL \_ DE (MCOPLUSCAL \_ DE)  | Skype for Business加上 CAL (MCOPLUSCAL)  |
| Visio联机计划 1（针对教职员工 \_ DE (VISIOONLINE \_ PLAN1 \_ FAC DE \_)  | Visio适用于 VISIOONLINE PLAN1 FAC (教职员工的在线计划 \_ \_ 1)  |
| Visio联机计划 1 \_ DE (VISIOONLINE \_ PLAN1 DE \_)  | Visio联机计划 1 (VISIOONLINE \_ PLAN1)  |
| VisioVISIOCLIENT FACULTY DE (ONLINE Plan 2 \_ for \_ faculty \_ DE)  | VisioVISIOCLIENT 教职员工 (联机计划 2 \_)  |
| VisioVISIOCLIENT DE (Online Plan 2 \_ \_ DE)  | VisioVISIOCLIENT (Online Plan 2)  |
| \_Visio 计划 1DE (VISIOONLINE \_ PLAN1 \_ DE)  | Visio 计划 1 (VISIOONLINE \_ PLAN1)  |
| \_Visio 计划 2DE (VISIOCLIENT \_ DE)  | Visio 计划 2 (VISIOCLIENT)  |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>我可如何获取帮助，让 Microsoft 帮我迁移到新的区域或解答支持问题？

如果你有问题，可以联系我们或你的合作伙伴：

- 对于 Azure，可在 Azure 门户提交[新的支持请求](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)。
- For Office 365， you may submit questions using the &quot; Need Help？ &quot; link of the [Microsoft 365 管理中心](https://portal.office.de/).
- 如果你是 Dynamics 365 客户参与度Power BI并且还具有Office 365，可以使用"需要帮助？"链接提交 &quot; &quot; Microsoft 365 管理中心。 [](https://portal.office.de/) 有关 Dynamics 365 Customer Engagement 支持选项，可查看[此处](/dynamics365/get-started/support/)。 有关 Power BI 支持选项，可查看[此处](https://powerbi.microsoft.com/support/)。

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>除了德国 Microsoft 云租户外，我的客户还具有全球 Microsoft 云中的 M365 租户。 这两个租户能否作为迁移的一部分合并到一个租户中？

否，没有租户合并功能。 租户将保持独立和唯一，因为每个租户都有自己的命名空间和唯一 ID。 如果需要，Microsoft 将德国 Microsoft 云租户迁移到全局云，否则客户可以取消并放弃它。


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>大多数最终用户在迁移过程中需要执行哪些操作？
迁移旨在对最终用户/客户产生最小影响。
- 确保Office应用程序正在运行最新的可用版本。 
- 使用 Skype for Business 的客户将在Teams迁移过程中转换到 Teams 设备。 [](/deployoffice/teams-install)
- 最终用户可能需要注销应用程序，Office迁移完成后重新登录。 
- 运行 OneDrive 同步客户端的客户需要注销其工作站并再次登录，以允许 OneDrive 同步客户端登录到全局 Azure Active Directory 服务。
- 迁移完成后请注意新的全局 URL，Outlook Web Access (示例：使用 outlook.office365.com) 。 SharePoint联机客户端将继续使用现有 URL 成功连接到 MCD 命名空间， (示例：contoso.sharepoint.de) 。


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>哪些客户受迁移Azure Active Directory影响？ 

所有客户Office 365都Azure Active Directory Microsoft 托管服务操作所需的关键服务组件进行身份验证和存储。 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>迁移对Azure Active Directory的影响？

早期阶段Azure Active Directory迁移对客户体验没有影响。 最终迁移阶段后，客户租户的所有服务完全处于全局服务中。 在此最后阶段Azure Active Directory，德国 Microsoft 云服务将不再接受授权请求，或不再提供访问令牌Office服务。


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>确保与服务 URL 和[IP Office 365网络连接意味着什么](./urls-and-ip-address-ranges.md)？

本文介绍使全局服务正常工作所需的必要 URL 和 IP 地址，以确保良好的客户体验。 在相对极少数情况下，一些客户尝试以最大程度减少流量的方式配置网络外围安全，并限制仅作为德国 Microsoft 云服务 IP 范围的一部分访问服务。


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>如何管理邮件的 DNS Exchange Online以便邮件继续流动？

Microsoft 管理的 IP 范围和 DNS 区域在迁移到全局服务期间进行转换，并作为全局服务的一部分进行转换。 

客户管理的 DNS 区域（如自定义域 MX 记录）由客户负责，但是，为了简化此迁移，客户管理的 MX 记录指向 office.de 区域中的 Office 365 服务终结点，Microsoft 自动管理此服务终结点的迁移。


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>如何管理客户端的 DNS Skype for Business？ 
 
所有 Skype For Business 客户都将过渡到 Microsoft Teams。 在迁移到 DNS Skype不需要转换客户Teams。 客户可以在迁移后立即Teams所有功能登录。
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>迁移Outlook适用于 iOS 和 Android 的 IOS 和 Android 版本会正常工作吗？ 

是。 Microsoft 的建议是，所有客户运行最新可用版本的 Office 客户端，Outlook适用于 iOS 和 Android 客户端的客户端。 迁移到 Office 365 全局服务后，所有 Office 客户端都需要注销并重新登录，才能从全局Azure Active Directory获取新的 Azure Active Directory 访问令牌。 



## <a name="next-step"></a>后续步骤

[选择加入迁移](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>更多信息

入门：

- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 迁移计划信息](/power-bi/admin/service-admin-migrate-data-germany)
- [开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)
