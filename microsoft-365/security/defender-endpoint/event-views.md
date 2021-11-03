---
title: 查看攻击面减少活动
description: 导入自定义视图以查看攻击面减少事件。
keywords: 事件视图， 攻击防护， 审核， 审查， 事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 4ca3058db2f3f2e8ac79c7388d9a68ead1f48d38
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704843"
---
# <a name="view-attack-surface-reduction-events"></a>查看攻击面减少活动

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。

查看事件查看器中的攻击面减少事件，以监视哪些规则或设置正在工作。 您还可以确定任何设置是否过于"干扰"或影响您的日常工作流。

评估功能时，查看事件很方便。 您可以为功能或设置启用审核模式，然后查看在完全启用这些功能或设置后将发生的情况。

本文列出了所有事件及其关联的功能或设置，并介绍如何创建自定义视图以筛选到特定事件。

获取事件、阻止和警告的详细报告，Windows 安全中心 E5 订阅并使用[Microsoft Defender for Endpoint。](microsoft-defender-endpoint.md)

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>使用自定义视图查看攻击面减少功能

在事件查看器中Windows视图，以仅查看特定功能和设置的事件。 最简单的方法是将自定义视图导入为 XML 文件。 您可以直接从此页面复制 XML。

还可以手动导航到与功能对应的事件区域。

### <a name="import-an-existing-xml-custom-view"></a>导入现有 XML 自定义视图

1. 创建一个.txt文件，将想要使用的自定义视图的 XML 复制到.txt文件中。 为想要使用的每个自定义视图执行这一操作。 按如下所示重命名文件 (请确保将类型从 .txt 更改为 .xml) ：
    - 受控文件夹访问事件自定义视图 *：cfa-events.xml*
    - Exploit Protection 事件自定义视图 *：ep-events.xml*
    - 攻击面减少事件自定义视图 *：asr-events.xml*
    - 网络/保护事件自定义视图 *：np-events.xml*

2. 在 **事件查看器** 中键入"开始"菜单并打开 **事件查看器**。

3. 选择 **操作** \> **导入自定义视图...**

   > [!div class="mx-imgBorder"]
   > ![突出显示"Even viewer"窗口左侧的"导入自定义视图"的动画。](images/events-import.gif)

4. 导航到您为您想要的自定义视图提取 XML 文件的位置并选择它。

5. 选择 **“打开”**。

6. 它将创建一个自定义视图，该视图筛选为只显示与该功能相关的事件。

### <a name="copy-the-xml-directly"></a>直接复制 XML

1. 在 **事件查看器** 中键入"开始"菜单，然后Windows **事件查看器。**

2. 在左侧面板的"操作 **"下**，选择 **"创建自定义视图..."。**

   > [!div class="mx-imgBorder"]
   > ![突出显示"事件查看器"窗口上的"创建自定义视图"选项的动画。](images/events-create.gif)

3. 转到"XML"选项卡，然后选择"**手动编辑查询"。** 如果使用的是 XML 选项，则会看到一条警告，提示你无法使用"筛选器"选项卡编辑查询。 选择“**是**”。

4. 将您希望从中筛选事件的功能的 XML 代码粘贴到 XML 部分。

5. 选择“**确定**”。 为筛选器指定名称。 这将创建一个自定义视图，该视图筛选为只显示与该功能相关的事件。

### <a name="xml-for-attack-surface-reduction-rule-events"></a>攻击面减少规则事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>受控文件夹访问事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>Exploit Protection 事件的 XML

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

### <a name="xml-for-network-protection-events"></a>网络保护事件的 XML

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>攻击面减少事件列表

所有攻击面减少事件都位于 Microsoft > 服务日志> Windows **下，** 然后位于下表中列出的文件夹或提供程序下。

可以在事件查看器中Windows这些事件：

1. 打开" **开始"** 菜单并 **键入事件查看器**，然后选择 **事件查看器** 结果。
2. 展开 **Microsoft >** 应用程序和服务日志> Windows然后转到下表中的提供程序 **/源** 下列出的文件夹。
3. 双击子项以查看事件。 滚动浏览事件以查找你正在查找的事件。

   ![使用事件查看器显示动画。](images/event-viewer.gif)

<br>

****

|功能|提供程序/源|事件 ID|描述|
|---|---|:---:|---|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |1|ACG 审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |2|ACG 强制|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |3|不允许子进程审核|
|漏洞保护|Security-Mitigations (内核模式/用户模式) |4 |不允许子进程阻止|
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
|漏洞保护|Win32K (Operational) |260|不受信任的字体|
|网络保护|Windows Defender (操作) |5007|更改设置时的事件|
|网络保护|Windows Defender (操作) |1125|在审核模式下触发网络保护时的事件|
|网络保护|Windows Defender (操作) |1126|在阻止模式下触发网络保护时的事件|
|文件夹限制访问|Windows Defender (操作) |5007|更改设置时的事件|
|文件夹限制访问|Windows Defender (操作) |1124|已审核的受控文件夹访问权限事件|
|文件夹限制访问|Windows Defender (操作) |1123|阻止的受控文件夹访问权限事件|
|文件夹限制访问|Windows Defender (操作) |1127|阻止的受控文件夹访问权限扇区写入块事件|
|文件夹限制访问|Windows Defender (操作) |1128|审核的受控文件夹访问权限扇区写入块事件|
|攻击面减少|Windows Defender (操作) |5007|更改设置时的事件|
|攻击面减少|Windows Defender (操作) |1122|在审核模式下触发规则时的事件|
|攻击面减少|Windows Defender (操作) |1121|在阻止模式下触发规则时的事件|

>[!NOTE]
> 从用户的角度来看，ASR 警告模式通知是作为攻击Windows减少规则的一个 Toast 通知。
>
> 在 ASR 中，网络保护仅提供审核和阻止模式。
