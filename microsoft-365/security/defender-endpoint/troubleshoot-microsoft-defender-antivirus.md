---
title: Microsoft Defender 防病毒事件 ID 和错误代码
description: 查找事件MICROSOFT DEFENDER 防病毒和错误的原因和解决方案
keywords: 事件， 错误代码， siem， 日志记录， 疑难解答， wef， windows 事件转发
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/19/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 0bf6b5ed0d59e445eba4f8146d8321cf5bff1bf9
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881700"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>查看事件日志和错误代码，解决 Microsoft Defender 防病毒软件问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

如果遇到与Microsoft Defender 防病毒问题，可以搜索本主题中的表以查找匹配的问题和潜在的解决方案。

表列表：

- [Microsoft Defender 防病毒事件 (](#windows-defender-av-ids)适用于Windows 10、Windows 11和Windows Server 2016) 
- [Microsoft Defender 防病毒客户端错误代码](#error-codes)
- [内部Microsoft Defender 防病毒客户端错误 (开发和测试过程中由 Microsoft 使用) ](#internal-error-codes)

> [!TIP]
> 还可以访问 Microsoft Defender for Endpoint 演示[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 确认以下功能是否正常工作：
>
> - 云端保护
> - 快速学习 (包括首次看到时阻止) 
> - 可能不需要的应用程序阻止

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Microsoft Defender 防病毒事件 ID

Microsoft Defender 防病毒事件日志中记录事件Windows。

你可以直接查看事件日志，或者如果你有第三方安全信息和事件管理 (SIEM) 工具，还可以使用 Microsoft Defender 防病毒 客户端事件[ID](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids)查看终结点中的特定事件和错误。

本节中的表列出了主要事件Microsoft Defender 防病毒，并尽可能提供建议的解决方案来修复或解决错误。

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>查看事件Microsoft Defender 防病毒事件

1. 打开 **事件查看器**。
2. 在控制台树中，展开"**应用程序和服务** 日志"，然后展开 **"Microsoft"，** 然后Windows"，Windows Defender"。  
3. 双击操作 **。**
4. 在详细信息窗格中，查看各个事件的列表以查找事件。
5. 单击事件以查看有关下窗格中"常规"和"详细信息"选项卡下 **的事件****的特定** 详细信息。

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
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>扫描资源： &lt;扫描 (文件/目录/BHO) 等资源。 &gt; </dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
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
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>扫描时间 &lt; ：扫描的持续时间。 &gt; </dt>
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
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domain &gt; &amp; lt;用户 &gt; </dt>
<dt>扫描时间 &lt; ：扫描的持续时间。 &gt; </dt>
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
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户&gt;</dt>
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
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户&gt;</dt>
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
<dt>扫描 ID： &lt;相关扫描的 ID 号 &gt; 。</dt> 
<dt>扫描类型 &lt; ：扫描类型 &gt; ，例如：<ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
</ul>
</dt>
<dt>扫描参数 &lt; ：扫描参数 &gt; ，例如：<ul>
<li>完全扫描</li>
<li>快速扫描</li>
<li>客户扫描</li>
</ul>
</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
防病毒客户端遇到错误，并且当前扫描已停止。 扫描可能由于客户端问题而失败。 此事件记录包括扫描 ID、扫描类型 (Microsoft Defender 防病毒、反间谍软件、反恶意软件) 、扫描参数、启动扫描的用户、错误代码和错误说明。
若要对此事件进行疑难解答：
<ol>
<li>再次运行扫描。</li>
<li>如果以相同方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持</a>站点，在"搜索"框中输入错误编号<b></b>以查找错误代码。</li>
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
<b>反恶意软件引擎发现恶意软件或其他可能不需要的软件。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>具体</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：<ul>
<li>用户：用户启动</li>
<li>系统：系统已启动</li>
<li>实时：启动实时组件</li>
<li>IOAV：IE 下载Outlook快速附件启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>反恶意软件扫描接口 (AMSI) 。 主要用于保护 PowerShell (脚本，) VBS 脚本，但也可由第三方调用。
UAC </dt> 
<dt>状态 &lt; ： &gt; 状态</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt>签名版本中的进程
<dt>： &lt; 定义版本 &gt; </dt>引擎
<dt>版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
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
<b>反恶意软件平台执行了一个操作来保护系统免受恶意软件或其他可能不需要的软件的攻击。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已采取措施保护此计算机免受恶意软件或其他可能不需要的软件的攻击。 有关详细信息，请参阅：
<dl>
<dt>用户： &lt;Domain &gt; \& lt;用户名 &gt; </dt>
<dt>： &lt; 威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ： &gt; 严重性，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt> 
<dt>操作： &lt; 操作 &gt; ，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：已隔离资源</li>
<li>删除：已删除资源</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作，通常来自用户指定的操作列表</li>
<li>无操作：无操作</li>
<li>阻止：资源被阻止执行</li>
</ul>
</dt>
<dt>状态： &lt;状态 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
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
<b>反恶意软件平台尝试执行保护系统免受恶意软件或其他可能不需要的软件的攻击，但操作失败。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒恶意软件或其他可能不需要的软件时遇到错误。 有关详细信息，请参阅：
<dl>
<dt>用户： &lt;Domain &gt; \& lt;用户名 &gt; </dt>
<dt>： &lt; 威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ： &gt; 严重性，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 操作 &lt; ：操作 &gt; ，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：已隔离资源</li>
<li>删除：已删除资源</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作，通常来自用户指定的操作列表</li>
<li>无操作：无操作</li>
<li>阻止：资源被阻止执行</li>
</ul>
</dt>
<dt>错误代码： &lt;错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
<dt>状态： &lt;状态 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
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
<b>反恶意软件平台从隔离区还原了一个项目。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已还原隔离项目。 有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
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
<b>反恶意软件平台无法从隔离中还原项目。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试从隔离区还原项目时遇到错误。 有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
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
<b>反恶意软件平台从隔离区中删除了一个项目。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已删除隔离邮件。<br/>有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>签名版本： &lt; 定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
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
<b>反恶意软件平台无法从隔离区中删除项目。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试从隔离区删除项目时遇到错误。
有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
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
<b>反恶意软件平台已删除恶意软件和其他可能不需要的软件的历史记录。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已删除恶意软件和其他可能不需要的软件的历史记录。
<dl>
<dt>Time：事件发生的时间，例如清除历史记录的时间。此参数不用于威胁事件，因此不会混淆它是修正时间还是感染时间。对于这些时间，我们专门将它们称为"操作时间"或"检测时间"。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
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
<dt>Time：事件发生的时间，例如清除历史记录的时间。此参数不用于威胁事件，因此不会混淆它是修正时间还是感染时间。对于这些时间，我们专门将它们称为"操作时间"或"检测时间"。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述 &lt; ：错误 &gt; 描述 错误描述。</dt>
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
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>具体</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：<ul>
<li>用户：用户启动</li>
<li>系统：系统已启动</li>
<li>实时：启动实时组件</li>
<li>IOAV：IE 下载Outlook快速附件启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>反恶意软件扫描接口 (AMSI) 。 主要用于保护 PowerShell (脚本，) 也可由第三方调用。
UAC </dt> 
<dt>状态 &lt; ： &gt; 状态</dt>
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; ：PID &gt; 签名</dt>ID
<dt>中的进程：枚举匹配严重性。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎 &gt; </dt>保真
<dt>度标签：</dt>
<dt>目标文件名： &lt; &gt; 文件名文件的名称。</dt>
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
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>具体</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：<ul>
<li>用户：用户启动</li>
<li>系统：系统已启动</li>
<li>实时：启动实时组件</li>
<li>IOAV：IE 下载Outlook快速附件启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>反恶意软件扫描接口 (AMSI) 。 主要用于保护 PowerShell (脚本，) 也可由第三方调用。
UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt>签名版本中的进程
<dt>： &lt; 定义版本 &gt; </dt>引擎
<dt>版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
不需要执行任何操作。 Microsoft Defender 防病毒可以暂停此威胁并对此威胁采取常规操作。 如果要手动删除威胁，请在 Microsoft Defender 防病毒 界面中，单击"清理计算机<b>"。</b>
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
<b>反恶意软件平台执行了一个操作来保护系统免受恶意软件或其他可能不需要的软件的攻击。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒已采取措施保护此计算机免受恶意软件或其他可能不需要的软件的攻击。<br/>有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>具体</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：<ul>
<li>用户：用户启动</li>
<li>系统：系统已启动</li>
<li>实时：启动实时组件</li>
<li>IOAV：IE 下载Outlook快速附件启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>反恶意软件扫描接口 (AMSI) 。 主要用于保护 PowerShell (脚本，) 也可由第三方调用。
UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt> 
<dt> 操作中的进程： &lt; 操作 &gt; ，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：已隔离资源</li>
<li>删除：已删除资源</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作，通常来自用户指定的操作列表</li>
<li>无操作：无操作</li>
<li>阻止：资源被阻止执行</li>
</ul>
</dt>
<dt>操作状态： &lt;其他操作的说明 &gt; 错误</dt>
<dt>代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>引擎版本
<dt> &lt; ：反恶意软件引擎 &gt; </dt>版本 注意：每当 Microsoft Defender 防病毒、Microsoft Security Essentials、恶意软件删除工具或 System Center Endpoint Protection 检测到恶意软件时，它将还原恶意软件可能已更改的以下系统设置和服务：<ul>
<li>默认Internet Explorer或Microsoft Edge设置</li>
<li>用户访问控制设置</li>
<li>部件版式设置</li>
<li>启动控件数据</li>
<li>Regedit 和任务管理器注册表设置</li>
<li>Windows更新、后台智能传输服务和远程过程调用服务</li>
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
WindowsVista (Service Pack 1 或 Service Pack 2) 7 Windows更高版本
</td>
</tr>
<tr>
<td>
服务器操作系统
</td>
<td>
WindowsServer 2008、Windows Server 2008 R2、Windows Server 2012 和 Windows Server 2016
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
无需任何操作。 Microsoft Defender 防病毒或隔离威胁。
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
<b>反恶意软件平台尝试执行保护系统免受恶意软件或其他可能不需要的软件的攻击，但操作失败。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒恶意软件或其他可能不需要的软件时遇到非严重错误。<br/>有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>具体</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：<ul>
<li>用户：用户启动</li>
<li>系统：系统已启动</li>
<li>实时：启动实时组件</li>
<li>IOAV：IE 下载Outlook快速附件启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>反恶意软件扫描接口 (AMSI) 。 主要用于保护 PowerShell (脚本，) VBS 脚本，但也可由第三方调用。
UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt> 
<dt> 操作中的进程： &lt; 操作 &gt; ，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：已隔离资源</li>
<li>删除：已删除资源</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作，通常来自用户指定的操作列表</li>
<li>无操作：无操作</li>
<li>阻止：资源被阻止执行</li>
</ul>
</dt>
<dt>操作状态： &lt;其他操作的说明 &gt; 错误</dt>
<dt>代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需任何操作。 Microsoft Defender 防病毒未能完成与恶意软件修正相关的任务。 这不是一个关键故障。
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
<b>反恶意软件平台在尝试对恶意软件或其他可能不需要的软件采取操作时遇到严重错误。事件消息中会提供更多详细信息。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒恶意软件或其他可能不需要的软件时遇到严重错误。<br/>有关详细信息，请参阅：
<dl>
<dt>名称： &lt;威胁名称 &gt; </dt>
<dt>ID： &lt; 威胁 &gt; ID</dt> 
<dt> 严重性 &lt; ：严重性 &gt; ，例如：<ul>
<li>低</li>
<li>适度</li>
<li>高</li>
<li>严重</li>
</ul>
</dt>
<dt>类别： &lt;类别描述 &gt; ，例如任何威胁或恶意软件类型。</dt>
<dt>路径： &lt;文件路径 &gt; </dt> 
<dt> 检测来源： &lt; 检测 &gt; 来源 ，例如：
<ul>
<li>未知</li>
<li>本地计算机</li>
<li>网络共享</li>
<li>Internet</li>
<li>传入流量</li>
<li>传出流量</li>
</ul>
</dt>
<dt>检测类型 &lt; ：检测类型 &gt; ，例如：<ul>
<li>启发式</li>
<li>Generic</li>
<li>具体</li>
<li>动态签名</li>
</ul>
</dt>
<dt>检测源 &lt; ：检测 &gt; 源，例如：<ul>
<li>用户：用户启动</li>
<li>系统：系统已启动</li>
<li>实时：启动实时组件</li>
<li>IOAV：IE 下载Outlook快速附件启动</li>
<li>NIS：网络检查系统</li>
<li>IEPROTECT：IE - IExtensionValidation;这可抵御恶意网页控件</li>
<li>提前启动反恶意软件 (ELAM) 。 这包括启动序列检测到的恶意软件</li>
<li>远程证明</li>
</ul>反恶意软件扫描接口 (AMSI) 。 主要用于保护 PowerShell (脚本，) 也可由第三方调用。
UAC </dt> 
<dt>用户： &lt; 域 &gt; \& lt;用户 &gt; </dt>
<dt>进程名称 &lt; &gt; ：PID</dt> 
<dt> 操作中的进程： &lt; 操作 &gt; ，例如：<ul>
<li>清理：资源已清理</li>
<li>隔离：已隔离资源</li>
<li>删除：已删除资源</li>
<li>允许：允许执行/存在资源</li>
<li>用户定义：用户定义的操作，通常来自用户指定的操作列表</li>
<li>无操作：无操作</li>
<li>阻止：资源被阻止执行</li>
</ul>
</dt>
<dt>操作状态： &lt;其他操作的说明 &gt; 错误</dt>
<dt>代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
由于Microsoft Defender 防病毒，客户端遇到此错误。 终结点可能不受保护。 查看错误描述，然后按照下面的相关 <b>用户操作</b> 步骤操作。
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
<b>Clean</b>
</td>
<td>
更新定义，然后验证修正是否成功。
</td>
</tr>
<tr>
<td>
<b>隔离</b>
</td>
<td>
更新定义并验证用户是否有权访问必要的资源。
</td>
</tr>
<tr>
<td>
<b>允许</b>
</td>
<td>
验证用户是否有权访问必要的资源。
</td>
</tr>
</table>

如果此事件仍然存在：<ol>
<li>再次运行扫描。</li>
<li>如果以相同方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持</a>站点，在"搜索"框中输入错误编号<b></b>以查找错误代码。</li>
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
<b>Microsoft Defender 防病毒威胁资源推断哈希值。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒客户端正常运行。
<dl>
<dt>当前平台版本： &lt;当前平台版本 &gt; </dt>
<dt>威胁资源路径 &lt; ：路径 &gt; </dt>
<dt>哈希： &lt; 哈希 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>注意：仅在设置了以下策略时，才能记录 <b>此事件：ThreatFileHashLogging 未签名</b>。</div>
<div> </div>
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
<b>如果反恶意软件平台向监控平台报告状态，则此事件指示反恶意软件平台正在运行且状态正常。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒客户端正常运行。
<dl>
<dt>平台版本： &lt;当前平台版本 &gt; </dt>
<dt>签名版本 &lt; ：定义版本 &gt; </dt>引擎
<dt>版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需任何操作。 客户端Microsoft Defender 防病毒状态正常。 此事件每小时报告一次。
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
<b>Endpoint Protection客户端运行状况报告 (UTC 时间) </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
防病毒客户端运行状况报告。
<dl>
<dt>平台版本： &lt;&gt;当前平台</dt>版本 引擎
<dt>版本 &lt; ：反恶意软件引擎 版本 &gt; </dt>网络实时检查引擎版本：
<dt> &lt; 网络实时 &gt; </dt>检查引擎版本 防病毒签名版本：
<dt> &lt; 防病毒 &gt; </dt>签名版本 反
<dt>间谍软件签名版本： &lt; 反间谍软件签名版本 &gt; </dt>网络实时检查
<dt>签名版本： &lt; 网络实时检查签名 &gt; </dt>版本 RTP 状态：实时保护状态 (已启用或已禁用
<dt> &lt; &gt;) </dt>OA 状态：访问状态 (启用或禁用
<dt> &lt; &gt;) </dt> 
<dt>IOAV 状态：IE 下载和 Outlook 快速附件状态 &lt; (&gt; 已启用或</dt>已禁用) BM 状态：行为监视状态 (已启用或已禁用
<dt> &lt; &gt;) </dt>防病毒签名年龄：防病毒签名年龄
<dt> &lt; &gt; (days) </dt> 
<dt>Antispyware signature age： &lt; Antispyware signature age &gt; (in days) </dt>Last quick scan 
<dt>age： Last quick scan age (&lt; in days &gt;) </dt> 
<dt>Last full scan age： Last full scan &lt; age (in days &gt;) </dt> 
<dt>Antivirus signature creation time： ？ &lt;防病毒签名创建时间 &gt; </dt>
<dt>反间谍软件签名创建时间：？ &lt;反间谍软件签名创建时间 上次 &gt; </dt>
<dt>快速扫描开始时间：？ &lt;上次快速扫描开始时间 &gt; 上次</dt>
<dt>快速扫描结束时间：？ &lt;上次快速 &gt; </dt>扫描结束时间 上次快速扫描源：上次快速扫描源 (0 = 扫描未
<dt> &lt; &gt; 运行，1 = 用户启动，2 =</dt>系统启动) 上次完全扫描
<dt>开始时间：？ &lt;上次完全扫描开始时间 &gt; 上次</dt>
<dt>完全扫描结束时间：？ &lt;上次完全 &gt; </dt>扫描结束时间 上次完全扫描源：上次完全扫描源
<dt> (0 = 未运行扫描 &lt; ，1 = 用户启动 &gt; ，2 =</dt>系统启动) 
<dt> 产品状态：用于内部疑难解答
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
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt>
<dt>上一个签名版本 &lt; ： &gt; 上一个签名版本</dt>签名 
<dt> 类型 &lt; ：签名 &gt; 类型，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>更新类型： &lt;更新类型 &gt; ，Full 或 Delta。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎版本 &gt; </dt>
<dt>上一个引擎 &lt; 版本： &gt; 上一个引擎版本</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需任何操作。 客户端Microsoft Defender 防病毒状态正常。 当签名成功更新时，将报告此事件。
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
<dt>新的安全智能版本： &lt;新版本号 &gt; 以前的</dt>
<dt>安全智能版本： &lt; 上一 &gt; 版本</dt> 
<dt> 更新源 &lt; ：更新 &gt; 源，例如：
<ul>
<li>安全智能更新文件夹</li>
<li>内部安全智能更新服务器</li>
<li>Microsoft Update Server</li>
<li>文件共享</li>
<li>Microsoft 恶意软件防护中心 (MMPC) </li>
</ul>
</dt>
<dt>更新阶段 &lt; ：更新阶段 &gt; ，例如：
<ul>
<li>搜索</li>
<li>下载</li>
<li>安装</li>
</ul>
</dt>
<dt>源路径：通用命名约定的文件共享名称 (UNC) 、Windows Server Update Services (WSUS) /Microsoft Update/ADL 的服务器名称。</dt> 
<dt>签名类型 &lt; ：签名类型 &gt; ，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>更新类型： &lt;更新类型 &gt; ，Full 或 Delta。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎版本 &gt; </dt>上一个引擎版本
<dt>： &lt; 上 &gt; </dt>一个引擎版本
<dt>错误代码： &lt; 错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
当更新定义时出现问题时，将发生此错误。
若要对此事件进行疑难解答：
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定义</a> 并强制直接在终结点上重新扫描。</li>
<li>有关此错误的详细信息，请查看 %Windir%\WindowsUpdate.日志文件中的条目。</li>
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
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt>上一个引擎版本：
<dt> &lt; &gt; 以前的</dt>引擎版本 引擎
<dt>类型： &lt; 引擎类型 &gt; ，反恶意软件引擎或网络检查系统引擎。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需任何操作。 客户端Microsoft Defender 防病毒状态正常。 当反恶意软件引擎成功更新时，将报告此事件。
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
<dt>以前的引擎版本： &lt; &gt; 以前的</dt>引擎版本 引擎类型：引擎类型 ，反
<dt> &lt; &gt; 恶意软件引擎或网络检查系统引擎。</dt>
<dt>用户： &lt;Domain &gt; \& lt;用户 &gt; </dt>
<dt>错误代码： &lt; 错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
客户端Microsoft Defender 防病毒失败。 当客户端无法更新自身时，将发生此事件。 此事件通常是由于更新期间网络连接中断引起的。
若要对此事件进行疑难解答：
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">更新定义</a> 并强制直接在终结点上重新扫描。</li>
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
<b>加载反恶意软件定义时出现问题。反恶意软件引擎将尝试加载上一个已知良好的定义集。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试加载签名时遇到错误，并且将尝试还原回已知良好的签名集。
<dl>
<dt>尝试签名：</dt>
<dt>错误代码 &lt; ：错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>签名版本： &lt;定义版本 &gt; </dt>
<dt>引擎版本 &lt; ：反恶意软件引擎版本 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
客户端Microsoft Defender 防病毒下载并安装最新的定义文件，但失败。 当客户端在尝试加载定义时遇到错误，或者文件已损坏时，可能会发生此错误。 Microsoft Defender 防病毒将尝试还原到已知良好的定义集。
若要对此事件进行疑难解答：
<ol>
<li>重新启动计算机并重试。</li>
<li>从网站 下载Microsoft 安全智能<a href="https://aka.ms/wdsi">定义</a>。
注意：从网站下载的定义文件的大小可能超过 60 MB，不应用作更新定义的长期解决方案。
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
<b>反恶意软件引擎加载失败，因为反恶意软件平台已过期。反恶意软件平台将加载已知良好的反恶意软件引擎并尝试更新。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒无法加载反恶意软件引擎，因为当前平台版本不受支持。 Microsoft Defender 防病毒还原到上一个已知良好的引擎，并且将尝试进行平台更新。
<dl>
<dt>当前平台版本： &lt; 当前平台版本&gt;</dt>
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
<dt>当前平台版本： &lt;当前平台版本 &gt; </dt>
<dt>错误代码 &lt; ：错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
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
<b>该平台即将过期。下载最新的平台以保持最新的保护。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒需要更新的平台版本来支持反恶意软件引擎的未来版本。 下载最新的 Microsoft Defender 防病毒 平台以保持可用的最佳保护级别。
<dl>
<dt>当前平台版本： &lt; 当前平台版本&gt;</dt>
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
Microsoft Defender 防病毒动态<i>签名服务</i>检索其他签名以帮助保护你的计算机。
<dl>
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt> 
<dt> 签名类型： &lt; 签名 &gt; 类型 ，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt> 
<dt> 动态签名类型 &lt; ：动态签名 &gt; 类型 ，例如：
<ul>
<li>版本</li>
<li>Timestamp</li>
<li>无限制</li>
<li>期限</li>
</ul>
</dt>
<dt>持久性路径： &lt;路径 &gt; </dt>
<dt>动态签名版本 &lt; ： &gt; 版本号</dt>动态签名编译时间戳：
<dt> &lt; 时间戳 &gt; </dt> 
<dt> 持久性限制类型： &lt; 持久性限制 &gt; 类型，例如：
<ul>
<li>VDM 版本</li>
<li>Timestamp</li>
<li>无限制</li>
</ul>
</dt>
<dt>持久性限制：fastpath 签名的持久性限制。</dt>
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
<b>动态签名服务删除了过期的动态定义。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒动态<i>签名服务丢弃</i>过时的签名。
<dl>
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt> 
<dt> 签名类型： &lt; 签名 &gt; 类型 ，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt> 
<dt> 动态签名类型 &lt; ：动态签名 &gt; 类型 ，例如：
<ul>
<li>版本</li>
<li>Timestamp</li>
<li>无限制</li>
<li>期限</li>
</ul>
</dt>
<dt>持久性路径： &lt;路径 &gt; </dt>
<dt>动态签名版本： &lt; 版本号 &gt; </dt>动态签名
<dt>编译 &lt; &gt; </dt>时间戳：时间戳删除
<dt>原因：</dt> 
<dt> 持久性限制类型： &lt; 持久性限制 &gt; 类型，例如：
<ul>
<li>VDM 版本</li>
<li>Timestamp</li>
<li>无限制</li>
</ul>
</dt>
<dt>持久性限制：fastpath 签名的持久性限制。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
无需任何操作。 客户端Microsoft Defender 防病毒状态正常。 当动态签名服务成功删除过期的动态定义时，将报告此事件。
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
Microsoft Defender 防病毒尝试使用动态签名服务<i>时遇到错误</i>。
<dl>
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt> 
<dt> 签名类型： &lt; 签名 &gt; 类型 ，例如： <ul>
<li>防病毒</li>
<li>反间谍软件</li>
<li>反恶意软件</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>当前引擎版本： &lt;当前引擎版本 &gt; </dt>
<dt>错误代码 &lt; ：错误代码 与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt> 
<dt>动态签名类型： &lt; 动态签名类型 &gt; ，例如：
<ul>
<li>版本</li>
<li>Timestamp</li>
<li>无限制</li>
<li>期限</li>
</ul>
</dt>
<dt>持久性路径： &lt;路径 &gt; </dt>
<dt>动态签名版本 &lt; ： &gt; 版本号</dt>动态签名编译时间戳：
<dt> &lt; 时间戳 &gt; </dt> 
<dt> 持久性限制类型： &lt; 持久性限制 &gt; 类型，例如：
<ul>
<li>VDM 版本</li>
<li>Timestamp</li>
<li>无限制</li>
</ul>
</dt>
<dt>持久性限制：fastpath 签名的持久性限制。</dt>
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
<dt>当前签名版本： &lt; 当前签名版本&gt;</dt>
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
<b>反恶意软件引擎下载了一个干净文件。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒下载了一个干净文件。
<dl>
<dt>文件名： &lt;文件名 &gt; 文件的名称。</dt>
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎 &gt; 版本</dt>
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
<b>反恶意软件引擎无法下载干净文件。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒尝试下载干净文件时遇到错误。
<dl>
<dt>文件名： &lt;文件名 &gt; 文件的名称。</dt>
<dt>当前签名版本： &lt;当前签名版本 &gt; </dt>
<dt>当前引擎版本： &lt; 当前引擎 &gt; 版本</dt>
<dt>错误代码： &lt; 错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
检查 Internet 连接设置。
使用Microsoft Defender 防病毒签名服务将最新定义下载到特定威胁时，客户端遇到错误。 此错误可能是由网络连接问题导致的。
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
<b>反恶意软件引擎已下载，并配置为在下次系统重启时脱机运行。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒下载并配置脱机防病毒，以在下次重启时运行。
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
<dt>错误代码： &lt;错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。 </dt>
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
<b>此操作系统版本的反恶意软件支持即将结束。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
对操作系统的支持即将过期。 在Microsoft Defender 防病毒操作系统上运行非支持操作系统不是防止威胁的足够解决方案。
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
<b>此操作系统的反恶意软件支持已终止。必须升级操作系统，获得持续支持。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
对操作系统的支持已过期。 在Microsoft Defender 防病毒操作系统上运行非支持操作系统不是防止威胁的足够解决方案。
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
<b>反恶意软件引擎不再支持此操作系统，并且不再保护系统免受恶意软件的攻击。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
对操作系统的支持已过期。 Microsoft Defender 防病毒操作系统上不再支持，已停止运行，并且无法抵御恶意软件威胁。
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
Microsoft Defender 防病毒 Real-Time保护功能遇到了错误并失败。
<dl>
<dt>功能 &lt; ：功能 &gt; ，例如：
<ul>
<li>On Access</li>
<li>Internet Explorer下载和 Microsoft Outlook Express 附件</li>
<li>行为监视</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>错误代码： &lt;错误代码 &gt; 与威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。</dt>
<dt>原因：Microsoft Defender 防病毒保护已重启功能的原因。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
应重新启动系统，然后运行完整扫描，因为系统可能一段时间未受保护。
客户端Microsoft Defender 防病毒保护功能由于其中一个服务无法启动而遇到错误。
如果后跟 3007 事件 ID，则失败是临时性的，并且反恶意软件客户端从故障中恢复。
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
<b>从故障中恢复实时保护。当看到此错误时，我们建议运行完整系统扫描。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒实时保护已重新启动功能。 建议运行完整系统扫描，以检测此代理关闭时可能错过的任何项目。
<dl>
<dt>功能 &lt; ：功能 &gt; ，例如：
<ul>
<li>On Access</li>
<li>IE 下载和Outlook Express 附件</li>
<li>行为监视</li>
<li>网络检查系统</li>
</ul>
</dt>
<dt>原因：Microsoft Defender 防病毒实时保护已重启功能的原因。</dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
实时保护功能已重新启动。 如果再次发生此事件，请联系 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持</a>。
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
<b>实时保护已启用。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒恶意软件和其他可能不需要的软件进行实时保护扫描。
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
<b>实时保护处于禁用状态。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒恶意软件和其他可能不需要的软件进行实时保护扫描已禁用。
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
<dt>功能 &lt; ：功能 &gt; ，例如：
<ul>
<li>On Access</li>
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
Microsoft Defender 防病毒已更改。 如果这是意外事件，应查看设置，因为这可能是恶意软件的结果。
<dl>
<dt>旧值： &lt;旧值编号 &gt; 旧的防病毒配置值。</dt>
<dt>新值： &lt;新值编号 &gt; 新的防病毒配置值。</dt>
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
Microsoft Defender 防病毒引擎由于意外错误而终止。
<dl>
<dt>失败类型： &lt;失败类型 &gt; ，例如：崩溃或挂起</dt>
<dt>异常代码 &lt; ：错误代码 &gt; </dt>
<dt>资源： &lt; 资源 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
若要对此事件进行疑难解答：<ol>
<li>尝试重新启动该服务。<ul>
<li>对于反恶意软件、防病毒和间谍软件，在提升的命令提示符下，键入 <b>net stop msmpsvc</b>，然后键入 <b>net start msmpsvc</b> 以重新启动反恶意软件引擎。</li>
<li>对于<i>网络检查系统</i>，在提升的命令提示符下，键入<b>net start nissrv</b>，然后键入<b>net start nissrv</b>以使用 NiSSRV.exe 文件重新启动网络检查系统引擎。 <i></i>
</li>
</ul>
</li>
<li>如果以相同方式失败，请通过访问<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>支持站点，在"搜索"框中输入错误号来查找错误代码<b></b>，然后联系<a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 技术支持</a>。</li>
</ol>
</td>
</tr>
<tr>
<td>
用户操作：
</td>
<td >
由于Microsoft Defender 防病毒错误，客户端引擎停止运行。
若要对此事件进行疑难解答：
<ol>
<li>再次运行扫描。</li>
<li>如果以相同方式失败，请转到<a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft 支持</a>站点，在"搜索"框中输入错误编号<b></b>以查找错误代码。</li>
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
<b>扫描恶意软件和其他可能不需要的软件已启用。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒恶意软件和其他可能不需要的软件扫描已启用。
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
<b>扫描恶意软件和其他可能不需要的软件处于禁用状态。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒恶意软件和其他可能不需要的软件扫描处于禁用状态。
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
<b>扫描病毒已启用。</b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒病毒扫描已启用。
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
<b>扫描病毒已禁用。 </b>
</td>
</tr>
<tr>
<td>
说明:
</td>
<td >
Microsoft Defender 防病毒病毒扫描处于禁用状态。
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
Microsoft Defender 防病毒已进入宽限期并且即将过期。 过期后，此计划将禁用对病毒、间谍软件和其他可能不需要的软件的保护。
<dl>
<dt>过期原因：Microsoft Defender 防病毒过期的原因。</dt>
<dt>到期日期：Microsoft Defender 防病毒到期日期。</dt>
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
Microsoft Defender 防病毒宽限期已过期。 对病毒、间谍软件和其他可能不需要的软件的保护处于禁用状态。
<dl>
<dt>过期原因：</dt>
<dt>到期日期： </dt>
<dt>错误代码： &lt; 错误代码与 &gt; 威胁状态关联的结果代码。标准 HRESULT 值。</dt>
<dt>错误描述： &lt;错误 &gt; 描述 错误描述。 </dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Microsoft Defender 防病毒客户端错误代码 如果Microsoft Defender 防病毒遇到任何问题，它通常会提供一个错误代码来帮助你解决问题。 最常见的错误意味着安装更新时出现问题。
本节提供有关客户端错误的Microsoft Defender 防病毒信息。
- 错误代码 - 错误建议 - 现在要执行哪些操作的可能原因

使用这些表中的信息帮助排查错误Microsoft Defender 防病毒错误代码。


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
此错误指示您可能内存不足。
</td>
</tr>
<tr>
<td>解决方案</td>
<td>
<ol>
<li>检查设备上可用的内存。</li>
<li>关闭运行以释放设备上内存的任何未使用的应用程序。</li>
<li>重新启动设备并再次运行扫描。
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
<li>单击"<b>更新"</b>选项卡上的"更新<b></b>定义"Microsoft Defender 防病毒。 <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>或者，
</li>
<li>从网站 下载Microsoft 安全智能<a href="https://aka.ms/wdsi">定义</a>。
注意：从网站下载的定义文件的大小可能超过 60 MB，不应用作更新定义的长期解决方案。
</li>
</ol>
</li>
<li>运行完整扫描。
</li>
<li>重新启动设备并重试。</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508020</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示可能有引擎配置错误;通常，这与不允许引擎正常运行的输入数据相关。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x805080211
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示无法Microsoft Defender 防病毒威胁。
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
此错误指示威胁可能不再存在于媒体上，或者恶意软件可能会阻止你扫描设备。
</tr><tr><td>解决方案
</td>
<td>
运行<a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft 安全扫描程序，</a>然后更新你的安全软件，然后重试。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508024 </th></tr>
<tr>
<td>邮件</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示可能需要进行完整系统扫描。
</td></tr>
<tr>
<td>解决方案</td><td>
运行完整系统扫描。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508025
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示需要手动步骤才能完成威胁删除。
</td></tr><tr><td>解决方案</td><td>
按照 Microsoft Malware Protection Malware 中概述的 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">手动修正步骤操作</a>。 可以在事件历史记录中查找特定于威胁的链接。<br/></td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508026
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示可能不支持在容器类型内删除。
</td></tr><tr><td>解决方案</td><td>
Microsoft Defender 防病毒无法修正在存档中检测到的威胁。 请考虑手动删除检测到的资源。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508027
</th>
</tr><tr><td>邮件</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示可能会禁用低威胁和中等威胁的删除。
</td></tr><tr><td>解决方案</td><td>
检查检测到的威胁并按要求解决它们。
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
运行完整系统扫描。
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
脱机运行Microsoft Defender 防病毒。 可以在脱机访问文章中Microsoft Defender 防病毒<a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">操作</a>。
</td>
</tr>
<tr>
<th colspan="2">错误代码：0x80508031
</th>
</tr><tr><td>邮件</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>可能的原因</td>
<td>
此错误指示Microsoft Defender 防病毒平台的当前版本，并且需要新版本的平台。
</td></tr><tr><td>解决方案</td><td>
只能在 Microsoft Defender 防病毒 和 Windows 10 Windows 11。 对于 Windows 8、Windows 7 和 Windows Vista，可以使用<a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>。<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a>以下错误代码用于内部测试Microsoft Defender 防病毒。

如果看到这些错误，可以尝试 [更新定义](manage-updates-baselines-microsoft-defender-antivirus.md) 并强制直接在终结点上重新扫描。


<table>
<tr>
<th colspan="3">内部错误代码</th>
</tr>
<tr>
<th><b>错误代码</b></th>
<th>显示的消息</th>
<th>可能的错误原因和解决方法</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
请检查 Internet 连接，然后再次运行扫描。
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
这是内部错误。 原因未明确定义。
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
这是内部错误。 在恶意软件删除未成功时可能会触发它。
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
这是内部错误。 它可能在扫描无法完成时触发。
</td>
</tr>
</table>

## <a name="related-topics"></a>相关主题

- [有关保护Microsoft Defender 防病毒报告](report-monitor-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
