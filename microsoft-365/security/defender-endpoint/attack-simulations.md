---
title: 通过模拟攻击体验 Microsoft Defender for Endpoint
description: 运行提供的攻击方案模拟，体验 Microsoft Defender for Endpoint 如何检测、调查和响应泄露。
keywords: 测试， 方案， 攻击， 模拟， 模拟， diy， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 73a226d83e46cf06aa9d3cceb903a2b142604179
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213153"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>通过模拟攻击体验 Microsoft Defender for Endpoint 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-abovefoldlink)。

> [!TIP]
>
> - 了解适用于终结点的 Microsoft Defender 中的最新增强功能[：Defender for Endpoint 中的新增功能是什么？。](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
> - Defender for Endpoint 在最新的 MITRE 评估中展示了行业领先的光学镜头和检测功能。 阅读：[来自基于 MITRE ATT&CK 的评估的见解](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

在将多个设备载入服务之前，你可能想要体验 Defender for Endpoint。 为此，可以在一些测试设备上运行受控攻击模拟。 运行模拟攻击后，你可以查看 Defender for Endpoint 如何显示恶意活动，并探索它如何启用有效的响应。

## <a name="before-you-begin"></a>准备工作

若要运行任何提供的模拟，你至少需要一 [个已载入的设备](onboard-configure.md)。

阅读每个攻击方案提供的演练文档。 每个文档都包括操作系统和应用程序要求，以及特定于攻击方案的详细说明。

## <a name="run-a-simulation"></a>运行模拟

1. 在 **终结点** \> **评估&教程**&模拟中，选择要模拟的可用 \> 攻击方案：
   - **方案 1：文档丢弃后门** - 模拟传递社交工程的诱使文档。 文档启动一个专门设计的后门，该后门为攻击者提供控制。
   - **方案 2：** 无文件攻击中的 PowerShell 脚本 - 模拟依赖于 PowerShell 的无文件攻击，展示攻击面减少和设备学习检测恶意内存活动。
   - **方案 3：自动事件响应** - 触发自动调查，自动搜寻并修正泄露项目，从而扩展事件响应容量。

2. 下载并阅读所选方案提供的相应演练文档。

3. 下载模拟文件或复制模拟脚本，方法为导航到评估&**教程** 教程& \> **模拟。** 你可以选择在测试设备上下载文件或脚本，但这不是强制性的。

4. 根据演练文档中的指示，在测试设备上运行模拟文件或脚本。

> [!NOTE]
> 模拟文件或脚本模拟攻击活动，但实际上是恶意的，不会损害或损害测试设备。
>
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-attacksimulations-belowfoldlink)。

## <a name="related-topics"></a>相关主题

- [载入设备](onboard-configure.md)
- [载入 Windows 设备](configure-endpoints.md)
