---
title: Microsoft Defender 防病毒事件 ID 和错误代码
description: 查找Microsoft Defender 防病毒事件 ID 和错误的原因和解决方案
keywords: 事件， 错误代码， siem， 日志记录， 故障排除， wef， windows 事件转发
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/27/2022
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: c1fcf71aa91e944e36050dae85f0c31a316df344
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665439"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>查看事件日志和错误代码，解决 Microsoft Defender 防病毒软件问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

如果遇到Microsoft Defender 防病毒问题，可以搜索本主题中的表以查找匹配问题和潜在解决方案。

表列表：

- [这些 (Microsoft Defender 防病毒事件 ID](#windows-defender-av-ids) 适用于Windows 10、Windows 11和Windows Server 2016) 
- [Microsoft Defender 防病毒客户端错误代码](#error-codes)
- [Microsoft 在开发和测试期间 (使用的内部Microsoft Defender 防病毒客户端错误代码) ](#internal-error-codes)

> [!TIP]
> 还可以访问 [demo.wd.microsoft.com 的Microsoft Defender for Endpoint](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)演示网站，确认以下功能正常工作：
>
> - 云端保护
> - 快速学习 (包括一见钟情) 
> - 可能不需要的应用程序阻止

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Microsoft Defender 防病毒事件 ID

Microsoft Defender 防病毒记录Windows事件日志中的事件 ID。

可以直接查看事件日志，或者，如果有第三方安全信息和事件管理 (SIEM) 工具，还可以使用[Microsoft Defender 防病毒客户端事件 ID](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) 查看终结点中的特定事件和错误。

本部分中的表列出了主要Microsoft Defender 防病毒事件 ID，并尽可能提供用于修复或解决错误的建议解决方案。

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>查看Microsoft Defender 防病毒事件

1. 打开 **事件查看器**。
2. 在控制台树中，展开 **应用程序和服务日志**，然后展开 **Microsoft**，然后 **Windows**，然后 **Windows Defender**。
3. 双击 **"操作**"。
4. 在详细信息窗格中，查看单个事件的列表以查找事件。
5. 单击该事件可在" **常规** "和" **详细信息** "选项卡下的下窗格中查看有关事件的特定详细信息。

<table>
<tr>
<th colspan="2" >事件 ID：1000</th>
</tr>
<tr>
<td>
符号名称：
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件扫描已启动。 </b>
</td>
</tr>
<tr>
<td >
说明:
</td>
<td >
<dl>
<dt>扫描 ID： &lt;相关扫描的 ID 号。&gt;</dt>
<dt>扫描类型： &lt;扫描类型&gt;，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数： &lt;扫描参数&gt;，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>扫描资源： &lt;资源 (，例如已扫描的文件/目录/BHO) 。&gt;</dt>
<dt>用户： &lt;Domainlt&gt;\&;用户&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1001</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件扫描已完成。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
<dl>
<dt>扫描 ID： &lt;相关扫描的 ID 号。&gt;</dt>
<dt>扫描类型： &lt;扫描类型&gt;，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数： &lt;扫描参数&gt;，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domainlt&gt;\&;UserScan&gt;</dt> 
<dt>时间：&lt;扫描的持续时间。&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1002</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件扫描在完成之前已停止。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
<dl>
<dt>扫描 ID： &lt;相关扫描的 ID 号。&gt;</dt>
<dt>扫描类型： &lt;扫描类型&gt;，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数： &lt;扫描参数&gt;，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domainlt&gt;&amp;;UserScan&gt;</dt> 
<dt>时间：&lt;扫描的持续时间。&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1003</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件扫描已暂停。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
<dl>
<dt>扫描 ID： &lt;相关扫描的 ID 号。&gt;</dt>
<dt>扫描类型： &lt;扫描类型&gt;，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数： &lt;扫描参数&gt;，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domainlt&gt;\&;用户&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1004</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件扫描已恢复。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
<dl>
<dt>扫描 ID： &lt;相关扫描的 ID 号。&gt;</dt>
<dt>扫描类型： &lt;扫描类型&gt;，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数： &lt;扫描参数&gt;，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domainlt&gt;\&;用户&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1005</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件扫描失败。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
<dl>
<dt>扫描 ID： &lt;相关扫描的 ID 号。&gt;</dt>
<dt>扫描类型： &lt;扫描类型&gt;，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数： &lt;扫描参数&gt;，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domainlt&gt;\&;UserError&gt;</dt> 
<dt>代码：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt;错误说明。 </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
防病毒客户端遇到错误，当前扫描已停止。 扫描可能由于客户端问题而失败。 此事件记录包括扫描 ID、扫描 (Microsoft Defender 防病毒类型、反间谍软件、反恶意软件) 、扫描参数、启动扫描的用户、错误代码以及错误说明。
若要对此事件进行故障排除：
<ol>
<li>再次运行扫描。</li>
<li>如果以相同的方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持部门站点</a>，在<b>"搜索</b>"框中输入错误编号以查找错误代码。</li>
<li>与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1006</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎发现了恶意软件或其他可能不需要的软件。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathDetection&gt;</dt>
<dt> Origin： &lt;检测源&gt;，例如：<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型： &lt;检测类型&gt;，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>混凝土</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源： &lt;检测源&gt; ，例如：<ul>
<li>用户：用户发起</li>
<li>系统：系统启动</li>
<li>实时：已启动实时组件</li>
<li>IOAV：IE 下载和Outlook快速附件已启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可防止恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>AMSI)  (反恶意软件扫描接口。 主要用于保护 PowerShell、VBS)  (脚本，但也可以由第三方调用。
UACStatus</dt>
<dt>： &lt;StatusUser&gt;</dt>
<dt>： &lt;Domainlt&gt;\&;UserProcess&gt;</dt> 
<dt>名称：&lt;PIDSignature&gt;</dt> 
<dt>版本中的进程：&lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1007</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台执行了一项操作来保护系统免受恶意软件或其他可能不需要的软件的侵害。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已采取措施保护此计算机免受恶意软件或其他可能不需要的软件的侵害。 有关详细信息，请参阅：
<dl>
<dt>用户： &lt;Domainlt&gt;\&;UserName&gt;</dt>
<dt>： &lt;Threat nameID&gt;</dt>
<dt>： &lt;Threat IDSeverity&gt;</dt>
<dt>： &lt;Severity&gt;， 例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>操作： &lt;操作&gt;，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：资源被隔离</li>
<li>删除：资源已删除</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作通常是用户指定的操作列表中的操作之一</li>
<li>无操作：无操作</li>
<li>阻止：阻止资源执行</li>
</ul>
</dt>
<dt>地位： &lt;StatusSignature&gt;</dt> 
<dt>版本：&lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1008</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台尝试执行一项操作来保护系统免受恶意软件或其他可能不需要的软件的侵害，但操作失败。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒在对恶意软件或其他可能不需要的软件采取措施时遇到错误。 有关详细信息，请参阅：
<dl>
<dt>用户： &lt;Domainlt&gt;\&;UserName&gt;</dt>
<dt>： &lt;Threat nameID&gt;</dt>
<dt>： &lt;Threat IDSeverity&gt;</dt>
<dt>： &lt;Severity&gt;， 例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathAction&gt;</dt>
<dt>： &lt;操作&gt;，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：资源被隔离</li>
<li>删除：资源已删除</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作通常是用户指定的操作列表中的操作之一</li>
<li>无操作：无操作</li>
<li>阻止：阻止资源执行</li>
</ul>
</dt>
<dt>错误代码： &lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明：&lt;错误描述&gt;。 </dt>
<dt>地位： &lt;StatusSignature&gt;</dt> 
<dt>版本：&lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1009</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台还原了隔离项。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已从隔离区还原项。 有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathUser&gt;</dt>
<dt>：&lt;Domainlt&gt;\&;UserSignature&gt;</dt> 
<dt>版本：&lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1010</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台无法从隔离区还原项。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试从隔离区还原项时遇到错误。 有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathUser&gt;</dt>
<dt>：&lt;Domainlt&gt;\&;UserError&gt;</dt> 
<dt>代码：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明：&lt;错误描述&gt;。 </dt>
<dt>签名版本： &lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1011</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台从隔离区中删除了项。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已从隔离区中删除项。<br/>有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathUser&gt;</dt>
<dt>：&lt;Domainlt&gt;\&;UserSignature&gt;</dt> 
<dt>版本：&lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1012</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台无法从隔离区中删除项。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试从隔离区中删除项时遇到错误。
有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathUser&gt;</dt>
<dt>：&lt;Domainlt&gt;\&;UserError&gt;</dt> 
<dt>代码：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明：&lt;错误描述&gt;。 </dt>
<dt>签名版本： &lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1013</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台删除了恶意软件和其他可能不需要的软件的历史记录。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒删除了恶意软件和其他可能不需要的软件的历史记录。
<dl>
<dt>时间：事件发生的时间，例如清除历史记录的时间。此参数不用于威胁事件，因此不会混淆它是修正时间还是感染时间。对于这些用户，我们特别将其称为操作时间或检测时间。</dt>
<dt>用户： &lt;Domainlt&gt;\&;用户&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1014</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
反恶意软件平台无法删除恶意软件和其他可能不需要的软件的历史记录。
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试删除恶意软件和其他可能不需要的软件的历史记录时遇到错误。
<dl>
<dt>时间：事件发生的时间，例如清除历史记录的时间。此参数不用于威胁事件，因此不会混淆它是修正时间还是感染时间。对于这些用户，我们特别将其称为操作时间或检测时间。</dt>
<dt>用户： &lt;Domainlt&gt;\&;UserError&gt;</dt> 
<dt>代码：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明：&lt;错误描述&gt;。 </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1015</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台检测到可疑行为。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒检测到可疑行为。<br/>有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathDetection&gt;</dt>
<dt> Origin： &lt;检测源&gt;，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型： &lt;检测类型&gt;，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>混凝土</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源： &lt;检测源&gt; ，例如：<ul>
<li>用户：用户发起</li>
<li>系统：系统启动</li>
<li>实时：已启动实时组件</li>
<li>IOAV：IE 下载和Outlook快速附件已启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可防止恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>AMSI)  (反恶意软件扫描接口。 主要用于保护 PowerShell、VBS)  (脚本，但也可以由第三方调用。
UACStatus</dt>
<dt>： &lt;StatusUser&gt;</dt>
<dt>： &lt;Domainlt&gt;\&;UserProcess&gt;</dt> 
<dt>名称：&lt;PIDSignature&gt; ID 中的进程</dt>
<dt>：枚举匹配严重性。</dt>
<dt>签名版本： &lt;Definition versionEngine&gt;</dt> 
<dt>Version： &lt;反恶意软件引擎 versionFidelity&gt;</dt> 
<dt>Label：</dt>
<dt>Target File Name： &lt;file name&gt; of the file.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1116</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台检测到恶意软件或其他可能不需要的软件。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒检测到恶意软件或其他可能不需要的软件。<br/>有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathDetection&gt;</dt>
<dt> Origin： &lt;检测源&gt;，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型： &lt;检测类型&gt;，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>混凝土</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源： &lt;检测源&gt; ，例如：<ul>
<li>用户：用户发起</li>
<li>系统：系统启动</li>
<li>实时：已启动实时组件</li>
<li>IOAV：IE 下载和Outlook快速附件已启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可防止恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>AMSI)  (反恶意软件扫描接口。 主要用于保护 PowerShell、VBS)  (脚本，但也可以由第三方调用。
UACUser</dt>
<dt>：&lt;Domainlt&gt;\&;UserProcess&gt;</dt> 
<dt>名称：&lt;PIDSignature&gt;</dt> 
<dt>版本中的进程：&lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
不需要执行任何操作。 Microsoft Defender 防病毒可以对此威胁暂停并采取例行操作。 如果要手动删除威胁，请在Microsoft Defender 防病毒界面中单击<b>"清理计算机</b>"。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1117</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台执行了一项操作来保护系统免受恶意软件或其他可能不需要的软件的侵害。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已采取措施保护此计算机免受恶意软件或其他可能不需要的软件的侵害。<br/>有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathDetection&gt;</dt>
<dt> Origin： &lt;检测源&gt;，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型： &lt;检测类型&gt;，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>混凝土</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源： &lt;检测源&gt; ，例如：<ul>
<li>用户：用户发起</li>
<li>系统：系统启动</li>
<li>实时：已启动实时组件</li>
<li>IOAV：IE 下载和Outlook快速附件已启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可防止恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>AMSI)  (反恶意软件扫描接口。 主要用于保护 PowerShell、VBS)  (脚本，但也可以由第三方调用。
UACUser</dt>
<dt>：&lt;Domainlt&gt;\&;UserProcess&gt;</dt> 
<dt>名称：&lt;PIDAction&gt;</dt>
<dt> 中的进程：&lt;操作&gt;，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：资源被隔离</li>
<li>删除：资源已删除</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作通常是用户指定的操作列表中的操作之一</li>
<li>无操作：无操作</li>
<li>阻止：阻止资源执行</li>
</ul>
</dt>
<dt>操作状态： &lt;其他操作&gt;说明</dt>
<dt>：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt;错误说明。 </dt>
<dt>签名版本： &lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>注意：每当Microsoft Defender 防病毒、Microsoft Security Essentials、恶意软件删除工具或System Center Endpoint Protection检测到恶意软件，它将还原恶意软件可能已更改的以下系统设置和服务：<ul>
<li>默认 Internet Explorer 或 Microsoft Edge 设置</li>
<li>用户访问控制设置</li>
<li>Chrome 设置</li>
<li>启动控制数据</li>
<li>Regedit 和 Task Manager 注册表设置</li>
<li>Windows 更新、后台智能传输服务和远程过程呼叫服务</li>
<li>Windows操作系统文件</li></ul>
上述上下文适用于以下客户端和服务器版本：
<table>
<tr>
<th>操作系统</th>
<th>操作系统版本</th>
</tr>
<tr>
<td>
客户端操作系统
</td>
<td>
Windows Vista (Service Pack 1 或 Service Pack 2) ，Windows 7 及更高版本
</td>
</tr>
<tr>
<td>
服务器操作系统
</td>
<td>
Windows Server 2008、Windows Server 2008 R2、Windows Server 2012 和 Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需执行任何操作。 Microsoft Defender 防病毒删除或隔离了威胁。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1118</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台尝试执行一项操作来保护系统免受恶意软件或其他可能不需要的软件的侵害，但操作失败。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒在对恶意软件或其他可能不需要的软件采取措施时遇到非严重错误。<br/>有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathDetection&gt;</dt>
<dt> Origin： &lt;检测源&gt;，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型： &lt;检测类型&gt;，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>混凝土</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源： &lt;检测源&gt; ，例如：<ul>
<li>用户：用户发起</li>
<li>系统：系统启动</li>
<li>实时：已启动实时组件</li>
<li>IOAV：IE 下载和Outlook快速附件已启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可防止恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>AMSI)  (反恶意软件扫描接口。 主要用于保护 PowerShell、VBS)  (脚本，但也可以由第三方调用。
UACUser</dt>
<dt>：&lt;Domainlt&gt;\&;UserProcess&gt;</dt> 
<dt>名称：&lt;PIDAction&gt;</dt>
<dt> 中的进程：&lt;操作&gt;，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：资源被隔离</li>
<li>删除：资源已删除</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作通常是用户指定的操作列表中的操作之一</li>
<li>无操作：无操作</li>
<li>阻止：阻止资源执行</li>
</ul>
</dt>
<dt>操作状态： &lt;其他操作&gt;说明</dt>
<dt>：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt;错误说明。 </dt>
<dt>签名版本： &lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需执行任何操作。 Microsoft Defender 防病毒无法完成与恶意软件修正相关的任务。 这不是严重故障。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1119</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台在尝试对恶意软件或其他可能不需要的软件采取措施时遇到严重错误。事件消息中包含更多详细信息。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒在对恶意软件或其他可能不需要的软件采取措施时遇到严重错误。<br/>有关详细信息，请参阅：
<dl>
<dt>名字： &lt;威胁名称&gt;</dt> 
<dt>ID：&lt;威胁 IDSeverity&gt;</dt>
<dt>：&lt;严重性&gt;，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别说明&gt;，例如，任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件 pathDetection&gt;</dt>
<dt> Origin： &lt;检测源&gt;，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型： &lt;检测类型&gt;，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>混凝土</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源： &lt;检测源&gt; ，例如：<ul>
<li>用户：用户发起</li>
<li>系统：系统启动</li>
<li>实时：已启动实时组件</li>
<li>IOAV：IE 下载和Outlook快速附件已启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可防止恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>AMSI)  (反恶意软件扫描接口。 主要用于保护 PowerShell、VBS)  (脚本，但也可以由第三方调用。
UACUser</dt>
<dt>：&lt;Domainlt&gt;\&;UserProcess&gt;</dt> 
<dt>名称：&lt;PIDAction&gt;</dt>
<dt> 中的进程：&lt;操作&gt;，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：资源被隔离</li>
<li>删除：资源已删除</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作通常是用户指定的操作列表中的操作之一</li>
<li>无操作：无操作</li>
<li>阻止：阻止资源执行</li>
</ul>
</dt>
<dt>操作状态： &lt;其他操作&gt;说明</dt>
<dt>：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt;错误说明。 </dt>
<dt>签名版本： &lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
Microsoft Defender 防病毒客户端由于严重问题而遇到此错误。 终结点可能不受保护。 查看错误说明，然后按照下面的相关 <b>用户操作</b> 步骤操作。
<table>
<tr>
<th>Action</th>
<th>用户操作</th>
</tr>
<tr>
<td>
<b>删除</b>
</td>
<td>
更新定义，然后验证删除是否成功。
</td>
</tr>
<tr>
<td>
<b>清洁</b>
</td>
<td>
更新定义，然后验证修正是否成功。
</td>
</tr>
<tr>
<td>
<b>检疫</b>
</td>
<td>
更新定义并验证用户是否有权访问所需的资源。
</td>
</tr>
<tr>
<td>
<b>允许</b>
</td>
<td>
验证用户是否有权访问所需的资源。
</td>
</tr>
</table>

如果此事件仍然存在：<ol>
<li>再次运行扫描。</li>
<li>如果以相同的方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持部门站点</a>，在<b>"搜索</b>"框中输入错误编号以查找错误代码。</li>
<li>与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1120</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>Microsoft Defender 防病毒推断出威胁资源的哈希。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒客户端处于正常运行状态。
<dl>
<dt>当前平台版本： &lt;当前平台版本&gt;</dt> 
<dt>Threat 资源路径：&lt;PathHashes&gt;</dt>
<dt>：&lt;Hashes&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>注意：仅当设置了以下策略时，才会记录此事件： <b>ThreatFileHashLogging 未签名</b>。</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1127</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_FOLDER_GUARD_SECTOR_BLOCK</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>受控文件夹访问 (CFA) 阻止不受信任的进程对内存进行更改。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
受控文件夹访问阻止了不受信任的进程可能修改磁盘扇区。
<br/> 有关事件记录的详细信息，请参阅以下内容：
<dl>
<dt>EventID： &lt;EventID&gt;，例如：1127Version</dt>
<dt>：&lt;版本&gt;，例如：</dt>
<dt>0Level：&lt;Level&gt;，例如：win：</dt>
<dt>WarningTimeCreated：&lt;SystemTime&gt;，创建事件的时间</dt>
<dt>EventRecordID：&lt;EventRecordID&gt;，事件</dt> 
<dt>logExecution ProcessID：Execution ProcessID 中事件的索引号：&lt;执行进程ID&gt;，生成</dt> 
<dt>eventChannel：&lt;事件通道&gt;的进程，例如：Microsoft-Windows-Windows Defender/</dt>
<dt>OperationalComputer：&lt;计算机名称&gt;</dt>
<dt>Security UserID：&lt;安全 UserIDProduct&gt;</dt> 
<dt>名称：&lt;产品名称&gt;，例如：Microsoft Defender 防病毒</dt>
<dt>Product 版本：&lt;Product VersionDetection&gt;</dt> 
<dt>Time： &lt;检测时间&gt;，CFA 阻止不受信任的</dt> 
<dt>processUser 的时间：&lt;Domainlt&gt;\&;UserPath&gt;</dt>
<dt>：&lt;设备名称&gt;、不受信任的进程访问用于修改的设备或磁盘的名称</dt>
<dt>：&lt;进程路径&gt;，CFA 阻止其访问设备或磁盘以进行修改的进程路径名称</dt>：
<dt>安全智能版本&gt;Engine 版本：&lt;</dt>
<dt>&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
用户可以使用 Powershell 或 Windows 安全中心 Center 将阻止的进程添加到 CFA <i>的允许进程</i>列表中。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：1150</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>如果反恶意软件平台向监视平台报告状态，则此事件指示反恶意软件平台正在运行并处于正常状态。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒客户端处于正常运行状态。
<dl>
<dt>平台版本： &lt;当前平台版本&gt;</dt>
<dt>Signature 版本：&lt;定义版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需执行任何操作。 Microsoft Defender 防病毒客户端处于正常状态。 此事件按小时报告。
</td>
</tr>

<tr>
<th colspan="2">事件 ID：1151</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>Endpoint Protection UTC) 中的客户端运行状况报告 (时间</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
防病毒客户端运行状况报告。
<dl>
<dt>平台版本： &lt;当前平台版本&gt;</dt>
<dt>Engine 版本：&lt;反恶意软件引擎 versionNetwork&gt;</dt> 
<dt>实时检查引擎版本：&lt;网络实时检查引擎版本&gt;</dt>
<dt>Antivirus 签名版本：&lt;防病毒签名版本&gt;</dt>
<dt>Antispyware签名版本：&lt;反软件签名版本&gt;</dt>
<dt>Network 实时检查签名版本：&lt;网络实时检查签名 versionRTP&gt;</dt> 
<dt>状态：&lt;实时保护状态&gt; (启用或禁用) </dt>
<dt>OA 状态：&lt;在访问状态&gt; (启用或禁用) </dt>
<dt>IOAV 状态：&lt;IE 下载和Outlook快速附件状态&gt; (启用或禁用) </dt>
<dt>BM 状态：&lt;启用或禁用 (行为监视状态&gt;) </dt>
<dt>防病毒签名年龄：&lt;防病毒签名年龄&gt; (日) </dt>
<dt>反间谍软件签名年龄：&lt;反间谍软件签名年龄&gt; (天) </dt>
<dt>上次快速扫描年龄：&lt;上次快速扫描年龄&gt; (天) </dt>
<dt>上次完全扫描年龄：&lt;上次完全扫描年龄&gt; (天) </dt>
<dt>防病毒签名创建时间：&lt;防病毒签名创建 timeAntispyware&gt;</dt> 
<dt>签名创建时间： ？&lt;反间谍软件签名创建时间&gt;</dt>
<dt>上次快速扫描开始时间： ？&lt;上次快速扫描开始时间&gt;</dt>
<dt>上次快速扫描结束时间：&lt;上次快速扫描结束时间&gt;</dt>
<dt>上次快速扫描源：&lt;上次快速扫描源&gt; (0 = 扫描未运行，1 = 用户启动，2 = 系统启动) </dt>
<dt>上次完全扫描开始时间：&lt;上次完全扫描开始时间&gt;</dt>
<dt>最后一次完全扫描结束时间： ？&lt;上次完全扫描结束时间&gt;</dt>
<dt>上次完全扫描源：&lt;上次完整扫描源&gt; (0 = 扫描未运行，1 = 用户启动，2 = 系统启动) </dt>
<dt>产品状态：对于内部故障排除
</dl>
</td>
</tr>

<tr>
<th colspan="2">事件 ID：2000</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件定义已成功更新。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
防病毒签名版本已更新。
<dl>
<dt>当前签名版本： &lt;当前签名版本&gt;</dt>
<dt>Previous 签名版本： &lt;以前的签名版本&gt;</dt>
<dt>签名类型： &lt;签名类型&gt;，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>更新类型： &lt;更新类型&gt;（完整或增量）。</dt>
<dt>用户： &lt;Domainlt&gt;\&;UserCurrent&gt;</dt> 
<dt>引擎版本：&lt;当前引擎版本&gt;</dt>
<dt>Previous 引擎版本：&lt;以前的引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需执行任何操作。 Microsoft Defender 防病毒客户端处于正常状态。 成功更新签名时会报告此事件。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2001</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>安全智能更新失败。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试更新签名时遇到错误。
<dl>
<dt>新的安全智能版本： &lt;新版本号&gt;</dt>
<dt>Previous 安全智能版本： &lt;以前的 versionUpdate&gt;</dt>
<dt> 源： &lt;更新源&gt;，例如：
<ul>
<li>安全智能更新文件夹</li>
<li>内部安全智能更新服务器</li>
<li>Microsoft Update Server</li>
<li>文件共享</li>
<li>Microsoft 恶意软件防护中心 (MMPC) </li>
</ul>
</dt>
<dt>更新阶段： &lt;更新阶段&gt;，例如：
<ul>
<li>搜索</li>
<li>下载</li>
<li>安装</li>
</ul>
</dt>
<dt>源路径：通用命名约定 (UNC) 的文件共享名称，Windows Server Update Services (WSUS) /Microsoft Update/ADL 的服务器名称。</dt>
<dt>签名类型：&lt;签名类型&gt;，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>更新类型： &lt;更新类型&gt;（完整或增量）。</dt>
<dt>用户： &lt;Domainlt&gt;\&;UserCurrent&gt;</dt> 
<dt>引擎版本：&lt;当前引擎版本&gt;</dt>
<dt>Previous 引擎版本：&lt;以前的引擎版本&gt;</dt>
<dt>Error Code：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt;错误说明。 </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
更新定义时出现问题时，会发生此错误。
若要对此事件进行故障排除：
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定义并</a> 直接在终结点上强制重新扫描。</li>
<li>有关此错误的详细信息，请查看 %Windir%\WindowsUpdate.log 文件中的条目。</li>
<li>与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2002</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎已成功更新。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒引擎版本已更新。
<dl>
<dt>当前引擎版本： &lt;当前引擎版本&gt;</dt>
<dt>Previous Engine 版本： &lt;以前的引擎版本&gt;</dt>
<dt>Engine 类型： &lt;引擎类型&gt;，反恶意软件引擎或网络检查系统引擎。</dt>
<dt>用户： &lt;Domainlt&gt;\&;用户&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需执行任何操作。 Microsoft Defender 防病毒客户端处于正常状态。 成功更新反恶意软件引擎时，会报告此事件。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2003</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎更新失败。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试更新引擎时遇到错误。
<dl>
<dt>新引擎版本：</dt>
<dt>以前的引擎版本：&lt;以前的引擎版本&gt;</dt>
<dt>Engine类型：&lt;引擎类型&gt;，反恶意软件引擎或网络检查系统引擎。</dt>
<dt>用户： &lt;Domainlt&gt;\&;UserError&gt;</dt> 
<dt>代码：&lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt;错误说明。 </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
Microsoft Defender 防病毒客户端更新失败。 当客户端无法更新自身时，会发生此事件。 此事件通常是由于更新期间网络连接中断而导致的。
若要对此事件进行故障排除：
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定义并</a> 直接在终结点上强制重新扫描。</li>
<li>与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2004</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>加载反恶意软件定义时出现问题。反恶意软件引擎将尝试加载最后已知的良好定义集。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒在尝试加载签名时遇到错误，将尝试还原到已知良好的签名集。
<dl>
<dt>签名尝试：</dt>
<dt>错误代码： &lt;与威胁状态关联的错误代码&gt; 结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt; 错误说明。 </dt>
<dt>签名版本： &lt;定义版本&gt;</dt>
<dt>Engine 版本： &lt;反恶意软件引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
Microsoft Defender 防病毒客户端尝试下载并安装最新定义文件，但失败。 当客户端在尝试加载定义时或文件损坏时遇到错误时，可能会发生此错误。 Microsoft Defender 防病毒将尝试还原到已知良好的定义集。
若要对此事件进行故障排除：
<ol>
<li>重新启动计算机，然后重试。</li>
<li>从<a href="https://aka.ms/wdsi">Microsoft 安全智能站点</a>下载最新定义。
注意：从站点下载的定义文件的大小可以超过 60 MB，不应用作更新定义的长期解决方案。
</li>
<li>与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2005</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎无法加载，因为反恶意软件平台已过期。反恶意软件平台将加载最后已知的好反恶意软件引擎并尝试更新。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒无法加载反恶意软件引擎，因为当前平台版本不受支持。 Microsoft Defender 防病毒将还原到最后一个已知的良好引擎，并且将尝试平台更新。
<dl>
<dt>当前平台版本： &lt;当前平台版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2006</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>平台更新失败。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试更新平台时遇到错误。
<dl>
<dt>当前平台版本： &lt;当前平台版本&gt;</dt>
<dt>Error Code： &lt;与威胁状态关联的错误代码&gt; 结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt; 错误说明。 </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2007</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>平台即将过期。下载最新平台以维护最新保护。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒很快需要更新的平台版本来支持反恶意软件引擎的未来版本。 下载最新的Microsoft Defender 防病毒平台，以保持可用的最佳保护级别。
<dl>
<dt>当前平台版本： &lt;当前平台版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2010</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎使用动态签名服务获取其他定义。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒使用<i>动态签名服务</i>检索其他签名以帮助保护计算机。
<dl>
<dt>当前签名版本： &lt;当前签名版本&gt;</dt>
<dt>签名类型： &lt;签名类型&gt;，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>当前引擎版本： &lt;当前引擎版本&gt;</dt>
<dt>Dynamic 签名类型： &lt;动态签名类型&gt;，例如：
<ul>
<li>版本</li>
<li>Timestamp</li>
<li>无限制</li>
<li>期限</li>
</ul>
</dt>
<dt>持久性路径： &lt;PathDynamic&gt;</dt> 
<dt>签名版本：&lt;版本号&gt;</dt>
<dt>Dynamic 签名编译时间戳：&lt;TimestampPersistence&gt;</dt>
<dt> 限制类型：&lt;持久性限制类型&gt;，例如：
<ul>
<li>VDM 版本</li>
<li>Timestamp</li>
<li>无限制</li>
</ul>
</dt>
<dt>持久性限制：快速路径签名的持久性限制。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2011</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>动态签名服务删除了过时的动态定义。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒使用<i>动态签名服务</i>丢弃过时的签名。
<dl>
<dt>当前签名版本： &lt;当前签名版本&gt;</dt>
<dt>签名类型： &lt;签名类型&gt;，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>当前引擎版本： &lt;当前引擎版本&gt;</dt>
<dt>Dynamic 签名类型： &lt;动态签名类型&gt;，例如：
<ul>
<li>版本</li>
<li>Timestamp</li>
<li>无限制</li>
<li>期限</li>
</ul>
</dt>
<dt>持久性路径： &lt;PathDynamic&gt;</dt> 
<dt>签名版本：&lt;版本号&gt;</dt>
<dt>Dynamic 签名编译时间戳：&lt;TimestampRemoval&gt;</dt> 
<dt>原因：</dt>
<dt>持久性限制类型：&lt;持久性限制类型&gt;，例如：
<ul>
<li>VDM 版本</li>
<li>Timestamp</li>
<li>无限制</li>
</ul>
</dt>
<dt>持久性限制：快速路径签名的持久性限制。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需执行任何操作。 Microsoft Defender 防病毒客户端处于正常状态。 当动态签名服务成功删除过时的动态定义时，将报告此事件。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2012</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎在尝试使用动态签名服务时遇到错误。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试使用<i>动态签名服务</i>时遇到错误。
<dl>
<dt>当前签名版本： &lt;当前签名版本&gt;</dt>
<dt>签名类型： &lt;签名类型&gt;，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>当前引擎版本： &lt;当前引擎版本&gt;</dt>
<dt>Error Code： &lt;与威胁状态关联的错误代码&gt; 结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt; 错误说明。 </dt>
<dt>动态签名类型： &lt;动态签名类型&gt;，例如：
<ul>
<li>版本</li>
<li>Timestamp</li>
<li>无限制</li>
<li>期限</li>
</ul>
</dt>
<dt>持久性路径： &lt;PathDynamic&gt;</dt> 
<dt>签名版本：&lt;版本号&gt;</dt>
<dt>Dynamic 签名编译时间戳：&lt;TimestampPersistence&gt;</dt>
<dt> 限制类型：&lt;持久性限制类型&gt;，例如：
<ul>
<li>VDM 版本</li>
<li>Timestamp</li>
<li>无限制</li>
</ul>
</dt>
<dt>持久性限制：快速路径签名的持久性限制。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
检查 Internet 连接设置。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2013</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>动态签名服务删除了所有动态定义。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒丢弃所有<i>动态签名服务</i>签名。
<dl>
<dt>当前签名版本： &lt;当前签名版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2020</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎下载了一个干净的文件。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒下载了一个干净的文件。
<dl>
<dt>文件名： &lt;文件的文件名&gt; 。</dt>
<dt>当前签名版本： &lt;当前签名版本&gt;</dt>
<dt>Current 引擎版本： &lt;当前引擎版本&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2021</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎无法下载干净的文件。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试下载干净文件时遇到错误。
<dl>
<dt>文件名： &lt;文件的文件名&gt; 。</dt>
<dt>当前签名版本： &lt;当前签名版本&gt;</dt>
<dt>Current 引擎版本： &lt;当前引擎版本&gt;</dt>
<dt>Error Code： &lt;与威胁状态关联的错误代码&gt; 结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt; 错误说明。 </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
检查 Internet 连接设置。
使用动态签名服务将最新定义下载到特定威胁时，Microsoft Defender 防病毒客户端遇到错误。 此错误可能是由网络连接问题引起的。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2030</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎已下载，并配置为在下一次系统重启时脱机运行。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒下载并配置脱机防病毒，以便在下次重启时运行。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2031</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎无法下载和配置脱机扫描。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试下载和配置脱机防病毒时遇到错误。
<dl>
<dt>错误代码： &lt;与威胁状态关联的错误代码&gt; 结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt; 错误说明。 </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2040</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>此操作系统版本的反恶意软件支持将很快结束。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
对操作系统的支持将很快过期。 在不受支持操作系统上运行Microsoft Defender 防病毒不足以防范威胁。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2041</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>此操作系统的反恶意软件支持已结束。必须升级操作系统以获得持续支持。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
对操作系统的支持已过期。 在不受支持操作系统上运行Microsoft Defender 防病毒不足以防范威胁。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：2042</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎不再支持此操作系统，并且不再保护系统免受恶意软件的侵害。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
对操作系统的支持已过期。 Microsoft Defender 防病毒在操作系统上不再受支持，已停止运行，并且无法防范恶意软件威胁。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：3002</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>实时保护遇到错误并失败。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒 Real-Time保护功能遇到错误并失败。
<dl>
<dt>功能： &lt;功能&gt;，例如：
<ul>
<li>在 Access 上</li>
<li>Internet Explorer 下载和 Microsoft Outlook Express 附件</li>
<li>行为监视</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>错误代码： &lt;与威胁状态关联的错误代码&gt;结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt;错误说明。 </dt>
<dt>原因：实时保护Microsoft Defender 防病毒重启功能的原因。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
应重启系统，然后运行完全扫描，因为系统可能在一段时间内不受保护。
Microsoft Defender 防病毒客户端的实时保护功能遇到错误，因为其中一个服务无法启动。
如果后面是 3007 事件 ID，则故障是暂时的，反恶意软件客户端会从故障中恢复。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：3007</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>从故障中恢复的实时保护。当看到此错误时，建议运行完整的系统扫描。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒实时保护已重启功能。 建议运行完整的系统扫描，以检测此代理关闭时可能遗漏的任何项。
<dl>
<dt>功能： &lt;功能&gt;，例如：
<ul>
<li>在 Access 上</li>
<li>IE 下载和Outlook Express 附件</li>
<li>行为监视</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>原因：实时保护Microsoft Defender 防病毒重启功能的原因。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
实时保护功能已重启。 如果再次发生此事件，请联系 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5000</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>已启用实时保护。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒启用了恶意软件和其他可能不需要的软件的实时保护扫描。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5001</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>已禁用实时保护。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已禁用恶意软件和其他可能不需要的软件的实时保护扫描。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5004</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>实时保护配置已更改。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒实时保护功能配置已更改。
<dl>
<dt>功能： &lt;功能&gt;，例如：
<ul>
<li>在 Access 上</li>
<li>IE 下载和Outlook Express 附件</li>
<li>行为监视</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>配置： </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5007</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台配置已更改。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒配置已更改。 如果这是意外事件，则应查看设置，因为这可能是恶意软件的结果。
<dl>
<dt>旧值： &lt;旧值编号&gt; 旧防病毒配置值。</dt>
<dt>新值： &lt;新值编号&gt; 新建防病毒配置值。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5008</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件引擎遇到错误并失败。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒引擎因意外错误而终止。
<dl>
<dt>故障类型： &lt;故障类型&gt;，例如：崩溃或</dt> 
<dt>HangException 代码：&lt;错误代码&gt;</dt>
<dt>资源：&lt;资源&gt;</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
若要对此事件进行故障排除：<ol>
<li>尝试重启服务。<ul>
<li>对于反恶意软件、防病毒软件和间谍软件，在提升的命令提示符下键入 <b>net stop msmpsvc</b>，然后键入 <b>net start msmpsvc</b> 以重启反恶意软件引擎。</li>
<li>对于 <i>网络检查系统</i>，在提升的命令提示符下，键入 <b>net start nissrv</b>，然后键入 <b>net start nissrv</b> 以使用NiSSRV.exe文件重启 <i>网络检查系统</i> 引擎。
</li>
</ul>
</li>
<li>如果以同样的方式失败，请通过访问<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持部门站点</a>并在<b>搜索</b>框中输入错误编号来查找错误代码，并联系 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>。</li>
</ol>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
Microsoft Defender 防病毒客户端引擎因意外错误而停止。
若要对此事件进行故障排除：
<ol>
<li>再次运行扫描。</li>
<li>如果以相同的方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持部门站点</a>，在<b>"搜索</b>"框中输入错误编号以查找错误代码。</li>
<li>与 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持部门</a>联系
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5009</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>已启用对恶意软件和其他可能不需要的软件的扫描。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已启用恶意软件和其他可能不需要的软件的扫描。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5010</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>已禁用对恶意软件和其他可能不需要的软件的扫描。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒禁用恶意软件和其他可能不需要的软件的扫描。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5011</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>已启用病毒扫描。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已启用病毒扫描。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5012</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>已禁用病毒扫描。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒病毒扫描已禁用。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5013</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>
</b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>篡改保护阻止了对Microsoft Defender 防病毒的更改。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
如果启用了篡改保护，则如果阻止并生成事件 ID 5013，则任何更改 Defender 设置的尝试都表示阻止了哪个设置更改。
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5100</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台即将过期。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已进入宽限期，即将过期。 过期后，此程序将禁用对病毒、间谍软件和其他可能不需要的软件的保护。
<dl>
<dt>过期原因：Microsoft Defender 防病毒过期的原因。</dt>
<dt>到期日期：日期Microsoft Defender 防病毒到期。</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">事件 ID：5101</th>
</tr>
<tr><td>
符号名称：
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
消息：
</td>
<td >
<b>反恶意软件平台已过期。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒宽限期已过期。 禁用对病毒、间谍软件和其他可能不需要的软件的保护。
<dl>
<dt>过期原因：</dt>
<dt>到期日期： </dt>
<dt>错误代码： &lt;与威胁状态关联的错误代码&gt; 结果代码。标准 HRESULT 值。</dt>
<dt>错误说明： &lt;错误说明&gt; 错误说明。 </dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Microsoft Defender 防病毒客户端错误代码如果Microsoft Defender 防病毒遇到任何问题，通常会提供错误代码来帮助你解决问题。 通常，错误意味着安装更新时出现问题。
本部分提供以下有关Microsoft Defender 防病毒客户端错误的信息。
-错误代码-错误建议当前操作的可能原因-

使用这些表中的信息来帮助排查Microsoft Defender 防病毒错误代码。


<table>
<tr>
<th colspan="2">错误代码：0x80508007</th>
</tr>
<tr>
<td>邮件</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
可能的原因
</td>
<td>
此错误指示可能内存不足。
</td>
</tr>
<tr>
<td>解决方案</td>
<td>
<ol>
<li>检查设备上的可用内存。</li>
<li>关闭正在运行的任何未使用的应用程序，以释放设备上的内存。</li>
<li>重启设备并再次运行扫描。
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x8050800C</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示安全产品可能有问题。
</td>
</tr><tr><td>解决方案</td><td>
<ol>
<li>更新定义。 任一：<ol>
<li>单击Microsoft Defender 防病毒中<b>"更新</b>"选项卡上的"<b>更新定义</b>"按钮。 <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>或者，
</li>
<li>从<a href="https://aka.ms/wdsi">Microsoft 安全智能站点</a>下载最新定义。
注意：从站点下载的定义文件的大小可以超过 60 MB，不应用作更新定义的长期解决方案。
</li>
</ol>
</li>
<li>运行完整扫描。
</li>
<li>重新启动设备，然后重试。</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508020</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示可能存在引擎配置错误;这通常与不允许引擎正常运行的输入数据相关。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x805080211
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示Microsoft Defender 防病毒无法隔离威胁。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508022
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示需要重新启动才能完成威胁删除。
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示媒体上可能不再存在威胁，或者恶意软件可能会阻止你扫描设备。
</tr><tr><td>解决方案
</td>
<td>
运行<a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft 安全扫描程序</a>然后更新安全软件，然后重试。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508024 </th></tr>
<tr>
<td>邮件</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示可能需要完全系统扫描。
</td></tr>
<tr>
<td>解决方案</td><td>
运行完整的系统扫描。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508025
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示完成威胁消除需要手动步骤。
</td></tr><tr><td>解决方案</td><td>
按照 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft 恶意软件保护百科全书</a>中概述的手动修正步骤进行操作。 可以在事件历史记录中找到特定于威胁的链接。<br/></td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508026
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误表示可能不支持在容器类型内删除。
</td></tr><tr><td>解决方案</td><td>
Microsoft Defender 防病毒无法修正存档中检测到的威胁。 请考虑手动删除检测到的资源。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508027
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示可能禁用删除低威胁和中等威胁。
</td></tr><tr><td>解决方案</td><td>
检查检测到的威胁并根据需要解决这些威胁。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508029
</th>
</tr><tr><td>邮件</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示需要重新扫描威胁。
</td></tr><tr><td>解决方案</td><td>
运行完整的系统扫描。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508030
</th>
</tr><tr><td>邮件</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示需要脱机扫描。
</td></tr><tr><td>解决方案</td><td>
脱机运行Microsoft Defender 防病毒。 可以在<a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">脱机Microsoft Defender 防病毒文章</a>中了解如何执行此操作。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508031
</th>
</tr><tr><td>邮件</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示Microsoft Defender 防病毒不支持平台的当前版本，并且需要新版本的平台。
</td></tr><tr><td>解决方案</td><td>
只能在Windows 10和Windows 11中使用Microsoft Defender 防病毒。 对于 Windows 8，Windows 7 和 Windows Vista，可以使用<a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>。<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a>在内部测试Microsoft Defender 防病毒期间使用以下错误代码。

如果看到这些错误，可以尝试 [更新定义](manage-updates-baselines-microsoft-defender-antivirus.md) ，并直接在终结点上强制重新扫描。


<table>
<tr>
<th colspan="3">内部错误代码</th>
</tr>
<tr>
<th><b>错误代码</b></th>
<th>显示的消息</th>
<th>错误和解决方法的可能原因</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
检查 Internet 连接，然后再次运行扫描。
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E
</td>
<td rowspan="34">
这是一个内部错误。 原因未明确定义。
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
这是一个内部错误。 当恶意软件删除不成功时，可能会触发它。
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
这是一个内部错误。 当扫描无法完成时，它可能已触发。
</td>
</tr>
</table>

## <a name="related-topics"></a>相关主题

- [有关Microsoft Defender 防病毒保护的报告](report-monitor-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
