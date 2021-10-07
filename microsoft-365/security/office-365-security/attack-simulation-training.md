---
title: 使用 Microsoft Defender for Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中通过攻击模拟培训其用户进行网络钓鱼防护。
ms.technology: mdo
ms.openlocfilehash: fec06f65c67f0ec4c470660689a1f3fc1d9bfbcd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213501"
---
# <a name="simulate-a-phishing-attack"></a>模拟网络钓鱼攻击

**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)

Microsoft Defender for Office 365 中的攻击模拟培训允许你在组织中运行恶意网络攻击模拟，以测试你的安全策略和做法，以及培训员工提高认知度并减少他们对攻击的敏感性。 本文将指导你完成使用攻击模拟培训创建模拟网络钓鱼攻击。

有关攻击模拟培训的入门信息，请参阅使用 [攻击模拟培训入门](attack-simulation-training-get-started.md)。

若要启动模拟网络钓鱼攻击，请打开 Microsoft 365 Defender 门户 () ，转到电子邮件 & 协作攻击模拟培训，然后切换到 <https://security.microsoft.com/>  \> **[模拟](https://security.microsoft.com/attacksimulator?viewid=simulations)** 选项卡。

在 **"模拟"** 下，选择 **"+ 启动模拟"。**

![在应用门户中启动Microsoft 365 Defender按钮。](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> 在模拟创建期间的任何时间点，你都可以保存并关闭，以在以后继续配置模拟。

## <a name="selecting-a-social-engineering-technique"></a>选择社交工程技术

从 4 种不同的技术中选择，这些技术由 [MITRE ATT&CK®设计](https://attack.mitre.org/techniques/enterprise/)。 不同的有效负载可用于不同的技术：

- **凭据收集** 尝试通过让用户到具有输入框的已知网站提交用户名和密码来收集凭据。
- **恶意软件附件** 向邮件添加恶意附件。 当用户打开附件时，将运行任意代码，以帮助攻击者破坏目标设备。
- **附件中的链接** 是凭据获取混合的一种类型。 攻击者将 URL 插入到电子邮件附件中。 附件中的 URL 遵循与凭据获取相同的技术。
- **指向恶意软件** 的链接将运行一些来自已知文件共享服务上托管的文件的任意代码。 发送给用户的邮件将包含指向此恶意文件的链接。 打开文件并帮助攻击者破坏目标设备。
- **在"** 按 URL 驱动器"中，消息中的恶意 URL 会让用户访问一个看起来熟悉的网站，该网站以静默方式运行和/或在用户的设备上安装代码代码。

> [!TIP]
> 单击 **每种技术** 描述中的"查看详细信息"将显示该技术的进一步信息和模拟步骤。
>
> ![在攻击门户中攻击模拟培训中凭据收集的Microsoft 365 Defender步骤。](../../media/attack-sim-preview-sim-steps.png)

选择该技术并单击"下一步"后，为模拟指定名称和说明（可选）。

## <a name="selecting-a-payload"></a>选择有效负载

接下来，你需要从预先存在的有效负载目录中选择有效负载。

有效负载具有多个数据点，可帮助你选择：

- **语言** 显示有效负载内容的语言。 Microsoft 的有效负载目录 (全局) 提供 10 多种语言（也可以筛选）的有效负载。
- **单击率** 计算单击此有效负载的人数。
- **预测的泄露率** 根据 Microsoft Defender 中负载的历史数据预测受此负载危害的百分比，Office 365客户。
- **模拟启动** 计算此有效负载在其他模拟中使用的次数。
- **复杂度**（通过 **筛选器提供**）根据有效负载中的指示器数量计算，这些指示器可提示攻击中的目标。 指示器越多，复杂性越低。
- **Source**（通过 **筛选器提供**）指示有效负载是在租户上创建的，还是 Microsoft 预先存在的有效负载目录的一部分， (全局) 。

![在攻击门户中，在攻击模拟Microsoft 365 Defender有效负载。](../../media/attack-sim-preview-select-payload.png)

从列表中选择一个有效负载，以查看有效负载的预览，并提供有关它的其他信息。

如果你想要创建自己的有效负载，请阅读 [为攻击模拟培训创建有效负载](attack-simulation-training-payloads.md)。

## <a name="audience-targeting"></a>受众定向

现在，该选择此模拟的受众了。 可以选择包括 **组织中所有用户，** 也可以仅 **包含特定用户和组**。

当你选择仅 **包含特定用户和组时** ，你可以：

- **添加** 用户 ，这允许你利用租户的搜索以及高级搜索和筛选功能，如面向过去 3 个月内未通过模拟确定目标的用户。

  ![客户门户中攻击模拟培训中的Microsoft 365 Defender筛选。](../../media/attack-sim-preview-user-targeting.png)

- **从 CSV 导入** 允许你导入此模拟的预定义用户集。 CSV 文件每行应包含一个电子邮件地址。

## <a name="assigning-training"></a>分配培训

我们建议你为每个模拟分配培训，因为通过培训的员工不太容易遭受类似的攻击。

可以选择为自己分配培训，也可以自己选择培训课程和模块。

选择 **培训截止日期** ，确保员工及时完成培训。

> [!NOTE]
> 如果你选择自己选择课程和模块，你仍然可以看到推荐的内容以及所有可用的课程和模块。
>
> ![在攻击模拟门户中添加建议Microsoft 365 Defender培训。](../../media/attack-sim-preview-add-training.png)

在以下步骤中，如果选择自己选择培训，将需要添加培训，并自定义培训登陆页面。 你将能够预览培训登陆页面，并更改其标头和正文。

## <a name="launch-details-and-review"></a>启动详细信息和查看

现在，一切都已配置完成，你可以立即启动此模拟或安排在以后日期进行。 你还需要选择何时结束此模拟。 在选定时间后，我们将停止捕获此模拟的交互。

**启用区域感知时区传递** ，以根据员工的区域在工作时间向员工传递模拟攻击邮件。

完成后，单击"下一步 **"** 并查看模拟的详细信息。 单击任何 **部件的** "编辑"可返回并更改需要更改的任何详细信息。 完成后，单击"提交 **"。**

> [!NOTE]
> 某些商标、徽标、符号、签名和其他源标识符受到当地、州、联邦法律的高度保护。 未经授权使用此类指示器可能会使用户遭受处罚，包括罚款。 虽然这不是一个广泛列表，但其中包括"百科百科"、"Vice Vice"和"一流"（该名称为"一家"）、"社会保险局"、"一流"和"Medic一"（美国国家/局）和"美国商务部"。 除了这些类别的商标之外，使用和修改任何第三方商标会带来固有风险。 在有效负载中使用自己的商标和徽标的风险较低，尤其是在组织允许使用的情况下。 如果你对创建或配置负载时适合使用或不适合使用的任何进一步问题，应咨询法律顾问。
