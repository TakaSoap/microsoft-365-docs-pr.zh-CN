---
title: 在 Microsoft 365 Defender 中配置自动调查和响应功能
description: 使用自动修复功能配置自动调查和响应Microsoft 365 Defender
search.appverid: MET150
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 4ec06a96e345345560a2714fa7e23d91a6f5832f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314205"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中配置自动调查和响应功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender强大的自动[调查和响应功能](m365d-autoir.md)，可以节省安全运营团队的时间和精力。 借助 [自我修复](m365d-autoir.md#how-automated-investigation-and-self-healing-works)，这些功能可以模仿安全分析师为调查和响应威胁而执行的步骤，只是速度更快，并且具有更多扩展能力。

本文介绍如何通过以下步骤在 Microsoft 365 Defender配置自动<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">调查和</a>响应：

1. [查看先决条件](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [查看或更改设备组的自动化级别](#review-or-change-the-automation-level-for-device-groups)。
3. [在安全与警报策略中查看Office 365](#review-your-security-and-alert-policies-in-office-365)。
4. [请确保Microsoft 365 Defender打开。](#make-sure-microsoft-365-defender-is-turned-on)

然后，完成所有设置后，可以在操作中心查看和管理 [修正操作](m365d-autoir-actions.md)。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>在部署中自动调查和响应的先决条件Microsoft 365 Defender

<br>

****

|要求|详细信息|
|---|---|
|订阅要求|以下订阅之一： <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3加载项Microsoft 365 E5 安全性加载项</li><li>Microsoft 365 A3安全Microsoft 365 A5加载项一起添加</li><li>Office 365 E5 E5 企业移动性 + 安全性+E5 Windows E5</li></ul> <p> 请参阅[Microsoft 365 Defender许可要求](./prerequisites.md#licensing-requirements)。|
|网络要求|<ul><li>[已启用 Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)</li><li>[已配置的 Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)</li><li>[Microsoft Defender for Identity 集成](/cloud-app-security/mdi-integration)</li></ul>|
|Windows设备要求|<ul><li>Windows 11</li><li>Windows 10版本 1709 或更高版本 (请参阅 Windows [release information) ](/windows/release-information/)</li><li>配置了以下威胁防护服务：<ul><li>[Microsoft Defender for Endpoint](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender 防病毒](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|保护电子邮件内容和Office文件|[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies)配置|
|权限|若要配置自动调查和响应功能<https://portal.azure.com>，必须在 Azure Active Directory () 或 Microsoft 365 管理中心 () 中分配全局管理员或安全管理员<https://admin.microsoft.com>角色。 <p> 若要获取使用自动调查和响应功能（如审阅、批准或拒绝挂起操作）所需的权限，请参阅操作中心任务所需的 [权限](m365d-action-center.md#required-permissions-for-action-center-tasks)。|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>查看或更改设备组的自动化级别

自动调查是运行，还是自动执行修正操作，还是仅在设备批准后执行，取决于某些设置，如组织的设备组策略。 查看为设备组策略配置的自动化级别。

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 转到"**设置** > "下的"设置 **""****EndpointsDevice** >  组"。

3. 查看设备组策略。 特别是，查看"自动化 **级别"** 列。 我们建议使用 **完整 - 自动修正威胁**。  你可能需要创建或编辑设备组，以获得所需的自动化级别。 若要获取有关此任务的帮助，请参阅以下文章：
   - [如何修正威胁](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [创建和管理设备组](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>查看安全与警报策略Office 365

Microsoft 提供可帮助识别 [特定](../../compliance/alert-policies.md) 风险的内置警报策略。 这些风险包括Exchange权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 某些警报可能会触发[自动调查和响应Office 365](../office-365-security/office-365-air.md)。 请确保你的 [Defender for Office 365](../office-365-security/defender-for-office-365.md)功能配置正确。

尽管某些警报和安全策略可能会触发自动调查， *但不会自动* 对电子邮件和内容执行修正操作。 相反，电子邮件和电子邮件内容的所有修正操作都等待操作中心的安全运营团队 [批准](m365d-action-center.md)。

电子邮件中的安全设置Office 365保护电子邮件和内容。 若要查看或更改这些设置，请按照防止 [威胁中的指南操作](../office-365-security/protect-against-threats.md)。

1. 在 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>，转到"策略"**&"规则威胁** \> **策略"**。

2. 确保配置了以下所有策略。 若要获取帮助和建议，请参阅 [防范威胁](/microsoft-365/security/office-365-security/protect-against-threats)。
   - [反恶意软件](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [防钓鱼](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [安全附件](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [安全链接](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [反垃圾邮件](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)

3. 确保[保险箱"SharePoint、OneDrive](../office-365-security/mdo-for-spo-odb-and-teams.md)和Microsoft Teams附件"已打开。

4. 确保["零时差自动清除 (ZAP) Exchange Online](../office-365-security/zero-hour-auto-purge.md)有效。

5.  (可选步骤。) 在Office 365[中](../../compliance/alert-policies.md)查看你的Microsoft 365 合规中心 () [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 。 多个默认警报策略都属于威胁管理类别。 其中一些警报可以触发自动调查和响应。 若要了解更多信息，请参阅默认 [警报策略](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>确保Microsoft 365 Defender打开

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="如何确保Microsoft 365 Defender启用。" lightbox="../../media/mtp-enable/mtp-on.png":::

1. 登录到 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>

2. 在导航窗格中，查找事件&**警报**、搜寻和操作 **中心，如** 上图所示。
   - 如果看到事件 **&警报****、搜寻** 和操作中心，Microsoft 365 Defender打开。 请参阅 [本文的查看或更改设备组的](#review-or-change-the-automation-level-for-device-groups) 自动化级别部分。
   - 如果看不到 *事件***、** 操作中心 **或搜寻，** Microsoft 365 Defender可能未打开。 在这种情况下，请访问 [操作中心](m365d-action-center.md)。

> [!TIP]
> 需要帮助？ 请参阅[打开Microsoft 365 Defender](m365d-enable.md)。

## <a name="next-steps"></a>后续步骤

- [方法中的修正Microsoft 365 Defender](m365d-remediation-actions.md)
- [访问操作中心](m365d-action-center.md)
