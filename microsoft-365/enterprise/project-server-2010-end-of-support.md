---
title: Project Server 2010 终止支持路线图
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Project Server 2010 的支持结束时间在2021年4月13日结束。 将本文作为升级到 Project Online 或本地 Project Server 的更新版本的指南。
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519698"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 支持终止路线图

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

Project Server 2010 将于 **2021 年4月13日** 到达支持结束。 此日期已从上一年10月13日的支持结束日期扩展2020。 如果你当前使用的是 Project Server 2010，请注意，这些相关产品的支持截止日期如下：

|产品 |支持结束日期|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 专业版|2020 年 10 月 13 日|

有关到达支持终止的详细信息，请参阅 [从 Office 2010 服务器和客户端产品升级](plan-upgrade-previous-versions-office.md)。

## <a name="what-does-end-of-support-mean"></a>*支持终止的* 含义是什么？

几乎所有 Microsoft 产品都有支持生命周期，在此期间，它们将获取新功能、缺陷修补程序和安全更新。 此生命周期通常是从产品的初始版本中持续10年的时间。 此生命周期的结束被称为产品的支持终止。 在 Project Server 2010 在2021年4月13日到达其支持结束后，Microsoft 将不再提供：

- 可能出现的问题的技术支持。

- 针对所发现的问题的 Bug 修复，并且可能会影响服务器的稳定性和可用性。

- 针对发现的漏洞的安全修补程序，并且可能会使服务器容易受到安全破坏。

- 时区更新。

在此日期之后，Project Server 2010 的安装将继续运行。 但是，由于前面列出了所做的更改，因此强烈建议您尽快从 Project Server 2010 迁移。

## <a name="what-are-my-options"></a>我的选项是什么？

您的迁移选项为：

- 迁移到 Project Online

- 迁移到 Project Server 的更新的本地版本 (最好的 Project Server 2019) 

若要避免停止对 Project Server 2010 的支持，可以采用以下两种途径。

