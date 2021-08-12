---
title: Web 内容筛选
description: 使用 Microsoft Defender for Endpoint 中的 Web 内容筛选，根据网站的内容类别跟踪和监管对网站的访问。
keywords: Web 保护， Web 威胁防护， Web 浏览， 监视， 报告， 卡， 域列表， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7395e7fb22c8ad090ab35868d385fa240700505c
ms.sourcegitcommit: b3c4816b55657b87ed4a5f6a4abe3d505392218e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2021
ms.locfileid: "53726402"
---
# <a name="web-content-filtering"></a>Web 内容筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Web 内容筛选当前处于公共预览阶段**<br>
> 此预览版未提供服务水平协议，不建议用于生产工作负载。 某些功能可能不受支持，也可能具有受限功能。
> 有关详细信息，请参阅 [Microsoft Defender for Endpoint 预览功能](preview.md)。

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)。

Web 内容筛选是 Microsoft Defender for Endpoint 中的 [Web](web-protection-overview.md) 保护功能的一部分。 它使组织能够根据网站的内容类别跟踪和监管对网站的访问。 许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。

配置跨设备组的策略以阻止某些类别。 阻止类别会阻止指定设备组内的用户访问与该类别关联的 URL。 对于未阻止的任何类别，将自动审核 URL。 用户无需中断即可访问 URL，并且你将收集访问统计信息以帮助创建更自定义的策略决策。 如果用户正在查看的页面上的元素正在调用阻止的资源，则会看到阻止通知。

Web 内容筛选在主要 Web 浏览器上可用，其中包含由 Windows Defender SmartScreen (Microsoft Edge) 和网络保护 (Chrome、Firefox、Filtering 和 Opera) 执行) 。 有关浏览器支持的信息，请参阅先决条件部分。

总结优点：

- 阻止用户访问被阻止类别的网站，无论他们是在内部浏览还是离开
- 安全团队可以使用 Microsoft Defender for Endpoint 基于角色的访问控制设置中定义的设备组，便捷地将策略 [部署到用户组](/microsoft-365/security/defender-endpoint/rbac)
- 安全团队可以访问位于相同中心位置的 Web 报告，并查看实际块和 Web 使用情况

## <a name="prerequisites"></a>先决条件

在尝试此功能之前，请确保满足以下要求：

