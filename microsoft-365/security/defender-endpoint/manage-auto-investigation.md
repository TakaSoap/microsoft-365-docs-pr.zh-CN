---
title: 查看自动调查后修正操作
description: 在自动调查 (批准或拒绝) 修正操作。
keywords: autoir， 自动化， 调查， 检测， 修正， 操作， 挂起， 已批准
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: 22229d495e9b7694d07f25b60e854240f7c420c8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152028"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>在自动调查后查看修正操作

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>修正操作

当 [自动调查](automated-investigations.md) 运行时，将针对调查的每个证据生成裁定。 裁定结果可以是 *"恶意"、"**可疑"* 或 *"未找到威胁"。*

取决于

- 威胁的类型，
- 结果裁定，
- 如何配置 [组织的设备](/microsoft-365/security/defender-endpoint/machine-groups) 组，

修正操作可以自动执行，或仅在组织的安全运营团队批准后执行。

下面是一些示例：

- **示例 1：Fabrikam** 的设备组设置为"完全 **-** 根据建议设置 (自动修正) 。 在这种情况下，对于在自动调查后被视为恶意的项目，将自动采取修正 [ (请参阅查看](#review-completed-actions) 已完成) 。

- **示例** 2：Contoso 的设备包含在为 Semi 设置的设备组中 ， **需要批准任何修正**。 在这种情况下，Contoso 的安全运营团队必须审阅和批准自动调查后的所有修正操作 [ (查看挂起](#review-pending-actions) 的操作) 。

- **示例 3：Tailspin** Toys 的设备组设置为"无自动响应 (不建议) 。 在这种情况下，不会发生自动调查。 不会执行或挂起任何修正操作，并且不会在操作中心中记录其[](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)设备的任何 (请参阅管理[设备](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)组) 。

无论是自动执行还是批准，自动调查都可能导致一个或多个修正操作：

- 隔离文件
- 删除注册表项
- 终止进程
- 停止服务
- 禁用驱动程序
- 删除计划任务

## <a name="review-pending-actions"></a>查看挂起的操作

1. 转到安全Microsoft 365中心 [https://security.microsoft.com](https://security.microsoft.com) () 登录。
2. 在“导航”窗格中，选择“操作中心”。
3. 查看"挂起" **选项卡上的** 项目。
4. 选择一个操作以打开其飞出窗格。
5. 在飞出窗格中，查看信息，然后执行以下步骤之一：
   - 选择 **"打开调查"** 页以查看有关调查的更多详细信息。
   - 选择 **"批准** "以启动挂起的操作。
   - 选择 **"** 拒绝"以防止执行挂起的操作。
   - 选择 **"开始搜寻**"转到"[高级搜寻"。](advanced-hunting-overview.md)

## <a name="review-completed-actions"></a>查看已完成的操作

1. 转到安全Microsoft 365中心 [https://security.microsoft.com](https://security.microsoft.com) () 登录。
2. 在“导航”窗格中，选择“操作中心”。
3. 查看"历史记录" **选项卡上的** 项目。
4. 选择一个项目以查看有关该修正操作的详细信息。

## <a name="undo-completed-actions"></a>撤消已完成的操作

如果你已确定设备或文件不是威胁，你可以撤消已采取的修正操作，无论这些操作是自动执行还是手动执行。 在操作中心的"历史记录 **"** 选项卡上，可以撤消以下任何操作：

<br>

****

|操作源|支持的操作|
|---|---|
|<ul><li>自动调查</li><li>Microsoft Defender 防病毒</li><li>手动响应操作</li></ul>|<ul><li>隔离设备</li><li>限制代码执行</li><li>隔离文件</li><li>删除注册表项</li><li>停止服务</li><li>禁用驱动程序</li><li>删除计划任务</li></ul>|
|

### <a name="to-undo-multiple-actions-at-one-time"></a>一次撤消多个操作

1. 转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 并登录。
2. 在 **"历史记录** "选项卡上，选择要撤消的操作。 确保选择操作类型相同的项目。 将打开一个飞出窗格。
3. 在飞出窗格中， **选择撤消**。

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>跨多个设备从隔离中删除文件

1. 转到操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 并登录。
2. 在" **历史记录"** 选项卡上，选择操作类型为"隔离 **文件"的项目**。
3. 在飞出窗格中，选择 **"应用到此文件** 的 X 更多实例"，然后选择"撤消 **"。**

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>自动化级别、自动调查的结果和结果操作

自动化级别会影响某些修正操作是自动执行还是仅在审批后执行。 有时，根据自动调查的结果，安全运营团队需要执行更多步骤。 下表汇总了自动化级别、自动调查的结果以及每种情况下要执行哪些操作。

<br>

****

|设备组设置|自动调查结果|需执行的操作|
|---|---|---|
|**完全 - 根据建议设置** (自动修正) |对于一 *条证据* ，已到达"恶意"裁定。 <p> 将自动执行相应的修正操作。|[查看已完成的操作](#review-completed-actions)|
|**完全 - 自动修正威胁**|对于一 *条证据* ，已到达"可疑"裁定。 <p> 修正操作正在等待审批以继续。|[批准 (或拒绝) 挂起的操作](#review-pending-actions)|
|**Semi - 需要批准任何修正**|对于一条 *证据，* 已 *到达* "恶意"或"可疑"裁定。 <p> 修正操作正在等待审批以继续。|[批准 (或拒绝) 挂起的操作](#review-pending-actions)|
|**Semi - 需要批准核心文件夹修正**|对于一 *条证据* ，已到达"恶意"裁定。 <p> 如果项目是文件或可执行文件，并且位于操作系统目录（如 Windows 文件夹或 Program files 文件夹）中，则修正操作将等待审批。 <p> 如果项目 *不在操作系统* 目录中，将自动执行修正操作。|<ol><li>[批准 (或拒绝) 挂起的操作](#review-pending-actions)</li><li>[查看已完成的操作](#review-completed-actions)</li></ol>|
|**Semi - 需要批准核心文件夹修正**|对于一 *条证据* ，已到达"可疑"裁定。 <p> 修正操作正在等待审批。|[批准 (或拒绝) 挂起的操作。](#review-pending-actions)|
|**Semi - 需要审批非临时文件夹修正**|对于一 *条证据* ，已到达"恶意"裁定。 <p> 如果项目是不在临时文件夹中的文件或可执行文件（如用户的下载文件夹或临时文件夹）中，则修正操作将等待审批。 <p> 如果项目是临时 *文件夹中的文件或* 可执行文件，将自动执行修正操作。|<ol><li>[批准 (或拒绝) 挂起的操作](#review-pending-actions)</li><li>[查看已完成的操作](#review-completed-actions)</li></ol>|
|**Semi - 需要审批非临时文件夹修正**|对于一 *条证据* ，已到达"可疑"裁定。 <p> 修正操作正在等待审批。|[批准 (或拒绝) 挂起的操作](#review-pending-actions)|
|任何完全 **或****半** 自动化级别|对于一 *条证据，* 未发现任何威胁裁定。 <p> 不执行修正操作，并且没有任何操作等待审批。|[查看自动化调查的详细信息和结果](/microsoft-365/security/defender-endpoint/auto-investigation-action-center)|
|**不建议 (** 自动响应) |没有自动调查运行，因此不会做出裁定，并且不会采取修正操作或等待批准。|[考虑设置或更改设备组以使用 **完全或****半** 自动化](/microsoft-365/security/defender-endpoint/machine-groups)|
|

在 Microsoft Defender for Endpoint 中，所有裁定都跟踪在 [操作中心 中](auto-investigation-action-center.md#new-a-unified-action-center)。

## <a name="next-steps"></a>后续步骤

- [了解实时响应功能](live-response.md)
- [使用高级搜寻主动搜寻威胁](advanced-hunting-overview.md)
- [解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>另请参阅

- [自动调查概述](automated-investigations.md)
