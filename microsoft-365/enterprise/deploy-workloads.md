---
title: Microsoft 365 企业版工作负载和方案
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/15/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 将组织用户载入到 Microsoft 365 企业版的工作效率工作负载。
ms.openlocfilehash: 730826f388364d1232f1750059002d111279c1be
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981933"
---
# <a name="microsoft-365-enterprise-workloads-and-scenarios"></a>Microsoft 365 企业版工作负载和方案

为了实现 Microsoft 365 企业版在创造力和团队合作方面的优势，请在基础结构上部署这些工作负载：

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint Online](sharepoint-online-onedrive-workload.md)

有关将整个组织迁移到 Microsoft 365 企业版的常规路线图，请参阅[迁移](migration-microsoft-365-enterprise-workload.md)工作负载，其中包括 Microsoft Office 客户端产品、本地 Office Server 产品和基于 Microsoft Windows 的设备。

这些方案以集成的方式使用 Microsoft 365 企业版中的功能和服务来满足业务需求。 其中一项需求是保护存储在 Microsoft 365 中的高度管控数据。 高度管控数据包括的数字资产：

- 受地区法规约束。
- 组织最有价值的数据，例如商业机密、财务或人力资源信息以及组织策略。

要保护此数据免受内部和外部威胁的影响，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站](teams-sharepoint-online-sites-highly-regulated-data.md)。 此方案将指导你配置 SharePoint Online 网站或 Microsoft Teams 团队，以便安全地存储最有价值的数据。

以下是 Microsoft 365 企业版部署指南中的工作负载和方案：

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

请参阅 [Microsoft 365 工作效率库](https://www.microsoft.com/microsoft-365/success/)了解更多方案。 

1. 在此网页中，键入搜索字符串或单击**筛选依据**，然后在 Microsoft 365 中指定行业、角色（部门）和产品。
2. 从结果中，单击卡片以查看可以帮助你入门的步骤。

## <a name="foundation-infrastructure-prerequisites"></a>基础结构先决条件

*理想情况下*，你应该在配置[基础结构](deploy-foundation-infrastructure.md)的所有阶段后部署工作负载和方案。 这可确保所有基础层设施都准备就绪，以便为用户及其设备提供集成、安全性和最佳体验。

| 阶段 | 结果 |
|:-------|:-----|
| 网络 | 你的网络已更新，可以为 Microsoft 365 云服务提供最佳性能。 |
| 标识 | 通过对用户帐户进行强身份验证和保护管理员帐户来同步和保护身份。 |
| Windows 10 企业版 | 运行 Windows 7 或 Windows 8.1 的计算机可以升级至 Windows 10 企业版，并且新设备已安装了 Windows 10 企业版。 |
| Office 365 专业增强版 | 现有 Microsoft Office 用户可以升级到 Office 365 专业增强版。 |
| 移动设备管理 | 可以注册和管理你的设备。 |
| 信息保护 | 已启用 Office 365 安全功能，并且你的敏感度标签或 Azure 信息保护标签已准备好保护文档。 |

请记住，这是理想方案，可能需要一些时间来规划、配置、测试和试用，尤其是在具有现有基础架构和多个位置的大型组织中。 不必在所有位置完成所有这些阶段，也可快速从 Microsoft 365 企业版中获得业务价值。 

以下是一些可立即部署的常见工作负载： 

- 向用户推出基础架构的**标识**阶段后，许多组织都会部署：
  - 与 [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) 结合使用的 [Office 365 专业增强版](office365proplus-infrastructure.md)。 Office 365 专业增强版提供了新式身份验证的安全性和最新 Microsoft Office 客户端的用户体验。 将用户的个人文件迁移到 OneDrive for Business 可以减少对基础架构以及为主文件夹和驱动器提供支持的需要。
  - [Exchange Online](exchangeonline-workload.md)，以便用户可以开始使用基于云的电子邮件。
- 如果你不需要在云中存储受到严格监管的数字资产，请在部署**信息保护**阶段之前为用户部署 [Microsoft Teams](teams-workload.md) 和 [SharePoint Online](sharepoint-online-onedrive-workload.md)。

必须确定采用何种最佳方式来排序和部署基础结构先决条件阶段的配置，以满足业务需求。

### <a name="best-practice"></a>最佳做法

我们强烈建议你在将用户载入任何工作负载或方案之前部署并推出基础架构的**标识**阶段。

**标识**阶段可确保基于云的标识（无论是仅限云还是与本地 Active Directory 域服务 (AD DS) 同步）包含用于管理身份验证和访问的用户和计算机帐户及组。 将组织的数字资产置于 Microsoft 365 云中之前，需要对所有用户进行强身份验证并为管理员帐户提供强大的保护。

虽然是基础性的并且对整体性能非常重要，在将用户载入工作负载的过程中，可以推出**网络**阶段，而你知道 Microsoft 365 应用程序和服务性能将随着时间的推移而提高。 对于具有多个位置、混合边缘设备和 Internet 连接的企业组织尤其如此。

