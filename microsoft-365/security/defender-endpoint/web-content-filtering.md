---
title: Web 内容筛选
description: 使用 Microsoft Defender for Endpoint 中的 Web 内容筛选，根据网站的内容类别跟踪和监管对网站的访问。
keywords: Web 保护， Web 威胁防护， Web 浏览， 监视， 报告， 卡， 域列表， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， Edge， Internet Explorer， Chrome， Firefox， Web 浏览器
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4c316c09ced5e38b51395faea7a84adccc2c2645
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962623"
---
# <a name="web-content-filtering"></a>Web 内容筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)。

Web 内容筛选是 Microsoft Defender for Endpoint 中的 [Web](web-protection-overview.md) 保护功能的一部分。 它使组织能够根据网站的内容类别跟踪和监管对网站的访问。 许多此类网站虽然不是恶意网站，但由于合规性法规、带宽使用情况或其他问题，可能存在问题。

配置跨设备组的策略以阻止某些类别。 阻止类别会阻止指定设备组内的用户访问与该类别关联的 URL。 对于未阻止的任何类别，将自动审核 URL。 用户无需中断即可访问 URL，并且你将收集访问统计信息以帮助创建更自定义的策略决策。 如果用户正在查看的页面上的元素正在调用阻止的资源，则会看到阻止通知。

Web 内容筛选在主要 Web 浏览器上可用，其中包含由 Windows Defender SmartScreen (Microsoft Edge) 和网络保护 (Chrome、Firefox、Filtering 和 Opera) 执行) 。 有关浏览器支持的信息，请参阅先决条件部分。

## <a name="benefits-of-web-content-filtering"></a>Web 内容筛选的好处

- 阻止用户访问被阻止类别的网站，无论他们是在内部浏览还是离开。

- 安全团队可以使用 Microsoft Defender for Endpoint 基于角色的访问控制设置中定义的设备组，便捷地将策略 [部署到用户组](/microsoft-365/security/defender-endpoint/rbac)。

- 安全团队可以访问位于相同中心位置的 Web 报告，并查看实际块和 Web 使用情况。

## <a name="prerequisites"></a>先决条件

在尝试此功能之前，请确保满足以下要求：

- 订阅包括以下各项之一：Windows 10 企业版 E5、Microsoft 365 E5、Microsoft 365 E5 安全性、Microsoft 365 E3 + Microsoft 365 E5 安全性 加载项或 Microsoft Defender for Endpoint独立许可证。 

- 你有权访问 Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户</a>。

- 组织的设备正在运行 Windows 10 周年更新 (版本 1607) 或更高版本，或 Windows 11最新防病毒/反恶意软件[更新](manage-updates-baselines-microsoft-defender-antivirus.md)。

- Windows Defender在组织的设备上启用 SmartScreen 和网络保护。

## <a name="data-handling"></a>数据处理

数据存储在已选择作为 Microsoft Defender 终结点数据处理设置的[一部分的区域。](data-storage-privacy.md) 您的数据不会离开该区域中的数据中心。 此外，你的数据不会与任何第三方共享，包括我们的数据提供程序。

## <a name="turn-on-web-content-filtering"></a>打开 Web 内容筛选

从左侧导航门户中 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">，Microsoft 365 Defender"</a>**终结点设置** \>  \> **高级** \> **功能"。** 向下滚动，直到您看到用于 Web 内容 **筛选的条目**。 将开关切换到 **开** 和 **保存首选项**。

### <a name="configure-web-content-filtering-policies"></a>配置 Web 内容筛选策略

Web 内容筛选策略指定在哪些设备组上阻止哪些网站类别。 若要管理策略，请转到"设置"下 (终结点 \>  \> **Web** 内容) 。 

可以部署策略来阻止以下任何父类别或子类别：

<details>
<summary>成人内容</summary>

**网站：** 与组或运动相关的网站，这些团队或活动的成员对不同于社交接受的社交系统具有信心。 

**培训：** 在线培训以及促进培训技能和实践的网站。

**Nudity：** 通常以艺术形式提供全面和半录制图像或视频的网站，并且可能允许下载或出售此类材料。

**黄色/广告：** 基于图像或文本形式包含明确内容的网站。 此处还列出了任何形式的面向材质的材料。

性教育：以信息和非 voyeuristic 方式讨论性与性的网站，包括提供有关人类感染和性取向的教育的网站、提供防止性感染建议的网站，以及提供有关性健康问题建议的网站。

