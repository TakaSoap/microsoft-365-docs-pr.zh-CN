---
title: 步骤 4. 企业租户Microsoft 365迁移
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 为 Windows 租户Windows迁移 Office 设备、Office客户端应用Microsoft 365服务器。
ms.openlocfilehash: 1892ae3da900f1c940866a2b2a3c70c1d6cb5db3
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524245"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>步骤 4. 企业租户Microsoft 365迁移

大多数企业组织具有异类环境，其中包括操作系统、客户端软件和服务器软件的多个版本。 Microsoft 365企业版包括 IT 基础结构的关键组件的最安全版本。 它还包括旨在利用云技术的生产力功能。

若要最大化企业集成产品套件Microsoft 365业务价值，请开始规划和实施迁移这些版本的策略：

| 发件人 | To |
|:-------|:-----|
| Windows 7 和 Windows 8.1 | Windows 10 企业版 |
| Office工作人员设备上安装的客户端产品 | Microsoft 365 企业应用版 |
| Office本地服务器上安装的服务器产品 | 它们相同的基于云的服务Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>迁移到Windows 10

企业Microsoft 365的每个许可证都包括一个Windows 10 企业版。 若要迁移运行 Windows 7 或 Windows 8.1 的设备，可以执行就地升级。 *2020 年 1* Windows 7 日结束支持。 

有关在就地升级Windows 10 企业版其他安装方法，请参阅Windows 10[部署方案](/windows/deployment/windows-10-deployment-scenarios)。 也可以自行[计划 Windows 10 部署](/windows/deployment/planning/)。

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>迁移到Microsoft 365 企业应用版

Microsoft 365企业版包括 Microsoft 365 企业应用版、从 Microsoft 云安装并更新的 Office 客户端产品 (Word、PowerPoint、Excel 和 Outlook) 。 有关详细信息，请参阅关于[Microsoft 365 企业应用版](/deployoffice/about-microsoft-365-apps)。

不要使计算机在 Office 2019 或较旧版本中保持最新，请执行以下步骤：

1. 获取并分配Microsoft 365许可证。
2. 卸载Office 2013 或 Office 2016。
3. 在Microsoft 365 企业应用版 IT 部署期间单独安装或安装。 有关详细信息，请参阅 [Microsoft 365 应用版部署指南](/deployoffice/deployment-guide-microsoft-365-apps)。

Microsoft 365 企业应用版可自动安装安全更新和新功能更新，并可以利用 Microsoft 365 中的基于云的服务，从而增强安全性和工作效率。

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>将本地服务器和数据迁移到Microsoft 365

Microsoft 365 企业版包括基于云的 Office 服务器服务版本，这些服务使用与本地版本的 Office 服务器软件（如 Web 浏览器和 Outlook 客户端）相同的工具。 这些基于云的服务会针对安全性和新功能自动更新。 迁移后，IT 部门可以节省维护和更新本地服务器所花的时间。

使用以下资源获取有关迁移特定应用程序工作负载的用户Microsoft 365数据：

- [将邮箱从内部部署Exchange Server移动到Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [将SharePoint数据从 SharePoint Server 迁移到 SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [将 Skype for Business Online 迁移到 Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>转换整个组织

若要更好地了解如何将整个组织移动到 Microsoft 365 企业版中的产品和服务，请下载此转换海报：

[![显示"转换到Microsoft 365的图像。](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

通过这份两页的海报可以快速清点现有基础结构。 使用它获取有关移动到适用于企业的 Microsoft 365 的指南。 它显示了Windows和Office以及其他基础结构和安全元素（如设备管理、标识和威胁防护以及信息保护和合规性）的信息。

## <a name="results-of-step-4"></a>步骤 4 的结果

对于迁移租户Microsoft 365，已确定：

- 哪些设备在 Windows 7 或 Windows 8.1 以及计划将其更新为 Windows 10 企业版。
- 哪些设备在运行 Office 客户端应用，以及计划将它们更新为Microsoft 365企业应用。
- 哪些本地Office服务器服务应迁移到其Microsoft 365迁移服务及其数据的计划。

下面是一个租户示例，该租户已完成本地服务器的迁移。

![已完成本地服务器的迁移的租户示例。](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

在此图中，组织具有：

- 将其本地邮箱Exchange Server到Exchange Online。
- 将其本地 SharePoint Server 网站和数据迁移到 SharePoint Microsoft 365。

## <a name="ongoing-maintenance-for-migration"></a>正在进行的迁移维护

您可能需要持续：

- 根据您的邮箱迁移Exchange，继续向组织Exchange Online转换。
- 根据本地部署迁移SharePoint，继续向组织SharePoint Microsoft 365迁移。

## <a name="next-step"></a>后续步骤

[![步骤 5.部署设备和应用管理。](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

继续执行 [设备和应用管理，](tenant-management-device-management.md) 以部署设备和应用管理。