- Windows 10 企业版E5、Microsoft 365 E5、Microsoft 365 E5 安全性、Microsoft 365 E3 + Microsoft 365 E5 安全性 加载项或 Microsoft Defender for Endpoint 独立许可证。 
- 访问 Microsoft 365 Defender 门户 (https://security.microsoft.com) 。
- 运行 Windows 10 周年更新 (版本 1607) 或更高版本使用最新的 MoCAMP 更新。
- Windows DefenderSmartScreen 和网络保护已启用。

## <a name="user-experience"></a>用户体验

第三方支持的浏览器的阻止体验由网络保护提供，它提供一个系统级 Toast，以通知用户阻止的连接。 为获得更用户友好的浏览器内体验，请考虑使用Microsoft Edge。

## <a name="data-handling"></a>数据处理

数据存储在已选择作为 Microsoft Defender 终结点数据处理设置的[一部分的区域。](data-storage-privacy.md) 您的数据不会离开该区域中的数据中心。 此外，你的数据不会与任何第三方共享，包括我们的数据提供程序。

## <a name="turn-on-web-content-filtering"></a>打开 Web 内容筛选

从左侧导航菜单中，选择"设置  >    >  **终结点常规**  >  **高级功能"。** 向下滚动，直到您看到用于 Web 内容 **筛选的条目**。 将开关切换到 **开** 和 **保存首选项**。

### <a name="configure-web-content-filtering-policies"></a>配置 Web 内容筛选策略

Web 内容筛选策略指定在哪些设备组上阻止哪些网站类别。 若要管理策略，请转到"设置"下 (终结点  >    >  **Web** 内容) 。 

使用筛选器查找包含特定阻止类别或应用于特定设备组的策略。

### <a name="create-a-policy"></a>创建策略

添加新策略：

1. 选择 **"Web 内容** 筛选"**页上的"** 添加 **设置"。**

2. 指定名称。

3. 选择要阻止的类别。 使用展开图标完全展开每个父类别并选择特定的 Web 内容类别。

4. 指定策略作用域。 选择设备组以指定在何处应用策略。 将仅阻止所选设备组中设备访问所选类别中的网站。

5. 查看摘要并保存策略。 策略刷新可能需要 2 个小时才能应用到所选设备。

> [!NOTE]
> - 无需在设备组上选择任何类别即可部署策略。 此操作将创建仅审核策略，以帮助你在创建阻止策略之前了解用户行为。
> - 如果同时删除策略或更改设备组，这可能会导致策略部署延迟。
> - 阻止"未分类"类别可能会导致意外和意外的结果。  

### <a name="allow-specific-websites"></a>允许特定网站

通过创建自定义指示器策略，可以覆盖 Web 内容筛选中阻止的类别以允许单个网站。 当自定义指示器策略应用于有关设备组时，它将取代 Web 内容筛选策略。

1. 通过Microsoft 365 Defender终结点设置 URL/域 **添加项**，在 Microsoft 365 Defender 门户  >    >    >    >  **中创建自定义指示器**。

2. 输入网站的域。

3. 将策略操作设置为 **"允许"。**  

### <a name="dispute-categories"></a>争议类别

如果遇到未正确分类的域，可以直接在门户中就类别进行争议。 

要争议域的类别，请导航 **到"报告** Web 保护 Web 内容  >    >  **筛选详细信息** 域  >  **"。** 在"Web 内容筛选"报表的"域"选项卡上，你将在每个域旁边看到省略号。 将鼠标悬停在此省略号上，然后选择"**争议类别"。**

将打开一个面板，您可以在其中选择优先级并添加其他详细信息，例如建议用于重新分类的类别。 完成表单后，选择"提交 **"。** Our team will review the request within one business day. 若要立即取消阻止，请创建自定义 [允许指示器](indicator-ip-domain.md)。

### <a name="url-category-lookup"></a>URL 类别查找

若要确定网站的类别，可以使用网站门户或网站上提供的 URL https://security.microsoft.com) Microsoft 365 Defender (。 在 URL 搜索结果中，Web 内容筛选类别显示在 **"URL/域详细信息"下**。 管理员也可以直接从此页面就域的类别进行争议，如下图所示。 如果未显示类别结果，则当前未将 URL 分配给现有的 Web 内容筛选类别。

![Web 内容筛选类别查找结果的图像](../../media/web-content-filtering-category-lookup.png)

## <a name="web-content-filtering-cards-and-details"></a>Web 内容筛选卡和详细信息

选择 **"**  >  **报告 Web 保护**"以查看包含有关 Web 内容筛选和 Web 威胁防护信息的卡片。 以下卡片提供有关 Web 内容筛选的摘要信息。

### <a name="web-activity-by-category"></a>按类别分类的 Web 活动

此卡片列出了访问尝试次数最大或减少的父 Web 内容类别。 了解过去 30 天、3 个月或 6 个月内组织中 Web 活动模式的变化。 选择类别名称以查看详细信息。

在使用此功能的前 30 天内，您的组织可能没有足够的数据来显示此信息。

![按类别卡片分类的 Web 活动的图像](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Web 内容筛选摘要卡

此卡片显示阻止访问尝试跨不同父 Web 内容类别的分布。 选择其中一个彩色栏以查看有关特定父 Web 类别的信息。

![Web 内容筛选摘要卡的图像](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Web 活动摘要卡片

此卡片显示所有 URL 中 Web 内容的请求总数。

![Web 活动摘要卡片的图像](images/web-activity-summary.png)

### <a name="view-card-details"></a>查看卡片详细信息

通过从卡片 **的** 图表中选择表格行或彩色条，可以访问每张卡片的报告详细信息。 每个卡片的报告详细信息页面包含有关 Web 内容类别、网站域和设备组的广泛统计数据。

![Web 保护报告详细信息的图像](images/web-protection-report-details.png)

- **Web 类别**：列出组织中已尝试访问的 Web 内容类别。 选择特定类别以打开摘要飞出。

- **域**：列出组织中已访问或阻止的 Web 域。 选择特定域以查看有关该域的详细信息。

- **设备组**：列出在组织中生成 Web 活动的所有设备组

使用页面左上方的时区筛选器选择时间段。 还可以筛选信息或自定义列。 选择一行以打开一个包含有关所选项目的详细信息的飞出窗格。

## <a name="errors-and-issues"></a>错误和问题

### <a name="limitations-and-known-issues-in-this-preview"></a>此预览版中的限制和已知问题

- 如果你Microsoft Edge操作系统配置是 Server (  >  **systeminfo** OS Configuration) ，则仅支持此  >  ) 。 网络保护仅在服务器设备的"检查"模式下受支持，它负责保护受支持的第三方浏览器上的流量。

- 未分配的设备将在报告内显示不正确的数据。 在"**报告详细信息**  >  **""** 设备组透视表"中，你可能会看到一个包含空白"设备组"字段的行。 此组包含未分配设备，然后再放入指定组。 此行的报告可能不包含设备或访问计数的准确计数。

- Web 内容筛选报告当前限制为显示前 5000 条记录。 例如，"域"报告最多只显示给定筛选器查询前 5000 个域（如果适用）。 



- [Web 保护功能概述](web-protection-overview.md)
- [Web 威胁防护功能](web-threat-protection.md)
- [监视 web 安全性](web-protection-monitoring.md)
- [响应 web 威胁](web-protection-response.md)
- [网络保护的要求](web-content-filtering.md)

