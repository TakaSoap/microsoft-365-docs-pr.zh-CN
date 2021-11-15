---
title: Microsoft Defender for Office 365电子邮件实体页面
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: mdo
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: admindeeplinkDEFENDER
description: Microsoft Defender for Office 365 E5 P1 和 P2 客户现在可以通过电子邮件实体页面获得每个电子邮件的 360 度视图。
ms.openlocfilehash: 6a742653f5c249da356b9295572085733ecec5bf
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60960642"
---
# <a name="the-email-entity-page"></a>"电子邮件实体"页面

**本文内容：**
- [访问电子邮件实体页面](#reach-the-email-entity-page)
- [读取电子邮件实体页面](#read-the-email-entity-page)
- [使用电子邮件实体页面选项卡](#use-email-entity-page-tabs)
- [电子邮件实体页面的新增内容](#new-to-the-email-entity-page)

Microsoft Defender for Office 365 E5 管理员和适用于 Office P1 和 P2 的 Defender 管理员使用"电子邮件"实体页面 360 度 **查看电子邮件**。 创建此转到电子邮件页面是增强威胁资源管理器"电子邮件详细信息"飞[出上的信息。](threat-explorer-views.md)

## <a name="reach-the-email-entity-page"></a>访问电子邮件实体页面

电子邮件实体页面位于电子邮件Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">协作</a>资源管理器&**门户** \> **中**。 或者，若要直接转到资源管理器 **页面** ，请使用 <https://security.microsoft.com/threatexplorer> 。

在 **资源管理器** 中，选择要调查的电子邮件的主题。 该邮件的电子邮件飞出顶部将显示一个金色条。 此新页面邀请显示"尝试使用包含丰富数据的新电子邮件实体页面..."。 选择以查看新页面。

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="你将看到一个金色横幅，标题为&quot;*尝试使用包含丰富数据的新电子邮件实体页面*&quot;，以导航到新体验。":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="此电子邮件实体页面的图形重点介绍您将看到的标题。请注意，电子邮件头显示在此处。":::

> [!NOTE]
> 查看和使用此页面所需的权限与查看资源管理器 **的权限相同**。 管理员必须是全局管理员或全局读者、安全管理员或安全读者的成员。 有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

## <a name="read-the-email-entity-page"></a>读取电子邮件实体页面

结构设计为易于阅读和浏览，一目了然。 页面顶部的各种选项卡允许你进行更详细的调查。 下面是布局的工作原理：

1. The most required fields are on the left side of the fly-out.这些详细信息是"粘滞"，这意味着无论你在飞出的其他部分导航到的选项卡如何，它们都定位到左侧。

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="突出显示左侧的电子邮件实体页面的图形。此处包含有关邮件传递的标题和事实。":::

2. 右上角是可通过电子邮件采取的操作。 通过资源管理器可执行 **的任何操作** 也将通过电子邮件实体页面提供。

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="此时突出显示 *right* 侧的电子邮件实体页面的图形。此处包含&quot;电子邮件预览&quot;和&quot;转到隔离&quot;等操作。":::

3. 可以通过对页面的其余部分进行排序进行更深入的分析。 检查电子邮件检测详细信息、电子邮件身份验证状态和标头。 应按情况查看此区域，但这些选项卡中的信息可用于任何电子邮件。

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="此页面的主面板包括电子邮件头和身份验证状态。":::

### <a name="use-email-entity-page-tabs"></a>使用电子邮件实体页面选项卡

实体页面顶部的选项卡将允许您高效地调查电子邮件。

1. **时间线**：电子邮件时间线视图 (**资源管理器** 时间线) 显示电子邮件上发生的传递后事件的原始传递。 对于没有传递后操作的电子邮件，视图在日程表视图中显示原始传递行。 来自系统、管理员和用户等来源的零时差自动清除 (ZAP) 、修正、URL 单击次数等事件按发生顺序显示在此处。
2. **分析**：分析显示可帮助管理员深入分析电子邮件的字段。 对于管理员需要了解有关检测、发件人/收件人和电子邮件身份验证详细信息的详细信息的情况，他们应当使用"分析"选项卡。此页上的"相关实体"下也提供了附件和 URL 的链接。 此处对附件和已识别的威胁进行编号，单击将直接进入"附件"和"URL"页面。 此选项卡还具有"查看邮件头"选项 *，用于显示电子邮件头*。 为清楚起见，管理员可以将电子邮件头中的详细信息与主面板上的信息并排比较。
3. **附件**：这将检查电子邮件中的附件，以及附件上找到的其他详细信息。 目前显示的附件数限制为 10 个。 请注意，发现恶意附件的触发详细信息也在此处显示。
4. **URL**：此选项卡列出了电子邮件中的 URL，并包含有关 URL 的其他详细信息。 目前，URL 的数量限制为 10 个，但这 10 个已优先显示 *恶意 URL。* 优先顺序可节省时间和猜测工作。 此处还将显示被发现为恶意并触发的 URL。
5. **类似电子邮件**：此选项卡列出与此电子邮件特定的网络邮件 *ID +* 收件人组合类似的所有电子邮件。 相似性仅 *基于邮件正文*。 对邮件进行分类为"类似"的决定不包括附件 *的注意事项*。

## <a name="new-to-the-email-entity-page"></a>电子邮件实体页面的新增内容

此电子邮件实体页面提供了一些新功能。 以下是列表。

### <a name="email-preview-for-cloud-mailboxes"></a>云邮箱的电子邮件预览

如果邮件仍存在于云中，管理员可以预览云邮箱中的电子邮件。 如果管理员、 (或用户) 或 ZAP (执行软删除操作以隔离) ，电子邮件将不再存在于云位置。 在这种情况下，管理员将无法预览这些特定邮件。 已丢弃或传递失败的电子邮件永远不会进入邮箱。 因此，管理员也将无法预览这些电子邮件。

> [!WARNING]
> 预览电子邮件需要一个称为预览的特殊 **角色**。 可以将此角色添加到 Microsoft 365 Defender 门户中，如 & 门户中的电子邮件Microsoft 365 Defender[协作角色中所述](permissions-microsoft-365-security-center.md#email--collaboration-roles-in-the-microsoft-365-defender-portal)。 你可能需要在那里创建一个新的"电子邮件"&协作角色组，将 **"** 预览"角色添加到该新角色组，或将 **"** 预览"角色添加到角色组，该角色组允许贵组织的管理员在资源管理器中 **工作**。

### <a name="detonation-details"></a>触发详细信息

这些详细信息特定于电子邮件附件和 URL。 用户可以通过进入资源管理器，将检测技术筛选器集应用于文件触发或 URL 触发来查看这些详细信息。 针对文件触发筛选的电子邮件将包含具有触发详细信息的恶意文件，并且筛选出 URL 的电子邮件包含恶意 URL 及其触发详细信息。

用户会看到其电子邮件中发现的已知恶意附件或 URL 的丰富触发详细信息，这些附件或 URL 已针对其特定租户触发。 它将包含触发链、触发摘要、屏幕截图和观察行为详细信息，帮助客户了解附件或 URL 被视为恶意并触发的原因。

1. *触发链*。 单个文件或 URL 触发可以触发多个爆炸。 爆炸链跟踪触发路径，包括导致裁定的原始恶意文件或 URL，以及受爆炸影响的其他所有文件或 URL。 这些 URL 或附加的文件可能不会直接存在于电子邮件中，但包含该分析对于确定发现文件或 URL 是恶意文件的原因非常重要。  

    > [!NOTE]
    > 如果发现链接到顶级项目的任何实体都未发现问题或触发，这可能只显示顶级项目。

1. 触发摘要提供触发的基本摘要，如分析时间、发生爆炸的时间、操作系统和应用程序、发生爆炸的操作系统和应用程序、文件大小和裁定原因。
1. *屏幕截图* 显示触发期间捕获的屏幕截图。 触发期间可以有多个屏幕截图。 不会捕获任何屏幕截图
    - 容器类型文件，.zip或.rar。
    - 如果 URL 打开为直接下载文件的链接。 但是，你将在触发链中看到下载的文件。
1. 行为详细信息是一个导出，用于显示行为详细信息，如触发期间发生的确切事件，以及包含在触发期间发现的 URL、IP、域和文件的可观测项 (它们可能是有问题的或不良的) 。 请注意，可能没有以下行为详细信息：
    - 容器文件.zip或.rar保存其他文件的容器文件。

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="触发摘要的屏幕截图，显示在标题 *Deep Analysis*下显示链、摘要、爆炸详细信息和屏幕截图。":::

### <a name="other-innovations"></a>其他创新

*标记*：这些是应用于用户的标记。 如果用户是收件人，管理员将 *看到收件人标记* 。 同样，如果用户是发件人，则使用 *发件人* 标记。 这将显示在电子邮件实体页面左侧 (被描述为粘滞的部分，因此定位到页面) 。 

*最新送达位置*：最新的送达位置是电子邮件在系统操作（如 ZAP）或管理员操作（如"移动到已删除项目"）之后登录的位置。 最新送达位置并不用于通知管理员邮件 *的当前位置。* 例如，如果用户删除邮件或将其移动到存档，则传递位置将不会更新。 但是，如果已执行系统操作并更新位置 (如 ZAP 导致电子邮件移动到隔离邮箱) 这会将"最新送达位置"更新为隔离。

*电子邮件详细信息*：深入了解"分析"选项卡中提供的电子邮件 *所需的* 详细信息。

- Exchange传输规则 (也称为邮件流规则或 *ETR) ：* 这些规则适用于传输层的邮件，优先于网络钓鱼和垃圾邮件裁定。 只能在管理中心内创建和Exchange，但如果任何 ETR 适用于邮件，则此处将显示 ETR 名称和 GUID。 用于跟踪的有用信息。

- 系统 *覆盖：这是* 根据威胁和检测技术要求覆盖系统 (给定的传递位置来对邮件的传递位置进行) 。

- *批量投诉级别 (BCL) ：* 邮件的批量 () BCL 级别。 BCL 越高，表明如果电子邮件可能是垃圾邮件，则 (产生投诉的可能性更大，这是) 。

- *垃圾邮件可信度 (SCL) ：* 邮件 (SCL) 的垃圾邮件可信度。 值越高，邮件是垃圾邮件的可能性就越大。

- *域名*：是发件人域名。

- *域所有者*：指定发送域的所有者。

- *域* 位置：指定发送域的位置。

- *域创建日期*：指定发送域的创建日期。 如果其他信号指示某些可疑行为，则新创建的域是你可以小心的。

*电子邮件身份验证*：电子邮件身份验证方法Microsoft 365 SPF、DKIM 和 DMARC。

- 发件人策略框架 (**SPF**) ：描述邮件的 SPF 检查结果。 可能的值可以是：
  - Pass (IP address) ： The SPF check for the message passed and includes the sender's IP address. 已授权客户端代表发件人的域发送或中继电子邮件。
  - IP (地址) ：邮件的 SPF 检查失败，包括发件人的 IP 地址。 有时也称其为硬失败。
  - 软 (原因) ：SPF 记录将主机指定为不允许发送但正在转换。
  - 中性：SPF 记录明确声明它不会断言 IP 地址是否有权发送。
  - 无：域没有 SPF 记录，或者 SPF 记录未计算结果。
  - 恢复器：已发生临时错误。 例如，DNS 错误。 相同的检查稍后可能会成功。
  - Permerror：发生了永久性错误。 例如，域的 SPF 记录格式不正确。

- 域密钥识别邮件 (**DKIM**) ：
  - Pass：指示通过邮件的 DKIM 检查。
  - 失败 (原因) ：指示邮件的 DKIM 检查失败以及原因。 例如，如果邮件未签名或签名未经验证。
  - 无：指示邮件未签名。 这可能表示或不表示域存在 DKIM 记录或 DKIM 记录未生成结果，仅表示该邮件未签名。

- 基于域的邮件身份验证、报告和一致性 (**DMARC**) ：
  - Pass：指示通过邮件的 DMARC 检查。
  - 失败：指示邮件的 DMARC 检查失败。
  - Bestguesspass：指示域不存在 DMARC TXT 记录，但如果已存在，则邮件的 DMARC 检查已经通过。
  - 无：指示 DNS 中不存在发送域的 DMARC TXT 记录。

*复合身份验证*：这是一个值，Microsoft 365 SPF、DKIM 和 DMARC 等电子邮件身份验证，以确定邮件是否可信。 它使用 *邮件的 From：* 域作为评估的基础。
