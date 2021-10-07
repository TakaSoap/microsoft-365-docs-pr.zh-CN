---
title: 调查 Microsoft Defender for Endpoint 警报
description: 使用调查选项获取有关影响网络的警报的详细信息、它们的含义以及如何解决它们。
keywords: 调查， 调查， 设备， 设备， 警报队列， 仪表板， IP 地址， 文件， 提交， 提交， 深入分析， 时间线， 搜索， 域， URL， IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: f41be6057f1e66eb13001d4ed7d304d76e895c3d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198213"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>调查 Microsoft Defender for Endpoint 中的警报

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatealerts-abovefoldlink)。

调查影响网络的警报，了解它们的含义以及如何解决它们。

从警报队列中选择警报以转到警报页面。 此视图包含警报标题、受影响的资产、详细信息侧窗格和警报情景。

从警报页面，通过选择警报情景树视图下受影响的资产或任何实体开始调查。 详细信息窗格将自动填充有关所选内容的详细信息。 若要查看可以在此处查看的信息类型，请阅读查看 Microsoft [Defender for Endpoint 中的警报](/microsoft-365/security/defender-endpoint/review-alerts)。

## <a name="investigate-using-the-alert-story"></a>使用警报情景进行调查

警报情景详细介绍了触发警报的原因、之前和之后发生的相关事件以及其他相关实体。

实体是可单击的，并且每个不是警报的实体都可用该实体卡片右侧展开图标进行扩展。 焦点中的实体将用该实体卡片左侧的蓝色条带指示，标题中的警报首先处于焦点状态。

展开实体，一目了然地查看详细信息。 选择实体将详细信息窗格的上下文切换到此实体，并允许您查看详细信息以及管理该实体。 选择 *实体* 卡片右侧"..."将显示该实体的所有可用操作。 当实体具有焦点时，这些相同的操作将显示在详细信息窗格中。

> [!NOTE]
> 警报情景部分可能包含多个警报，与相同执行树相关的其他警报显示在所选警报之前或之后。

![具有焦点的警报和一些扩展卡片的警报情景的示例。](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>从详细信息窗格中采取操作

选择感兴趣的实体后，详细信息窗格将更改为显示有关所选实体类型的信息、可用时的历史信息，并提供直接从警报页对此实体采取措施的控件。 

完成调查后，返回到开始使用的警报，将警报状态标记为"已解决"，然后将其分类为 **"False 警报**"或"**真警报"。**  对警报进行分类有助于调整此功能，以提供更多真实警报和更少的假警报。

如果将其分类为真正的警报，则还可以选择一个决定，如下图所示。

![详细信息窗格的代码段，其中展开已解决警报和确定下拉列表。](images/alert-details-resolved-true.png)

如果业务线应用程序遇到错误警报，请创建抑制规则以避免将来出现此类型的警报。

![突出显示抑制规则的详细信息窗格中的操作和分类。](images/alert-false-suppression-rule.png)

> [!TIP]
> 如果遇到上面未介绍的任何问题，请使用按钮 🙂 提供反馈或打开支持票证。


## <a name="related-topics"></a>相关主题
- [查看并组织 Microsoft Defender for Endpoint 警报队列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警报](manage-alerts.md)
- [调查与 Defender for Endpoint 警报关联的文件](investigate-files.md)
- [调查 Defender for Endpoint Devices 列表中的设备](investigate-machines.md)
- [调查与 Defender for Endpoint 警报关联的 IP 地址](investigate-ip.md)
- [调查与 Defender for Endpoint 警报关联的域](investigate-domain.md)
- [调查 Defender for Endpoint 中的用户帐户](investigate-user.md)


