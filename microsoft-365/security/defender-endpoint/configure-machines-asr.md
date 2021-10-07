---
title: 优化 ASR 规则部署和检测
description: 优化攻击面减少 (ASR) 规则，以识别和阻止典型的恶意软件攻击。
keywords: 载入， Intune 管理， Microsoft Defender for Endpoint， Microsoft Defender， Windows Defender， 攻击面减少， ASR， 安全基线
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 612a68e4b0804ed6419511ee7505ed13a49883bb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205663"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>优化 ASR 规则部署和检测

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

[攻击面减少 (ASR) 识别](./attack-surface-reduction.md) 并阻止典型的恶意软件攻击。 它们控制何时以及如何运行潜在的恶意代码。 例如，它们可以防止 JavaScript 或 VBScript 启动下载的可执行文件、阻止从 Office 宏调用 Win32 API 以及阻止从 USB 驱动器运行的进程。


:::image type="content" source="../../media/attack-surface-mgmt.png" alt-text="攻击面管理卡。":::
<br>
*攻击面管理卡*

攻击 *面管理卡* 是安全中心Microsoft 365工具的入口点，可用于：

* 了解 ASR 规则当前在组织中是如何部署的。
* 查看 ASR 检测并识别可能的不正确检测。
* 分析排除的影响并生成要排除的文件路径列表。

选择 **转到攻击面管理** \> **报告** \> **攻击面减少规则** \> **添加排除** 项。 然后，你可以导航到安全中心Microsoft 365分区。

![在安全中心的"攻击面减少规则"页中添加Microsoft 365排除项"选项卡。](images/secconmgmt_asr_m365exlusions.png)<br>
安全 ***中心的"攻击** 面减少规则"页中的"添加排除Microsoft 365选项卡*

> [!NOTE]
> 若要访问Microsoft 365中心，您需要一个 Microsoft 365 E3 E5 许可证和一个在安全中心上具有特定角色Azure Active Directory。 [阅读所需的许可证和权限](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

有关安全中心中 ASR 规则部署Microsoft 365，请参阅监视和管理[ASR 规则部署和检测](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)。

**相关主题**

* [确保设备配置正确](configure-machines.md)
* [获取载入到 Microsoft Defender for Endpoint 的设备](configure-machines-onboarding.md)
* [监视 Microsoft Defender 终结点安全基线的合规性](configure-machines-security-baseline.md)
