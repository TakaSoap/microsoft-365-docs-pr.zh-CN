---
title: 模拟使用 Microsoft Defender 进行的网络钓鱼攻击
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 了解如何通过 Microsoft Defender for Office 365 中的攻击模拟培训来模拟网络钓鱼攻击并向用户提供网络仿冒防御的培训。
ms.openlocfilehash: b9b8a431fc28942f5e11bc7ce2e805ca082cf36b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944428"
---
# <a name="simulate-a-phishing-attack"></a>模拟网络钓鱼攻击

通过 Microsoft Defender for Office 365 的攻击模拟器培训使您能够在组织中运行良性的网络攻击模拟，以测试安全策略和做法，并培训组织的员工以提高其知名度并降低对攻击的敏感程度。 下面将引导您使用攻击模拟器培训模拟网络钓鱼攻击。

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

若要启动模拟的网络钓鱼攻击，请导航到 [Microsoft 365 安全中心](https://security.microsoft.com/)。 在 " **电子邮件 & 协作** " 下，单击 " **攻击模拟器** " 并切换到 " [**模拟**](https://security.microsoft.com/attacksimulator?viewid=simulations) " 选项卡。

在 " **模拟** " 下 **，选择 + 启动模拟** 。

![在 Microsoft 365 安全中心中启动模拟按钮](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> 在模拟创建过程中的任何时候，都可以保存和关闭，以便以后继续配置模拟。

## <a name="selecting-a-social-engineering-technique"></a>选择社会工程技术

从4种不同的技术中进行选择，curated 从 [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/)。 不同的负载可用于不同的技术。

- **凭据收集** 将尝试通过将用户带到已知的外观网站（包含输入框来提交用户名和密码）来收集员工的凭据。
- **恶意软件附件** 将恶意附件添加到邮件中。 打开时，此附件将运行一些可帮助攻击者危害目标设备的任意代码。
- **附件中的链接** 是一种凭据搜集混合类型。 攻击者将 URL 插入到电子邮件附件中。 附件中的 URL 遵循与凭据搜集相同的技术。
- **链接到恶意软件** 将通过在已知文件共享网站上托管的文件运行某些任意代码。 指向此恶意文件的链接将添加到发送给目标的邮件中，单击它将运行该文件，并帮助攻击者危害目标设备。

> [!TIP]
> 单击每种技术的说明中的 " **查看详细信息** "，将显示有关该技术的详细信息以及该技术的模拟步骤。
>
> ![Microsoft 365 安全中心内的凭据收集攻击模拟培训的模拟步骤](../../media/attack-sim-preview-sim-steps.png)

选择该技术并单击 " **下一步** " 后，会为模拟提供一个名称和（可选）说明。

## <a name="selecting-a-payload"></a>选择有效负载

接下来，你需要从预先存在的有效负载目录中选择有效负载。

负载具有许多可帮助您选择的数据点：

- **单击 "汇率计数"** 多少人单击了此有效负载。
- **预测的泄露率** 预测基于此有效负载的人员在 Microsoft Defender for Office 365 客户之间的历史数据所占的百分比。
- **模拟已启动** 计数此负载在其他模拟中使用的次数。
- 通过 **筛选器** 提供的 **复杂性** 是根据有效负载中的指示目标为攻击目标的指示器数计算得出的。 更多指标导致较低的复杂性。
- **Source** ，通过 **筛选器** 提供，指示有效负载是否已在你的租户上创建，或者是否是 Microsoft 的已预先存在的有效负载目录 (全局) 的一部分。

![Microsoft 365 安全中心中的受攻击模拟培训中选定的有效负载](../../media/attack-sim-preview-select-payload.png)

从列表中选择有效负载，以查看有效负载的预览，并提供有关它的其他信息。

如果您想要创建自己的有效负载，请参阅 [创建攻击模拟培训的有效负载](attack-simulation-training-payloads.md)。

## <a name="audience-targeting"></a>访问群体设定

现在是时候选择此模拟受众了。 您可以选择 **包括组织中的所有用户** 或 **仅包括特定的用户和组** 。 

当您选择 **仅包括特定的用户和组** 时，可以执行以下操作之一：

- **添加用户** ，使您可以利用对租户的搜索以及高级搜索和筛选功能，如将最近3个月内未被模拟的用户作为目标。
  ![Microsoft 365 安全中心的攻击模拟培训中的用户筛选](../../media/attack-sim-preview-user-targeting.png)
- **从 CSV 导入** 允许您导入此模拟的一组预定义用户。

## <a name="assigning-training"></a>分配培训

我们建议您为每个模拟分配培训，因为参加培训的员工不易受到类似攻击。

您可以选择为您分配培训，也可以选择 "培训课程和模块"。

选择 **培训截止日期** 以确保员工及时完成其培训。

> [!NOTE]
> 如果选择自己选择课程和模块，您仍可以查看推荐的内容以及所有可用的课程和模块。
>
> ![在 Microsoft 365 安全中心中的攻击模拟培训中添加建议的培训](../../media/attack-sim-preview-add-training.png)

在接下来的步骤中，您需要 **添加培训** （如果选择自己选择培训）并自定义 "培训" 登录页。 您将能够预览 "培训" 登陆页面，还可以更改其标题和正文。

## <a name="launch-details-and-review"></a>启动详细信息和评审

现在，所有内容都已配置，您可以立即启动此模拟，也可以将其安排在更晚的日期。 您还需要选择何时结束此模拟。 我们将在所选时间之后停止捕获与此模拟的交互。 

**启用区域感知时区传递** ，以便在员工的工作时间内根据区域将模拟的攻击邮件传递给员工。

完成后，单击 " **下一步** " 并查看你的模拟的详细信息。 单击任意要返回的部件上的 " **编辑** "，并更改需要更改的任何详细信息。 完成后，单击 " **提交** "。
