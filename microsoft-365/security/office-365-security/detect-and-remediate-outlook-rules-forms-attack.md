---
title: 检测并修正Outlook和自定义表单注入攻击。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MET150
description: 了解如何识别和修正 Outlook 中的自定义窗体注入Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6c715552fedeefeb87206d889aa448609e8d7f60
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157634"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>检测和修正Outlook和自定义窗体注入攻击

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**摘要** 了解如何识别和修正 Outlook 中的自定义窗体注入Office 365。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>什么是规则Outlook自定义窗体注入攻击？

攻击者获取对组织的访问权限后，将尝试建立一个保留的页脚，或在发现后重新进入。 此活动称为 *建立持久性机制*。 攻击者可通过两种方法Outlook持久性机制：

- 通过利用Outlook规则。
- 将自定义表单注入Outlook。

重新安装Outlook，甚至向受影响的人员提供一台新计算机将没有帮助。 当新安装的 Outlook连接到邮箱时，所有规则和表单都从云中同步。 规则或表单通常设计为在本地计算机上运行远程代码和安装恶意软件。 恶意软件窃取凭据或执行其他非法活动。

好消息是：如果你将Outlook客户端修补为最新版本，则你无法易受威胁，因为当前 Outlook 客户端默认设置会阻止这两种机制。

攻击通常遵循以下模式：

**规则攻击**：

1. 攻击者窃取了用户的凭据。

2. 攻击者登录该用户的邮箱Exchange或 (Exchange Online内部部署Exchange) 。

3. 攻击者在邮箱中创建了转发收件箱规则。 当邮箱从攻击者收到匹配规则条件的特定邮件时，将触发转发规则。 规则条件和邮件格式是互为定制的。

4. 攻击者将触发器电子邮件发送到遭到入侵的邮箱，不知情的用户仍正常使用该邮箱。

5. 当邮箱收到与规则条件匹配的邮件时，将应用该规则的操作。 通常，规则操作是在远程 WebDAV (启动) 应用程序。

