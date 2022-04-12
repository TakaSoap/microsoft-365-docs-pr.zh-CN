---
title: Web 内容筛选
description: 使用Microsoft Defender for Endpoint中的 Web 内容筛选，根据网站的内容类别跟踪和规范对网站的访问。
keywords: Web 防护、Web 威胁防护、Web 浏览、监视、报表、卡片、域列表、安全性、网络钓鱼、恶意软件、攻击、网站、网络保护、Edge、Internet Explorer、Chrome、Firefox、Web 浏览器
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
ms.openlocfilehash: 01000e08153e96042e6873dc45fcb0627ea82e47
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782976"
---
# <a name="web-content-filtering"></a>Web 内容筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)。

Web 内容筛选是Microsoft Defender for Endpoint中的 [Web 保护](web-protection-overview.md)功能的一部分。 它使你的组织能够根据网站的内容类别跟踪和规范对网站的访问。 其中许多网站（虽然不是恶意网站）可能会因为合规性法规、带宽使用或其他问题而出现问题。

跨设备组配置策略以阻止某些类别。 阻止类别可阻止指定设备组中的用户访问与类别关联的 URL。 对于未阻止的任何类别，将自动审核 URL。 用户可以访问 URL 而不会中断，你将收集访问统计信息，以帮助创建更自定义的策略决策。 如果用户正在查看的页面上的元素正在调用被阻止的资源，则会看到块通知。

Web 内容筛选在主要 Web 浏览器上可用，其中包含由 Windows Defender SmartScreen (Microsoft Edge) 和网络保护 (Chrome、Firefox、Brave 和 Opera) 执行的块。 有关浏览器支持的详细信息，请参阅先决条件部分。

## <a name="benefits-of-web-content-filtering"></a>Web 内容筛选的优点

- 无论用户是在本地还是在本地浏览，都无法访问被阻止类别中的网站。

- 安全团队可以使用Microsoft Defender for Endpoint[基于角色的访问控制设置](/microsoft-365/security/defender-endpoint/rbac)中定义的设备组，方便地将策略部署到用户组。

- 安全团队可以访问同一中心位置的 Web 报表，可查看实际块和 Web 使用情况。

## <a name="prerequisites"></a>先决条件

在尝试此功能之前，请确保满足以下要求：

- 订阅包括以下内容之一：Windows 10 企业版 E5、Microsoft 365 E5、Microsoft 365 E5 安全性、Microsoft 365 E3 或Microsoft Defender for Endpoint独立许可证。 

- 可以访问<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>。

- 组织设备运行Windows 10周年更新 (版本 1607) 或更高版本，或Windows 11[最新的防病毒/反恶意软件更新](manage-updates-baselines-microsoft-defender-antivirus.md)。

- Windows Defender在组织的设备上启用 SmartScreen 和网络保护。

## <a name="data-handling"></a>数据处理

数据存储在选择为[Microsoft Defender for Endpoint数据处理设置](data-storage-privacy.md)的一部分的区域中。 数据不会离开该区域中的数据中心。 此外，数据不会与任何第三方（包括我们的数据提供程序）共享。

## <a name="turn-on-web-content-filtering"></a>打开 Web 内容筛选

在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>的左侧导航中，选择 **设置** \> **终结点** \> **常规** \> **高级功能**。 向下滚动，直到看到 **Web 内容筛选** 的条目。 将切换开关切换到 **“打开** ”并 **保存首选项**。

### <a name="configure-web-content-filtering-policies"></a>配置 Web 内容筛选策略

