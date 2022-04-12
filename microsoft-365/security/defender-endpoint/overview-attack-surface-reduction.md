---
title: '了解并使用攻击面减少 (ASR) '
ms.reviewer: ''
description: 了解Microsoft Defender for Endpoint的攻击面减少功能。
keywords: asr， 攻击面减少， 攻击面减少规则， Microsoft Defender for Endpoint， microsoft defender， 防病毒， av， windows defender
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 5c3724989db1bd8e6389b8a70ba591ce4e109390
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787701"
---
# <a name="understand-and-use-attack-surface-reduction-capabilities"></a>了解并使用攻击面减少功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

攻击面是组织容易受到网络威胁和攻击的所有位置。 Defender for Endpoint 包含多种功能，可帮助减少攻击面。 观看以下视频，了解有关攻击面减少的详细信息。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="configure-attack-surface-reduction-capabilities"></a>配置攻击面减少功能

若要在环境中配置攻击面减少，请执行以下步骤：

1. [为Microsoft Edge启用基于硬件的隔离](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)。

2. 启用应用程序控制。

   1. 在Windows中查看基本策略。 请参阅 [示例基本策略](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。
   2. 请参阅[Windows Defender应用程序控制设计指南](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。
   3. 请参阅[部署Windows Defender应用程序控制 (WDAC) 策略](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。

3. [启用受控文件夹访问权限](enable-controlled-folders.md)。

4. [启用网络保护](enable-network-protection.md)。

5. [启用攻击保护](enable-exploit-protection.md)。

6. [部署攻击面减少规则](attack-surface-reduction-rules-deployment.md)。

7. 设置网络防火墙。

   1. 获取具有[高级安全性的Windows Defender防火墙](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)的概述。
   2. 使用[Windows Defender防火墙设计指南](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)确定要如何设计防火墙策略。
   3. 使用[Windows Defender防火墙部署指南](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)设置具有高级安全性的组织防火墙。

> [!TIP]
> 在大多数情况下，在配置攻击面减少功能时，可以从以下几种方法中进行选择：
>
> - Microsoft Endpoint Manager (现在包括Microsoft Intune和Microsoft Endpoint Configuration Manager) 
> - 组策略
> - PowerShell cmdlet

## <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>测试攻击面减少Microsoft Defender for Endpoint

作为组织安全团队的一部分，可以配置攻击面减少功能以在审核模式下运行，以了解其工作原理。 可以在审核模式下启用以下 ASR 安全功能：

- 攻击面减少规则
- 漏洞保护
- 网络保护
- 和受控文件夹访问

审核模式允许你查看如果启用了该功能 *将* 发生的情况的记录。

测试功能的工作原理时，可以启用审核模式。 仅为测试启用审核模式有助于防止审核模式影响业务线应用。 还可以了解在一定时间段内发生了多少次可疑的文件修改尝试。

这些功能不会阻止或阻止应用、脚本或文件被修改。 但是，Windows事件日志将记录事件，就像功能已完全启用一样。 使用审核模式时，可以查看事件日志，查看如果启用该功能会对该功能产生的影响。

若要查找审核的条目，请转到 **应用程序和服务** \> **Microsoft** \> **Windows Windows Defender** \>  \> **操作**。

使用 Defender for Endpoint 获取每个事件的更多详细信息。 这些详细信息对于调查攻击面减少规则特别有帮助。 使用 Defender for Endpoint 控制台可以 [调查警报时间线和调查方案中的问题](investigate-alerts.md)。

可以使用 组策略、PowerShell 和配置服务提供商 (CSP) 启用审核模式。

> [!TIP]
> 还可以访问 [demo.wd.microsoft.com 的Windows Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)测试场网站，确认功能是否正常工作，并了解其工作原理。

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

| 审核选项 | 如何启用审核模式 | 如何查看事件 |
|---|---|---|
| 审核适用于所有事件 | [启用受控文件夹访问](enable-controlled-folders.md) | [受控文件夹访问事件](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer) |
| 审核适用于单个规则 | [步骤 1：使用审核模式测试 ASR 规则](attack-surface-reduction-rules-deployment-test.md#step-1-test-asr-rules-using-audit) | [步骤 2：了解攻击面减少规则报告页](attack-surface-reduction-rules-deployment-test.md#step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal) |
| 审核适用于所有事件 | [启用网络保护](enable-network-protection.md) | [网络保护事件](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer) |
| 审核适用于各个缓解措施 | [启用漏洞保护](enable-exploit-protection.md) | [攻击保护事件](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer) |

### <a name="attack-surface-reduction-asr-rules"></a>攻击面减少（ASR）规则

预先定义了攻击面减少 (ASR) 规则，以强化常见的已知攻击面。 有几种方法可用于实现攻击面减少规则。 以下攻击面减少 (ASR) 规则部署主题中介绍了首选方法：

- [攻击面减少 (ASR) 规则部署概述](attack-surface-reduction-rules-deployment.md)
- [计划攻击面减少 (ASR) 规则部署](attack-surface-reduction-rules-deployment-plan.md)
- [测试攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-test.md)
- [启用攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-implement.md)
- [操作攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-operationalize.md)

## <a name="view-attack-surface-reduction-events"></a>查看攻击面减少活动

查看事件查看器中的攻击面减少事件，以监视哪些规则或设置正常工作。 还可以确定任何设置是否过于“干扰”或影响日常工作流。

评估功能时，查看事件很方便。 可以为功能或设置启用审核模式，然后查看如果完全启用这些功能或设置会发生什么情况。

本部分列出了所有事件及其关联的功能或设置，并介绍了如何创建自定义视图以筛选到特定事件。

如果有 E5 订阅[并使用Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，请在Windows 安全中心中详细报告事件、块和警告。

### <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>使用自定义视图查看攻击面减少功能

在Windows 事件查看器中创建自定义视图，以仅查看特定功能和设置的事件。 最简单的方法是将自定义视图导入为 XML 文件。 可以直接从此页面复制 XML。

还可以手动导航到与该功能相对应的事件区域。

#### <a name="import-an-existing-xml-custom-view"></a>导入现有 XML 自定义视图

1. 创建空.txt文件并将要使用的自定义视图的 XML 复制到.txt文件中。 针对要使用的每个自定义视图执行此操作。 按如下所示重命名文件 (确保将类型从.txt更改为.xml) ：
    - 受控文件夹访问事件自定义视图： *cfa-events.xml*
    - 攻击保护事件自定义视图： *ep-events.xml*
    - 攻击面减少事件自定义视图： *asr-events.xml*
    - 网络/保护事件自定义视图： *np-events.xml*

2. 在"开始"菜单中键入 **事件查看器** 并打开 **事件查看器**。

3. 选择 **操作** \> **导入自定义视图...**

   > [!div class="mx-imgBorder"]
   > ![突出显示“偶数查看器”窗口左侧的“导入自定义”视图的动画。](images/events-import.gif)

4. 导航到提取所需自定义视图的 XML 文件的位置，然后选择它。

5. 选择 **“打开”**。

6. 它将创建一个自定义视图，用于筛选以仅显示与该功能相关的事件。

#### <a name="copy-the-xml-directly"></a>直接复制 XML

1. 在"开始"菜单中键入 **事件查看器** 并打开Windows **事件查看器**。

2. 在左侧面板的 **“操作”** 下，选择 **“创建自定义视图...”**

   > [!div class="mx-imgBorder"]
   > ![在事件查看器窗口上突出显示“创建自定义视图”选项的动画。](images/events-create.gif)

3. 转到“XML”选项卡， **并手动选择“编辑查询**”。 如果使用 XML 选项，则会看到一条警告，指出无法使用 **“筛选器”** 选项卡编辑查询。 选择“**是**”。

4. 粘贴要从 XML 部分筛选事件的功能的 XML 代码。

5. 选择“确定”。 为筛选器指定名称。 这将创建一个自定义视图，该视图筛选为仅显示与该功能相关的事件。

#### <a name="xml-for-attack-surface-reduction-rule-events"></a>用于攻击面减少规则事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-controlled-folder-access-events"></a>受控文件夹访问事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-exploit-protection-events"></a>用于攻击保护事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-network-protection-events"></a>用于网络保护事件的 XML

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

### <a name="list-of-attack-surface-reduction-events"></a>攻击面减少事件列表

所有攻击面减少事件都位于 **Microsoft > Windows>应用程序和服务日志** 下，然后位于下表中列出的文件夹或提供程序下。

可以在Windows事件查看器中访问这些事件：

1. 打开 **“开始”** 菜单并键入 **事件查看器**，然后选择 **事件查看器** 结果。
2. 展开 **应用程序和服务日志> Microsoft > Windows**，然后转到下表中“**提供程序/源**”下列出的文件夹。
3. 双击子项以查看事件。 滚动浏览事件以查找要查找的事件。

   ![显示使用事件查看器的动画。](images/event-viewer.gif)

<br>

****

|功能|提供程序/源|事件 ID|描述|
|---|---|:---:|---|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |1|ACG 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |2|ACG 强制|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |3|不允许子进程审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |4|不允许子进程阻止|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |5|阻止低完整性图像审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |6 |阻止低完整性图像阻止|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |7 |阻止远程图像审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |8 |阻止远程图像阻止|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |9 |禁用 win32k 系统调用审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |10 |禁用 win32k 系统调用阻止|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |11|代码完整性防护审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |12 |代码完整性防护阻止|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |13|EAF 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |14 |EAF 强制|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |15 |EAF+ 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |16|EAF+ 强制|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |17 |IAF 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |18 |IAF 强制|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |19|ROP StackPivot 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |20|ROP StackPivot 强制|
|漏洞保护|Security-Mitigations (内核模式/用户模式) | 21|ROP CallerCheck 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |22|ROP CallerCheck 强制|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |23|ROP SimExec 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |24|ROP SimExec 强制|
|漏洞保护|WER-诊断|5|CFG 阻止|
|漏洞保护|Win32K (操作) |260|不受信任的字体|
|网络保护|Windows Defender (操作) |5007|更改设置时的事件|
|网络保护|Windows Defender (操作) |1125|网络保护在审核模式下触发时的事件|
|网络保护|Windows Defender (操作) |1126|网络保护在阻止模式下触发时的事件|
|文件夹限制访问|Windows Defender (操作) |5007|更改设置时的事件|
|文件夹限制访问|Windows Defender (操作) |1124|已审核的受控文件夹访问事件|
|文件夹限制访问|Windows Defender (操作) |1123|阻止的受控文件夹访问事件|
|文件夹限制访问|Windows Defender (操作) |1127|阻止的受控文件夹访问扇区写入块事件|
|文件夹限制访问|Windows Defender (操作) |1128|审核的受控文件夹访问扇区写入块事件|
|攻击面减少|Windows Defender (操作) |5007|更改设置时的事件|
|攻击面减少|Windows Defender (操作) |1122|在审核模式下触发规则时的事件|
|攻击面减少|Windows Defender (操作) |1121|规则在阻止模式下触发时的事件|

>[!NOTE]
> 从用户的角度来看，ASR 警告模式通知作为攻击面减少规则的Windows Toast 通知。
>
> 在 ASR 中，网络保护仅提供审核和阻止模式。

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a>详细了解攻击面减少的资源

如视频中所述，Defender for Endpoint 包含多个攻击面减少功能。 使用以下资源了解详细信息：

| 文章 | 说明 |
|:---|:---|
| [基于硬件的隔离](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | 在系统启动和运行时保护和维护系统的完整性。 通过本地和远程证明验证系统完整性。 对Microsoft Edge使用容器隔离来帮助防范恶意网站。 |
| [应用程序控制](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | 使用应用程序控件，使应用程序必须赢得信任才能运行。 |
| [受控文件夹访问](controlled-folders.md) | 帮助防止恶意或可疑应用 (包括文件加密勒索软件恶意软件)  (需要Microsoft Defender 防病毒) 对密钥系统文件夹中的文件进行更改。 |
| [网络保护](network-protection.md) | 将保护扩展到组织的设备上的网络流量和连接。  (需要Microsoft Defender 防病毒) 。 |
| [漏洞保护](exploit-protection.md) | 帮助保护组织使用的操作系统和应用免受攻击。 攻击保护还适用于第三方防病毒解决方案。 |
| [设备控制](device-control-report.md) | 通过监视和控制组织中设备上使用的媒体（如可移动存储和 USB 驱动器）来防止数据丢失。 |
| [攻击面减少 (ASR) 规则部署指南](attack-surface-reduction-rules-deployment.md) | 介绍部署攻击面减少规则的概述信息和先决条件。 |
| [计划攻击面减少 (ASR) 规则部署](attack-surface-reduction-rules-deployment-plan.md) | 列出了用于攻击面减少规则部署的建议步骤。 |
| [测试攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-test.md) | 提供使用审核模式测试攻击面减少规则的步骤。 |
| [启用攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-implement.md) | 显示将攻击面减少规则从测试 (审核) 模式转换为已启用的活动 (阻止) 模式的步骤。 |
| [操作攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-operationalize.md) | 提供有关日常评审和维护活动的信息。 |
| [攻击面减少 (ASR) 规则参考](attack-surface-reduction-rules-reference.md) | 提供有关每个攻击面减少规则的详细信息。 |
| [攻击面减少规则](attack-surface-reduction.md) | 使用有助于停止恶意软件的智能规则，减少应用程序中的漏洞（攻击面）。  (需要Microsoft Defender 防病毒) 。 |
