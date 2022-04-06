---
title: Microsoft Defender for Office 365 计划中的市场活动视图
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 了解 Microsoft Defender for Office 365 中的市场活动Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d8fad29e82b647d309d3b7046e36bd03b64de81d
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682540"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的市场活动视图

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)

市场活动视图是 Microsoft Defender for Office 365 计划 2 中的一项功能 (例如，Microsoft 365 E5 或具有 Defender for Office 365 计划 2 加载项的) 。 活动门户中的Microsoft 365 Defender标识和分类服务中的网络钓鱼攻击。 Campaign Views 可以帮助你：

- 高效调查和应对钓鱼攻击。
- 更好地了解攻击范围。
- 向决策者展示价值。

借助 Campaign Views，可以让你比任何人都更快获得有关攻击的更全面概览。

## <a name="what-is-a-campaign"></a>什么是活动 (campaign)？

活动是针对一个或多个组织的协同式电子邮件攻击。 窃取凭据和公司数据的电子邮件攻击是一个规模较大且非常大规模的行业。 随着技术不断增强，攻击者会修改其方法以确保持续成功。

Microsoft 利用整个服务中的大量反网络钓鱼、反垃圾邮件和反恶意软件数据来帮助识别活动。 我们根据多个因素分析和分类攻击信息。 例如：

- **攻击源**：源 IP 地址和发件人电子邮件域。
- **邮件** 属性：邮件的内容、样式和语气。
- **邮件收件人**：收件人如何相关。 例如，收件人域、收件人工作职能 (管理员、主管人员等 ) 、公司类型 (大型、小型、公共、私有等 ) 和行业。
- **攻击负载**：邮件中的恶意链接、附件或其他有效负载。

活动可能是短期的，或者可能跨越几天、几周或几个月的活动和无效时段。 可能针对你的特定组织启动市场活动，或者你的组织可能是跨多个公司进行更大活动的一部分。

## <a name="campaign-views-in-the-microsoft-365-defender-portal"></a>活动门户中的Microsoft 365 Defender视图

Campaign Views is available in the Microsoft 365 Defender portal at <https://security.microsoft.com> **Email & collaboration** \> **Campaigns**， or directly at <https://security.microsoft.com/campaigns>.

![活动门户中的Microsoft 365 Defender概述。](../../media/campaigns-overview.png)

还可以从：

- **电子邮件&协作** \>**资源管理器** \>**视图** \>**市场活动**
- **电子邮件&协作** \>**资源管理器** \>**视图** \>**所有电子邮件** \>**"市场活动"** 选项卡
- **电子邮件&协作** \>**资源管理器** \>**视图** \>**钓鱼邮件** \>**"市场活动"** 选项卡
- **电子邮件&协作** \>**资源管理器** \>**视图** \>**恶意软件** \>**"市场活动"** 选项卡

若要访问市场活动视图，你需要是组织管理、安全管理员或安全读者角色组的成员，Microsoft 365 Defender组。 有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

## <a name="campaigns-overview"></a>市场活动概述

概述页面显示有关所有市场活动的信息。

在默认 **"市场活动"** 选项卡上，"市场活动类型"区域显示一个条形图，显示每天的收件人数。 默认情况下，此图显示钓鱼 **和****恶意软件** 数据。

