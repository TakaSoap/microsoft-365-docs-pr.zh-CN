---
title: 迁移到 Microsoft 365 企业版
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 逐步完成将 Microsoft Office、Office 服务器和 Windows 的版本迁移到组织中的 Microsoft 365 企业版的过程。
ms.openlocfilehash: 6830b4627eea799e18d32d3f9150617df339d7d4
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011791"
---
# <a name="migration-to-microsoft-365-enterprise"></a>迁移到 Microsoft 365 企业版

大多数企业组织拥有带有多种版本的操作系统、客户端软件和服务器软件的异类环境。Microsoft 365 企业版包含这些 IT 基础结构的关键组件的最安全版本，其中生产功能利用云技术设计。

要最大限度提高集成了产品套件的 Microsoft 365 企业版的业务价值，请开始规划并实施迁移以下版本的策略：

- 计算机上安装的 Office 客户端迁移到 Microsoft 365 企业应用版
- 服务器上安装的 Office 服务器迁移到 Office 365 中的等效服务中
- 设备上 Windows 7 和 Windows 8.1 迁移到 Windows 10 企业版

>[!Note]
>已于 **2020 年 1 月 14 日**结束了对 Windows 7 的支持。 有关详细信息，请单击[此处](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020)。
>

随着时间的推移，完成所有这些迁移使你的组织更接近[新式工作区](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)，这是一种安全且集成的环境，可释放组织中的团队合作精神和创造力，所有这些都由 Microsoft 365 企业版启用和授权。 

有关迁移特定 Office 365 工作负载的用户和数据的信息：

- 从 Exchange Server 到 Exchange Online 的用户邮箱，请参阅 [Exchange Online 工作负载](exchangeonline-workload.md)。
- 从 SharePoint Server 到 SharePoint Online 的 SharePoint 数据，请参阅 [SharePoint Online 工作负载](sharepoint-online-onedrive-workload.md)。
- Microsoft Teams 的 Skype for Business，请参阅 [Microsoft Teams 工作负载](teams-workload.md)。

## <a name="migration-for-microsoft-office-client-products"></a>Microsoft Office 客户端产品迁移

在许多大小组织中，你可能都会使用旧版 Office 客户端产品（如 Word、Excel 和 PowerPoint）的组合。这些旧版本：

