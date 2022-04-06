---
title: Web 保护
description: 了解Microsoft Defender for Endpoint中的 Web 保护以及它如何保护组织
keywords: Web 保护、Web 威胁防护、Web 浏览、安全、网络钓鱼、恶意软件、攻击、网站、网络保护、Edge、Internet Explorer、Chrome、Firefox、Web 浏览器、恶意网站
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4184948316e683a59b45b9397aaea74260e290ee
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664163"
---
# <a name="web-protection"></a>Web 保护

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)。


## <a name="about-web-protection"></a>关于 Web 保护

Microsoft Defender for Endpoint中的 Web 保护是由 [Web 威胁防护](web-threat-protection.md)、[Web 内容筛选](web-content-filtering.md)和[自定义指示器](manage-indicators.md)组成的功能。 Web 保护使你能够保护设备免受 Web 威胁，并帮助你监管不需要的内容。 可以通过转到 **报表> Web 保护**，在Microsoft 365 Defender门户中找到 Web 保护报告。

:::image type="content" source="images/web-protection.png" alt-text="Web 保护卡" lightbox="images/web-protection.png":::

### <a name="web-threat-protection"></a>Web 威胁防护功能

构成 Web 威胁防护的卡片是 **一段时间内的 Web 威胁检测** 和 **Web 威胁摘要**。

Web 威胁防护包括：

- 全面了解影响组织的 Web 威胁。
- 通过警报以及 URL 和访问这些 URL 的设备的综合配置文件，调查与 Web 相关的威胁活动的功能。
- 一整套安全功能，用于跟踪恶意和不需要网站的常规访问趋势。

有关详细信息，请参阅 [Web 威胁防护](web-threat-protection.md)。

### <a name="custom-indicators"></a>自定义指示器

自定义指示器检测也会在组织 Web 威胁报告中汇总，这些报告 **在一段时间内的 Web 威胁检测** 和 **Web 威胁摘要下进行汇总**。

自定义指示器包括：

- 能够创建基于 IP 和 URL 的入侵指标，以保护组织免受威胁。
- 调查与自定义 IP/URL 配置文件相关的活动以及访问这些 URL 的设备的功能。
- 为 IP 和 URL 创建允许、阻止和警告策略的功能。

有关详细信息，请参阅 [创建 IP 和 URL/域的指示器](indicator-ip-domain.md)

### <a name="web-content-filtering"></a>Web 内容筛选

Web 内容筛选包括 **按类别列出的 Web 活动**、 **Web 内容筛选摘要** 和 **Web 活动摘要**。

Web 内容筛选包括：

- 无论用户是在本地还是在本地浏览，都无法访问被阻止类别中的网站。
- 可以使用Microsoft Defender for Endpoint[基于角色的访问控制设置](/microsoft-365/security/defender-endpoint/rbac)中定义的设备组，方便地将各种策略部署到各种用户集。
- 可以访问同一中心位置的 Web 报表，可查看实际块和 Web 使用情况。

有关详细信息，请参阅 [Web 内容筛选](web-content-filtering.md)。

## <a name="order-of-precedence"></a>优先顺序

Web 保护由以下组件组成，按优先顺序列出。 这些组件中的每一个都由 Microsoft Edge 中的 SmartScreen 客户端以及所有其他浏览器和进程中的网络保护客户端强制执行。

- 自定义指示器 (IP/URL、Microsoft Defender for Cloud Apps策略) 
  - 允许
  - 警告
  - 阻止

- Web 威胁 (恶意软件、网络钓鱼) 
  - SmartScreen Intel，包括 Exchange Online Protection (EOP) 
  - 升级

- Web 内容筛选 (WCF) 

> [!NOTE]
> Microsoft Defender for Cloud Apps当前仅为被阻止的 URL 生成指示器。