![Project Server 2010 升级路径](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|为什么我更喜欢迁移到 Project Server 2019？|为什么我更愿意迁移到 Project Online？|
|---|---|
|业务规则限制我在云中运行我的业务。  <br/><br/>  我需要控制环境的更新。|我有移动或远程用户。<br/><br/>  迁移本地服务器所需的成本是一个重要的问题 (硬件、软件、实现的时间和工作，等等。 ) 。 <br/><br/>  迁移后，维护我的环境所需的成本是一个需要考虑的事项 (例如，自动更新、保证的正常运行时间等) 。|

> [!NOTE]
> 有关迁移选项的详细信息，请参阅可 [帮助您从 Office 2010 服务器和客户端进行升级的资源](upgrade-from-office-2010-servers-and-products.md)。 请注意，Project Server 不支持混合配置，因为 Project Server 和 Project Online 无法共享同一个资源池。

### <a name="what-are-my-options-for-project-client"></a>我的 Project 客户端选项是什么？

如果您使用的是 Project Professional 2010 或 Project Standard 2010，则可以选择以下选项：

- 移动到较新版本的 Project Professional 或 Project Standard
- 移动到联机解决方案，例如 Project Online 或 web 项目

#### <a name="move-to-a-newer-version-of-project-client"></a>移动到 Project 客户端的较新版本

如果是从 Project Standard 2010 迁移，您可以转到项目标准的较新版本， (Project Standard 2016 or Project Standard 2019) 。 我们建议您转到最新版本，以利用最新的功能。 迁移到不到最新版本 (项目标准 2016) 也意味着您需要更快地再次迁移。

同样，如果是从 Project Professional 2010 迁移，您可以转到较新版本 (Project Professional 2019 或 Project Professional 2016) 。 如果可能，请再次移动到最新版本。 如果您使用 Project Professional 连接到 Project Server，请确保迁移到与您使用的 Project Server 版本相连接的 Project Professional 版本。

Project Professional 2010 用户还可以迁移到 Project Online 桌面客户端，这是一种基于订阅的 Project Professional 2019 版本。 它包含在项目计划3和项目计划5订阅中。

#### <a name="move-to-an-online-solution"></a>移动到联机解决方案

您还可以从 Project Professional 2010 或 Project Standard 2010 迁移到基于项目订阅的联机解决方案。 Project Plan 3 和 Plan 5 都包括 Project Online 和最新的云服务，即 [web 的项目](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)。 两者都提供了值得研究的新功能和好处。

有关功能和许可证的详细信息，请参阅 [Microsoft Project service description](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)。

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>从 Project Server 2010 迁移的重要注意事项

当您计划从 Project Server 2010 迁移时，请考虑以下事项：

- **从 Microsoft 解决方案提供商获取帮助** -从 Project Server 2010 升级可能是一项挑战。 它需要进行大量准备和规划。 如果您不是最初设置 Project Server 2010 的人，则可能尤其有挑战性。 Microsoft 解决方案提供商可用于帮助，无论您计划迁移到 Project Server 2019 还是 Project Online。 在 [Microsoft 解决方案提供商中心](https://go.microsoft.com/fwlink/p/?linkid=841249)搜索解决方案提供商。

- 在 Project Server 2010 环境中 **规划自定义** 项-自定义项在迁移到 Project server 2019 或 project Online 时可能不起作用。 在不同版本的 Project Server 体系结构中有很大差异。 此外，使用这些版本的所需操作系统、数据库服务器和 web 浏览器也有所不同。 规划如何在新环境中测试或重建自定义项。 利用此机会确定是否仍需要特定的自定义项。 有关详细信息，请参阅[Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)。

- **时间和耐心** 升级规划、执行和测试需要相当长的时间和精力，尤其是在升级到 Project Server 2019 时。 如果要从 Project Server 2010 迁移到 Project Server 2019，则必须先迁移到 Project Server 2013，检查数据，然后迁移到 Project Server 2016，然后再迁移到 project server 2019。 您可能需要与 Microsoft 解决方案提供商联系以获取时间范围和估计成本以供他们协助。

## <a name="migrate-to-project-online"></a>迁移到 Project Online

如果选择从 Project Server 2010 迁移到 Project Online，则可以按照以下步骤手动迁移项目计划数据：

1. 将项目计划从 Project Server 2010 保存到. mpp 格式。

2. 使用 Project Professional 2016、Project Professional 2019 或 Project Online 桌面客户端，打开每个 mpp 文件，然后将其保存并发布到 Project Online。

您可以在 Project Online 中手动创建 PWA 配置 (例如，重新创建任何所需的自定义字段或企业日历) 。 Microsoft 解决方案提供商还可以帮助此过程。

主要资源：

|资源|说明|
|---|---|
|[Project Online 入门](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|如何设置和使用 Project Online|
|[Project Online 服务说明](https://go.microsoft.com/fwlink/p/?linkid=829088)|有关可用的不同 Project Online 计划的信息|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>迁移到 Project Server 的更新的本地版本

我们强烈认为，通过迁移到 Project Online，你可以获得最佳价值和用户体验。 但我们还了解一些组织需要将项目数据保留在本地。 如果选择将您的项目数据保留在本地，则可以将 Project Server 2010 环境迁移到 Project Server 2013、Project Server 2016 或 Project Server 2019。

如果无法迁移到 Project Online，我们建议您迁移到 Project Server 2019。 Project Server 2019 包含早期版本的 Project Server 中的大部分主要功能。 而且，它与 Project Online 中可用的体验最为匹配，但某些功能仅在 Project Online 中可用。

完成每个迁移后，请确保数据已成功迁移。

> [!NOTE]
> 如果您仅限于使用本地解决方案且仅考虑迁移到 Project Server 2013，请注意此版本仅有几年的支持剩余。 Project Server 2013 Service Pack 2 年10月13日的支持日期的结束日期为2023。 有关支持终止日期的详细信息，请参阅 [Microsoft 产品生命周期策略](https://go.microsoft.com/fwlink/p/?linkid=842066)。

### <a name="how-do-i-migrate-to-project-server-2019"></a>如何迁移到 Project Server 2019？

Project Server 2010 与 Project Server 2019 之间的体系结构差异阻止了直接迁移路径。 因此，您需要将 Project Server 2010 数据迁移到 Project Server 的每个后续版本，直到达到 Project Server 2019。 将 Project Server 2010 升级到 Project Server 2019 的步骤：

1. 迁移到 Project Server 2013。

2. 从 Project for 2013 to Project Server 2016 进行迁移。

3. 从 Project Server 2016 迁移到 Project Server 2019。

完成每个迁移后，请确保数据已成功迁移。

### <a name="step-1-migrate-to-project-server-2013"></a>步骤1：迁移到 Project Server 2013

有关从 Project Server 2010 升级到 Project Server 2013 的详细信息，请参阅 [Upgrade To Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)。

主要资源：

- [Project Server 2013 升级过程概述](https://go.microsoft.com/fwlink/p/?linkid=841822)

  了解如何从 Project Server 2010 升级到 Project Server 2013 的高级别概述。
- [计划升级到 Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841823)

  查看从 Project Server 2010 升级到 Project Server 2013 （包括系统要求）时的规划注意事项。

- [Project Server 2013 中的新增功能升级](https://go.microsoft.com/fwlink/p/?linkid=841824) 涵盖了此版本的重要更改，包括：

   - 没有到 Project Server 2013 的就地升级。 数据库附加方法是从 Project Server 2010 升级到 Project Server 2013 的唯一受支持的方法。

   - 升级过程不仅会将 Project Server 2010 数据转换为 Project Server 2013 格式，还会将四个 Project Server 2010 数据库合并到一个 Project Web App 数据库中。

   - SharePoint Server 2013 和 Project Server 2013 都更改为以前版本中基于声明的身份验证。 如果使用的是经典身份验证，则在升级时需要考虑这一点。 有关详细信息，请参阅[在 SharePoint 2013 中从经典模式身份验证迁移到基于声明的身份验证]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)。

主要资源：

- [升级到 Project Server 2013 的流程概述](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [升级数据库和 Project Web App 网站集 (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Microsoft Project Server 升级过程关系图](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [在8个简单的步骤中执行大量数据库整合（Project Server 2010 至2013迁移）](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>步骤2：迁移到 Project Server 2016

在迁移到 Project Server 2013 并验证数据是否已成功迁移之后，下一步是迁移到 Project Server 2016。

有关详细信息，请参阅 [Upgrade To Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。

主要资源：

- [Project Server 2016 升级流程概述](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  了解从 Project Server 2013 升级到 Project Server 2016 时需要执行的操作。

- [规划升级到 Project Server 2016](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  请查看从 Project Server 2013 升级到 Project Server 2016 时的规划注意事项。

[有关 Project Server 2016 升级的详细](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) 信息，请参阅升级到此版本需要了解的重要更改，其中包括以下内容：

- 当您创建 Project Server 2016 环境时，请注意，Project Server 2016 安装文件包含在 SharePoint Server 2016 中。 有关详细信息，请参阅 [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)。

- 资源计划在 Project Server 2016 中已被弃用。 您的 Project Server 2013 资源计划将迁移到 Project Server 2016 和 Project Online 中的资源预订。 有关详细信息，请参阅 [概述：资源预订](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 。

### <a name="step-3-migrate-to-project-server-2019"></a>步骤3：迁移到 Project Server 2019

迁移到 Project Server 2016 并验证数据是否成功迁移之后，下一步是将数据迁移到 Project Server 2019。

若要了解从 Project Server 2016 升级到 Project Server 2019 时需要执行的操作，请参阅 [upgrade To Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)。

主要资源：

- [Project Server 2019 升级过程概述](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  了解从 Project Server 2013 升级到 Project Server 2016 时需要执行的操作的简要概述。

- [规划升级到 Project Server 2019](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  查看从 Project Server 2016 升级到 Project Server 2019 时的规划注意事项。

- [您需要了解的有关 Project Server 2019 升级的事项](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>了解升级到此版本的重要更改，其中包括：

   - 升级过程会将您的数据从 Project Server 2016 数据库迁移到 SharePoint Server 2019 内容数据库。  Project Server 2019 将不再在 SharePoint Server 服务器场中创建自己的 Project Server 数据库。

   - 升级后，请注意 Project Web App 中的几项更改。  有关详细信息，请参阅 [Project Server 2019 中的新增功能](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。

**其他资源**：

- [Project Online 服务说明](https://go.microsoft.com/fwlink/p/?linkid=841280)：请参阅 project Server 2016 附带的项目组合管理功能和 Project Online 高级版。

- [Microsoft Office Project 项目组合服务器2010迁移指南](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 客户端和服务器以及 Windows 7 的选项的摘要

有关 Office 2010 客户端和服务器以及 Windows 7 的升级、迁移和移动到云选项的直观摘要，请参阅[终止支持海报](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![对 Office 2010 客户端和服务器和 Windows 7 海报的支持结束](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

此海报说明了您可以采取的各种途径以避免在 Microsoft 365 企业版中突出显示了对 Office 2010 客户端和服务器产品和 Windows 7 的结束支持，并在 Microsoft 企业版中突出显示了首选路径和选项

您还可以 [下载](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 此海报并在信件、法律或 tabloid (11 x 17) 格式打印它。

## <a name="related-topics"></a>相关主题

[升级自 SharePoint 2010](upgrade-from-sharepoint-2010.md)

[从 Office 2010 服务器和客户端进行升级](upgrade-from-office-2010-servers-and-products.md)