**无理**：面向不适合学校儿童查看的内容的网站，或者雇主会随员工访问而感到不满意，但不一定令人信念或色情。

**暴力**：显示或宣传与针对人类或动物的暴力相关的内容的网站。

</details>

<details>
<summary>高带宽</summary>

**下载网站**：主要功能是允许用户下载媒体内容或程序（如计算机程序）的网站。

**图像共享**：主要用于搜索或共享照片的网站，包括具有社交方面的内容。

**对等：** 承载对等 (P2P) 或促进使用 P2P 软件共享文件的网站。

**流&** 下载：主要功能是流式媒体分发的网站，或允许用户搜索、观看或收听流式媒体的网站。
  
</details>

<details>
<summary>法律责任</summary>

**儿童滥用图像**：包括儿童滥用图像或滥用的网站。 

**犯罪活动**：对非法活动进行说明、建议或宣传的网站。

**黑客** 攻击：提供资源以非法或有问题地使用计算机软件或硬件的网站，包括分发已被盗的受版权保护材料的网站。

**恶意&：** 网站宣传有关可能由种族、性别、性别、年龄、年龄、身体障碍、经济状况、性取向或其他任何生活方式选择识别的任何部分具有攻击性、降级或滥用性观点的网站。

**非法武器**：销售非法/受控非法非法者、宣传滥用或销售相关参数的站点。

**非法软件**：包含或宣传使用恶意软件、间谍软件、botnet、欺诈邮件或盗用版权&的网站。

**学校欺诈**：与欺骗或学校欺骗相关的网站。 

**自我危害**：宣传自我危害的网站，包括包含滥用和/或威胁用户消息的网络威胁网站。

**武器**：任何销售武器或宣传使用武器的网站，包括但不限于武器、武器和武器。

</details>

<details>
<summary>百分百</summary>

**聊天**：主要是基于 Web 的聊天室的网站。

**游戏**：与视频或计算机游戏相关的网站，包括通过托管联机服务或与游戏有关的信息推广游戏的网站。

**即时消息：** 可用于下载即时消息软件或基于客户端的即时消息的网站。

**Professional网络**：提供专业网络服务的网站。

**社交网络：** 提供社交网络服务的网站。

**基于 Web 的电子邮件**：提供基于 Web 的邮件服务的网站。
  
</details>

<details>
<summary>未分类</summary>

**新注册的** 域：过去 30 天内新注册但尚未移至其他类别的网站。

**已停域**：没有内容或已等待以后使用的网站。
  
**注意**：未分类仅包含新注册的域和已注册的域，不包括这些类别之外的所有其他网站。
  
</details>

### <a name="create-a-policy"></a>创建策略

若要添加新策略，请按照以下步骤操作：

1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal，</a>choose **设置**  >  **Web content filtering**+ Add  >  **policy**.

2. 指定名称。

3. 选择要阻止的类别。 使用展开图标完全展开每个父类别并选择特定的 Web 内容类别。

4. 指定策略作用域。 选择设备组以指定在何处应用策略。 将仅阻止所选设备组中设备访问所选类别中的网站。

5. 查看摘要并保存策略。 策略刷新可能需要 2 个小时才能应用到所选设备。

> [!NOTE]
>
> - 无需在设备组上选择任何类别即可部署策略。 此操作将创建仅审核策略，以帮助你在创建阻止策略之前了解用户行为。
> - 如果同时删除策略或更改设备组，这可能会导致策略部署延迟。
> - 阻止"未分类"类别可能会导致意外和意外的结果。

## <a name="end-user-experience"></a>最终用户体验

第三方支持的浏览器的阻止体验由网络保护提供，它提供一条系统级消息，通知用户阻止的连接。 为获得更用户友好的浏览器内体验，请考虑使用Microsoft Edge。

### <a name="allow-specific-websites"></a>允许特定网站

通过创建自定义指示器策略，可以覆盖 Web 内容筛选中阻止的类别以允许单个网站。 当自定义指示器策略应用于有关设备组时，它将取代 Web 内容筛选策略。

若要定义自定义指示器，请按照以下步骤操作：

1. 在Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中</a>，**转到"设置** 终结点指示器 \>  \>  \> **URL/域** \> **添加项"。**

2. 输入网站的域。

3. 将策略操作设置为 **"允许"。**

