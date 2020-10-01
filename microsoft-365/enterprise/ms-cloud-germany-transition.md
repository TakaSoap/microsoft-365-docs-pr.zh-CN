---
title: 从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
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
ms.openlocfilehash: a77dc43c4c30992d2e50aad94878f9269573db52
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327113"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务

> [!NOTE]
> 本文仅适用于符合条件的 Microsoft 云德国客户。

在8月2018日，Microsoft 宣布我们打算提供完整的 Microsoft 云– Azure、Office 365、Dynamics 365 和 Power Platform-从德国的新云区域，以更好地实现我们客户的数字转换。 2019 年 8 月，我们宣布已启动在德国开放新的云区域的流程。 我们已经宣布了 Azure、Office 365、Dynamics 365 和 Power Platform 的可用性。

新的区域旨在满足以更灵活、最新的智能云服务以及与365我们在德国的客户数据派驻服务的完整连接的德语客户的发展需求。

## <a name="how-to-migrate-to-the-new-german-regions"></a>如何迁移到新的德语区域

现有 Microsoft 云德国客户现在可以开始迁移其 Office 365、Dynamics 365 客户接洽和 Power Platform 客户。 首先要[选择采用 Microsoft 引导的迁移](https://aka.ms/office365germanymoveoptin)方法，迁移到新的德国数据中心区域。

对于选择参加 Microsoft 驱动的方法的组织，预计迁移将在2021年初开始，并将于2021年10月29日完成。 迁移后，核心客户数据和订阅会迁移到新的德国区域。

本文概述了用于迁移的 Microsoft 驱动的方法、迁移过程中和迁移后对用户和管理员的体验的清晰性，以及根据您所使用的工作负载，客户可能需要的操作。

下列服务将采用 Microsoft 提出的方法进行迁移：

- Azure Active Directory (Azure AD) 
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive for Business

- Skype for Business Online\*\*
- Office 365 组
- Dynamics 365/Power Platform\*\*\*

\*\*在将 Microsoft 云德国迁移到德国数据中心区域的过程中，现有的 Skype for Business Online 客户将转到 Microsoft 团队。 有关详细信息，请参阅[开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)。

\*\*\*这些服务的迁移的先决条件和影响将在 [Dynamics 365 Customer engagement](https://aka.ms/d365ceoptin) 文章中介绍。

Office 365 视频将于 2021年 3 月 1 日停用。 如果选择将 Office 365 租户迁移到新德国数据中心区域，则 SharePoint Online 迁移完成后，将不支持 Office 365 视频。 若要了解详细信息，请单击 [此处](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) 。

## <a name="how-is-the-migration-organized"></a>迁移是如何组织的？

此图表示迁移到新的德国数据中心的 Office 365 和 Dynamics 365 的各种组件。

![迁移到新的德国数据中心的 Office 365 和 Dynamics 365 的组件](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

在 [选择迁移](https://aka.ms/office365germanymoveoptin)时，将在所有启动的阶段执行迁移。 大多数迁移阶段都是作为后端服务操作执行的，并需要最少的客户交互，并在另一阶段执行。 在迁移过程中，将在迁移过程中通过 Microsoft 365 管理中心的邮件中心传递其他客户指导任务和整体迁移状态的启动。 任务的示例可能包括客户托管的 DNS 更新、Exchange 混合客户的混合安装或 Azure 迁移的重新配置。

当自愿加入时，迁移并不会立即开始。 您的组织将添加到计划稍后迁移的租户列表中。 您可以立即开始 "预备工作" 阶段，因为这些阶段是确保成功迁移和完成后使用的关键。

在租户迁移开始之前的一周，您将在邮件中心服务中收到通知，作为最后一条警告，指出所有先决条件都必须完整完成。

迁移会将 Azure AD 租户从 sovereign 德国 Azure AD 服务移动到欧盟地区的 Azure AD 的 Office 365 服务实例。

下一阶段是从德国特定产品迁移租户&#39;s 订阅和用户许可证。

在完成所有步骤（包括客户 Azure 迁移）后，您的租户将在 Office 365 服务服务中完成，并将迁移标记为已完成。 在这种情况下，将向您提供对邮件中心的最终更新。 租户现在不是完全全局的 Office 365 组织。

将通过邮件中心帖子通知你迁移进度。 张贴内容将在特定的里程碑发生，并将提供有关步骤的指导，并提供有关客户根据过程要求进行操作的重要信息。 消息中心通知在以下里程碑处提供：

- 开始迁移 (在 Azure AD 迁移开始之前的5个工作日内) 
- Azure AD 迁移完成
- 订阅和许可证迁移完成
- SharePoint 迁移完成
- Exchange 迁移完成
- Skype for Business 完成
- Dynamics 完成
- Power BI 完成
- 服务的最终转换已完成

## <a name="moving-to-the-new-german-regions"></a>移到新的德国区域

Microsoft 云德国中现有的 Microsoft 云德国 () 客户现在可以开始迁移其 Office 365、Dynamics 365 客户接洽和 Power Platform 客户。 首先要[选择采用 Microsoft 引导的迁移](https://aka.ms/office365germanymoveoptin)方法，迁移到新的德国数据中心区域。 续订订阅时，将自动选择加入 Microsoft 辅助迁移。 当发生这种情况时，microsoft 会使用电子邮件和 Microsoft 365 管理中心的邮件中心通知客户租户管理员。 但是，如果你更愿意现在开始此过程，你现在可以直接在 Microsoft 365 管理中心中 [选择加入](https://aka.ms/office365germanymoveoptin) 。 预计迁移将于2021年10月29日开始，并将于2021年10月29日完成。 

迁移后，核心客户数据和订阅会迁移到新的德国区域。

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>如何做好准备以迁移到新的德国数据中心区域内的 Office 365 服务

第一步是通知 Microsoft，让我们有权将您的订阅和数据从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务。 有关说明，请参阅 [自愿加入过程](https://aka.ms/office365germanymoveoptin) ，并注意以下几点：

- 所有正在迁移的客户需要验证与 Office 365 服务 [Office 365 url 和 IP 地址](urls-and-ip-address-ranges.md)的连接，其中包括新的德国数据中心区域。 Inaction 可能会导致服务和客户端出现故障。
- 应查看 Office 365 platform 服务说明，以了解迁移到德语区域后，贵组织将提供哪些功能和服务。
- 不会迁移试用版订阅，并将阻止所有付费订阅的迁移。 在迁移开始之前，您必须取消任何试用版或转换为付费订阅。

## <a name="where-do-i-go-from-here"></a>从此处转到哪里？

查看下面的常见问题解答部分。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="is-migration-required"></a>是否需要迁移？

Microsoft 在新的德国数据中心区域提供 Office 365 租户从 Microsoft 云德国迁移到 Office 365 服务，无额外收费。 虽然强烈建议您选择将迁移到新的德国数据中心区域，但我们将继续向 Microsoft 云德国区域提供必要的安全更新。

新德国数据中心区域中的 Office 365 服务：

- 为 [Azure](https://azure.microsoft.com/pricing/calculator/)、[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans)、[Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) 和 [Power BI](https://powerbi.microsoft.com/pricing/) 提供具有市场竞争力的定价。
- 连接到 Microsoft&#39;s 全局网络，提供数百个网络边缘网站、对等位置和出局点，以在世界各地提供强健的用户体验。
- 帮助你满足德国境内的当地客户数据驻留要求。
- 使用我们的服务的最新版本和 Office 365 中的新功能（包括 Microsoft 团队和多地理位置）提供全功能的全球云产品。 按 [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central)、、[Office 365](o365-data-locations.md) 和 [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability) 的区域比较产品。
- 提供完备功能、企业级安全性和全面的功能，帮助客户满足合规性和法规要求。
- 可通过现有在线服务合同访问。

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>不同 Office 365 云服务方案中的服务可用性是什么？

Microsoft 云德国云服务提供了以下15个服务。 我们不会将新服务添加到 Microsoft 云德国。

1. Exchange Online
2. 客户密码箱 (Exchange Online)
3. 组（新式组）
4. Delve 配置文件
5. Exchange Online Protection
6. 高级威胁防护 (ATP)
7. 高级电子数据展示
8. 高级数据管理
9. SharePoint Online
10. 客户密码箱 (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online、Excel Online、PowerPoint, OneNote、Visio Online
14. Office 365 专业增强版
15. Outlook Mobile

目前，新的德国数据中心区域提供 29 项服务，是 Office 365 服务的一部分。 新功能和服务的可用性将持续与全球 Office 365 服务的保持一致。

1. Exchange Online
2. Exchange Online 的客户密码箱
3. Microsoft 365 组
4. Delve 配置文件
5. MyAnalytics
6. 工作区分析
7. Exchange Online Protection
8. 高级威胁防护 (ATP)
9. 高级电子数据展示
10. 高级安全管理
11. 信息权限管理
12. 高级数据管理
13. SharePoint Online
14. SharePoint Online 的客户密码箱
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (将在迁移过程中迁移到 Microsoft 团队) 
18. 云 PBX
19. PSTN 会议
20. PSTN 呼叫
21. Microsoft Teams
22. 管理员报告/使用率报告
23. Word Online、Excel Online、PowerPoint、OneNote 和 Visio Online
24. 规划器
25. Sway
26. Microsoft 365 应用版
27. Outlook Mobile
28. 企业移动性 + 安全性 (EMS) E3 (Azure AD Premium P1、Intune 和 Rights Management Service) 
29. Yammer Online

### <a name="when-will-migration-happen"></a>何时将进行迁移？

**Azure**

如果你仅为 Azure 客户，则可以立即开始将 Azure 资源 [迁移](https://docs.microsoft.com/azure/germany/germany-migration-main) 到其他区域。 如果你拥有 Office 365、Dynamics 365 或 Power BI 的 Azure，请按照以下步骤操作。

**Office 365**

立即[选择加入](https://aka.ms/office365germanymoveoptin)以执行 Microsoft 引导的迁移。 当我们准备好开始迁移时，我们将通过 Microsoft 365 管理中心中的邮件中心通知你。

**Dynamics 365 和 Power BI**

选择参加 Microsoft 驱动的针对 [Dynamics 365 客户接洽](https://aka.ms/D365ceOptIn) 和 [power BI](https://aka.ms/PBIOptIn) 的迁移。 在我们准备好开始你的迁移时，我们将通过 Microsoft 365 管理中心内的消息中心通知你。

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>是否将对我使用的 Office 365 服务价格进行更改？

是。 Microsoft&#39;s 全局云区域中的定价 (包括新的数据中心区域) 通常较低。

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>在订阅迁移过程中，哪些 Sku 和许可证将应用到我的组织和用户？

在从 Microsoft 云德国迁移到 Office 365 服务时，德国特定于服务的 Sku 将替换为相同或类似 SKU 的全球版本。 在大多数情况下，Office 365 服务中的 SKU 是相同的，但是，在 Office 365 服务中，德国的 SKU 不再可用。 如果您希望在迁移完成后更新分配给您的组织的 SKU，请联系您的卖家以添加或修改分配的服务。

| Microsoft 云德国-产品 SKU (DE)  | Microsoft 云全局产品 SKU (WW)  |
| --- | --- |
| 客户密码箱 \_ de (密码箱 \_ de)  | 客户密码箱 (密码箱)  |
| Dynamics 365 Enterprise Edition-额外的数据库存储 \_ de (CRMSTORAGE \_ de)  | Dynamics 365 Enterprise Edition-其他数据库存储 (CRMSTORAGE)  |
| Dynamics 365 Enterprise Edition-其他非生产实例 \_ de (CRMTESTINSTANCE \_ de)  | Dynamics 365 Enterprise Edition-其他非生产实例 (CRMTESTINSTANCE)  |
| Dynamics 365 for Customer Service Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Customer \_ Service \_ DE)  | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ Enterprise \_ Customer \_ Service)  |
| Dynamics 365 for Sales Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Sales \_ DE)  | 用于 Sales Enterprise Edition (DYN365 \_ Enterprise \_ Sales) 的 Dynamics 365 |
| 适用于团队成员的 Dynamics 365 企业版 \_ (DYN365 \_ 企业 \_ 团队 \_ 成员 \_ de)  | Team Members Enterprise Edition (DYN365 \_ enterprise \_ 团队 \_ 成员) 的 Dynamics 365 |
| Dynamics 365 Plan 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ PLAN1 \_ de)  | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1)  |
| ECAL Services (EOA、EOP、DLP) \_ de (ECAL \_ Services \_ de)  | ECAL Services (EOA、EOP、DLP)  (ECAL \_ Services)  |
| 企业移动性 + 安全 E3 \_ de (EMS \_ de)  | 企业移动性 + 安全 E3 (EMS)  |
| Exchange Online (Plan 1) \_ de (EXCHANGESTANDARD \_ de)  | Exchange Online (Plan 1)  (EXCHANGESTANDARD)  |
| Exchange Online (Plan 2) \_ de (EXCHANGEENTERPRISE \_ de)  | Exchange Online (Plan 2)  (EXCHANGEENTERPRISE)  |
| Exchange Online 存档 for Exchange Online \_ de (EXCHANGEARCHIVE \_ 加载项 \_ de)  | Exchange Online 存档 for Exchange Online (EXCHANGEARCHIVE \_ 加载项)  |
| Exchange Online 存档，用于 Exchange Server \_ de (EXCHANGEARCHIVE \_ de)  | Exchange Online 存档 for Exchange Server (EXCHANGEARCHIVE)  |
| Exchange Online Essentials \_ de (EXCHANGE \_ S \_ essentials \_ de)  | Exchange Online Essentials (EXCHANGE \_ S \_ essentials)  |
| Exchange Online 展台 \_ de (EXCHANGEDESKLESS \_ de)  | Exchange Online 展台 (EXCHANGEDESKLESS)  |
| Exchange Online Protection \_ de (EOP \_ 企业版 \_ de)  | Exchange Online Protection (EOP \_ ENTERPRISE)  |
| Microsoft 365 Business Standard (O365 \_ 商业 \_ 高级版)  | Microsoft 365 Business Standard (O365 \_ 商业 \_ 高级版)  |
| Microsoft Dynamics CRM Online 实例 \_ de (CRMINSTANCE \_ de)  | Microsoft Dynamics CRM Online 实例 (CRMINSTANCE)  |
| Office 365 A1 for 教职员 \_ (STANDARDWOFFPACK \_ 教职员 \_ de)  | Office 365 A1 for 教职员工 (STANDARDWOFFPACK \_ 教职员)  |
| Office 365 A1 学生版 \_ de (STANDARDWOFFPACK \_ 学生版 \_)  | Office 365 A1 学生版 (STANDARDWOFFPACK \_ 学生)  |
| Office 365 高级合规性 \_ de (EQUIVIO \_ ANALYTICS \_ de)  | Microsoft 365 E5 合规性 (信息 \_ 保护 \_ 合规性)  |
| Office 365 高级威胁防护 (计划 1) \_ DE (ATP \_ 企业版 \_ de)  | Office 365 高级威胁防护 (计划 1)  (ATP \_ ENTERPRISE)  |
| Office 365 商业协作版 \_ (O365 \_ 商业版 \_ essentials \_ de)  | Microsoft 365 Business Basic (O365 \_ 商业 \_ ESSENTIALS)  |
| Office 365 商业高级版 \_ de (O365 \_ 商业 \_ 高级版 \_ de)  | Microsoft 365 Business Standard (O365 \_ 商业 \_ 高级版)  |
| Office 365 商业版 \_ de (O365 \_ 商业版 \_ de)  | 适用于 business (O365 商业版的 Microsoft 365 应用程序 \_)  |
| Office 365 E1 \_ de (STANDARDPACK \_ de)  | Office 365 E1 (STANDARDPACK)  |
| 不带专业增强版 \_ de (ENTERPRISEPACKWITHOUTPROPLUS de 的 Office 365 E3 \_)  | 没有专业增强版 (ENTERPRISEPACKWITHOUTPROPLUS 的 Office 365 E3)  |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de)  | Office 365 E3 (ENTERPRISEPACK)  |
| Office 365 企业版 E1 \_ de (STANDARDPACK \_ de)  | Office 365 企业版 E1 (STANDARDPACK)  |
| Office 365 企业版 E3 \_ de (ENTERPRISEPACK \_ DE)  | Office 365 企业版 E3 (ENTERPRISEPACK)  |
| Office 365 额外文件存储 \_ de (SHAREPOINTSTORAGE \_ de)  | Office 365 额外文件存储 (SHAREPOINTSTORAGE)  |
| Office 365 F1 \_ de (DESKLESSPACK \_ DE)  | Office 365 F1 (DESKLESSPACK)  |
| Office 365 专业增强版的教职员 de \_ (officesubscription 处于 \_ 教职员 \_ de)  | Office 365 专业增强版面向教职员 (OFFICESUBSCRIPTION 处于 \_ 教职员)  |
| Office 365 专业增强版 for 学生 \_ (officesubscription 处于 \_ 学生版 \_ de)  | Office 365 专业增强版学生版 (OFFICESUBSCRIPTION 处于 \_ 学生版)  |
| Office 365 专业增强版 \_ de (officesubscription 处于 \_ de)  | Office 365 专业增强版 (OFFICESUBSCRIPTION 处于)  |
| OneDrive for Business (Plan 1) \_ de (WACONEDRIVESTANDARD \_ de)  | OneDrive for Business (Plan 1)  (WACONEDRIVESTANDARD)  |
| OneDrive for Business (Plan 2) \_ de (WACONEDRIVEENTERPRISE \_ de)  | OneDrive for Business (Plan 2)  (WACONEDRIVEENTERPRISE)  |
| Power BI Pro for 教职员 \_ de (power \_ bi \_ pro \_ 教员 \_)  | Power BI Pro for 教职员工 (POWER \_ bi \_ pro \_ 教职员)  |
| Power bi pro \_ de (power \_ bi \_ pro \_ de)  | Power bi Pro (POWER \_ bi \_ pro)  |
| Project Online Essentials \_ de (PROJECTESSENTIALS \_ de)  | Project Online Essentials (PROJECTESSENTIALS)  |
| Project Online 高级版 \_ de (PROJECTPREMIUM \_ de)  | Project Online Premium (PROJECTPREMIUM)  |
| Project Online Professional \_ de (PROJECTPROFESSIONAL \_ DE)  | Project Online Professional (PROJECTPROFESSIONAL)  |
| 项目计划 3 \_ de (PROJECTPROFESSIONAL \_ de)  | 项目计划 3 (PROJECTPROFESSIONAL)  |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de)  | Office 365 E3 (ENTERPRISEPACK)  |
| SharePoint Online (Plan 1) \_ de (SHAREPOINTSTANDARD \_ de)  | SharePoint Online (Plan 1)  (SHAREPOINTSTANDARD)  |
| SharePoint Online (Plan 2) \_ de (SHAREPOINTENTERPRISE \_ de)  | SharePoint Online (Plan 2)  (SHAREPOINTENTERPRISE)  |
| Skype for Business Online (计划 1) \_ de (MCOIMP \_ de)  | Office 365 E1 (STANDARDPACK)  |
| Skype for Business Online (计划 1) \_ de (MCOIMP \_ de)  | Skype for Business Online (Plan 1)  (MCOIMP)  |
| Skype for Business Online (Plan 2) \_ de (MCOSTANDARD \_ de)  | Skype for Business Online (Plan 2)  (MCOSTANDARD)  |
| Skype for Business Plus CAL \_ de (MCOPLUSCAL \_ de)  | Skype for Business Plus CAL (MCOPLUSCAL)  |
| Visio Online 计划1（教职员） \_ (VISIOONLINE \_ PLAN1 \_ FAC \_ DE)  | Visio Online Plan 1 for 教职员工 (VISIOONLINE \_ PLAN1 \_ FAC)  |
| Visio Online 计划 1 \_ de (VISIOONLINE \_ PLAN1 \_ de)  | Visio Online 计划 1 (VISIOONLINE \_ PLAN1)  |
| Visio Online 计划2的教职员 \_ de (VISIOCLIENT \_ 教职员 \_ de)  | Visio Online Plan 2 教职员工 (VISIOCLIENT \_ 教职员)  |
| Visio Online 计划 2 \_ de (VISIOCLIENT \_ de)  | Visio Online 计划 2 (VISIOCLIENT)  |
| Visio 计划 1 \_ de (VISIOONLINE \_ PLAN1 \_ de)  | Visio Plan 1 (VISIOONLINE \_ PLAN1)  |
| Visio 计划 2 \_ de (VISIOCLIENT \_ de)  | Visio Plan 2 (VISIOCLIENT)  |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>我可如何获取帮助，让 Microsoft 帮我迁移到新的区域或解答支持问题？

如果你有任何疑问，可以联系我们或你的合作伙伴：

- 对于 Azure，可在 Azure 门户提交[新的支持请求](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest)。
- 对于 Office 365，您可以使用 &quot; &quot; [Microsoft 365 管理中心](https://portal.office.de/)的 "需要帮助" 链接提交问题。
- 如果您是 Dynamics 365 客户接洽和 Power BI 客户，也是 Office 365，则可以使用 &quot; &quot; [Microsoft 365 管理中心](https://portal.office.de/)的 "需要帮助" 链接提交问题。 有关 Dynamics 365 Customer Engagement 支持选项，可查看[此处](https://docs.microsoft.com/dynamics365/get-started/support/)。 有关 Power BI 支持选项，可查看[此处](https://powerbi.microsoft.com/support/)。

## <a name="more-information"></a>详细信息

即将推出有关迁移到新的德国数据中心区域的其他信息。 将此页面做成书签，以便您可以签入并保持最新。

- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](https://aka.ms/office365germanymoveoptin)
- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [Office 365 URL 和 IP 地址范围](https://aka.ms/o365endpoints)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
