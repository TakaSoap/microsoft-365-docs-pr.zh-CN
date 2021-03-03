---
title: 步骤 4. 适用于企业租户的 Microsoft 365 迁移
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 为 Microsoft 365 租户迁移 Windows 设备、Office 客户端应用和 Office 服务器。
ms.openlocfilehash: 85f1c0d927b881c4d1526ce538ae54f5954a0664
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406356"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>步骤 4. 适用于企业租户的 Microsoft 365 迁移

大多数企业组织都有一个异类环境，其中包括多个版本的操作系统、客户端软件和服务器软件。 Microsoft 365 企业版包括 IT 基础结构的关键组件的最安全版本。 它还包括旨在利用云技术生产力功能。

若要最大化 Microsoft 365 企业版集成产品套件的业务价值，请开始规划和实施迁移这些版本的策略：

| 发件人 | 到 |
|:-------|:-----|
| Windows 7 和 Windows 8.1 | Windows 10 企业版 |
| 在工作者设备上安装的 Office 客户端产品 | Microsoft 365 企业应用版 |
| 本地服务器上安装的 Office 服务器产品 | Microsoft 365 中的等效基于云的服务 |
|  |  |

## <a name="migrating-to-windows-10"></a>迁移到 Windows 10

每个 Microsoft 365 企业版许可证都包括 Windows 10 企业版许可证。 若要迁移运行 Windows 7 或 Windows 8.1 的设备，可以执行就地升级。 对 Windows 7 的支持已于 *2020* 年 1 月 14 日结束。 

有关在就地升级之外安装 Windows 10 企业版的其他方法，请参阅 [Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。 也可以自行[计划 Windows 10 部署](https://aka.ms/planforwin10deployment)。

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>迁移到 Microsoft 365 企业应用版

Microsoft 365 企业版包括 Microsoft 365 企业应用版，它是从 Microsoft 云安装和更新的 Office 客户端产品 (Word、PowerPoint、Excel 和 Outlook) 的一个版本。 有关详细信息，请参阅关于 [Microsoft 365 企业应用版](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。

与其使计算机保持 Office 2019 或旧版本的最新版本，不如执行以下步骤：

1. 获取并分配用户的 Microsoft 365 许可证。
2. 卸载其计算机上的 Office 2013 或 Office 2016。
3. 单独或在 IT 推出期间安装 Microsoft 365 企业应用版。 有关详细信息，请参阅 [Microsoft 365 应用](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)版部署指南。

Microsoft 365 企业应用版会自动安装安全更新和新功能更新，并可以利用 Microsoft 365 中的基于云的服务来增强安全性和工作效率。

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>将本地服务器和数据迁移到 Microsoft 365

Microsoft 365 企业版包括基于云的 Office 服务器服务版本，这些服务使用与 Office 服务器软件本地版本相同的一些工具，如 Web 浏览器和 Outlook 客户端。 这些基于云的服务会针对安全性和新功能自动更新。 迁移后，IT 部门可以节省维护和更新本地服务器所花的时间。

有关迁移特定 Microsoft 365 工作负载的用户和数据的信息，请使用以下资源：

- [将邮箱从本地Exchange Server移动到 Exchange Online](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [将 SharePoint 数据从 SharePoint Server 迁移到 SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [将 Skype for Business Online 迁移到 Microsoft Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>转换整个组织

若要更好地了解如何将整个组织移动到 Microsoft 365 企业版中的产品和服务，请下载此转换海报：

[![显示"转换到 Microsoft 365"海报的图像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

通过这份两页的海报可以快速清点现有基础结构。 使用它获取有关迁移到 Microsoft 365 企业版中的产品或服务的指导。 它显示了 Windows 和 Office 产品以及其他基础结构和安全元素，如设备管理、标识和威胁防护以及信息保护和合规性。

## <a name="results-of-step-4"></a>步骤 4 的结果

对于 Microsoft 365 租户的迁移，已确定：

- 哪些设备正在运行 Windows 7 或 Windows 8.1 以及计划将其更新到 Windows 10 企业版。
- 哪些设备正在运行 Office 客户端应用以及计划将其更新为 Microsoft 365 企业应用。
- 哪些本地 Office 服务器服务应迁移到其 Microsoft 365 等效服务和迁移服务及其数据的计划。

下面是已完成本地服务器的迁移的租户示例。

![已完成本地服务器的迁移的租户示例](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

在此图中，组织具有：

- 将其本地邮箱Exchange Server Exchange Online。
- 将其本地 SharePoint Server 网站和数据迁移到 Microsoft 365 中的 SharePoint。

## <a name="ongoing-maintenance-for-migration"></a>迁移的正在进行的维护

你可能需要持续：

- 根据 Exchange 邮箱迁移的状态，继续向组织推出到 Exchange Online 的转换。
- 根据本地 SharePoint 网站迁移的状态，继续将迁移到 Microsoft 365 中的 SharePoint 迁移到组织。

## <a name="next-step"></a>后续步骤

[![步骤 5.部署设备和应用管理](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

继续执行 [设备和应用管理，](tenant-management-device-management.md) 以部署设备和应用管理。