Web 内容筛选策略指定在哪些设备组上阻止哪些站点类别。 若要管理策略，请转到“**规则**) ”下 **设置** \> **终结点** \> **Web 内容筛选** (。

可以部署策略来阻止以下任一父类别或子类别：

<details>
<summary>成人内容</summary>

**邪教**：与团体或运动有关的网站，其成员表现出对不同于社会接受的信念制度的热情。 

**赌博**：网上赌博和网站，促进赌博技能和实践。

**Nudity**：提供全正面和半裸图像或视频的网站，通常采用艺术形式，并且可能允许下载或销售此类材料。

**色情/色情**：以基于图像或文本形式包含色情内容的网站。 此处还列出了任何形式的面向性的内容。

**性教育**：以信息和非偷窥方式讨论性与性行为的网站，包括提供人类生殖和避孕教育的网站、提供预防性疾病感染建议的网站，以及提供性健康问题建议的网站。

**无味**：面向不适合学童观看的内容的网站，或者雇主会对其员工接触感到不自在，但不一定是暴力或色情内容。

**暴力**：显示或宣传与暴力侵害人类或动物有关的内容的网站。

</details>

<details>
<summary>高带宽</summary>

**下载网站**：其主要功能是允许用户下载媒体内容或程序（如计算机程序）的网站。

**图像共享**：主要用于搜索或共享照片的网站，包括具有社交方面的照片。

**对等**：托管对等 (P2P) 软件或使用 P2P 软件促进文件共享的站点。

**流媒体&下载**：其主要功能是流媒体分发的站点，或允许用户搜索、监视或侦听流媒体的网站。
  
</details>

<details>
<summary>法律责任</summary>

**虐待儿童图像**：包括虐待儿童图像或色情制品的网站。 

**犯罪活动**：提供有关非法活动的指导、建议或宣传的网站。

**黑客攻击**：为非法或可疑使用计算机软件或硬件提供资源的网站，包括分发已破解的受版权保护材料的网站。

**仇恨&不容忍**：网站宣传对任何可由种族、宗教、性别、年龄、国籍、身体残疾、经济形势、性偏好或任何其他生活方式选择识别的人口部分的侵略性、降级或辱骂性意见。

**非法药物**：销售非法/受管制物质、促进滥用药物或销售相关用具的场所。

**非法软件**：包含或促进使用恶意软件、间谍软件、僵尸网络、网络钓鱼诈骗或盗版&版权盗窃的网站。

**学校作弊**：与抄袭或学校作弊有关的网站。 

**自残**：促进自残的网站，包括包含针对用户的辱骂和/或威胁性消息的网络欺凌网站。

**武器**：任何出售武器或主张使用武器的地点，包括但不限于枪支、刀具和弹药。

</details>

<details>
<summary>休闲</summary>

**聊天**：主要是基于 Web 的聊天室的网站。

**游戏**：与视频或计算机游戏相关的网站，包括通过托管联机服务或与游戏相关的信息来推广游戏的网站。

**即时消息**：可用于下载即时消息软件或基于客户端的即时消息的站点。

**Professional网络**：提供专业网络服务的站点。

**社交网络**：提供社交网络服务的站点。

**基于 Web 的电子邮件**：提供基于 Web 的邮件服务的网站。
  
</details>

<details>
<summary>未分类</summary>

**新注册的域**：在过去 30 天内新注册但尚未移动到其他类别的站点。

**已寄存的域**：没有内容或已停放以供以后使用的网站。
  
**注意**：未分类仅包含新注册的域和寄存域，并且不包括这些类别之外的所有其他网站。
  
</details>

### <a name="create-a-policy"></a>创建策略

若要添加新策略，请执行以下步骤：

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>中，选择 **设置** > **Web 内容筛选** > **+ 添加策略**。

2. 指定名称。

3. 选择要阻止的类别。 使用展开图标完全展开每个父类别，并选择特定的 Web 内容类别。

4. 指定策略范围。 选择设备组以指定应用策略的位置。 将只阻止所选设备组中的设备访问所选类别中的网站。

5. 查看摘要并保存策略。 策略刷新可能需要长达 2 小时才能应用于所选设备。

> [!NOTE]
>
> - 可以在不选择设备组上的任何类别的情况下部署策略。 此操作将创建仅审核策略，以帮助你在创建块策略之前了解用户行为。
> - 如果同时删除策略或更改设备组，这可能会导致策略部署延迟。
> - 阻止“未分类”类别可能会导致意外和不受欢迎的结果。

## <a name="end-user-experience"></a>最终用户体验

网络保护提供了第三方支持的浏览器的阻止体验，该网络保护提供系统级消息，通知用户连接被阻止。 若要获得更易于用户的浏览器内体验，请考虑使用Microsoft Edge。

### <a name="allow-specific-websites"></a>允许特定网站

可以通过创建自定义指示器策略来重写 Web 内容筛选中阻止的类别以允许单个网站。 当 Web 内容筛选策略应用于相关设备组时，自定义指示器策略将取代该策略。

若要定义自定义指示器，请执行以下步骤：

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender门户</a>中，转到 **设置** \> **终结点****指示**\>器 \> **URL/域** \> **添加项**。

2. 输入网站的域。

3. 将策略操作设置为 **“允许**”。

### <a name="dispute-categories"></a>争议类别

如果遇到已错误分类的域，则可以直接从门户对类别进行争议。

若要对域类别提出异议，请导航到 **报表** \> **Web 保护** \> **Web 内容筛选详细信息** \> **域**。 在 Web 内容筛选报表的“域”选项卡上，会看到每个域旁边的省略号。 将鼠标悬停在此省略号上，然后选择 **“争议类别**”。

将打开一个面板，可在其中选择优先级，并添加更多详细信息，例如建议的类别以进行重新分类。 完成窗体后，选择“ **提交**”。 我们的团队将在一个工作日内查看请求。 若要立即取消阻止，请创建 [自定义允许指示器](indicator-ip-domain.md)。

## <a name="web-content-filtering-cards-and-details"></a>Web 内容筛选卡片和详细信息

选择 **“报表** \> **Web 保护** ”以查看包含有关 Web 内容筛选和 Web 威胁防护的信息的卡片。 以下卡片提供有关 Web 内容筛选的摘要信息。

### <a name="web-activity-by-category"></a>按类别排列的 Web 活动

此卡列出了访问尝试次数增加或减少最多的父 Web 内容类别。 了解组织中 Web 活动模式在过去 30 天、3 个月或 6 个月内发生的激烈变化。 选择类别名称以查看详细信息。

在使用此功能的前 30 天，组织可能没有足够的数据来显示此信息。

:::image type="content" source="images/web-activity-by-category600.png" alt-text="按类别卡分的 Web 活动" lightbox="images/web-activity-by-category600.png":::

### <a name="web-content-filtering--summary-card"></a>Web 内容筛选摘要卡

此卡片显示跨不同父 Web 内容类别的阻止访问尝试的分布。 选择其中一个彩色条形图可查看有关特定父 Web 类别的详细信息。

:::image type="content" source="images/web-content-filtering-summary.png" alt-text="Web 内容筛选摘要卡" lightbox="images/web-content-filtering-summary.png":::

### <a name="web-activity-summary-card"></a>Web 活动摘要卡

此卡片显示所有 URL 中 Web 内容的请求总数。

:::image type="content" source="images/web-activity-summary.png" alt-text="Web 活动摘要卡" lightbox="images/web-activity-summary.png":::

### <a name="view-card-details"></a>查看卡片详细信息

可以通过从卡片中的图表中选择表格行或彩色条来访问每张卡的 **报表详细信息** 。 每张卡的报表详细信息页包含有关 Web 内容类别、网站域和设备组的大量统计数据。

:::image type="content" source="images/web-protection-report-details.png" alt-text="Web 保护报告详细信息" lightbox="images/web-protection-report-details.png":::

- **Web 类别**：列出在组织中尝试访问权限的 Web 内容类别。 选择特定类别以打开摘要浮出控件。

- **域**：列出已在组织中访问或阻止的 Web 域。 选择特定域以查看有关该域的详细信息。

- **设备组**：列出组织中生成 Web 活动的所有设备组

使用页面左上角的时间范围筛选器选择时间段。 还可以筛选信息或自定义列。 选择一行以打开浮出窗格，其中包含有关所选项的详细信息。

### <a name="known-issues-and-limitations"></a>已知问题和限制

仅当设备的 OS 配置为服务器 (**cmd** \> **Systeminfo** \> **OS 配置**) 时，才支持Microsoft Edge。 网络保护仅在服务器设备上的“检查”模式中受支持，服务器设备负责跨受支持的第三方浏览器保护流量。

仅支持Microsoft Edge，Windows 10 Azure 虚拟桌面多会话主机上不支持网络保护。

网络保护目前不支持 SSL 检查，这可能会导致 Web 内容筛选允许某些网站，而这些网站通常会被阻止。 由于在 TLS 握手后对加密流量缺乏可见性，并且无法分析某些重定向，因此允许站点。  这包括将某些基于 Web 的邮件登录页面重定向到邮箱页面。 作为公认的解决方法，可以为登录页创建自定义块指示器，以确保没有用户能够访问该网站。 请记住，这可能会阻止他们访问与同一网站关联的其他服务。 

## <a name="see-also"></a>另请参阅

- [Web 保护功能概述](web-protection-overview.md)
- [Web 威胁防护功能](web-threat-protection.md)
- [监视 web 安全性](web-protection-monitoring.md)
- [响应 web 威胁](web-protection-response.md)
- [网络保护的要求](web-content-filtering.md)
