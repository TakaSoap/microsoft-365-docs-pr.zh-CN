---
title: 优化 ASR 规则部署和检测
description: 优化攻击面减少 (ASR) 规则，以识别和阻止典型的恶意软件攻击。
keywords: 载入， Intune 管理， Microsoft Defender for Endpoint， Microsoft Defender， Windows Defender， 攻击面减少， ASR， 安全基线
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d2bf9a6fa1f874e7d550d0d0f7a42742a07665eb
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468250"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>优化 ASR 规则部署和检测

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

[攻击面减少 (ASR) 识别](./attack-surface-reduction.md) 并阻止典型的恶意软件攻击。 它们控制何时以及如何运行潜在的恶意代码。 例如，它们可以防止 JavaScript 或 VBScript 启动下载的可执行文件、阻止从 Office 宏调用 Win32 API 以及阻止从 USB 驱动器运行的进程。


:::image type="content" source="../../media/attack-surface-mgmt.png" alt-text="攻击面管理卡" lightbox="../../media/attack-surface-mgmt.png":::
<br>
*攻击面管理卡*

攻击 *面管理卡* 是一个入口点，可用于Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>中的工具：

* 了解 ASR 规则当前在组织中是如何部署的。
* 查看 ASR 检测并识别可能的不正确检测。
* 分析排除的影响并生成要排除的文件路径列表。

选择 **转到攻击面管理报告** \>  \> **攻击面减少规则** \> **添加排除项**。 可以在那里导航到门户的其他Microsoft 365 Defender部分。

:::image type="content" source="images/secconmgmt_asr_m365exlusions.png" alt-text="Microsoft 365 Defender门户中攻击面减少规则页中的&quot;添加排除项Microsoft 365 Defender选项卡" lightbox="images/secconmgmt_asr_m365exlusions.png":::<br>
Microsoft 365 Defender ***门户** 中攻击面减少规则页中的"添加排除项Microsoft 365 Defender选项卡*

> [!NOTE]
> 若要访问Microsoft 365 Defender门户，您需要一个 Microsoft 365 E3 或 E5 许可证以及一个在 Azure Active Directory 上具有特定角色Azure Active Directory。 [阅读所需的许可证和权限](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

有关在管理门户中部署 ASR 规则<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender，</a>请参阅监视和管理 [ASR 规则部署和检测](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)。

**相关主题**

* [确保设备配置正确](configure-machines.md)
* [获取载入到 Microsoft Defender for Endpoint 的设备](configure-machines-onboarding.md)
* [监视 Microsoft Defender 终结点安全基线的合规性](configure-machines-security-baseline.md)