- 可以使用最新的安全更新和支持修补程序[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，但该过程有时是手动的，可能无法在整个组织内缩放。
- 未能最佳利用 Microsoft 云技术并帮助你数字化转换业务。
- 不包含新功能。
 
Microsoft 365 企业版包含 Microsoft 365 企业应用版，这是 Office 客户端产品的一个版本，可与 Microsoft 365 企业版许可证一起使用，并从 Microsoft 云j进行安装和更新。 Microsoft 365 企业应用版包括安全更新和最新功能。 有关详细信息，请参阅[关于 Microsoft 365 企业应用版](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)。

### <a name="office-2007"></a>Office 2007

对于 Office 2007 版本中的 Office 版本，停止提供支持时间已过。有关详细信息，请参阅 [Office 2007 停止提供支持路线图](https://docs.microsoft.com/deployoffice/office-2007-end-support-roadmap)。

与其通过 Office 2010、Office 2013 或 Office 2016 升级运行 Office 2007 的计算机，不如考虑：

1. 为用户获取并分配 Microsoft 365 许可证。
2. 卸载其计算机中的 Office 2007。
3. 单独安装或联合 IT 推出的内容一起安装 Microsoft 365 企业应用版。 有关详细信息，请参阅[阶段 4：Microsoft 365 企业应用版](office365proplus-infrastructure.md)。

Microsoft 365 企业应用版会自动安装更新，并可利用基于云的服务来提高安全性和生产效率。

### <a name="office-2010"></a>Office 2010

对于 Office 2010 版本中的 Office 版本，将于 **2020 年 10 月 13 日**停止提供支持。 有关详细信息，请参阅 [Office 2010 的停止提供支持路线图](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)。

与其通过 Office 2013 或 Office 2016 升级运行 Office 2010 的计算机（两种方式均必须手动更新），不如考虑： 

1. 为用户获取并分配 Microsoft 365 许可证。
2. 卸载其计算机中的 Office 2010。
3. 单独安装或联合 IT 推出的内容一起安装 Microsoft 365 企业应用版。 有关详细信息，请参阅[阶段 4：Microsoft 365 企业应用版](office365proplus-infrastructure.md)。

Microsoft 365 企业应用版会自动安装安全更新和新功能更新，并可利用 Microsoft 365 中基于云的服务来提高安全性和生产效率。

### <a name="office-2013-and-office-2016"></a>Office 2013 和 Office 2016

尚未确定针对 Office 的 Office 2013 和 Office 2016 版本的支持终止路线图。 但是，与 Office 2010 一样，仍然必须[安装安全更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)这些更新可能没法很好地缩放，具体取决于组织的规模。

与其使用 Office 2013 或 Office 2016 最新安全更新保证计算机处于最新状态或者将计算机从 Office 2013 更新到 Office 2016，请考虑执行以下操作：

1. 为用户获取并分配 Microsoft 365 许可证。
2. 卸载其计算机中的 Office 2013 或 Office 2016。
3. 单独安装或联合 IT 推出的内容一起安装 Microsoft 365 企业应用版。 有关详细信息，请参阅[阶段 4：Microsoft 365 企业应用版](office365proplus-infrastructure.md)。

Microsoft 365 企业应用版会自动安装安全更新和新功能更新，并可利用 Microsoft 365 中基于云的服务来提高安全性和生产效率。

## <a name="migration-for-microsoft-office-server-products"></a>Microsoft Office 服务器产品迁移

在许多大小组织中，你可能都会使用旧版 Office 服务器产品（如 Exchange Server 和 SharePoint Server）的组合。这些旧版本：

- 应该更新最新的安全更新并支持修补程序。在某些情况下，这些更新每月发布一次。
- 未能最佳利用 Microsoft 云技术并帮助你数字化转换业务。
- 请勿包含新的生产应用程序，例如 Microsoft Teams。
- 请勿包含最新的安全功能，例如 Exchange 高级威胁防护。

Microsoft 365 企业版包含 Office 365，后者包含 Office 服务基于云的版本，这些版本使用 Web 浏览器和 Outlook 客户端等与 Office 服务器软件本地版本相同的工具。 这些服务持续更新来保障安全性，但无需 IT 操作，从而节省维护和更新本地服务器所耗的时间。 这些服务还包含 Office 服务器软件中当前未提供的新功能增强版。 

### <a name="office-server-2007"></a>Office Server 2007

对于 Office 2007 版本中的服务器产品，停止提供支持时间已过。有关详细信息，请参阅以下文章：

- [Exchange 2007 停止提供支持路线图](https://docs.microsoft.com/office365/enterprise/exchange-2007-end-of-support)
- [SharePoint Server 2007 停止提供支持路线图](https://docs.microsoft.com/office365/enterprise/sharepoint-2007-end-of-support)
- [Project Server 2007 停止提供支持路线图](https://docs.microsoft.com/office365/enterprise/project-server-2007-end-of-support)
- [Office Communications Server 停止提供支持路线图](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/upgrade)
- [PerformancePoint Server 2007 停止提供支持路线图](https://docs.microsoft.com/office365/enterprise/pps-2007-end-of-support)

与其通过 Office 2010、Office 2013 或 Office 2016 版本中的服务器产品升级 Office 2007 版本中的服务器产品，不如考虑：

1. 将 Office 2007 服务器上的数据迁移到 Office 365。为顺利完成此操作，请聘用 Microsoft 合作伙伴。
2. 向用户推出新功能和工作流程。
3. 如果不再需要运行 Office 2007 服务器产品的本地服务器，请将其停用。

### <a name="office-server-2010"></a>Office Server 2010

对 [Exchange Server 2010](https://docs.microsoft.com/office365/enterprise/exchange-2010-end-of-support) 的支持将于 **2020 年 10 月 13 日**结束。

对 [SharePoint Server 2010](https://docs.microsoft.com/office365/enterprise/upgrade-from-sharepoint-2010) 的支持将于 **2021 年 4 月 13 日**结束。

与其通过 Office 2013 或 Office 2016 版本中的服务器产品升级 Office 2010 版本中的服务器产品，不如考虑：

1. 将 Office 2010 服务器上的数据迁移到 Microsoft 365。 有关此方面的帮助，请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或雇用 Microsoft 合作伙伴。
2. 向用户推出新功能和工作流程。
3. 如果不再需要运行 Office 2010 服务器产品的本地服务器，请将其停用。

### <a name="office-server-2013"></a>Office Server 2013

对于 Office 2013 版本中的服务器产品，停止提供支持的时间尚未确定。与其通过 Office 2016 版本中的服务器产品升级 Office 2013 版本中的服务器产品，不如考虑：

1. 将 Office 2013 服务器上的数据迁移到 Office 365。为顺利完成此操作，请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或聘用 Microsoft 合作伙伴。
2. 向用户推出新功能和工作流程。
3. 如果不再需要运行 Office 2013 服务器产品的本地服务器，请将其停用。

### <a name="office-server-2016"></a>Office Server 2016

对于 Office 2016 版本中的服务器产品，停止提供支持的时间尚未确定。要利用基于云的服务和增强功能对业务进行数字化转型，请考虑：

1. 将 Office 2016 服务器上的数据迁移到 Office 365。为顺利完成此操作，请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或聘用 Microsoft 合作伙伴。
2. 向用户推出新功能和工作流程。
3. 如果不再需要运行 Office 2016 服务器产品的本地服务器，请将其停用。

## <a name="migration-for-microsoft-windows-7-and-81"></a>Microsoft Windows 7 和 8.1 迁移

已于 **2020 年 1 月 14 日**结束了对 Windows 7 的支持。 要迁移运行 Windows 7 或 Windows 8.1 的设备，可以执行[就地升级](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)。 

有关其他方法，请参阅 [Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。 也可以自行[计划 Windows 10 部署](https://aka.ms/planforwin10deployment)。

## <a name="summary-of-options-for-office-2010-clients-and-servers-and-windows-7"></a>Office 2010 客户端和服务器及 Windows 7 的选项摘要

有关这些产品的升级、迁移和移动到云选项的直观摘要，请参阅[停止提供支持海报](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)。

[![终止对 Office 2010 客户端和服务器及 Windows 7 的支持海报图像](../media/migration-microsoft-365-enterprise-workload/office2010-windows7-end-of-support.png)](../media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)

此海报包含一页内容，可借助它快速了解用于避免 Office 2010 客户端和服务器产品及 Windows 7 支持终止的各种方式，突出显示了 Microsoft 365 企业版中的首选方式及产生的目标支持。

可以[下载此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf)并按 letter、legal 或 tabloid (11 x 17) 格式打印。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

了解 Microsoft 的 IT 专家如何使用以下这些资源将公司迁移到 Microsoft 365 企业版： 

- [部署和更新 Microsoft 的 Microsoft 365 企业应用版](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft 将 150,000 个邮箱迁移到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [将 SharePoint 迁移到云：了解 Microsoft 如何运行自己的迁移](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [在 Microsoft 中将 Windows 10 部署为就地升级](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Windows 10 部署：来自 Microsoft IT 部门的提示和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)（视频）

## <a name="transition-your-entire-organization"></a>转换整个组织

要更好地了解如何将整个组织转移到 Microsoft 365 企业版中的产品和服务，参见[转换海报](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)。

[![转移到 Microsoft 365 海报图像](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.png)](../media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)

此海报包含两页内容，可借助它快速盘点现有基础结构并获取有关转移到 Microsoft 365 企业版中相应产品或服务的指南。 它包含 Windows 和 Office 产品，还涵盖了设备管理、标识及信息和威胁防护等其他基础结构和安全元素。

可以[下载此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-microsoft-365-enterprise/transition-org-to-m365.pdf)并按 letter、legal 或 tabloid (11 x 17) 格式打印。

## <a name="result"></a>结果

你的组织已将 Microsoft Office、Office 服务器和 Windows 的早期版本迁移到 Microsoft 365 企业版。
