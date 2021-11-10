---
title: ProjectServer 2013 停止提供支持路线图
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 10/11/2021
audience: ITPro
ms.topic: conceptual
ms.prod: project-server-itpro
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
description: 2023 Project 2013 年 4 月 11 日终止对 Project Server 2013 的支持。 使用本文作为指南升级到本地 Project Online或更高版本的 Project Server。
ms.openlocfilehash: 5a9ae38e819dfdb8f9cc2ca3719dccea2d33fa3e
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889832"
---
# <a name="project-server-2013-end-of-support-roadmap"></a>ProjectServer 2013 停止提供支持路线图

Project服务器 2013 将于 **2023 年 4 月 11 日停止提供支持**。 如果当前使用的是 Project Server 2013，请注意，Project 2013 桌面应用也具有相同的停止支持日期。

## <a name="what-does-end-of-support-mean"></a>停止 *提供支持意味着什么* ？

几乎所有 Microsoft 产品都有一个支持生命周期，在此期间它们获取新功能、Bug 修复和安全更新。 此生命周期通常自产品初始版本起持续 10 年。 此生命周期的结束称为产品的停止支持。 在 Project Server 2013 于 2023 年 4 月 11 日终止支持后，Microsoft 将不再提供：

- 针对可能会出现的问题的技术支持。

- 发现并可能会影响服务器稳定性和可用性的问题的错误修复。

- 已发现且可能导致服务器易受安全漏洞攻击的漏洞的安全修复。

- 时区更新。

您的 Project Server 2013 安装在此日期后将继续运行。 但是，由于前面列出的更改，我们强烈建议您尽快从 Project Server 2013 迁移。

## <a name="what-are-my-options"></a>我的选项是什么？

迁移选项包括：

- 迁移到Project Online

- 迁移到较新的本地版本的 Project Server (最好是 Project Server Subscription Edition) 

|为什么我想要迁移到 Project Server 2019？|为什么我想要迁移到 Project Online？|
|---|---|
|业务规则限制我在云中运营业务。  <br/><br/>  我需要控制环境更新。|我拥有移动或远程用户。<br/><br/>  迁移内部部署服务器的成本是硬件 (、软件、实施时间和工作量等的一个) 。 <br/><br/>  迁移后，维护环境的成本是一 (，例如自动更新、保证正常运行时间等) 。|

> [!NOTE]
> Project服务器不支持混合配置，Project服务器Project Online服务器无法共享同一资源库。

## <a name="important-considerations-for-migrating-from-project-server-2013"></a>从 Project Server 2013 迁移的重要注意事项

当您计划从 Project Server 2013 迁移时，请考虑以下事项：

