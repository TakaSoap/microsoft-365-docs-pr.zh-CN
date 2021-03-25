---
title: 优化 ASR 规则部署和检测
description: 优化攻击面减少 (ASR) 规则，以识别和阻止典型的恶意软件攻击。
keywords: 载入， Intune 管理， MDATP， WDATP， Microsoft Defender， Windows Defender， 高级威胁防护， 攻击面减少， ASR， 安全基线
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5ce39bb3ff0bf3eea4ac4e89c554de43499b15f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165473"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>优化 ASR 规则部署和检测

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

[攻击面减少 (ASR) 识别](./attack-surface-reduction.md) 并阻止典型的恶意软件攻击。 它们控制何时以及如何运行潜在的恶意代码。 例如，它们可以防止 JavaScript 或 VBScript 启动下载的可执行文件、阻止从 Office 宏调用 Win32 API 以及阻止从 USB 驱动器运行的进程。

![攻击面管理卡](images/secconmgmt_asr_card.png)<br>
*攻击面管理卡*

攻击 *面管理卡* 是 Microsoft 365 安全中心工具的入口点，可用于：

* 了解 ASR 规则当前在组织中是如何部署的。
* 查看 ASR 检测并识别可能的不正确检测。
* 分析排除的影响并生成要排除的文件路径列表。

选择 **转到攻击面管理**  >  **监视&报告>攻击面减少规则>添加排除项**。 可以在那里导航到 Microsoft 365 安全中心的其他部分。

![Microsoft 365 安全中心的"攻击面减少规则"页中的"添加排除项"选项卡](images/secconmgmt_asr_m365exlusions.png)<br>
*Microsoft 365 安全中心的"攻击面减少规则"页中的"添加排除项"选项卡*

> [!NOTE]
> 若要访问 Microsoft 365 安全中心，你需要 Microsoft 365 E3 或 E5 许可证和在 Azure Active Directory 上具有特定角色的帐户。 [阅读所需的许可证和权限](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

有关 Microsoft 365 安全中心中的 ASR 规则部署详细信息，请参阅监视 [和管理 ASR 规则部署和检测](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)。

**相关主题**

* [确保设备配置正确](configure-machines.md)
* [获取载入到 Microsoft Defender for Endpoint 的设备](configure-machines-onboarding.md)
* [监视 Microsoft Defender 终结点安全基线的合规性](configure-machines-security-baseline.md)