> [!TIP]
> 如果看不到任何市场活动数据，请尝试更改日期范围或 [筛选器](#filters-and-settings)。

概述页面上图表下方的表在"市场活动"选项卡上 **显示** 以下信息：

- **名称**

- **示例主题**：活动中某封邮件的主题行。 请注意，活动的所有邮件不一定具有相同的主题。

- 目标：计算得出的百分比： (组织中活动收件人的数量) / (服务组织中所有组织的活动中的收件人) 。 此值指示仅将活动定向到组织的程度 (该值高于) ，而此值也指向服务中的其他组织 (值较低的) 。

- **类型**：此值为 **Phish** 或 **Malware**。

- **子类型**：此值包含有关市场活动的更多详细信息。 例如：
  - **网络钓鱼**：如果可用，则此市场活动所钓鱼的品牌。 例如，、 `Microsoft`、 `365`、 `Unknown`、 `Outlook`或 `DocuSign`。
  - **恶意软件**：例如 或 `HTML/PHISH` `HTML/<MalwareFamilyName>`。

  如果可用，此市场活动所钓鱼的品牌。 当 Defender 针对技术驱动检测Office 365，前缀 **ATP-** 将添加到子类型值。

- **收件人**：此活动所面向的用户数。

- **收件箱**：收件箱中接收来自此活动的邮件的用户数 ("垃圾邮件"文件夹) 。

- **单击**：单击 URL 或在网络钓鱼邮件中打开附件的用户数。

- **单击率**：由"**ClickedInboxed** / "**计算的百** 分比。 此值是活动有效性的指示器。 换句话说，如果收件人能够将邮件标识为网络钓鱼邮件，并且他们未单击有效负载 URL。

  请注意， **点击** 率不用于恶意软件市场活动。

- **已** 访问：实际上有多少用户进入有效负载网站。 如果存在 **Clicked 值**，保险箱链接阻止访问网站，则此值将为 0。

" **宣传活动源** "选项卡显示世界地图中的邮件源。

### <a name="filters-and-settings"></a>筛选器和设置

在" **市场活动"页面** 顶部，有几个筛选器和查询设置可帮助你查找和隔离特定市场活动。

![市场活动筛选器。](../../media/campaign-filters-and-settings.png)

可以执行的最基本筛选是开始日期/时间和结束日期/时间。

若要进一步筛选视图，可以通过单击"市场活动类型"按钮，进行选择，然后单击"刷新"，执行具有多个值的筛选的单个 **属性**。

以下列表介绍了"市场活动类型"按钮 **中提供的可** 筛选市场活动属性：

- **基本**：
  - **市场活动类型**：选择 **"恶意软件"** 或 **"钓鱼邮件"**。 清除选定内容与同时选择两者的结果相同。
  - **市场活动名称**
  - **Campaign 子类型**
  - **发件人**
  - **Recipients**
  - **发件人域**
  - **主题**
  - **附件的文件名**
  - **恶意软件系列**
  - **标记**：应用了指定用户标记的用户或组 (包括优先级帐户) 。 有关用户标记详细信息，请参阅用户 [标记](user-tags.md)。
  - **传递操作**
  - **其他操作**
  - **方向性**
  - **检测技术**
  - **原始送达位置**
  - **最新送达位置**
  - **系统覆盖**

- **高级**：
  - **Internet 邮件 ID**：在邮件 **头的 Message-ID** 头字段中可用。 示例值是 (`<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 尖括号) 。
  - **网络邮件 ID**：在邮件头的 **X-MS-Exchange-Organization-Network-Message-Id** 头字段中可用的 GUID 值。
  - **发件人 IP**
  - **附件 SHA256**：若要在 Windows 中查找文件的 SHA256 哈希值，在命令提示符中运行以下命令：`certutil.exe -hashfile "<Path>\<Filename>" SHA256`。
  - **群集 ID**
  - **警报 ID**
  - **警报策略 ID**
  - **市场活动 ID**
  - **ZAP URL 信号**

- **URL**：
  - **URL 域**
  - **URL 域和路径**
  - **URL**
  - **URL 路径**
  - **单击裁定**

对于更高级的筛选（包括按多个属性进行筛选）可以单击"高级筛选器"按钮生成查询。 相同的市场活动属性可用，但具有以下增强功能：

- 可以单击" **添加条件"** 选择多个条件。
- 您可以在条件之间 **选择 And** 或 **Or** 运算符。
- 可以选择条件 **列表底部的"** 条件"组项以形成复杂的复合条件。

完成后，单击"查询 **"** 按钮。

创建基本或高级筛选器后，可以使用"保存查询"或"另存为"**查询来保存它**。 稍后，当你返回到"市场活动"页面时，可以通过单击"已保存的查询设置"加载 **已保存的筛选器**。

若要导出图表或市场活动列表，请单击"导出"**，然后选择"****导出图表数据**"或"**导出市场活动列表"**。

如果你有 Microsoft Defender for Endpoint 订阅，可以单击 **MDE 设置** Microsoft Defender for Endpoint 连接或断开活动信息。 有关详细信息，请参阅将 [Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 集成](integrate-office-365-ti-with-mde.md)。

## <a name="campaign-details"></a>活动详细信息

当你单击某个市场活动的名称时，市场活动详细信息将显示在一个飞出内容中。

### <a name="campaign-information"></a>市场活动信息

在市场活动详细信息视图顶部，提供以下市场活动信息：

- **市场活动 ID**：唯一市场活动标识符。
- **活动**：活动的持续时间和活动。
- 所选日期范围筛选器或你在日程表 (中选择的日期范围筛选器的以下) ：
- **影响**
- **邮件**：收件人总数。
- **收件箱**：传递到收件箱而不是垃圾邮件文件夹的邮件数。
- **单击的链接**：单击网络钓鱼邮件中的 URL 有效负载的用户数。
- **已访问链接**：访问 URL 的用户数。
- **目标 (%)**：计算得出的百分比： (组织中活动收件人数) / (服务) 中所有组织的活动中的收件人总数。 请注意，此值在活动的整个生命周期内计算，不会基于日期筛选器更改。
- 市场活动流的开始日期/时间和结束数据/时间筛选器，如下一节中所述。
- 活动活动的交互式时间线：时间线显示活动在整个生命周期中的活动。 你可以将鼠标悬停在图形数据点上方，以查看检测到的邮件数量。

![市场活动信息。](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>活动流

在活动详细信息视图的中间，有关市场活动的重要详细信息在称为" _Sankey_ 图表"视图 (流程图) 。 这些详细信息将帮助你了解活动的元素和组织中的潜在影响。

> [!TIP]
> 流程图中显示的信息由日程表中的日期范围筛选器控制，如上一节中所述。

![不包含用户 URL 单击的市场活动详细信息。](../../media/campaign-details-no-recipient-actions.png)

如果将鼠标悬停在图表中的水平带区上，则将看到相关邮件的数目（例如来自特定来源 IP 的邮件，使用指定发件人域名的来自来源 IP 的邮件等）。

此图表包含以下信息：

- **发件人 IP**
- **发件人域名**
- **筛选器裁定**：裁定值与可用网络钓鱼和垃圾邮件筛选裁定相关，如 [反垃圾邮件邮件头中所述](anti-spam-message-headers.md)。 下表介绍了可用值：

  |值|垃圾邮件筛选器裁定|说明|
  |---|---|---|
  |**允许**|`SFV:SKN` <p> `SFV:SKI`|在垃圾邮件筛选评估之前，邮件被标记为非垃圾邮件和/或跳过筛选。 例如，邮件流规则将邮件标记为"非垃圾邮件 (也称为传输规则) 。 <p> 邮件由于其他原因跳过了垃圾邮件筛选。 例如，发件人和收件人似乎在同一个组织中。|
  |**已阻止**|`SFV:SKS`|在垃圾邮件筛选评估之前，邮件被标记为垃圾邮件。 例如，通过邮件流规则。|
  |**已检测**|`SFV:SPM`|邮件被垃圾邮件筛选标记为垃圾邮件。|
  |**未检测到**|`SFV:NSPM`|邮件被垃圾邮件筛选标记为非垃圾邮件。|
  |**已释放**|`SFV:SKQ`|邮件由于从隔离区中释放而跳过了垃圾邮件筛选。|
  |**租户允许**<sup>\*</sup>|`SFV:SKA`|邮件由于反垃圾邮件策略中的设置而跳过了垃圾邮件筛选。 例如，发件人在允许的发件人列表或允许的域列表中。|
  |**租户阻止**<sup>\*\*</sup>|`SFV:SKA`|邮件被垃圾邮件筛选阻止，因为反垃圾邮件策略中的设置。 例如，发件人在允许的发件人列表或允许的域列表中。|
  |**用户允许**<sup>\*</sup>|`SFV:SFE`|邮件跳过了垃圾邮件筛选，因为发件人位于用户的"发件人保险箱列表中。|
  |**用户阻止**<sup>\*\*</sup>|`SFV:BLK`|邮件被垃圾邮件筛选阻止，因为发件人位于用户的"阻止的发件人"列表中。|
  |**ZAP**|不适用|[零时差自动清除 (ZAP) ](zero-hour-auto-purge.md) 已送达邮件移动到垃圾邮件文件夹或隔离邮箱。 您可以在反垃圾邮件 [策略中配置操作](configure-your-spam-filter-policies.md)。|

  <sup>\*</sup> 查看反垃圾邮件策略，因为允许的邮件可能已被服务阻止。

  <sup>\*\*</sup> 查看反垃圾邮件策略，因为这些邮件应该隔离，而不是传递。

- 邮件目标：即使用户未单击邮件中的有效负载 URL，您也可能需要调查传递到收件人 (或垃圾邮件文件夹) 的邮件。 您还可以从隔离区中删除隔离邮件。 有关详细信息，请参阅 [EOP 中的隔离电子邮件](quarantine-email-messages.md)。
  - **已删除文件夹**
  - **已丢弃**
  - **外部**：收件人位于混合环境中本地电子邮件组织中。
  - **失败**
  - **转发**
  - **收件箱**
  - **垃圾邮件文件夹**
  - **隔离**
  - **Unknown**

- **URL 单击**：下一节将介绍这些值。

> [!NOTE]
> 在所有包含 10 多个项的层中，显示前 10 项，其余项捆绑在一起。其他 **。**

#### <a name="url-clicks"></a>URL 单击次数

当网络钓鱼邮件传递到收件人的"收件箱"或"垃圾邮件"文件夹时，用户始终有可能单击有效负载 URL。 不单击 URL 只是成功指标，但您需要确定网络钓鱼邮件甚至被传递到邮箱的原因。

如果用户单击网络钓鱼邮件的有效负载 URL，操作将显示在活动详细信息视图中图表的 **URL** 单击区域中。

- **允许**
- **BlockPage**：收件人单击了有效负载 URL，但他们对恶意网站的访问被保险箱 [链接](safe-links.md)策略阻止。
- **BlockPageOverride**：收件人单击了邮件中的有效负载 URL，保险箱链接尝试将其停止，但允许它们覆盖此阻止。 检查你的[保险箱链接](set-up-safe-links-policies.md)策略，查看为什么允许用户替代"链接保险箱裁定并继续访问恶意网站。
- **PendingDetonationPage**： 保险箱 Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.
- **PendingDetonationPageOverride**：允许收件人替代有效负载触发过程并打开 URL，而无需等待结果。

### <a name="tabs"></a>选项卡

市场活动详细信息视图中的选项卡允许你进一步调查市场活动。

> [!TIP]
> 选项卡上显示的信息由时间线中的日期范围筛选器控制，如"市场活动信息" [部分中所述](#campaign-information) 。

- **URL 单击**：如果用户未单击邮件中的有效负载 URL，则此部分将为空。 如果用户能够单击 URL，将填充以下值：
  - **用户**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **单击时间**
  - **单击裁定**

- **发件人 IP**
  - **发件人 IP**<sup>\*</sup>
  - **总计数**
  - **收件箱**
  - **非收件箱**
  - **SPF 通过**：发件人策略框架 ([SPF](how-office-365-uses-spf-to-prevent-spoofing.md)) 。 未通过 SPF 验证的发件人指示未经身份验证的发件人，或者邮件正在欺骗合法发件人。

- **发件人**
  - **发件人**：这是 SMTP MAIL FROM 命令中的实际发件人地址，不一定是用户在电子邮件客户端中看到的"发件人："电子邮件地址。
  - **总计数**
  - **收件箱**
  - **非收件箱**
  - **DKIM 通过**：发件人已通过 DKIM 身份验证的域密钥 ([邮件)](support-for-validation-of-dkim-signed-messages.md)。 未通过 DKIM 验证的发件人指示未经身份验证的发件人，或者邮件正在欺骗合法发件人。
  - **通过 DMARC**：发件人已通过基于域的邮件身份验证、报告和一致性 ([DMARC)](use-dmarc-to-validate-email.md)。 未通过 DMARC 验证的发件人指示未经身份验证的发件人，或者邮件正在欺骗合法发件人。

- **附件**
  - **Filename**
  - **SHA256**
  - **恶意软件系列**
  - **总计数**

- **URL**
  - **URL**<sup>\*</sup>
  - **总计数**

<sup>\*</sup> 单击此值将打开一个新浮出控件，其中包含有关“活动详细信息”视图顶部的指定项（用户、URL 等）的详细信息。 若要返回到“活动详细信息”视图，请单击新浮出控件中的“**完成**”。

### <a name="buttons"></a>按钮

通过市场活动详细信息视图底部的按钮，你可以调查和记录有关市场活动的详细信息：

- **浏览邮件**：使用威胁资源管理器功能进一步调查活动：
  - **所有邮件**：打开一个新的威胁资源管理器搜索选项卡，将 **市场活动 ID** 值用作搜索筛选器。
  - **收件箱邮件**：打开一个新的威胁资源管理器搜索选项卡，将" **市场活动 ID** "和"传递位置 **： 收件箱** "用作搜索筛选器。
  - **内部消息**：打开一个新的威胁资源管理器搜索选项卡，将 **"市场活动 ID** 和方向 **性： 组织** 内部"用作搜索筛选器。

- **下载威胁报告**：将市场活动详细信息下载到 Word (，默认名为 CampaignReport.docx) 。 请注意，下载包含市场活动的整个生命周期的详细信息 (选择筛选日期) 。