- **从 Microsoft 解决方案提供商获取帮助**- 从 Project Server 2013 进行升级可能是一个挑战。 这需要做很多准备和规划。 如果您不是最初在 Server 2013 中设置Project特别具有挑战性。 无论你计划迁移到 Project Server Subscription Edition 还是 Project Online，Microsoft 解决方案提供商都Project Online。 在 Microsoft 解决方案提供商中心 [中搜索解决方案提供商](https://go.microsoft.com/fwlink/p/?linkid=841249)。

- **时间和耐心**- 升级规划、执行和测试将投入大量时间和精力，尤其是升级到 Project Server Subscription Edition。 如果要从 Project Server 2013 迁移到 Project Server Subscription Edition，必须先迁移到 Project Server 2016，检查数据，然后Project Server Subscription Edition。 您可能需要与 Microsoft 解决方案提供商联系，了解一个时间范围及其协助的估计成本。

## <a name="migrate-to-project-online"></a>迁移到Project Online

如果您选择从 Project Server 2013 迁移到 Project Online，可以按照以下步骤手动迁移项目计划数据：

1. 将项目计划从 Project Server 2013 保存为 .mpp 格式。

2. 使用 Project Professional 2016、Project Professional 2019 或 Project Online 桌面客户端，打开每个 .mpp 文件，然后保存该文件并将其发布到Project Online。

您可以手动创建PWA配置Project Online (例如，重新创建任何所需的自定义域或企业日历) 。 Microsoft 解决方案提供商也可以帮助完成此过程。

关键资源：

|资源|说明|
|---|---|
|[Project Online 入门](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|如何设置和使用Project Online|
|[Project Online 服务说明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|有关可用的不同Project Online的信息|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>迁移到较新的本地版本的 Project Server

我们强烈建议您迁移到新用户，以获得最佳价值和Project Online。 但我们还了解一些组织需要将项目数据保留在本地。 如果选择将项目数据保留在本地，可以将 Project Server 2013 环境迁移到 Project Server 2016、Project Server 2019 或 Project Server Subscription Edition。

如果您无法迁移到 Project Online，建议您迁移到 Project Server Subscription Edition，其中包含以前版本的 Project Server 中的大多数关键功能。 此外，它还最符合 Project Online 提供的体验，尽管某些功能仅在 Project Online。 要考虑的其他因素包括：

- ProjectServer Subscription Edition 引入了一个持续更新模型，无需未来发布 Project Server 的新主要版本。
- 2026 Project Server 2016 2019 和 2019 都将在 2026 年 7 月 14 日终止支持。 如果迁移到任一版本，则需要规划三年内的另一次升级。 有关详细信息，请参阅 [2016 和 2019](/lifecycle/products/project-server-2016) 的支持 [生命周期页面](/lifecycle/products/project-server-2019)。

完成每个迁移后，请确保数据已成功迁移。

### <a name="how-do-i-migrate-to-project-server-subscription-edition"></a>如何迁移到 Project 订阅版本？

Project Server 2013 和 Project Server Subscription Edition 之间的体系结构差异会阻止直接迁移路径。 因此，您需要首先将 Project Server 2013 数据迁移到 Project Server 2016，然后Project Server Subscription Edition。 

1. 迁移到Project Server 2016。

2. 从 Project Server 2016 迁移到 Project Server Subscription Edition。

完成每个迁移后，请确保数据已成功迁移。

### <a name="step-1-migrate-to-project-server-2016"></a>步骤 1：迁移到Project Server 2016

有关从 Project Server 2013 升级到 Project Server 2016 的全面信息，请参阅升级到[Project Server 2016](/project/upgrade-to-project-server-2016)。

关键资源：

- [升级Project Server 2016](/project/upgrade-to-project-server-2016)概述：大致了解如何从 Project Server 2013 升级到 Project Server 2016。
- [Plan to upgrade to Project Server 2016](/project/plan-for-upgrade-to-project-server-2016)： Look at planning considerations when upgrading from Project Server 2013 to Project Server 2016， including system requirements.
- [升级到 Project Server 2016](/project/upgrading-to-project-server-2016)：请参阅有关升级过程的详细说明。

### <a name="step-2-migrate-to-project-server-subscription-edition"></a>步骤 2：迁移到 Project Server Subscription Edition

在迁移到 Project Server 2016并确认数据已成功迁移后，下一步是迁移到 Project Server Subscription Edition。

有关详细信息，请参阅升级到[Project Server Subscription Edition。](/project/upgrade-project-server-subscription-edition)

关键资源：

- [Project Server Subscription Edition](/project/overview-project-server-subscription-edition-upgrade-process)升级过程概述：了解从 Project Server 2013 升级到 Project Server 2016 需要执行哪些操作。
- [Plan for upgrade to Project Server Subscription Edition](/Project/plan-upgrade-project-server-subscription-edition)： Look at the planning considerations to make when upgrading from Project Server 2013 to Project Server 2016.
- [升级到 Project Server Subscription Edition：](/project/how-to-upgrade-project-server-subscription-edition)请参阅有关升级过程的详细说明。