### <a name="dispute-categories"></a>争议类别

如果遇到未正确分类的域，可以直接在门户中对类别进行争议。

要争议域的类别，请导航 **到"报告** Web 保护 Web 内容 \>  \> **筛选详细信息域** \> **"。** 在"Web 内容筛选"报表的"域"选项卡上，你将在每个域旁边看到省略号。 将鼠标悬停在此省略号上，然后选择"**争议类别"。**

将打开一个面板，可在其中选择优先级并添加更多详细信息，如建议重新分类的类别。 完成表单后，选择"提交 **"。** Our team will review the request within one business day. 若要立即取消阻止，请创建自定义 [允许指示器](indicator-ip-domain.md)。

### <a name="url-category-lookup"></a>URL 类别查找

若要确定网站的类别，可以使用终结点搜索 下Microsoft 365 Defender门户 () <https://security.microsoft.com> **URL** \> **搜索函数**。 在 URL 搜索结果中，Web 内容筛选类别显示在 **"URL/域详细信息"下**。 管理员也可以直接从此页面就域的类别进行争议，如下图所示。 如果未显示类别结果，则当前未将 URL 分配给现有的 Web 内容筛选类别。

![Web 内容筛选类别查找结果的图像。](../../media/web-content-filtering-category-lookup.png)

## <a name="web-content-filtering-cards-and-details"></a>Web 内容筛选卡和详细信息

选择 **"** \> **报告 Web 保护** "以查看包含有关 Web 内容筛选和 Web 威胁防护信息的卡片。 以下卡片提供有关 Web 内容筛选的摘要信息。

### <a name="web-activity-by-category"></a>按类别分类的 Web 活动

此卡片列出了访问尝试次数最大或减少的父 Web 内容类别。 了解过去 30 天、3 个月或 6 个月内组织中 Web 活动模式的变化。 选择类别名称以查看详细信息。

在使用此功能的前 30 天内，您的组织可能没有足够的数据来显示此信息。

![按类别卡片分类的 Web 活动的图像。](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Web 内容筛选摘要卡

此卡片显示阻止访问尝试跨不同父 Web 内容类别的分布。 选择其中一个彩色栏以查看有关特定父 Web 类别的信息。

![Web 内容筛选摘要卡的图像。](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Web 活动摘要卡片

此卡片显示所有 URL 中 Web 内容的请求总数。

![Web 活动摘要卡片的图像。](images/web-activity-summary.png)

### <a name="view-card-details"></a>查看卡片详细信息

通过从卡片 **的** 图表中选择表格行或彩色条，可以访问每张卡片的报告详细信息。 每个卡片的报告详细信息页面包含有关 Web 内容类别、网站域和设备组的广泛统计数据。

![Web 保护报告详细信息的图像。](images/web-protection-report-details.png)

- **Web 类别**：列出组织中已尝试访问的 Web 内容类别。 选择特定类别以打开摘要飞出。

- **域**：列出组织中已访问或阻止的 Web 域。 选择特定域以查看有关该域的详细信息。

- **设备组**：列出在组织中生成 Web 活动的所有设备组

使用页面左上方的时区筛选器选择时间段。 还可以筛选信息或自定义列。 选择一行以打开一个包含有关所选项目的详细信息的飞出窗格。

### <a name="known-issues-and-limitations"></a>已知问题和限制

如果你Microsoft Edge操作系统配置是 Server (**cmd** \> **Systeminfo** \> **OS Configuration**) 。 网络保护仅在服务器设备的检查模式下受支持，它负责保护跨受支持的第三方浏览器的流量。

网络保护当前不支持 SSL 检查，这可能会导致 Web 内容筛选允许某些网站，这些网站通常会被阻止。 由于 TLS 握手发生后无法查看加密流量，并且无法分析某些重定向，因此将允许网站。  这包括从一些基于 Web 的邮件登录页重定向到邮箱页面。 作为一种接受的解决方法，您可以为登录页创建自定义阻止指示器，以确保任何用户都无法访问该网站。 请记住，这可能会阻止他们访问与同一网站关联的其他服务。 

## <a name="see-also"></a>另请参阅

- [Web 保护功能概述](web-protection-overview.md)
- [Web 威胁防护功能](web-threat-protection.md)
- [监视 web 安全性](web-protection-monitoring.md)
- [响应 web 威胁](web-protection-response.md)
- [网络保护的要求](web-content-filtering.md)
