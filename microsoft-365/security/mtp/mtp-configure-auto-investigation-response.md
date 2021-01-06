---
title: 在 Microsoft 365 Defender 中配置自动调查和响应功能
description: 在 Microsoft 365 Defender 中通过自我修复配置自动调查和响应
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: b83bbf560e39fd268dd6be361c9928242357815f
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759906"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>在 Microsoft 365 Defender 中配置自动调查和响应功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender 包括强大的自动调查和响应 [功能](mtp-autoir.md) ，可节省安全运营团队的时间和精力。 借助自我修复，这些功能会模仿安全分析员为调查和响应威胁而执行的步骤，只是速度更快且扩展能力更高。 本文介绍如何在 Microsoft 365 Defender 中配置自动调查和响应。

若要配置自动调查和响应功能，请按照以下步骤操作：

1. [查看先决条件](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [查看或更改设备组的自动化级别](#review-or-change-the-automation-level-for-device-groups)。
3. [查看 Office 365 中的安全和警报策略](#review-your-security-and-alert-policies-in-office-365)。
4. [确保 Microsoft 365 Defender 已打开](#make-sure-microsoft-365-defender-is-turned-on)。

然后，完成所有设置后，在操作中心中查看挂起和 [已完成的操作](#review-pending-and-completed-actions-in-the-action-center)。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender 中自动调查和响应的先决条件

|要求 |详细信息 |
|--|--|
|订阅要求 |订阅之一： <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E5 安全版</li><li>Microsoft 365 A5 安全性</li><li>Office 365 E5 以及企业移动性 + 安全性 E5 以及 Windows E5</li></ul><p> 请参阅 [Microsoft 365 Defender 许可要求](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)。|
|网络要求 |<ul><li>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 已启用</li><li>[已配置 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</li><li>[Microsoft Defender 标识集成](https://docs.microsoft.com/cloud-app-security/mdi-integration)</li></ul>|
|Windows 计算机要求 |Windows 10 版本 1709 或更高版本 (请参阅 [Windows 10](https://docs.microsoft.com/windows/release-information/) 版本) 配置了以下威胁防护服务：<ul><li>[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</li><li>[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul>|
|保护电子邮件内容和 Office 文件 |[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) 配置 |
|权限 |<ul><li>若要配置自动调查和响应功能，必须在 Azure Active Directory () 或 Microsoft 365 管理中心 () 中分配全局管理员或 [https://portal.azure.com](https://portal.azure.com) [https://admin.microsoft.com](https://admin.microsoft.com) 安全管理员角色。</li><p><li>若要获取使用自动调查和响应功能（如审阅、批准或拒绝挂起的操作）所需的权限，请参阅操作中心任务所需的 [权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</li></ul>|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>查看或更改设备组的自动化级别

自动调查是否运行，以及是否自动执行修正操作，还是仅在批准设备后执行修正操作取决于某些设置，如组织的设备组策略。 查看为设备组策略设置的自动化级别。

1. 转到 Microsoft Defender 安全中心 [https://securitycenter.windows.com](https://securitycenter.windows.com) () 登录。

2. 转到 **"设置**  >  **权限设备**  >  **"组**。

3. 查看设备组策略。 特别是，查看修正 **级别** 列。 我们建议自动 **使用完全修正威胁**。  你可能需要创建或编辑设备组，以获得所需的自动化级别。 若要获取有关此任务的帮助，请参阅以下文章：

   - [如何修正威胁](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [创建和管理设备组](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>查看 Office 365 中的安全和警报策略

Microsoft 提供可帮助识别 [特定风险的](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 内置警报策略。 这些风险包括 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 某些警报可能会触发 [Office 365 中的自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 确保 [正确配置了适用于 Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 的 Microsoft Defender 功能。

尽管某些警报和安全策略可能会触发自动调查，但不会自动对电子邮件和内容执行任何修正操作。 相反，电子邮件和电子邮件内容的所有修正操作都在等待操作中心中安全运营团队 [的批准](mtp-action-center.md)。

Office 365 中的安全设置有助于保护电子邮件和内容。 若要查看或更改这些设置，请按照"防止威胁 ["中的指南操作](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。

1. 在 Microsoft 365 安全中心 [https://security.microsoft.com/](https://security.microsoft.com/) () ，转到"**策略**  >  **威胁防护"。**

2. 确保配置了以下所有策略。 若要获取帮助和建议，请参阅["防止威胁"。](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

   - [Office 365 (反恶意软件) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Defender for Office 365) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Office 365 (安全附件) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Office 365 (安全链接) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Office 365 (反垃圾邮件) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)

3. 确保 [Microsoft Defender for Office 365 for SharePoint、OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) 和 Microsoft Teams 已打开。

4. 确保 [电子邮件保护的零时差自动](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) 清除有效。

5.  (可选。) Microsoft 365 合规中心内查看 [Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 警报 [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) () 。 多个默认警报策略都属于威胁管理类别。 其中一些警报可触发自动调查和响应。 若要了解更多信息，请参阅默认 [警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>确保 Microsoft 365 Defender 已打开

1. 转到 Microsoft 365 安全中心 [https://security.microsoft.com](https://security.microsoft.com) () 登录。

2. 在导航窗格中 **，查找事件**、**操作中心和****搜寻**，如下图所示：

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP 打开":::

   - 如果你看到 **事件**、**操作中心和****搜寻**，Microsoft 365 Defender 将打开。 请参阅 [本文 (查看](#review-or-change-the-automation-level-for-device-groups) 或更改设备组的自动化) 。

   - 如果你看不到 *事件***、操作****中心****或搜寻**，则 Microsoft 365 Defender 可能无法打开。 在这种情况下，继续执行下一 ([查看](#review-pending-and-completed-actions-in-the-action-center)挂起和已完成的操作，本文) 。

3. 在导航窗格中，选择 **"**  >  **设置 Microsoft 365 Defender"。** 确认 Microsoft 365 Defender 已打开。

   需要帮助？ 请参阅["打开 Microsoft 365 Defender"。](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>在操作中心中查看挂起和已完成的操作

在 Microsoft 365 Defender 中配置自动调查和响应后，下一步是访问操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () 。 在那里，你可以查看和批准挂起的操作，并查看自动或手动采取的修正操作。

[访问操作中心](mtp-action-center.md)。
