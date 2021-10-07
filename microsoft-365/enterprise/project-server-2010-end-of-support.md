---
title: ProjectServer 2010 停止提供支持路线图
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: 对 Server 2010 的支持Project 2010 年 4 月 13 日结束。 使用本文作为指南升级到本地 Project Online或更高版本的 Project Server。
ms.openlocfilehash: 9d04df22af0a0614270907f4ad4026324b026211
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213321"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 支持终止路线图

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

ProjectServer 2010 将于 **2021** 年 4 月 13 日停止提供支持。 此日期自上一个支持结束日期 2020 年 10 月 13 日起延长。 如果当前正在使用 Project Server 2010，请注意，这些相关产品具有以下停止提供支持的日期：

|产品 |支持结束日期|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 Professional|2020 年 10 月 13 日|

有关停止提供支持的信息，请参阅从 Office [2010 服务器和客户端产品升级](plan-upgrade-previous-versions-office.md)。

## <a name="what-does-end-of-support-mean"></a>停止 *提供支持意味着什么* ？

几乎所有 Microsoft 产品都有一个支持生命周期，在此期间它们获取新功能、Bug 修复和安全更新。 此生命周期通常自产品初始发布起持续 10 年。 此生命周期的结束称为产品的停止支持。 在 Project Server 2010 于 2021 年 4 月 13 日停止提供支持后，Microsoft 将不再提供：

- 针对可能会出现的问题的技术支持。

- 发现并可能会影响服务器稳定性和可用性的问题的错误修复。

- 已发现且可能导致服务器易受安全漏洞攻击的漏洞的安全修复。

- 时区更新。

安装 Project Server 2010 将在此日期之后继续运行。 但是，由于前面列出的更改，我们强烈建议您尽快从 Project Server 2010 迁移。

## <a name="what-are-my-options"></a>我的选项是什么？

迁移选项包括：

- 迁移到Project Online

- 迁移到较新的本地版本的 Project Server (最好是 Project Server 2019) 

下面是避免停止对 Project Server 2010 提供支持的两种途径。

