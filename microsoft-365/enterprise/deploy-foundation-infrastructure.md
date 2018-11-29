---
title: Microsoft 365 企业版底层基础结构
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解组织中部署 Microsoft 365 企业版底层基础结构的主要阶段。
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865398"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a>Microsoft 365 企业版底层基础结构

若要充分实现 Microsoft 365 企业版的好处，请从其底层基础结构开始部署。 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a>部署 Microsoft 365 企业版的底层基础结构

底层基础结构是部署生产力工作负载（如 Office 365 中的 Microsoft Teams 和 Exchange Online）和方案（如迁移到 Microsoft 365 和自动执行客户端更新）的基础。它提供了智能安全性和集成功能，不仅简化了持续管理，还确保客户端软件更新有最新生产力和安全增强。

将通过以下阶段在组织中计划和部署 Microsoft 365 企业版的底层基础结构：

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[阶段 1：网络](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[阶段 2：身份](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[阶段 3：Windows 10 企业版](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[阶段 4：Office 365 专业增强版](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[阶段 5：移动设备管理](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[阶段 6：信息保护](infoprotect-infrastructure.md)|


在退出每个阶段之前，必须检查其退出条件，这是一组必须满足的必需条件和要考虑的可选条件。每个阶段的退出条件可确保本地和云基础结构以及生成的端到端配置满足对 Microsoft 365 企业版部署的要求。

观看此短视频，了解基础结构内容的原理。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

下图显示了整体 Microsoft 365 企业版部署内容的基础结构及熟悉方法。

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a>FastTrack

FastTrack 的优势在于持续且可重复（可用作订阅的一部分），由 Microsoft 工程师提供以帮助你按自己的节奏移动到云。此外，FastTrack 还可使你根据需要访问合格的合作伙伴以获取其他服务。目前为止，40,000 多个客户已启用此功能，FastTrack 可帮助最大化 ROI、加快部署，提高整个组织的采用率。请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。 

若要充分利用 FastTrack 来部署 Microsoft 365 企业版，可以使用 FastTrack [Microsoft 365 部署顾问](https://aka.ms/microsoft365setupguide)，了解如何部署和设置底层基础结构。必须以全局管理员的身份在 Office 365 或 Microsoft 365 租户中登录，才能访问此页面。

## <a name="next-step"></a>后续步骤

如果你有 Office 365、企业移动性 + 安全性或 Windows 10 企业版的现有基础结构，请参阅[使用现有基础结构部署 Microsoft 365 企业版](deploy-with-existing-infrastructure.md)。本文将系统介绍每个阶段的退出条件。使用此信息，可使你更快速地确定为使 IT 基础结构符合 Microsoft 365 企业版要求而需要更改的内容。

否则，可通过[阶段 1：网络](networking-infrastructure.md)开始你的 Microsoft 365 企业版端到端部署历程。