6. 通常，应用程序在用户计算机上安装恶意软件 (例如[，PowerShell 的) 。](https://www.powershellempire.com/)

7. 恶意软件允许攻击者从 (窃取用户) 密码或其他凭据，并执行其他恶意活动。

**表单攻击**：

1. 攻击者窃取了用户的凭据。

2. 攻击者登录该用户的邮箱Exchange或 (Exchange Online内部部署Exchange) 。

3. 攻击者将自定义邮件表单模板用户邮箱中。 当邮箱收到来自攻击者的特定邮件（要求邮箱加载自定义表单）时，将触发自定义表单。 自定义窗体和邮件格式是互为定制的。

4. 攻击者将触发器电子邮件发送到遭到入侵的邮箱，不知情的用户仍正常使用该邮箱。

5. 当邮箱收到邮件时，邮箱将加载所需的表单。 该表单在远程 WebDAV (启动) 应用程序。

6. 通常，应用程序在用户计算机上安装恶意软件 (例如[，PowerShell 的) 。](https://www.powershellempire.com/)

7. 恶意软件允许攻击者从 (窃取用户) 密码或其他凭据，并执行其他恶意活动。

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>规则和自定义窗体注入攻击看起来可能Office 365？

这些持久性机制不太可能被你的用户注意到，并且在某些情况下甚至对它们不可见。 本文将告诉你如何查找下面列出的七个泄露 (标记) 之一。 如果发现其中任何一种，则需要采取修正步骤。

- **规则泄露的指示器**：
  - 规则操作是启动应用程序。
  - 规则 引用 EXE、ZIP 或 URL。
  - 在本地计算机上，查找源自 PID 的新Outlook进程。

- **自定义表单泄露的指示器**：
  - 呈现为其自己的邮件类的自定义表单。
  - 邮件类包含可执行代码。
  - 通常，恶意表单存储在个人窗体库或收件箱文件夹中。
  - 表单名为 IPM。注意。[自定义名称]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>查找此攻击的迹象并确认它的步骤

可以使用以下任一方法确认攻击：

- 使用客户端手动检查每个邮箱Outlook表单。 此方法很全面，但一次只能检查一个邮箱。 如果你有许多用户要检查，此方法可能非常耗时，并且还可能会感染你使用的计算机。

- 使用 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 脚本自动转储租赁中所有用户的所有邮件转发规则和自定义表单。 这是最快速、最安全的方法，开销最少。

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>使用客户端确认规则Outlook攻击

1. 以用户Outlook客户端打开用户。 用户可能需要你的帮助来检查其邮箱上的规则。

2. 请参阅[使用规则管理](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)电子邮件一文，了解如何在规则中打开规则Outlook。

3. 查找用户未创建的规则，或任何具有可疑名称的意外规则或规则。

4. 在规则说明中查找启动和应用程序的规则操作，或引用.EXE、.ZIP文件或启动 URL 的规则操作。

5. 查找开始使用新进程 ID Outlook进程。 请参阅[查找进程 ID。](/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>使用 Outlook 客户端确认表单攻击的步骤

1. 以用户Outlook用户打开客户端。

2. 按照"显示用户版本的开发人员["选项卡](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)中的步骤操作Outlook。

3. 打开窗体中现在可见的开发人员Outlook然后单击设计 **窗体**。

4. 从" **查找** " **列表中选择"收件箱** "。 查找任何自定义窗体。 自定义窗体很少见，因此，如果有任何自定义窗体，则值得更深入地查看。

5. 调查任何自定义表单，尤其是标记为隐藏的表单。

6. 打开任何自定义窗体，在"窗体"组中 **，单击"** 查看代码"以查看加载窗体时运行哪些内容。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>使用 PowerShell 确认规则和表单攻击的步骤

验证规则或自定义表单攻击的最简单方法就是运行Get-AllTenantRulesAndForms.ps1[ PowerShell ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) 脚本。 此脚本连接到租户中的每个邮箱，并转储所有规则和表单到两个.csv文件中。

#### <a name="pre-requisites"></a>先决条件

您需要具有全局管理员权限才能运行脚本，因为脚本连接到租赁中的每个邮箱以读取规则和表单。

1. 使用本地管理员权限登录到您将从中运行脚本的机器。

2. 下载或将Get-AllTenantRulesAndForms.ps1脚本GitHub脚本下载到将运行该脚本的文件夹。 脚本将为此文件夹创建两个日期标记文件，MailboxFormsExport-yyyy-mm-dd.csv和MailboxRulesExport-yyyy-mm-dd.csv。

3. 以管理员角色打开 PowerShell 实例，然后打开将脚本保存到的文件夹。

4. 运行此 PowerShell 命令行，如下所示 `.\Get-AllTenantRulesAndForms.ps1` .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>解释输出

- **MailboxRulesExport-*yyyy-mm-dd*.csv：** 检查每 (行一) 的规则，了解包含应用程序或可执行文件的操作条件：

  - **ActionType (列 A)**：如果看到值"ID_ACTION_CUSTOM"，则规则可能是恶意的。

  - **IsPotentiallyMalicious (D**) ：如果此值为"TRUE"，则规则可能是恶意的。

  - **ActionCommand (** 列 G) ：如果此列列出了应用程序或具有 .exe 或 .zip 扩展名的任何文件，或引用 URL 的未知条目，则规则可能是恶意的。

- **MailboxFormsExport-*yyyy-mm-dd*.csv：** 通常，很少使用自定义窗体。 如果在此工作簿中发现任何内容，则打开该用户的邮箱并检查表单本身。 如果你的组织没有有意地将文件放在那里，则可能是恶意的。

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>如何停止和修正Outlook和表单攻击

如果发现这些攻击的任何证据，修正很简单，只需从邮箱中删除规则或表单。 为此，可以使用 Outlook 或远程 PowerShell 删除规则。

### <a name="using-outlook"></a>使用 Outlook

1. 标识用户已与设备一起使用的所有Outlook。 它们都需要清除潜在的恶意软件。 在清理所有设备之前，不允许用户登录并使用电子邮件。

2. 按照删除 [每个设备的规则](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) 中的步骤操作。

3. 如果你不确定存在其他恶意软件，可以在设备上格式化并重新安装所有软件。 对于移动设备，你可以按照制造商步骤将设备重置为出厂映像。

4. 安装最新版本的 Outlook。 请记住，当前版本的 Outlook默认情况下会阻止这两种类型的攻击。

5. 删除邮箱的所有脱机副本后，重置用户密码 (使用高质量的) 并按照为用户设置多重身份验证（如果尚未启用 MFA）中的步骤操作。 [](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) 这可确保不会通过其他方式公开用户的凭据， (例如钓鱼或密码重新使用) 。

### <a name="using-powershell"></a>使用 PowerShell

有两个远程 PowerShell cmdlet 可用于删除或禁用危险规则。 只需按照步骤操作。

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>邮箱服务器上邮箱Exchange步骤

1. 连接远程 PowerShell Exchange服务器。 按照使用远程[PowerShell 连接Exchange服务器中的步骤操作](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)。

2. 如果要从邮箱中完全删除单个规则、多个规则或所有规则，请使用 [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) cmdlet。

3. 如果要保留规则及其内容以进一步调查，请使用 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet。

#### <a name="steps-for-mailboxes-in-exchange-online"></a>邮箱管理中的Exchange Online

1. 按照[PowerShell 连接 Exchange Online中的步骤操作](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 如果要从邮箱中完全删除单个规则、多个规则或所有规则，请使用 [Remove-Inbox Rule](/powershell/module/exchange/Remove-InboxRule) cmdlet。

3. 如果要保留规则及其内容以进一步调查，请使用 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet。

## <a name="how-to-minimize-future-attacks"></a>如何最大程度地减少未来攻击

### <a name="first-protect-your-accounts"></a>首先：保护你的帐户

规则和表单攻击仅在攻击者窃取或破坏用户帐户之一后使用。 因此，阻止对组织使用这些攻击的第一步是主动保护你的用户帐户。 帐户遭到入侵的一些最常见方式是通过网络钓鱼或密码钓鱼 [攻击](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)。

保护用户帐户（尤其是管理员帐户）的最好办法就是为用户设置多重 [身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。 您还应该：

- 监视如何访问 [和使用用户帐户](/azure/active-directory/active-directory-view-access-usage-reports)。 虽然无法阻止初始泄露，但通过提前检测漏洞，可以缩短泄露的持续时间和影响。 可以使用[以下Office 365 云应用安全监视](/cloud-app-security/what-is-cloud-app-security)帐户和异常活动警报：

  - **多次登录失败尝试**：此策略配置文件您的环境，当用户在一个会话中执行多个与已了解基线（可能指示尝试的泄露）失败的登录活动时，将触发警报。

  - **不可能旅行**：此策略将配置文件您的环境，当在一个时间段内从不同位置检测到活动的时间短于两个位置之间的预期旅行时间时，将触发警报。 这可能表示其他用户使用相同的凭据。 检测此异常行为需要 7 天的初始学习期，在此期间它将了解新用户的活动模式。

  - 用户 (执行的异常模拟活动) ：此策略配置文件您的环境，当用户在一个会话中执行与所了解的基线（可能指示尝试的泄露）的多个模拟活动时，将触发警报。

- 使用安全分数等[Office 365](https://securescore.office.com/)管理帐户安全配置和行为。

### <a name="second-keep-your-outlook-clients-current"></a>第二步：Outlook客户端保持最新

2013 和 2016 的 Outlook 和 2016 的完全更新和修补版本默认禁用"启动应用程序"规则/表单操作。 这将确保即使攻击者违反了帐户，也会阻止该规则及表单操作。 你可以按照安装最新更新中的步骤安装最新更新Office[修补程序](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。

下面是适用于您的 Outlook 2013 和 2016 客户端的修补程序版本：

- **Outlook 2016**：16.0.4534.1001 或更大。

- **Outlook** 2013：15.0.4937.1000 或更大。

有关单个安全修补程序详细信息，请参阅：

- [Outlook 2016安全修补程序](https://support.microsoft.com/help/3191883)

- [Outlook 2013 安全修补程序](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>第三：监视Outlook客户端

请注意，即使安装了修补程序和更新，攻击者也可能会更改本地计算机配置以重新启用"启动应用程序"行为。 可以使用高级 [组策略管理](/microsoft-desktop-optimization-pack/agpm/) 监视和强制执行客户端上的本地计算机策略。

通过使用如何使用 64 位版本的 Windows 中的信息，可以查看"启动应用程序["是否通过注册表中的替代重新启用](https://support.microsoft.com/help/305097)。 检查以下子项：

- **Outlook 2016**：`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013：**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

查找 EnableUnsafeClientMailRules 密钥。 如果安全修补程序存在且设置为 1，则Outlook修补程序已被覆盖，并且计算机易受窗体/规则攻击。 如果值为 0，则禁用"启动应用程序"操作。 如果已安装更新和修补版本的 Outlook并且此注册表项不存在，则系统不会受到这些攻击。

使用本地安装Exchange应考虑阻止没有修补程序的Outlook版本。 有关此过程的详细信息，请参阅文章 Configure [Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help)。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>像网络安全专家那样保护 Microsoft 365

你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。 使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。

- 需要在前 30 天完成的任务。 它们立即生效，并且对用户影响较低。

- 要在 90 天内完成的任务。这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。

- 90 天后。这些增强功能基于前 90 天的工作构建。

## <a name="see-also"></a>另请参阅：

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector 提供了如何定义规则Outlook的详细说明。

- [有关 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)的 Sensepost 博客上的 MAPI over HTTP 和 Mailrule Pwnage 讨论了一种称为 Ruler 的工具，该工具允许您通过规则Outlook邮箱。

- [Outlook关于](https://sensepost.com/blog/2017/outlook-forms-and-shells/)Forms 威胁矢量的 Sensepost 博客上显示表单和 Shell。

- [标尺代码库](https://github.com/sensepost/ruler)

- [泄露标尺指示器](https://github.com/sensepost/notruler/blob/master/iocs.md)