![ProjectServer 2010 升级路径。](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|为什么我想要迁移到 Project Server 2019？|为什么我想要迁移到Project Online？|
|---|---|
|业务规则限制我在云中运营业务。  <br/><br/>  我需要控制环境更新。|我拥有移动或远程用户。<br/><br/>  迁移内部部署服务器的成本是硬件、 (、实现时间和工作量等方面的重要) 。 <br/><br/>  迁移后，维护环境的成本是一个 (，例如自动更新、保证正常运行时间等) 。|

> [!NOTE]
> 有关迁移选项的详细信息，请参阅帮助您从[Office 2010 服务器和客户端升级的资源](upgrade-from-office-2010-servers-and-products.md)。 请注意，Project Server 不支持混合配置，因为 Project Server 和 Project Online 无法共享同一资源库。

### <a name="what-are-my-options-for-project-client"></a>我的客户端选项Project是什么？

如果你使用的是 2010 Project Professional 2010 Project Standard 2010，你的选项是：

- 移动到更高版本的 Project Professional 或 Project Standard
- 移动到联机解决方案，例如Project Online或Project网页版

#### <a name="move-to-a-newer-version-of-project-client"></a>移动到较新版本的 Project 客户端

如果要从 Project Standard 2010 进行迁移，可以迁移到较新版本的 Project Standard (Project Standard 2016 或 Project Standard 2019) 。 我们建议你移动到最新版本，以利用最新功能。 迁移到不太最新的版本 (Project Standard 2016) 也意味着你需要更快重新迁移。

同样，如果要从 2010 Project Professional迁移，可以迁移到 2019 或 (Project Professional 版本Project Professional 2016) 。 同样，如果可能，请移动到最新版本。 如果使用 Project Professional 连接到 Project Server，请确保迁移到与使用的 Project Server 版本连接的 Project Professional 版本。

Project Professional 2010 用户还可以迁移到 Project Online 桌面客户端，这是 Project Professional 2019 的基于订阅的版本。 它包含在订阅Project 计划 3 Project 计划 5订阅中。

#### <a name="move-to-an-online-solution"></a>移动到联机解决方案

还可以从 2010 Project Professional 2010 Project Standard迁移到基于订阅Project的解决方案。 Project 计划 3计划 5 Project Online和最新的云产品/服务Project[适用于 Web。](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1) 这两者都提供了值得探究的新功能和优点。

有关功能和许可证详细信息，请参阅Microsoft Project[服务说明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)。

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>从 Project Server 2010 迁移的重要注意事项

在计划从 Project Server 2010 迁移时，请考虑以下事项：

- **从 Microsoft 解决方案提供商获取帮助**- 从 Project Server 2010 进行升级可能是一个挑战。 这需要做很多准备和规划。 如果您不是最初在 Server 2010 中设置Project可能会特别具有挑战性。 无论你计划迁移到 Project Server 2019 还是迁移到 Project Online，Microsoft 解决方案提供商都Project Online。 在 Microsoft 解决方案提供商中心 [中搜索解决方案提供商](https://go.microsoft.com/fwlink/p/?linkid=841249)。

- **规划自定义项**- 迁移到 Project Server 2019 或 Project Online 时，Project Server 2010 环境中自定义项Project Online。 版本之间的服务器Project存在显著差异。 此外，使用这些版本的所需操作系统、数据库服务器和 Web 浏览器也有所不同。 制定如何在新环境中测试或重新生成自定义项的计划。 利用此机会确定是否仍然需要特定的自定义项。 有关详细信息，请参阅[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)。

- **时间和耐心**- 升级规划、执行和测试需要大量时间和精力，尤其是升级到 Project Server 2019。 如果要从 Project Server 2010 迁移到 Project Server 2019，必须先迁移到 Project Server 2013，检查数据，然后迁移到 Project Server 2016，然后再迁移到 Project Server 2019。 您可能需要与 Microsoft 解决方案提供商联系，了解一个时间范围及其协助的估计成本。

## <a name="migrate-to-project-online"></a>迁移到Project Online

如果您选择从 Project Server 2010 迁移到 Project Online，可以按照以下步骤手动迁移项目计划数据：

1. 将项目计划从 Project Server 2010 保存为 .mpp 格式。

2. 使用 Project Professional 2016、Project Professional 2019 或 Project Online 桌面客户端，打开每个 .mpp 文件，然后保存该文件并将其发布到Project Online。

例如，您可以在 PWA中手动创建Project Online (配置，例如，重新创建任何所需的自定义域或企业日历) 。 Microsoft 解决方案提供商也可以帮助完成此过程。

关键资源：

|资源|说明|
|---|---|
|[Project Online 入门](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|如何设置和使用Project Online|
|[Project Online 服务说明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|有关可用的不同Project Online的信息|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>迁移到较新的本地版本的 Project Server

我们强烈建议您迁移到新用户，以获得最佳价值和Project Online。 但我们还了解一些组织需要将项目数据保留在本地。 如果您选择将项目数据保留在本地，您可以将 Project Server 2010 环境迁移到 Project Server 2013、Project Server 2016 或 Project Server 2019。

如果您无法迁移到 Project Online，建议您迁移到 Project Server 2019。 ProjectServer 2019 包括早期版本的 Project Server 中的大部分关键功能。 此外，它还最符合 Project Online 提供的体验，尽管某些功能仅在 Project Online。

完成每个迁移后，请确保数据已成功迁移。

> [!NOTE]
> 如果您仅限于本地解决方案，并考虑仅迁移到 Project Server 2013，请注意，此版本仅还有几年的支持。 2023 年 10 月 13 Project Server 2013 Service Pack 2 的支持结束日期。 有关停止提供支持日期的信息，请参阅 [Microsoft 产品生命周期策略](/lifecycle/)。

### <a name="how-do-i-migrate-to-project-server-2019"></a>如何迁移到 Project Server 2019？

Project Server 2010 和 Project Server 2019 之间的体系结构差异会阻止直接迁移路径。 因此，您需要将 Project Server 2010 数据迁移到每个连续版本的 Project Server，直到到达 Project Server 2019。 将 Project Server 2010 升级到 Project Server 2019 的步骤：

1. 迁移到 Project Server 2013。

2. 从 Project Serve 2013 迁移到 Project Server 2016。

3. 从 Project Server 2016 迁移到 Project Server 2019。

完成每个迁移后，请确保数据已成功迁移。

### <a name="step-1-migrate-to-project-server-2013"></a>步骤 1：迁移到 Project Server 2013

有关从 Project Server 2010 升级到 Project Server 2013 的综合信息，请参阅[Upgrade to Project Server 2013。](/project/upgrade-to-project-server-2016)

关键资源：

- [Project Server 2013 升级过程概述](/project/upgrade-to-project-server-2016)

  获取从 Project Server 2010 升级到 Project Server 2013 的简要概述。
- [计划升级到 Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  了解从 Project Server 2010 升级到 Project Server 2013 时的计划注意事项，包括系统要求。

- [Project Server 2013](/project/what-s-new-in-project-server-2013-upgrade)升级的新增功能涵盖了此版本的重要更改，包括：

  - 没有到 Project Server 2013 的就地升级。 数据库附加方法是从 Project Server 2010 升级到 Project Server 2013 的唯一受支持方法。

  - 升级过程不仅会将 Project Server 2010 数据转换为 Project Server 2013 格式，而且还会将四个 Project Server 2010 数据库合并为一个 Project Web App 数据库。

  - 与SharePoint版本相比，Project Server 2013 和 Project Server 2013 均更改为基于声明的身份验证。 如果使用的是经典身份验证，则需要在升级时考虑这一点。 有关详细信息，请参阅[在 SharePoint 2013 中从经典模式身份验证迁移到基于声明的身份验证](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)。

关键资源：

- [升级到 Project Server 2013 的流程概述](/project/overview-of-the-project-server-2016-upgrade-process)

- [升级数据库和 Project Web App 网站集 (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project服务器升级过程图](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [从 Server 2010 Project 2013 迁移到 8 个简单步骤的出色的数据库合并](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>步骤 2：迁移到Project Server 2016

在迁移到 Project Server 2013 并验证数据已成功迁移后，下一步是迁移到 Project Server 2016。

有关详细信息，请参阅升级到[Project Server 2016](/Project/upgrade-to-project-server-2016)。

关键资源：

- [Project Server 2016 升级流程概述](/Project/overview-of-the-project-server-2016-upgrade-process)

  了解从 Project Server 2013 升级到 Project Server 2016。

- [规划升级到 Project Server 2016](/Project/plan-for-upgrade-to-project-server-2016)

  查看从 Project Server 2013 升级到 Project Server 2016 时要考虑的规划Project Server 2016。

[有关升级的](/project/plan-for-upgrade-to-project-server-2016#thingknow)Project Server 2016包括升级到此版本的重要更改，其中包括：

- 创建环境Project Server 2016时，请注意 Project Server 2016 Server 2016 SharePoint安装文件。 有关详细信息，请参阅部署[Project Server 2016。](/project/deploy-project-server-2016)

- 资源计划在资源计划中Project Server 2016。 你的 Project Server 2013 资源计划将迁移到 Project Server 2016 和 Project Online 中的资源Project Online。 有关详细信息 [，请参阅概述：](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 资源活动。

### <a name="step-3-migrate-to-project-server-2019"></a>步骤 3：迁移到 Project Server 2019

迁移到 Project Server 2016并验证数据已成功迁移后，下一步是将数据迁移到 Project Server 2019。

若要了解从 Project Server 2016 Server 2019 升级到 Project 需要执行哪些操作，请参阅[Upgrade to Project Server 2019。](/Project/upgrade-to-project-server-2016)

关键资源：

- [Project Server 2019 升级过程概述](/project/overview-of-the-project-server-2019-upgrade-process)

  全面了解从 Project Server 2013 升级到 Project Server 2016。

- [规划升级到 Project Server 2019](/project/plan-for-upgrade-to-project-server-2019)

  查看从 Project Server 2016 升级到 Project Server 2019 的规划注意事项。

- [有关 Project Server 2019 升级的需知信息](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>了解升级到此版本的重要更改，其中包括：

  - 升级过程将您的数据从 Project Server 2016 数据库迁移到SharePoint Server 2019数据库。  ProjectServer 2019 将不再在 Project Server 场中创建自己的 SharePoint 服务器数据库。

  - 升级后，请注意升级过程中的几个Project Web App。  有关详细信息，请参阅[What's new in Project Server 2019](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。

**其他资源**：

- [Project Online服务说明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)：请参阅 Project Server 2016 和 Project Online 高级版 中包含的项目组合管理功能。

- [Microsoft Office Project Portfolio Server 2010 迁移指南](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 客户端和服务器以及 Windows 7 的选项摘要

有关 Office 2010 客户端和服务器以及 Windows 7 的升级、迁移和移动到云选项的直观摘要，请参阅[终止支持海报](../downloads/Office2010Windows7EndOfSupport.pdf)。

[![停止支持 Office 2010 客户端和服务器以及 Windows 7 海报。](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

此海报说明了避免停止支持 Office 2010 客户端和服务器产品和 Windows 7 的各种途径，并突出显示了 Microsoft 365 企业版 中的首选路径和选项支持。

您还可以 [下载此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) ，以 11 x 17 格式的信件、 (或) 打印。

## <a name="related-topics"></a>相关主题

[升级自 SharePoint 2010](upgrade-from-sharepoint-2010.md)

[从 Office 2010 服务器和客户端进行升级](upgrade-from-office-2010-servers-and-products.md)
