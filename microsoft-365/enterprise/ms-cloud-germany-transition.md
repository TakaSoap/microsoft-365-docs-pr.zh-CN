---
title: 从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务
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
description: 摘要：了解如何从德国 Microsoft 云迁移到新的德国数据中心区域内的 Office 365 服务
ms.openlocfilehash: 28344f1249e4f51bb9802bf19ca7561182610a7c
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921585"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务

> [!NOTE]
> 本文仅适用于符合条件的德国 Microsoft 云客户。

2018 年 8 月，Microsoft 宣布打算从德国的新云区域交付完整的 Microsoft 云（Azure、Office 365、Dynamics 365 和 Power Platform）以更好地实现客户数字化转型。 2019 年 8 月，我们宣布已启动在德国开放新的云区域的流程。 我们已宣布提供 Azure、Office 365、Dynamics 365 和 Power Platform。

新区域旨在满足德国客户不断变化的需求，这些客户具有更大的灵活性、最新的智能云服务、与 Microsoft 365 服务云服务网络的完整连接以及德国的客户数据驻留。

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>如何迁移到新的德国数据中心区域

现有 Microsoft 云德国客户现在可以开始迁移其 Office 365、Dynamics 365 客户参与度和 Power Platform 客户。 首先要[选择采用 Microsoft 引导的迁移](https://aka.ms/office365germanymoveoptin)方法，迁移到新的德国数据中心区域。

对于选择采用 Microsoft 驱动的方法的组织，迁移预计于 2021 年初开始，并将于 2021 年 10 月 29 日完成。 迁移后，核心客户数据和订阅会迁移到新的德国区域。

本文概述了 Microsoft 推动的迁移方法、迁移期间和迁移后用户和管理员的体验的清晰性，以及客户可能基于你利用的工作负荷需要采取的操作。

下列服务将采用 Microsoft 提出的方法进行迁移：

- Azure Active Directory (Azure AD) 
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business

- Skype for Business Online\*\*
- Office 365 组
- Dynamics 365 /Power Platform\*\*\*

\*\*在从德国 Microsoft 云迁移到德国数据中心区域期间，现有 Skype for Business Online 客户将过渡到 Microsoft Teams。 有关详细信息，请参阅[开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)。

\*\*\*Dynamics [365](https://aka.ms/d365ceoptin) 客户参与文章中介绍了这些服务迁移的先决条件和影响。

Office 365 视频将于 2021年 3 月 1 日停用。 如果选择将 Office 365 租户迁移到新德国数据中心区域，则 SharePoint Online 迁移完成后，将不支持 Office 365 视频。 有关详细信息，请参阅德国 [Microsoft](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)云时间线。

## <a name="how-is-the-migration-organized"></a>如何组织迁移？

此图显示了迁移到新的德国数据中心的九个阶段。

![迁移到新德国数据中心的九个阶段](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

当你选择加入迁移时 [，这些阶段将开始](https://aka.ms/office365germanymoveoptin)。 大多数迁移阶段都是作为后端服务操作执行的，所需的客户交互最少，并且执行一个阶段之后。 其他客户引导任务的开始和整体迁移状态将在迁移过程中通过 Microsoft 365 管理中心的消息中心进行通信。 任务示例可能包括客户管理的 DNS 更新、Exchange 混合客户的混合设置重新配置或 Azure 迁移。

选择加入时，迁移不会立即开始。 你的组织将添加到计划稍后迁移的租户列表中。 现在可以开始工作前阶段，这些阶段对于确保在完成时成功迁移和使用至关重要：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预工作](ms-cloud-germany-transition-add-pre-work.md)

在租户迁移开始的一周之前，你将在消息中心服务中收到通知，作为最终警告，指出所有先决条件都必须完成。

迁移将你的 Azure AD 租户从欧盟地区的独立德国 Azure AD 服务迁移到 Azure AD 的 Office 365 服务实例。

下一个阶段是，将租户&#39;订阅和用户许可证从德国特定产品迁移到全球产品。

完成所有步骤（包括客户 Azure 迁移）后，租户在 Office 365 服务服务中完成，迁移标记为完成。 此时，消息中心的最终更新将提供给您。 租户现在是一个完全全局的 Office 365 组织。

您将收到消息中心帖子的迁移进度通知。 这些帖子将出现在特定的里程碑上，并提供有关步骤进度的指导，以及客户根据流程要求采取行动的重要信息。 消息中心通知在下列里程碑中提供：

- 在 Azure AD (前 5 个工作日开始迁移) 
- Azure AD 迁移完成
- 订阅和许可证迁移完成
- SharePoint 迁移完成
- Exchange 迁移完成
- Skype for Business 完成
- Dynamics complete
- Power BI complete
- 服务的最终转换已完成

## <a name="moving-to-the-new-german-datacenter-regions"></a>移动到新的德国数据中心区域

现有 Microsoft 云德国客户现在可以开始迁移其 Office 365、Dynamics 365 客户参与度和 Power Platform 服务。 首先要[选择采用 Microsoft 引导的迁移](https://aka.ms/office365germanymoveoptin)方法，迁移到新的德国数据中心区域。 续订订阅时，将自动选择加入 Microsoft 协助的迁移。 发生此情况时，Microsoft 会通过电子邮件和 Microsoft 365 管理中心的消息中心通知客户租户管理员。 但是，如果你希望立即开始此过程，则现在可以直接选择在[](https://aka.ms/office365germanymoveoptin)Microsoft 365 管理中心中加入。 迁移预计于 2021 年初开始，并将于 2021 年 10 月 29 日完成。 

迁移后，核心客户数据和订阅将移动到新的德国数据中心区域。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>如何做好准备以迁移到新的德国数据中心区域内的 Office 365 服务

第一步是通知 Microsoft，以便我们有权将你的订阅和数据从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务。 有关说明 [，请参阅选择加入](https://aka.ms/office365germanymoveoptin) 过程，请注意：

- 所有迁移客户都需要验证与 Office 365 服务 [Office 365 URL](urls-and-ip-address-ranges.md)和 IP 地址的连接，其中包括新的德国数据中心区域。 不操作可能会导致服务和客户端失败。
- 查看工作 [前活动列表](ms-cloud-germany-transition-add-pre-work.md) ，确保组织已针对更改做好准备。
- 应查看 Office 365 平台服务说明，了解迁移到德国区域后，您的组织将可以使用哪些功能和服务。
- 试用版订阅将不会迁移，并且将阻止迁移所有付费订阅。 在迁移开始之前，必须取消任何试用版或转换为付费订阅。

## <a name="where-do-i-go-from-here"></a>从此处转到何处？

查看以下常见问题部分。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="is-migration-required"></a>是否需要迁移？

Microsoft 提供从德国 Microsoft 云到新的德国数据中心区域的 Office 365 服务的 Office 365 租户迁移，无需额外付费。 尽管我们强烈建议你选择迁移到新的德国数据中心区域，但我们将继续为德国 Microsoft 云区域提供必需的安全更新。

新的德国数据中心区域的 Office 365 服务：

- 为 [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) 和 [Power BI](https://powerbi.microsoft.com/pricing/) 提供具有市场竞争力的定价。
- 连接到 Microsoft&#39;全球网络，提供数百个网络边缘站点、对等位置和出口点，以在全球任何地方提供可靠的用户体验。
- 帮助你满足德国境内的当地客户数据驻留要求。
- 通过我们服务的最新版本和新功能（包括 Office 365 中的 Microsoft Teams 和多地理位置）提供我们功能齐全的全球云产品。 按 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、、[Office 365](o365-data-locations.md) 和 [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) 的区域比较产品。
- 提供完备功能、企业级安全性和全面的功能，帮助客户满足合规性和法规要求。
- 可通过现有在线服务合同访问。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>不同 Office 365 云服务方案中的服务可用性是什么？
<h2 id="serv-avail"></h2>

以下 15 项服务在 Microsoft 云德国云服务产品/服务中可用。 我们不会向德国 Microsoft 云添加新服务。

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

目前，新的德国数据中心区域有 39 个服务作为 Office 365 服务的一部分提供。 新功能和服务的可用性将持续与全球 Office 365 服务的保持一致。

1. Exchange Online
2. Exchange Online 的客户密码箱
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
17. 在迁移 (Skype for Business) 
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
29. Yammer 企业版
30. Microsoft Forms
31. Power Automate for Office 365
32. Power Virtual Agents for Office 365
33. PowerApps for Office 365
34. Microsoft Bookings
35. 微软待办
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. 列表

### <a name="when-will-migration-happen"></a>何时将进行迁移？

**Azure**

如果你只是 Azure 客户，你可以立即开始 [将](https://docs.microsoft.com/azure/germany/germany-migration-main) Azure 资源迁移到另一区域。 

如果你有带 Office 365、Dynamics 365 或 Power BI 的 Azure，则必须按照迁移过程操作，以确保在开始自动定向 Azure 迁移之前成功迁移 AzureAD。 必须在服务关闭之前完成 Azure 迁移，才能通过 AzureAD 和 Office 365 组织维护 Azure 工作负载。

**Office 365**

立即[选择加入](https://aka.ms/office365germanymoveoptin)以执行 Microsoft 引导的迁移。 当我们准备好开始迁移时，我们将通过 Microsoft 365 管理中心的消息中心通知你。

**Dynamics 365 和 Power BI**

现在，选择加入 Microsoft 推动的 [Dynamics 365 客户参与度和](https://aka.ms/D365ceOptIn) [Power BI](https://aka.ms/PBIOptIn) 迁移。 在我们准备好开始你的迁移时，我们将通过 Microsoft 365 管理中心内的消息中心通知你。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>我使用的 Office 365 服务的价格会发生变化吗？

是。 Microsoft 全球&#39;区域的定价 (包括新的数据中心区域) 通常较低。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>在订阅迁移期间，哪些 SUS 和许可证将应用于我的组织和用户？

在从德国 Microsoft 云迁移到 Office 365 服务期间，德国服务特定的 SKU 将替换为相同或类似 SKU 的全局版本。 在大多数情况下，Office 365 服务中的 SKU 是相同的，但是，在德国的 SKU 在 Office 365 服务中不再可用的替换项很少。 如果希望在迁移完成后更新分配给您的组织的 SKU，请与卖家联系，添加或修改所分配的服务。

| 德国 Microsoft 云 - 产品 SKU (DE)  | Microsoft 云全局 - 产品 SKU (WW)  |
| --- | --- |
| 客户密码箱 \_ DE (密码箱 \_ DE)  | 客户密码箱 (密码箱)  |
| Dynamics 365 Enterprise Edition - 其他数据库存储 \_ DE (CRMSTORAGE \_ DE)  | Dynamics 365 Enterprise Edition - CRMSTORAGE (数据库存储)  |
| Dynamics 365 Enterprise Edition - 其他非生产实例 \_ DE (CRMTESTINSTANCE \_ DE)  | Dynamics 365 Enterprise Edition - CRMTESTINSTANCE (其他非生产)  |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE DE \_ \_ \_)  | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER SERVICE \_)  |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE SALES DE \_ \_)  | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES)  |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS DE \_ \_ \_)  | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM MEMBERS \_)  |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 DE \_)  | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ \_ ENTERPRISE PLAN1)  |
| ECAL Services (EOA、EOP、DLP) \_ DE (ECAL \_ SERVICES \_ DE)  | ECAL Services (EOA、EOP、DLP)  (ECAL \_ SERVICES)  |
| 企业移动性 + 安全性 E3 \_ DE (EMS \_ DE)  | 企业移动性 + 安全性 E3 (EMS)  |
| Exchange Online (计划 1) \_ DE (EXCHANGESTANDARD \_ DE)  | Exchange Online (计划 1)  (EXCHANGESTANDARD)  |
| Exchange Online (计划 2) \_ DE (EXCHANGEENTERPRISE \_ DE)  | Exchange Online (计划 2)  (EXCHANGEENTERPRISE)  |
| Exchange Online Archiving EXCHANGE Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE)  | Exchange Online Archiving EXCHANGE ONLINE (EXCHANGEARCHIVE \_ ADDON)  |
| Exchange Online Archiving FOR EXCHANGE SERVER DE \_ (EXCHANGEARCHIVE DE \_)  | Exchange Online Archiving EXCHANGEARCHIVE Exchange Server (的)  |
| Exchange Online Essentials \_ DE (EXCHANGE S \_ \_ ESSENTIALS DE \_)  | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS)  |
| Exchange Online Kiosk \_ DE (EXCHANGEDESKLESS \_ DE)  | Exchange Online Kiosk (EXCHANGEDESKLESS)  |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE DE \_)  | Exchange Online Protection (EOP \_ ENTERPRISE)  |
| Microsoft 365 商业标准 (O365 \_ 商业 \_ 高级版)  | Microsoft 365 商业标准 (O365 \_ 商业 \_ 高级版)  |
| Microsoft Dynamics CRM Online实例 DE \_ (CRMINSTANCE DE \_)  | Microsoft Dynamics CRM Online CRMINSTANCE (实例)  |
| OFFICE 365 A1 for faculty \_ DE (STANDARDWOFFPACK \_ FACULTY DE \_)  | STANDARDWOFFPACK 教职员工 (Office 365 \_ A1)  |
| 适用于学生 DE 的 Office 365 A1 \_ (STANDARDWOFFPACK \_ STUDENT DE \_)  | 适用于 STANDARDWOFFPACK 学生 (Office 365 \_ A1)  |
| Office 365 高级合规性 \_ DE (EQUIVIO \_ ANALYTICS DE \_)  | Microsoft 365 E5 合规性 (信息 \_ 保护 \_ 合规性)  |
|Microsoft Defender for Office 365 (计划 1) \_ DE (ATP \_ ENTERPRISE DE \_)  |Microsoft Defender for Office 365 (计划 1)  (ATP \_ ENTERPRISE)  |
| Office 365 商业基础 \_ 版 DE (O365 BUSINESS \_ \_ ESSENTIALS DE \_)  | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS)  |
| Office 365 商业高级 \_ 版 DE (O365 \_ 商业 \_ 高级版 DE \_)  | Microsoft 365 商业标准 (O365 \_ 商业 \_ 高级版)  |
| Office 365 商业 \_ 版 DE (O365 \_ BUSINESS DE \_)  | Microsoft 365 商业应用版 (O365 \_ 商业版)  |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE)  | Office 365 E1 (STANDARDPACK)  |
| 不带 ProPlus DE 的 Office 365 \_ E3 (ENTERPRISEPACKWITHOUTPROPLUS \_ DE)  | 不带 ProPlus 的 Office 365 E3 (ENTERPRISEPACKWITHOUTPROPLUS)  |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE)  | Office 365 E3 (ENTERPRISEPACK)  |
| Office 365 企业版 E1 \_ DE (STANDARDPACK \_ DE)  | Office 365 企业版 E1 (STANDARDPACK)  |
| Office 365 企业版 E3 \_ DE (ENTERPRISEPACK \_ DE)  | Office 365 企业版 E3 (ENTERPRISEPACK)  |
| SHAREPOINTSTORAGE DE (Office 365 额外文件 \_ \_ 存储 DE)  | SHAREPOINTSTORAGE (Office 365 额外文件)  |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE)  | Office 365 F1 (DESKLESSPACK)  |
| Office 365 ProPlus for Faculty \_ DE (OFFICESUBSCRIPTION \_ FACULTY DE \_)  | Office 365 专业增强版（教职员工 (OFFICEUBSCRIPTION \_ 教职员工)  |
| Office 365 专业增强版（学生 \_ 版 DE (OFFICEUBSCRIPTION \_ 学生版 DE \_)  | Office 365 专业增强版（学生 (OFFICEUBSCRIPTION \_ 学生)  |
| Office 365 ProPlus \_ DE (OFFICESUBSCRIPTION \_ DE)  | Office 365 ProPlus (OFFICESUBSCRIPTION)  |
| ONEDrive for Business (计划 1) \_ DE (WACONEDRIVESTANDARD \_ DE)  | OneDrive for Business (计划 1)  (WACONEDRIVESTANDARD)  |
| OneDrive for Business (计划 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE)  | OneDrive for Business (计划 2)  (WACONEDRIVEENTERPRISE)  |
| Power BI Pro for faculty \_ DE (POWER BI PRO \_ \_ \_ FACULTY DE \_)  | Power BI Pro for faculty (POWER \_ BI \_ PRO \_ FACULTY)  |
| Power BI Pro \_ DE (POWER BI PRO DE \_ \_ \_)  | Power BI Pro (POWER \_ BI \_ PRO)  |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE)  | Project Online Essentials (PROJECTESSENTIALS)  |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE)  | Project Online Premium (PROJECTPREMIUM)  |
| Project Online Professional \_ DE (PROJECTPROFESSIONAL \_ DE)  | Project Online Professional (PROJECTPROFESSIONAL)  |
| PROJECT 计划 3 \_ DE (PROFESSIONAL \_ DE)  | Project 计划 3 (PROJECTPROFESSIONAL)  |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE)  | Office 365 E3 (ENTERPRISEPACK)  |
| SharePoint Online (计划 1) \_ DE (SHAREPOINTSTANDARD \_ DE)  | SharePoint Online (计划 1)  (SHAREPOINTSTANDARD)  |
| SharePoint Online (计划 2) \_ DE (SHAREPOINTENTERPRISE \_ DE)  | SharePoint Online (计划 2)  (SHAREPOINTENTERPRISE)  |
| SKYPE for Business Online (计划 1) \_ DE (MCOIMP \_ DE)  | Office 365 E1 (STANDARDPACK)  |
| SKYPE for Business Online (计划 1) \_ DE (MCOIMP \_ DE)  | SKYPE for Business Online (计划 1)  (MCOIMP)  |
| Skype for Business Online (计划 2) \_ DE (MCOSTANDARD \_ DE)  | MCOSTANDARD (计划 2)  (Skype for Business Online)  |
| Skype for Business Plus CAL \_ DE (MCOPLUSCAL \_ DE)  | Skype for Business Plus CAL (MCOPLUSCAL)  |
| Visio Online Plan 1 for faculty \_ DE (VISIOONLINE \_ PLAN1 \_ FAC DE \_)  | Visio Online Plan 1 for faculty (VISIOONLINE \_ PLAN1 \_ FAC)  |
| Visio Online 计划 1 \_ DE (VISIOONLINE \_ PLAN1 DE \_)  | Visio Online 计划 1 (VISIOONLINE \_ PLAN1)  |
| Visio Online Plan 2 for faculty \_ DE (VISIOCLIENT \_ FACULTY DE \_)  | Visio Online Plan 2 for faculty (VISIOCLIENT \_ FACULTY)  |
| Visio Online 计划 2 \_ DE (VISIOCLIENT \_ DE)  | Visio Online 计划 2 (VISIOCLIENT)  |
| Visio 计划 1 \_ DE (VISIOONLINE \_ PLAN1 DE \_)  | Visio 计划 1 (VISIOONLINE \_ PLAN1)  |
| Visio 计划 2 \_ DE (VISIOCLIENT \_ DE)  | Visio 计划 2 (VISIOCLIENT)  |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>我可如何获取帮助，让 Microsoft 帮我迁移到新的区域或解答支持问题？

如果你有问题，可以联系我们或你的合作伙伴：

- 对于 Azure，可在 Azure 门户提交[新的支持请求](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)。
- 对于 Office 365，可以使用 Microsoft &quot; &quot; [365](https://portal.office.de/)管理中心的"需要帮助？"链接提交问题。
- 如果你是 Dynamics 365 Customer Engagement and Power BI customer and also have Office 365， you may submit questions using the &quot; Need Help？ &quot; link of the [Microsoft 365 admin center.](https://portal.office.de/) 有关 Dynamics 365 Customer Engagement 支持选项，可查看[此处](https://docs.microsoft.com/dynamics365/get-started/support/)。 有关 Power BI 支持选项，可查看[此处](https://powerbi.microsoft.com/support/)。


## <a name="next-step"></a>后续步骤

[选择加入迁移](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>更多信息

入门：

- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
