---
title: 通过模拟攻击体验 Microsoft Defender (MDE) 体验
description: 试用你的Microsoft 365 Defender试验实验室或试验环境。
keywords: Microsoft 365 Defender试用版，请尝试Microsoft 365 Defender，评估Microsoft 365 Defender，Microsoft 365 Defender实验室，Microsoft 365 Defender试点， 网络安全性， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 93e5b0cb5a152868749a68d34ac476660b41cc92
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152402"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a>通过模拟攻击体验 Microsoft Defender (MDE) 体验

> [!TIP]
>
> - 了解适用于终结点的 Microsoft Defender 中的最新增强功能[：Defender for Endpoint 中的新增功能是什么？。](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
> - Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。 阅读：[来自基于 MITRE ATT&CK 的评估的见解](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

在将多个设备载入服务之前，你可能想要体验 Defender for Endpoint。 为此，可以在一些测试设备上运行受控攻击模拟。 运行模拟攻击后，你可以查看 Defender for Endpoint 如何显示恶意活动，并探索它如何启用有效的响应。

## <a name="before-you-begin"></a>准备工作

若要运行任何提供的模拟，你至少需要一 [个已载入的设备](onboard-configure.md)。

阅读每个攻击方案提供的演练文档。 每个文档都包括操作系统和应用程序要求，以及特定于攻击方案的详细说明。

## <a name="run-a-simulation"></a>运行模拟

1. 在 **帮助** \> **模拟&** 教程中，选择要模拟的可用攻击方案：

   - **方案 1：文档丢弃后门** - 模拟传递社交工程的诱使文档。 文档启动一个专门设计的后门，该后门为攻击者提供控制。

   - **方案 2：** 无文件攻击中的 PowerShell 脚本 - 模拟依赖于 PowerShell 的无文件攻击，展示攻击面减少和设备学习检测恶意内存活动。

   - **方案 3：自动事件响应** - 触发自动调查，自动搜寻并修正泄露项目，从而扩展事件响应容量。

2. 下载并阅读所选方案提供的相应演练文档。

3. 下载模拟文件或通过导航到帮助模拟和教程复制 \> **&脚本**。 你可以选择在测试设备上下载文件或脚本，但这不是强制性的。

4. 根据演练文档中的指示，在测试设备上运行模拟文件或脚本。

> [!NOTE]
> 模拟文件或脚本模拟攻击活动，但实际上是恶意的，不会损害或损害测试设备。

## <a name="alternate-topic-text"></a>备用主题文本

## <a name="simulate-attack-scenarios"></a>模拟攻击方案

通过连接到测试设备来运行自己的攻击模拟。

可以使用以下方法模拟攻击方案：

- " [自己执行"攻击方案](https://securitycenter.windows.com/tutorials)
- 威胁模拟器

您还可以使用 [高级搜寻](advanced-hunting-overview.md) 来查询数据和 [威胁分析](threat-analytics.md) ，以查看有关新出现的威胁的报告。

### <a name="do-it-yourself-attack-scenarios"></a>自己动手攻击方案

如果你要查找预先模拟，可以使用我们的"自己执行" [攻击方案](https://securitycenter.windows.com/tutorials)。 这些脚本安全、有记录且易于使用。 这些方案将反映 Defender for Endpoint 功能，并演练调查体验。

> [!NOTE]
> 与测试设备的连接使用 RDP 完成。 请确保防火墙设置允许 RDP 连接。

1. 连接你的设备，然后通过选择"攻击模拟 **"连接。**

    ![测试设备的连接按钮的图像。](images/test-machine-table.png)

2. 保存 RDP 文件，然后通过选择 **"连接"。**

    ![远程桌面连接的图像。](images/remote-connection.png)

    > [!NOTE]
    > 如果在初始设置期间没有保存密码的副本，则可以通过从菜单中选择"重置密码 **"来重置** 密码：
    >
    > ![重置密码的图像。](images/reset-password-test-machine.png)
    >
    > 设备会更改其状态为"正在执行密码重置"，然后你将在数分钟内看到新密码。

3. 输入在设备创建步骤期间显示的密码。

   ![用于输入凭据的窗口的图像。](images/enter-password.png)

4. 在设备上运行自己动手攻击模拟。

### <a name="threat-simulator-scenarios"></a>威胁模拟器方案

如果你在实验室设置期间选择安装任何受支持的威胁模拟器，可以在评估实验室设备上运行内置模拟。

使用第三方平台运行威胁模拟是在实验室环境中评估 Microsoft Defender for Endpoint 功能的良好方法。

> [!NOTE]
> 在运行模拟之前，请确保满足以下要求：
>
> - 必须将设备添加到评估实验室
> - 威胁模拟器必须安装在评估实验室中

1. 从门户中选择"**创建模拟"。**

2. 选择威胁模拟器。

    ![威胁模拟器选择的图像。](images/select-simulator.png)

3. 选择模拟或浏览模拟库以浏览可用的模拟。

   你可以从以下方法访问模拟库：

   - 模拟概述 **磁贴或**
   - 通过导航从导航窗格 **评估和教程** \> **模拟&教程，** 然后选择 **模拟目录**。

4. 选择要运行模拟的设备。

5. 选择 **创建模拟**。

6. 通过选择"模拟"选项卡查看 **模拟** 的进度。查看模拟状态、活动警报和其他详细信息。

    ![模拟选项卡的图像。](images/simulations-tab.png)

运行模拟后，我们鼓励你演练实验室进度栏，并探索 Microsoft Defender **for Endpoint 触发了自动调查和修正**。 查看功能收集和分析的证据。

使用丰富的查询语言和原始遥测通过高级搜寻来搜寻攻击证据，并查看威胁分析中记录一些全球威胁。
