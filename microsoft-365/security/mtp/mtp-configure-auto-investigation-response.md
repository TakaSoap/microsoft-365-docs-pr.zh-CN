---
title: 在 Microsoft 威胁防护中配置自动调查和响应功能
description: 在 Microsoft 威胁防护中使用自我修复配置自动调查和响应
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 10/07/2020
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection: M365-security-compliance.
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: f904512f9fd07e2065f3d27a5bd5adc56a3565d5
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384791"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>在 Microsoft 威胁防护中配置自动调查和响应功能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 威胁防护包括功能强大的 [自动化调查和响应功能](mtp-autoir.md) ，可将安全操作团队节省大量时间和精力。 通过自我修复功能，这些功能模仿安全分析员调查和响应威胁的步骤，且速度更快，并且能够更好地进行扩展。 本文介绍如何在 Microsoft 威胁防护中配置自动调查和响应。

若要配置自动调查和响应功能，请按照以下步骤操作：

1. [查看先决条件](#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)。
2. [查看或更改设备组的自动化级别](#review-or-change-the-automation-level-for-device-groups)。
3. [查看 Office 365 中的安全和通知策略](#review-your-security-and-alert-policies-in-office-365)。
4. [请确保已启用 Microsoft 威胁防护](#make-sure-microsoft-threat-protection-is-turned-on)。

然后，在完成所有设置后，请 [在操作中心中查看挂起和已完成的操作](#review-pending-and-completed-actions-in-the-action-center)。 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>在 Microsoft 威胁防护中进行自动调查和响应的先决条件

|要求 |详细信息 |
|--|--|
|订阅要求 |其中一个订阅： <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 安全<br/>-Microsoft 365 A5 安全性<br/>-Office 365 E5 plus 企业移动性 + 安全性 E5，外加 Windows E5<br/><br/>请参阅 [Microsoft 威胁防护许可要求](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)。|
|网络要求 |- 已启用 [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)<br/>- [Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 配置<br/>- [与 Azure ATP 集成的 Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 计算机要求 |-Windows 10 版本1709或更高版本安装的 (请参阅 [Windows 10 发行版信息](https://docs.microsoft.com/windows/release-information/)) 并配置以下威胁 protection 服务：<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|对电子邮件内容和 Office 文件的保护 |配置了[Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|权限 |-若要配置自动调查和响应功能，必须在任何 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 管理中心 () 中分配全局管理员或安全管理员角色 [https://admin.microsoft.com](https://admin.microsoft.com) 。<br/><br/>-若要获取使用自动调查和响应功能（如审阅、批准或拒绝待处理的操作）所需的权限，请参阅 [操作中心任务所需的权限](mtp-action-center.md#required-permissions-for-action-center-tasks)。 |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>查看或更改设备组的自动化级别

自动调查是否运行，以及是否自动或仅在为设备批准时采取更正措施取决于特定设置，例如组织的设备组策略。 查看为设备组策略设置的自动化级别。

1. 请转到 Microsoft Defender 安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 并登录。

2. 转到 "**设置**  >  **权限**"  >  **设备组**。 

3. 查看设备组策略。 尤其要注意的是，请查看 " **修正级别** " 列。 我们建议 **自动使用完全修正的威胁**。  您可能需要创建或编辑设备组，以获取所需的自动化级别。 若要获取有关此任务的帮助，请参阅以下文章：

   - [威胁的修正方式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [创建和管理设备组](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>查看 Office 365 中的安全和通知策略

Microsoft 提供了可帮助确定特定风险的内置 [通知策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 。 这些风险包括 Exchange 管理员权限滥用、恶意软件活动、潜在的外部和内部威胁以及信息治理风险。 某些警报可以触发 [Office 365 中的自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 请确保正确配置了 [Office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 功能。

尽管某些通知和安全策略可以触发自动调查，但不会为电子邮件和内容自动采取任何补救措施。 相反，电子邮件和电子邮件内容等待由 [操作中心](mtp-action-center.md)中的安全操作团队批准的所有修正操作。

Office 365 中的安全设置可帮助保护电子邮件和内容。 若要查看或更改这些设置，请遵循 [针对威胁的保护](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)指南。

1. 在 Microsoft 365 安全中心 ([https://security.microsoft.com/](https://security.microsoft.com/)) 中，转到 "策略" "**策略**  >  **威胁防护**"。

2. 请确保配置了以下所有策略。 若要获取帮助和建议，请参阅 [防止威胁](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。

   - [ (Office 365) 的反恶意软件 ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [ATP 反网络钓鱼 (Office 365) ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [ (Office 365) 的 ATP 安全附件 ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [ (Office 365) 的 ATP 安全链接 ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [ (Office 365) 的反垃圾邮件 ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. 请确保启用了 [Office 365 的适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) 。

5. 确保 [电子邮件保护的零小时自动清除](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) 有效。 

8.  (这是可选的。 ) 在 Microsoft 365 合规性中心 () 中查看 [Office 365 警报策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 。 "威胁管理" 类别中有几个默认的通知策略。 其中一些警报可触发自动调查和响应。 若要了解详细信息，请参阅 [默认通知策略](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)。
 
## <a name="make-sure-microsoft-threat-protection-is-turned-on"></a>确保已打开 Microsoft 威胁防护

1. 请转到 Microsoft 365 安全中心 ([https://security.microsoft.com](https://security.microsoft.com)) 并登录。

2. 在导航窗格中，查找 " **事件**"、" **操作中心**" 和 " **搜寻**"，如下图所示：

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP 打开":::

   - 如果你看到 **事件**、 **操作中心**和 **搜寻**，则会打开 Microsoft 威胁防护。 继续执行下一过程， [查看或更改设备组的自动化级别](#review-or-change-the-automation-level-for-device-groups)。

   - 如果你 *没有* 看到 **事件**、 **操作中心**或 **搜寻**，则可能无法打开 Microsoft 威胁防护。 在这种情况下，请继续执行下一步。

3. 在导航窗格中，选择 "**设置**  >  **Microsoft 威胁防护**"。 确认已打开 Microsoft 威胁防护。 

   需要帮助? 请参阅 [打开 Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)。

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>在操作中心中查看挂起和已完成的操作

在 Microsoft 威胁防护中配置了自动调查和响应之后，下一步是访问操作中心 ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) 。 在这里，您可以查看和批准挂起的操作，并查看自动执行的修正操作。 

[访问操作中心](mtp-action-center.md)。
