---
title: 调查Microsoft Defender for Endpoint警报
description: 使用调查选项获取有关警报影响网络、其含义以及如何解决它们的详细信息。
keywords: 调查， 调查， 设备， 设备， 警报队列， 仪表板， IP 地址， 文件， 提交， 提交， 深度分析， 时间线， 搜索， 域， URL， IP
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e4d379ee476276d24b683878bc4978addf220ced
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665791"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>调查Microsoft Defender for Endpoint中的警报

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatealerts-abovefoldlink)。

调查影响网络的警报，了解它们的含义以及如何解决它们。

从警报队列中选择警报以转到警报页。 此视图包含警报标题、受影响的资产、详细信息侧窗格和警报故事。

在警报页中，通过选择受影响的资产或警报故事树视图下的任何实体开始调查。 详细信息窗格会自动填充有关所选内容的更多信息。 若要查看可在此处查看的信息类型，请阅读[Microsoft Defender for Endpoint中的"查看"警报](/microsoft-365/security/defender-endpoint/review-alerts)。

## <a name="investigate-using-the-alert-story"></a>使用警报故事进行调查

警报故事详细介绍了触发警报的原因、之前和之后发生的相关事件以及其他相关实体。

实体是可单击的，并且每个不是警报的实体都可使用该实体卡右侧的展开图标展开。 焦点中的实体将由该实体卡片左侧的蓝色条纹指示，标题中的警报首先处于焦点。

展开实体以一目了然地查看详细信息。 选择实体会将详细信息窗格的上下文切换到此实体，并允许你查看更多信息以及管理该实体。 *选择实体* 卡右侧将显示该实体可用的所有操作。 当实体处于焦点时，这些相同的操作将显示在详细信息窗格中。

> [!NOTE]
> 警报故事部分可能包含多个警报，其中包含与所选警报之前或之后出现的同一执行树相关的其他警报。

:::image type="content" source="images/alert-story-tree.png" alt-text="一个警报故事，重点是警报和一些展开的卡片" lightbox="images/alert-story-tree.png":::

## <a name="take-action-from-the-details-pane"></a>从详细信息窗格执行操作

选择感兴趣的实体后，详细信息窗格将更改为显示有关所选实体类型的信息、可用的历史信息，并提供控件以直接从警报页对此实体 **采取行动** 。

完成调查后，返回到开始使用的警报，将警报的状态标记为 **"已解决** "，并将其归类为 **False 警报** 或 **True 警报**。 分类警报有助于优化此功能，以提供更多真实警报和更少的虚假警报。

如果将其归类为真实警报，也可以选择确定，如下图所示。

:::image type="content" source="images/alert-details-resolved-true.png" alt-text="详细信息窗格，其中已解析警报并展开了确定下拉列表" lightbox="images/alert-details-resolved-true.png":::

如果遇到带有业务线应用程序的虚假警报，请创建一个抑制规则，以避免将来出现此类警报。

:::image type="content" source="images/alert-false-suppression-rule.png" alt-text="详细信息窗格中的操作和分类，其中突出显示了抑制规则" lightbox="images/alert-false-suppression-rule.png":::

> [!TIP]
> 如果遇到上述任何问题，请使用该 🙂 按钮提供反馈或开具支持票证。

## <a name="related-topics"></a>相关主题

- [查看并组织 Microsoft Defender for Endpoint 警报队列](alerts-queue.md)
- [管理Microsoft Defender for Endpoint警报](manage-alerts.md)
- [调查与 Defender for Endpoint 警报关联的文件](investigate-files.md)
- [调查 Defender for Endpoint Devices 列表中的设备](investigate-machines.md)
- [调查与 Defender for Endpoint 警报关联的 IP 地址](investigate-ip.md)
- [调查与 Defender for Endpoint 警报关联的域](investigate-domain.md)
- [调查 Defender for Endpoint 中的用户帐户](investigate-user.md)
