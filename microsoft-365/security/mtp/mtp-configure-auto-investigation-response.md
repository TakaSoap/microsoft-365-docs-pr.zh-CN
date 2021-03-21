---
title: 在 Microsoft 365 Defender 中配置自动调查和响应功能
description: 在 Microsoft 365 Defender 中通过自我修复配置自动调查和响应
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.date: 02/08/2021
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 05170c212e5e35d328e50dc0ee48d5f37e72869e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928660"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中配置自动调查和响应功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender 包括强大的自动调查和响应 [功能](mtp-autoir.md) ，可节省安全运营团队的时间和精力。 借助 [自我修复](mtp-autoir.md#how-automated-investigation-and-self-healing-works)功能，这些功能模仿安全分析师调查和响应威胁时要执行的步骤，只有更快且具有更多扩展能力。 本文介绍了如何在 Microsoft 365 Defender 中配置自动调查和响应。

若要配置自动调查和响应功能，请按照以下步骤操作：

1. [查看先决条件](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [查看或更改设备组的自动化级别](#review-or-change-the-automation-level-for-device-groups)。
3. [查看 Office 365 中的安全和警报策略](#review-your-security-and-alert-policies-in-office-365)。
4. [确保 Microsoft 365 Defender 已打开](#make-sure-microsoft-365-defender-is-turned-on)。

然后，完成所有设置后，在操作中心 [中查看和管理操作](mtp-autoir-actions.md)。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中自动调查和响应的先决条件

|要求 |详细信息 |
|:----|:----|
|订阅要求 |以下订阅之一： <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>- Microsoft 365 E5 安全中心<br/>- Microsoft 365 A5 安全中心<br/>- Office 365 E5 以及企业移动性 + 安全性 E5 以及 Windows E5<p> 请参阅 [Microsoft 365 Defender 许可要求](./prerequisites.md#licensing-requirements)。|
|网络要求 |- [已启用 Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)<br/>- [已配置 Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)<br/>- [Microsoft Defender for Identity 集成](/cloud-app-security/mdi-integration) |
|Windows 计算机要求 |- 已安装 Windows 10 版本 1709 或更高版本（请参阅 [Windows 10 发行信息](/windows/release-information/)） <br/>- 已配置以下威胁防护服务：<br/>- [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)<br/>- [Microsoft Defender 防病毒](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|保护电子邮件内容和 Office 文件 |[配置了 Microsoft Defender for Office 365](../office-365-security/office-365-atp.md#configure-atp-policies) |
|权限 | 若要配置自动调查和响应功能，必须在 Azure Active Directory () 或 [https://portal.azure.com](https://portal.azure.com) Microsoft 365 管理中心 () 中分配全局管理员或安全管理员 [https://admin.microsoft.com](https://admin.microsoft.com) 角色。<p>若要获取使用自动调查和响应功能（如审阅、批准或拒绝挂起操作）所需的权限，请参阅操作中心任务所需的 [权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。 |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>查看或更改设备组的自动化级别

自动调查是运行，还是自动执行修正操作，还是仅在设备批准后执行，取决于某些设置，例如组织的设备组策略。 查看为设备组策略设置的自动化级别。

1. 转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 并登录。
2. 转到"**设置**  >  **""权限**  >  **""设备组"。**
3. 查看设备组策略。 特别是，查看"修正 **级别"** 列。 我们建议使用 **完全 - 自动修正威胁**。  你可能需要创建或编辑设备组，以获得所需的自动化级别。 若要获取有关此任务的帮助，请参阅以下文章：
   - [如何修正威胁](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [创建和管理设备组](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>查看 Office 365 中的安全和警报策略

Microsoft 提供可帮助识别 [特定](../../compliance/alert-policies.md) 风险的内置警报策略。 这些风险包括 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 某些警报可能会触发 [Office 365 中的自动调查和响应](../office-365-security/office-365-air.md)。 确保正确 [配置了适用于 Office 365](../office-365-security/office-365-atp.md) 的 Microsoft Defender 功能。

尽管某些警报和安全策略可能会触发自动调查，但不会自动对电子邮件和内容执行任何修正操作。 相反，电子邮件和电子邮件内容的所有修正操作都等待操作中心的安全运营团队 [批准](mtp-action-center.md)。

Office 365 中的安全设置有助于保护电子邮件和内容。 若要查看或更改这些设置，请按照防止 [威胁中的指南操作](../office-365-security/protect-against-threats.md)。

1. 在 Microsoft 365 安全中心 [https://security.microsoft.com](https://security.microsoft.com) () ，转到"策略  >  **""威胁防护"。**
2. 确保已配置以下所有策略。 若要获取帮助和建议，请参阅 [防止威胁](../office-365-security/protect-against-threats.md)。
   - [Office 365 (反恶意软件) ](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection)
   - [Defender for Office 365) ](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Office 365 (安全附件) ](../office-365-security/protect-against-threats.md#atp-safe-attachments-policies)
   - [Office 365 (安全) ](../office-365-security/protect-against-threats.md#atp-safe-links-policies)
   - [Office 365 (反垃圾邮件) ](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection)
3. 确保 [Microsoft Defender for Office 365 for SharePoint、OneDrive](../office-365-security/protect-against-threats.md#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) 和 Microsoft Teams 已打开。
4. 确保 [电子邮件保护的零时差自动](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) 清除有效。
5.  (可选步骤。) Microsoft 365 合规中心中的 [Office 365](../../compliance/alert-policies.md) 警报策略 [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) () 。 多个默认警报策略都属于威胁管理类别。 其中一些警报可以触发自动调查和响应。 若要了解更多信息，请参阅默认 [警报策略](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>确保 Microsoft 365 Defender 已打开

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP 打开":::

1. 转到 Microsoft 365 安全中心 [https://security.microsoft.com](https://security.microsoft.com) () 登录。
2. 在导航窗格中，查找 **事件**、**操作中心和****搜寻**，如上图所示。
   - 如果 **看到事件、****操作中心和** 搜寻，Microsoft 365 Defender 将打开。 请参阅本文中查看 [或更改](#review-or-change-the-automation-level-for-device-groups) 设备组的自动化级别 (查看) 。
   - 如果你看不到 *事件***、操作****中心或** 搜寻，则 Microsoft 365 Defender 可能无法打开。 在这种情况下，请继续 [访问操作](mtp-action-center.md) 中心) 。
3. 在导航窗格中，**选择"设置**  >  **""Microsoft 365 Defender"。** 确认 Microsoft 365 Defender 已打开。 

> [!TIP]
> 需要帮助？ 请参阅[打开 Microsoft 365 Defender。](./mtp-enable.md)

## <a name="next-steps"></a>后续步骤

- [Microsoft 365 Defender 中的修正操作](mtp-remediation-actions.md)
- [访问操作中心](mtp-action-center.md)