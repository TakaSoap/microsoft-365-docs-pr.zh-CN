---
title: 迁移到 Microsoft 365 企业版
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 逐步完成将 Microsoft Office、Office 服务器和 Windows 的版本迁移到组织中的 Microsoft 365 企业版的过程。
ms.openlocfilehash: 8fc0e0b117ef55597efeb139e68b6dbdd03de2db
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865708"
---
# <a name="migration-to-microsoft-365-enterprise"></a>迁移到 Microsoft 365 企业版

大多数企业组织拥有带有多种版本的操作系统、客户端软件和服务器软件的异类环境。Microsoft 365 企业版包含这些 IT 基础结构的关键组件的最安全版本，其中生产功能利用云技术设计。

要最大限度提高集成了产品套件的 Microsoft 365 企业版的业务价值，请开始规划并实施迁移以下版本的策略：

- 安装在计算机上的 Office 客户端迁移到 Office 365 专业增强版
- 安装在服务器上的 Office 服务器迁移到 Office 365 中的等效服务中
- 设备上 Windows 7 和 Windows 8.1 迁移到 Windows 10 企业版

随着时间的推移，完成所有这些迁移使你的组织更接近[新式工作区](https://www.microsoft.com/microsoft-365/blog/2018/04/27/making-it-simpler-with-a-modern-workplace/)，这是一种安全且集成的环境，可释放组织中的团队合作精神和创造力，所有这些都由 Microsoft 365 企业版启用和授权。 

## <a name="migration-for-microsoft-office-client-products"></a>Microsoft Office 客户端产品迁移

在许多大小组织中，你可能都会使用旧版 Office 客户端产品（如 Word、Excel 和 PowerPoint）的组合。这些旧版本：

- 可以使用最新的安全更新和支持修补程序[更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，但该过程有时是手动的，可能无法在整个组织内缩放。
- 未能最佳利用 Microsoft 云技术并帮助你数字化转换业务。
 
Microsoft 365 企业版包含 Office 365 专业增强版，这是 Office 365 客户端产品的一个版本，可与 Microsoft 365 企业版许可证一起使用，并从 Microsoft 云安装和更新。有关详细信息，请参阅[关于企业中的 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)。

### <a name="office-2007"></a>Office 2007

对于 Office 2007 版本中的 Office 版本，停止提供支持时间已过。有关详细信息，请参阅 [Office 2007 停止提供支持路线图](https://support.office.com/article/office-2007-end-of-support-roadmap-416c54d8-823c-4def-bb7a-6a9b14ef2745)。

与其通过 Office 2010、Office 2013 或 Office 2016 升级运行 Office 2007 的计算机，不如考虑：

1. 为用户获取并分配 Microsoft 365 许可证。
2. 卸载其计算机中的 Office 2007。
3. 单独安装 Office 365 专业增强版或在 IT 部署时安装 Office 365 专业增强版。有关详细信息，请参阅[阶段4：Office 365 专业增强版](office365proplus-infrastructure.md)。

Office 365 专业增强版会自动安装更新，并可利用 Office 365 中基于云的服务来提高安全性和生产效率。

### <a name="office-2010"></a>Office 2010

对于 Office 2010 版本中的 Office 版本，停止提供支持时间为 2020 年 10 月 13 日。有关详细信息，请参阅 [Office 2010 停止提供支持路线图](https://support.office.com/article/office-2010-end-of-support-roadmap-2a58999c-4d83-4e67-9fde-bc96d487105e)。

与其通过 Office 2013 或 Office 2016 升级运行 Office 2010 的计算机（两种方式均必须手动更新），不如考虑： 

1. 为用户获取并分配 Microsoft 365 许可证。
2. 卸载其计算机中的 Office 2010。
3. 单独安装 Office 365 专业增强版或在 IT 部署时安装 Office 365 专业增强版。有关详细信息，请参阅[阶段4：Office 365 专业增强版](office365proplus-infrastructure.md)。

Office 365 专业增强版会自动安装更新，并可利用 Office 365 中基于云的服务来提高安全性和生产效率。

### <a name="office-2013-and-office-2016"></a>Office 2013 和 Office 2016

尚未确定 Office 的 Office 2013 和 Office 2016 版本的停止提供支持路线图。但是，与 Office 2010 一样，你仍然必须[安装更新](https://support.office.com/article/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)，根据组织规模，这些更新可能无法很好地缩放。与其不断使用 Office 2013 或 Office 2016 的最新更新来更新计算机或将计算机从 Office 2013 更新到 Office 2016，不如考虑：

1. 为用户获取并分配 Microsoft 365 许可证。
2. 卸载其计算机中的 Office 2013 或 Office 2016。
3. 单独安装 Office 365 专业增强版或在 IT 部署时安装 Office 365 专业增强版。有关详细信息，请参阅[阶段4：Office 365 专业增强版](office365proplus-infrastructure.md)。

Office 365 专业增强版会自动安装更新，并可利用 Office 365 中基于云的服务来提高安全性和生产效率。

## <a name="migration-for-microsoft-office-server-products"></a>Microsoft Office 服务器产品迁移

在许多大小组织中，你可能都会使用旧版 Office 服务器产品（如 Exchange Server 和 SharePoint Server）的组合。这些旧版本：

- 应该更新最新的安全更新并支持修补程序。在某些情况下，这些更新每月发布一次。
- 未能最佳利用 Microsoft 云技术并帮助你数字化转换业务。
- 请勿包含新的生产应用程序，例如 Microsoft Teams。
- 请勿包含最新的安全功能，例如 Exchange 高级威胁防护。

Microsoft 365 企业版包括 Office 365，其中包括基于云的 Office 服务器服务版本，这些版本使用与本地 Office 服务器软件版本（如 Web 浏览器和 Outlook 客 户端）相同的工具。这些服务在不涉及 IT 的情况下不断更新，节省维护和更新本地服务器所需的时间。这些服务还具有 Office 服务器软件中没有的增强功能。 

### <a name="office-server-2007"></a>Office Server 2007

对于 Office 2007 版本中的服务器产品，停止提供支持时间已过。有关详细信息，请参阅以下文章：

- [Exchange 2007 停止提供支持路线图](https://support.office.com/article/exchange-2007-end-of-support-roadmap-c3024358-326b-404e-9fe6-b618e54d977d)
- [SharePoint Server 2007 停止提供支持路线图](https://support.office.com/article/sharepoint-server-2007-end-of-support-roadmap-ba124775-d5c0-4d68-b88d-8458ad4c3717)
- [Project Server 2007 停止提供支持路线图](https://support.office.com/article/project-server-2007-end-of-support-roadmap-d379018f-72b7-4284-b40a-6c23c8ae38fe)
- [Office Communications Server 停止提供支持路线图](https://support.office.com/article/office-communications-server-end-of-support-roadmap-54f3d5ba-bdf9-4b37-a9e8-f1ab452d4f78)
- [PerformancePoint Server 2007 停止提供支持路线图](https://support.office.com/article/performancepoint-server-2007-end-of-support-roadmap-89d9feee-2285-419c-8c14-0f7f583536e0)

与其通过 Office 2010、Office 2013 或 Office 2016 版本中的服务器产品升级 Office 2007 版本中的服务器产品，不如考虑：

1. 将 Office 2007 服务器上的数据迁移到 Office 365。为顺利完成此操作，请聘用 Microsoft 合作伙伴。
2. 向用户推出新功能和工作流程。
3. 如果不再需要运行 Office 2007 服务器产品的本地服务器，请将其停用。

### <a name="office-server-2010"></a>Office Server 2010

对于 Office 2010 版本中的服务器产品，已针对以下内容确定了停止提供支持的时间：

- [Exchange Server 2010](https://support.office.com/article/exchange-2010-end-of-support-roadmap-e150e7b9-c432-4c8d-a0ae-c11847129a7d)
- [SharePoint Server 2010](https://support.office.com/article/upgrading-from-sharepoint-2010-985a357f-6db7-401f-bf7a-1bafdf1f312c)

与其通过 Office 2013 或 Office 2016 版本中的服务器产品升级 Office 2010 版本中的服务器产品，不如考虑：

1. 将 Office 2010 服务器上的数据迁移到 Office 365。为顺利完成此操作，请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) 或聘用 Microsoft 合作伙伴。
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

## <a name="migration-for-microsoft-windows"></a>Microsoft Windows 迁移

要迁移运行 Windows 7 或 Windows 8.1 的设备，可以执行[就地升级](https://docs.microsoft.com/microsoft-365/enterprise/windows10-deploy-inplaceupgrade)。 

有关其他方法，请参阅 [Windows 10 部署方案](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)。你也可以自行规划 [Windows 10 部署](https://aka.ms/planforwin10deployment)。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

了解 Microsoft 的 IT 专家如何使用以下这些资源将公司迁移到 Microsoft 365 企业版： 

- [部署和更新 Microsoft Office 365 专业增强版](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Microsoft 将 150,000 个邮箱迁移到 Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [将 SharePoint 迁移到云：了解 Microsoft 如何运行自己的迁移](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)
- [在 Microsoft 中将 Windows 10 部署为就地升级](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Windows 10 部署：来自 Microsoft IT 部门的提示和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)（视频）

## <a name="result"></a>结果

你的组织已将 Microsoft Office、Office 服务器和 Windows 的早期版本迁移到 Microsoft 365 企业版。