优先顺序与计算 URL 或 IP 的操作顺序相关。 例如，如果有 Web 内容筛选策略，则可以通过自定义 IP/URL 指示器创建排除项。 与 WCF 块相比，IoC)  (折衷的自定义指示器优先级更高。

同样，在指示器之间的冲突期间，允许始终优先于块 (替代逻辑) 。 这意味着允许指示器将赢得存在的任何块指示器。

下表汇总了一些常见配置，这些配置会在 Web 保护堆栈中造成冲突。 它还根据上面列出的优先级来标识生成的确定。

<br>

****

|自定义指示器策略|Web 威胁策略|WCF 策略|Defender for Cloud应用策略|结果|
|---|---|---|---|---|
|允许|阻止|阻止|阻止|允许 (Web 保护替代) |
|允许|允许|阻止|阻止|允许 (WCF 异常) |
|警告|阻止|阻止|阻止|警告 (重写) |
|

自定义指示器不支持内部 IP 地址。 对于最终用户绕过时发出的警告策略，默认情况下，该用户的站点将取消阻止 24 小时。 管理员可以修改此时间范围，并由 SmartScreen 云服务传下。 在使用 CSP 进行 Web 威胁块 (恶意软件/网络钓鱼) Microsoft Edge，还可以禁用绕过警告的功能。 有关详细信息，请参阅[Microsoft Edge SmartScreen 设置](/DeployEdge/microsoft-edge-policies#smartscreen-settings-policies)。

## <a name="protect-browsers"></a>保护浏览器

在所有 Web 保护方案中，可以同时使用 SmartScreen 和网络保护来确保跨第一方和第三方浏览器和进程进行保护。 SmartScreen 直接内置于Microsoft Edge中，而网络保护则监视第三方浏览器和进程中的流量。 下图说明了此概念。 对于 Web 保护 (指标、Web 威胁、内容筛选) 的所有功能，两个客户端协同工作以提供多个浏览器/应用覆盖范围的图表是准确的。

:::image type="content" source="../../media/web-protection-protect-browsers.png" alt-text="将 smartScreen 和网络保护结合使用" lightbox="../../media/web-protection-protect-browsers.png":::

## <a name="troubleshoot-endpoint-blocks"></a>终结点块疑难解答

来自 SmartScreen 云的响应已标准化。 Fiddler 等工具可用于检查来自云服务的响应，这将有助于确定块的源。

当 SmartScreen 云服务使用允许、阻止或警告响应进行响应时，响应类别和服务器上下文将中继回客户端。 在Microsoft Edge中，响应类别用于确定适当的块页，以显示 (恶意、网络钓鱼、组织策略) 。

下表显示了响应及其相关功能。

<br>

****

|ResponseCategory|负责块的功能|
|---|---|
|CustomPolicy|WCF|
|CustomBlockList|自定义指示器|
|CasbPolicy|Defender for Cloud Apps|
|恶意|Web 威胁|
|网络钓鱼|Web 威胁|
|||

## <a name="advanced-hunting-for-web-protection"></a>高级搜寻 Web 保护

高级搜寻中的Kusto查询可用于汇总组织中长达 30 天的 Web 保护块。 这些查询使用上面列出的信息来区分各种块源，并以用户友好的方式对其进行汇总。 例如，下面的查询列出了源自Microsoft Edge的所有 WCF 块。

```kusto
DeviceEvents
| where ActionType == "SmartScreenUrlWarning"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, Experience=tostring(ParsedFields.Experience)
| where Experience == "CustomBlockList"
```

同样，可以使用下面的查询列出来自网络保护 (的所有 WCF 块，例如，第三方浏览器中的 WCF 块) 。 请注意，ActionType 已更新，"体验"已更改为"ResponseCategory"。

```kusto
DeviceEvents
| where ActionType == "ExploitGuardNetworkProtectionBlocked"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, ResponseCategory=tostring(ParsedFields.ResponseCategory)
| where ResponseCategory == "CustomPolicy"
```

若要列出因自定义指示器) 等 (其他功能而导致的块，请参阅上面概述每个功能及其各自响应类别的表。 还可以修改这些查询，以搜索与组织中的特定计算机相关的遥测数据。 请注意，上述每个查询中显示的 ActionType 将仅显示那些被 Web 保护功能阻止的连接，而不是所有网络流量。

## <a name="user-experience"></a>用户体验

如果用户访问存在恶意软件、网络钓鱼或其他 Web 威胁风险的网页，Microsoft Edge将触发一个块页，其中读取"此网站已报告为不安全"以及与威胁相关的信息。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-malicious-block.png" alt-text="被Microsoft Edge阻止的页面" lightbox="../../media/web-protection-malicious-block.png":::

如果被 WCF 或自定义指示器阻止，则Microsoft Edge中会显示一个块页，告知用户此网站被其组织阻止。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-indicator-blockpage.png" alt-text="组织阻止的页面" lightbox="../../media/web-protection-indicator-blockpage.png":::

在任何情况下，第三方浏览器中不会显示任何块页，并且用户会看到"安全连接失败"页以及 Toast 通知。 根据负责块的策略，用户将在 Toast 通知中看到另一条消息。 例如，Web 内容筛选将显示消息"此内容被阻止"。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-np-block.png" alt-text="由 WCF 阻止的页面" lightbox="../../media/web-protection-np-block.png":::

## <a name="report-false-positives"></a>报告误报

若要报告 SmartScreen 认为危险的网站的误报，请使用Microsoft Edge (块页上显示的链接，如上) 所示。

对于 WCF，可以对域的类别提出异议。 导航到 WCF 报表的 **"域** "选项卡，然后单击 **"报告不准确**"。 浮出控件将打开。 设置事件的优先级，并提供一些其他详细信息，例如建议的类别。 有关如何启用 WCF 以及如何对类别提出异议的详细信息，请参阅 [Web 内容筛选](web-content-filtering.md)。

有关如何提交误报/负数的详细信息，请参[阅Microsoft Defender for Endpoint中的地址误报/负](defender-endpoint-false-positives-negatives.md)数。

## <a name="related-information"></a>相关信息

<br>

****

|主题|说明|
|---|---|
|[Web 威胁防护功能](web-threat-protection.md) | 停止对网络钓鱼网站、恶意软件向量、攻击网站、不受信任或低信誉网站以及已阻止的网站的访问。|
|[Web 内容筛选](web-content-filtering.md) | 根据网站的内容类别跟踪和规范对网站的访问。|
|
