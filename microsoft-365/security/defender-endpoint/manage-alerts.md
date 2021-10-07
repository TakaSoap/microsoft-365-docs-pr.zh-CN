---
title: 管理 Microsoft Defender for Endpoint 警报
description: 使用"管理警报"菜单更改警报的状态、创建抑制规则以隐藏警报、提交注释并查看单个警报的更改历史记录。
keywords: 管理警报， 管理， 警报， 状态， 新建， 正在进行， 已解决， 解决警报， 抑制， 抑制， 规则， 上下文， 历史记录， 注释， 更改
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d6ce6d8f081141214c8d10ea21898fb66e3e0c10
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205363"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>管理 Microsoft Defender for Endpoint 警报

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-managealerts-abovefoldlink)。

Defender for Endpoint 通过警报通知你可能的恶意事件、属性和上下文信息。 新警报的摘要显示在安全操作仪表板中，并且可以访问警报 **队列中的所有警报**。

可以通过在警报队列中选择警报或单个设备的设备页面的警报选项卡来管理警报。 

在任一位置选择警报将打开警报 **管理窗格**。

![警报管理窗格和警报队列的图像。](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a>链接到其他事件

你可以从警报创建新事件或链接到现有事件。

## <a name="assign-alerts"></a>分配警报

如果尚未分配警报，可以选择"分配给 **我** "，将警报分配给自己。

## <a name="suppress-alerts"></a>抑制警报

在某些情况下，可能需要禁止警报显示在Microsoft Defender 安全中心。 通过 Defender for Endpoint，你可以为已知不安全的特定警报（如组织中已知的工具或流程）创建抑制规则。

可以从现有警报创建抑制规则。 如果需要，可以禁用和重新启用它们。

创建抑制规则时，它将从创建该规则时开始生效。 在规则创建之前，该规则不会影响队列中已有的现有警报。 规则将仅应用于满足创建规则后设置的条件的警报。

抑制规则有两个上下文可供选择：

- **抑制此设备的警报**
- **抑制我的组织的警报**

规则的上下文允许你定制门户中显示的内容，并确保门户中只显示真实的安全警报。

可以使用下表中的示例来帮助你选择抑制规则的上下文：

|上下文|定义|示例场景|
|---|---|---|
|**抑制此设备的警报**|将仅抑制具有相同的警报标题和特定设备的警报。 <p> 不会抑制该设备上所有其他警报。|<ul><li>安全研究人员正在调查用于攻击组织中其他设备的恶意脚本。</li><li>开发人员定期为团队创建 PowerShell 脚本。</li></ul>|
|**抑制我的组织的警报**|将抑制任何设备上具有相同的警报标题的警报。|<ul><li>组织中的每个人都使用良好的管理工具。</li></ul>|

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>抑制警报并创建新的抑制规则

创建自定义规则以控制何时抑制或解决警报。 通过指定警报标题、泄露指示器和条件，可以控制何时抑制警报的上下文。 指定上下文后，您将能够在警报上配置操作和范围。

1. 选择要抑制的警报。 此时将打开警报 **管理** 窗格。

2. 选择 **"创建抑制规则"。**

    可以使用这些属性创建抑制条件。 在每种条件之间应用 AND 运算符，因此仅在满足所有条件时才进行抑制。

    - 文件 SHA1
    - 文件名 - 支持通配符
    - 文件夹路径 - 支持通配符
    - IP 地址
    - URL - 支持通配符
    - 命令行 - 支持通配符

3. 选择 **"触发 IOC"。**

4. 指定警报的操作和范围。

   你可以自动解决警报或在门户中隐藏它。 自动解决的警报将显示在警报队列、警报页面和设备时间线的解析部分中，并且显示为跨 Defender for Endpoint API 解析。

   在设备的关联警报和仪表板上，标记为隐藏的警报都将从整个系统中抑制，并且不会跨 Defender for Endpoint API 流式传输。

5. 输入规则名称和注释。

6. 单击“**保存**”。

#### <a name="view-the-list-of-suppression-rules"></a>查看抑制规则列表

1. 在导航窗格中，选择 **"设置** \> **抑制"。**

2. 抑制规则列表显示组织中用户已创建的所有规则。

有关管理抑制规则的信息，请参阅 [管理抑制规则](manage-suppression-rules.md)

## <a name="change-the-status-of-an-alert"></a>更改警报的状态

你可以将警报分类为 (、正在进行或已解决) 调查时更改其状态。  这可帮助你组织和管理团队可以如何响应警报。

例如，团队主管可以审阅所有 **新** 警报，并决定将其分配给进行中 **队列** ，以进一步分析。

或者，如果团队领导知道警报是无害的、来自与安全管理员 (（例如属于安全管理员) 的设备）无关，或者正在通过早期警报处理，则他们可以将警报分配给已解决队列。

## <a name="alert-classification"></a>警报分类

可以选择不设置分类，也可以指定警报是真警报还是假警报。 提供真正的正/误报分类非常重要。 此分类用于监视警报质量，使警报更加准确。 "确定"字段定义"真正的正"分类的其他保真度。

## <a name="add-comments-and-view-the-history-of-an-alert"></a>添加注释并查看警报历史记录

你可以添加注释并查看有关警报的历史事件，以查看之前对警报所做的更改。

只要对警报进行了更改或注释，就会记录在"注释和历史记录" **部分** 。

添加的备注会立即显示在窗格中。

## <a name="related-topics"></a>相关主题

- [管理点规则](manage-suppression-rules.md)
- [查看并组织 Microsoft Defender for Endpoint 警报队列](alerts-queue.md)
- [调查 Microsoft Defender for Endpoint 警报](investigate-alerts.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的文件](investigate-files.md)
- [调查 Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址](investigate-ip.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的域](investigate-domain.md)
- [调查 Microsoft Defender for Endpoint 中的用户帐户](investigate-user.md)
