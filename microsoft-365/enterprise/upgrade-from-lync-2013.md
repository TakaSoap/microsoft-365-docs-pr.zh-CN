---
title: 从 Lync Server 2013 升级
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 查找要从 Lync Server 2013 升级的信息和资源。 支持将于 2023 年 4 月 11 日结束。
ms.openlocfilehash: a770ce6acab4320bc84e920b1c527e9c63e72bbb
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889835"
---
# <a name="upgrading-from-lync-server-2013"></a>从 Lync Server 2013 升级

Microsoft Lync Server 2013 将于 **2023** 年 4 月 11 日停止提供支持。 本文提供的资源可帮助您将现有 Lync Server 部署升级到本地Microsoft Teams Skype for Business部署。

## <a name="what-is-end-of-support"></a>停止 *提供支持的是什么*？

大多数 Microsoft 产品都有一个支持生命周期，在此期间它们获取新功能、Bug 修复、安全修补程序等。 在支持终止日期后，产品不会停止工作，但 Microsoft 不再提供：

- 针对可能会出现的问题的技术支持。

- 对可能会影响服务器稳定性和可用性的问题进行 Bug 修复。

- 针对可能导致服务器易受安全漏洞的漏洞进行安全修复。

- 时区更新。

这意味着不会为产品服务提供进一步的更新、修补程序或修补程序 (包括安全修补程序/修补程序) 。 Microsoft 支持将完全将支持工作转移到更新版本。

## <a name="plan-ahead"></a>提前规划

检查产品生命周期网站上[支持的日期。](/lifecycle/products/lync-server-2013) 请牢记这些日期，规划升级或迁移。 请记住， *产品不会在列出的日期* 停止工作。 但是，由于该日期之后将不再修补安装，因此你需要计划顺利过渡到产品的下一个版本。 下表列出了可用的选项。

|停止提供支持产品|支持|建议|
|---|---|---|
|Lync Server 2013|升级到 Skype for Business Server 2015 或 2019|升级到 Microsoft Teams

## <a name="whats-next"></a>下一步做什么？

我们建议升级到 Microsoft Teams。 Microsoft Teams Lync Server 的功能，将聊天、会议、呼叫、协作、应用集成和文件存储整合在一个界面中。 Teams帮助简化用户完成工作的方式，提高用户满意度并加快业务成果。 我们将不断扩展 Teams 的功能，使你能够以全新的方式进行沟通和协作，打破组织和地域障碍，并提高流程和决策制定的效率。

如果无法升级到 Microsoft Teams，可以升级到 Skype for Business Server 2015 或 2019。 关键规划注意事项是，这两种产品将于 2025 年 10 月 14 日终止支持。 有关详细信息，请参阅以下支持生命周期页面：

- [Skype for Business Server 2015 支持生命周期信息](/lifecycle/products/skype-for-business-server-2015)
- [Skype for Business Server 2019 支持生命周期信息](/lifecycle/products/skype-for-business-server-2019)

### <a name="upgrade-to-microsoft-teams"></a>升级到 Microsoft Teams

我们提供了从本地部署升级到Microsoft Teams部署的详细指导。 首先，我们介绍一些关键技术要求。 你将需要建立混合连接，这将使您能够将用户移动到Teams。 [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 提供设置混合的概述。 即使本文侧重于介绍Skype for Business，所有概念也适用于 Lync Server 2013。 请参阅 [特定于](/SkypeForBusiness/hybrid/plan-hybrid-connectivity#server-version-requirements) Lync Server 2013 的详细信息的服务器版本要求部分。

您还需要确保 Lync Server 2013 部署完全更新。 我们发布了[Lync Server 2013](https://support.microsoft.com/topic/updates-for-lync-server-2013-a2a042ac-79f0-2665-7453-0a541fb25164)的所有最新更新的列表。但是，以下更新是升级到 lync Server 2013 Microsoft Teams：

- [Lync Server 2013 核心组件 2021 年 9 月累积更新 5.0.8308.1149：](https://support.microsoft.com/topic/september-2021-cumulative-update-5-0-8308-1149-for-lync-server-2013-core-components-6755903a-fc9a-44d2-b835-2a6d01f14043)此更新将 Live ID 身份验证替换为 cmdlet 的 OAuth 身份验证协议，该协议用于将本地用户移动到 `Move-CSUser` Microsoft Teams。

尽管 Lync 中的用户体验Microsoft Teams丰富且优于 Lync，但它也截然不同。 因此，你还需要为组织和用户做好准备，以确保快速采用Microsoft Teams。 我们提供了大量可用于准备组织、规划升级到 Teams，以及确保成功推出的信息。 

**我们建议你从 [](/MicrosoftTeams/upgrade-skype-teams)** 我们的 Teams 升级门户开始，在这里可以找到技术信息、培训资源、Ignite 会话的链接、可用的帮助资源、案例研究等。

:::image type="content" source="../media/teams-upgrade-portal.png" alt-text="升级门户Teams屏幕截图":::

### <a name="upgrade-to-skype-for-business-server"></a>升级到 Skype for Business Server

该Skype for Business Server的路径将有所不同，具体取决于您选择升级到的版本。 Skype for Business Server 2015 支持从 Lync Server 2013 进行就地升级。 另一方面，为了升级到 Skype for Business Server 2019，首先需要向 Lync Server 2013 组织引入 Skype for Business Server 2019，然后将操作转移到新服务器。 

要考虑的一个重要点是，每个产品的当前支持阶段：Skype for Business 2019 是主要支持，Skype for Business 2015 目前处于扩展支持状态。  因此，我们建议升级到 Skype for Business Server 2019。 若要了解有关主流支持和扩展支持之间区别的更多信息，请参阅 [固定生命周期策略](/lifecycle/policies/fixed)。

有关每个升级方案的详细信息，请参阅以下资源。

- [升级到 Skype for Business Server 2019](/skypeforbusiness/migration/migration-to-skype-for-business-server-2019)
- [升级到 Skype for Business Server 2015](/skypeforbusiness/deploy/upgrade-to-skype-for-business-server)
