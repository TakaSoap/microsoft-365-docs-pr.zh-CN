---
title: Microsoft Defender for Office 365 (MDO) 电子邮件实体页面
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: How-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 E5 和 ATP P1 和 ATP P2 客户现在可以通过电子邮件实体页面获得每个电子邮件的 360 度视图。
ms.openlocfilehash: 3b9198c9d91969d3b57f379d17de33a1c00d37f6
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50143079"
---
# <a name="the-email-entity-page"></a>"电子邮件实体"页

**本文内容：**
- [访问电子邮件实体页面](#reach-the-email-entity-page)
- [读取电子邮件实体页面](#read-the-email-entity-page)
- [使用电子邮件实体页面选项卡](#use-email-entity-page-tabs)
- [电子邮件实体页面的新增内容](#new-to-the-email-entity-page)

Microsoft Defender for Office 365 (或 MDO) E5 以及 MDO P1 和 P2 的管理员使用"电子邮件"实体页面 360 度查看 **电子邮件**。 创建此转到电子邮件页面是增强威胁资源管理器"电子邮件详细信息 ["飞出上传递的信息](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views)。

## <a name="reach-the-email-entity-page"></a>访问电子邮件实体页面

现有的 Office 安全与合规中心 (protection.office.com) Microsoft 365 安全中心 (security.microsoft.com) ，你可以查看和使用电子邮件实体页面。

|居中  |URL  |导航  |
|---------|---------|---------|
|安全与合规 |protection.office.com | 威胁管理>资源管理器   |
|Microsoft 365 安全中心 |security.microsoft.com | 电子邮件&协作>资源管理器 |

在威胁资源管理器中，选择正在调查的电子邮件的主题。 该邮件的电子邮件飞出顶部将显示一个金色条。 此新页面邀请显示"尝试使用包含丰富数据的新电子邮件实体页面..."。 选择以查看新页面。

:::image type="content" source="../../media/email-entities-1-navigation-to-ee.png" alt-text="你将看到一个金色横幅，标题为&quot;*尝试使用包含丰富数据的新电子邮件实体页面*&quot;，以导航到新体验。":::

:::image type="content" source="../../media/email-entities-2-eep.png" alt-text="此电子邮件实体页面的图形重点介绍你将看到的标题。请注意，电子邮件头显示在此处。":::

> [!NOTE]
> 查看和使用此页面所需的权限与查看威胁资源管理器的权限相同。 管理员必须是全局管理员或全局读者、安全管理员或安全读者的成员。

## <a name="read-the-email-entity-page"></a>读取电子邮件实体页面

结构设计为易于阅读和浏览一目了然。 通过页面顶部的各种选项卡，你可以进行更详细的调查。 下面是布局的工作方式：

1. 最必需的字段位于飞出项的左侧。这些详细信息是"粘滞"，这意味着无论导航到的选项卡在其余飞出部分如何，它们都定位在左侧。

    :::image type="content" source="../../media/email-entities-3-left-panel.png" alt-text="突出显示左侧的电子邮件实体页面的图形。此处包含有关邮件传递的标题和事实。":::

2. 右上角是可以通过电子邮件采取的操作。 可通过资源管理器执行的任何操作也将通过电子邮件实体页面提供。

    :::image type="content" source="../../media/email-entities-5-preview.png" alt-text="此时突出显示了 *right* 侧的电子邮件实体页面的图形。此处包含&quot;电子邮件预览&quot;和&quot;转到隔离&quot;等操作。":::

3. 可以通过对页面的其余部分进行排序来进行更深入的分析。 检查电子邮件检测详细信息、电子邮件身份验证状态和标头。 应按情况查看此区域，但这些选项卡中的信息可用于任何电子邮件。

    :::image type="content" source="../../media/email-entities-4-middle-panel.png" alt-text="此页面的主面板包括电子邮件头和身份验证状态。":::

### <a name="use-email-entity-page-tabs"></a>使用电子邮件实体页面选项卡

实体页面顶部的选项卡将允许你高效地调查电子邮件。

1. **时间线**：根据威胁资源管理器时间线 (电子邮件时间线视图) 显示电子邮件上发生的传递后事件的原始传递。 对于没有传递后操作的电子邮件，视图在日程表视图中显示原始传递行。 从以下来源（如系统、管理员和用户）自动清除 (ZAP) 、修正、URL 单击、et cetera 等事件将在此处按发生顺序显示。
2. **分析**：分析显示可帮助管理员深入分析电子邮件的字段。 对于管理员需要了解有关检测、发件人/收件人和电子邮件身份验证详细信息的详细信息，他们应使用"分析"选项卡。此页上的"相关实体"下也提供了附件和 URL 的链接。 附件和标识的威胁都在此处进行编号，单击将直接进入"附件"和"URL"页面。 此选项卡还具有显示电子邮件头 *的视图标头选项*。 为清楚起见，管理员可以将电子邮件头中的详细信息与主面板上的信息并排比较。
3. **附件**：这将检查电子邮件中发现的附件以及附件上找到的其他详细信息。 目前显示的附件数限制为 10 个。 请注意，发现是恶意附件的触发详细信息也在此处显示。
4. **URL**：此选项卡列出了电子邮件中的 URL，以及有关 URL 的其他详细信息。 目前，URL 的数量限制为 10 个，但这 10 个 URL 已优先显示 *恶意 URL。* 优先顺序可节省时间和猜测工作。 发现为恶意 URL 并触发的 URL 也将在此处显示。
5. **类似电子邮件**：此选项卡列出与此电子邮件特定的网络邮件 *ID +* 收件人组合类似的所有电子邮件。 相似性仅 *基于邮件正文*。 对邮件进行分类为"类似"的决定不包括对附件 *的考虑*。

## <a name="new-to-the-email-entity-page"></a>电子邮件实体页面的新增内容

此电子邮件实体页面提供了一些新功能。 下面是列表。

### <a name="email-preview-for-cloud-mailboxes"></a>云邮箱的电子邮件预览
如果邮件仍存在于云中，管理员可以预览云邮箱中的电子邮件。 如果管理员、 (用户) 或 ZAP (进行软删除以隔离) ，则云位置中不再存在电子邮件。 在这种情况下，管理员将无法预览这些特定邮件。 已丢弃或传递失败的电子邮件实际上从未进入邮箱。 因此，管理员也将无法预览这些电子邮件。

> [!WARNING]
>预览电子邮件需要一个称为 ***Preview** _ 的特殊角色，才能分配给管理员。 可以通过访问 _ *Permissions & roles** > Email & **collaboration roles** in *security.microsoft.com，* or **Permissions** in protection.office.com 添加 *此角色*。 将 ***预览*** 角色添加到任何角色组，或允许组织中管理员在威胁资源管理器中工作的角色组副本。

### <a name="detonation-details"></a>触发详细信息

这些详细信息特定于电子邮件附件和 URL。

用户会看到其邮箱中发现的已知恶意附件或超链接的扩充的触发详细信息，包括触发链、爆炸摘要、屏幕截图和观察行为详细信息，帮助客户了解附件或 URL 为何被视为恶意并触发。
 
- *触发链*：单个文件或 URL 触发可以触发多个爆炸。 爆炸链跟踪触发路径，包括导致裁定的原始恶意文件或 URL，以及受爆炸影响的其他所有文件或 URL。 这些 URL 或附加文件可能未直接存在于电子邮件中，但包含该分析对于确定为何发现文件或 URL 是恶意文件非常重要。
- *触发摘要*：这将提供有关以下信息：
    - 触发时间范围。
    - 附加的文件或 URL 裁定。
    - 相关信息 (文件编号、URL、IP 或域) ，这些实体是触发期间检查的其他实体。
- *触发屏幕截图*：这将显示 () 过程中所拍摄照片的屏幕截图。
- *触发详细信息*：这些是触发期间发生的每个过程的确切行为详细信息。

:::image type="content" source="../../media/email-entities-6-detonation-page.png" alt-text="触发摘要的屏幕截图，显示链、摘要、爆炸详细信息以及标题 *Deep Analysis*下的屏幕截图。":::

### <a name="other-innovations"></a>其他创新

*标记*：这些是应用于用户的标记。 如果用户是收件人，管理员将 *看到收件人标记* 。 同样，如果用户是发件人，则使用 *发件人* 标记。 这将显示在电子邮件实体页面左侧， (被描述为粘滞的部分，因此定位到页面) 。 

*最新送达* 位置：最新的送达位置是电子邮件在系统操作（如 ZAP）或管理员操作（如"移动到已删除项目"）之后登录的位置。 最新送达位置不用于通知管理员 *邮件的当前位置* 。 例如，如果用户删除邮件或将其移动到存档，则传递位置将不会更新。 但是，如果已执行系统操作并更新位置 (如 ZAP 导致电子邮件移动到隔离邮箱) 这会将最新送达位置更新为"隔离"。

*电子邮件详细信息*：深入了解"分析"选项卡中提供的电子邮件 *所需的* 详细信息。

- *Exchange 传输规则 (ETR* 或邮件流规则) ：这些规则适用于传输层的邮件，优先于网络钓鱼和垃圾邮件裁定。 只能在 Exchange 管理中心创建和修改这些名称，但如果任何 ETR 适用于邮件，ETR 名称和 GUID 将在此处显示。 用于跟踪的有用信息。
    
- 系统 *覆盖：这是* 一种根据威胁和检测技术要求覆盖系统 (给定的传递位置，从而对邮件的传递位置进行例外) 。
    
- *垃圾邮件规则*："垃圾邮件"是隐藏的收件箱规则，默认在邮箱中启用。
    - 在邮箱上启用垃圾邮件规则后，Exchange Online Protection (EOP) 可根据某些条件将邮件移动到垃圾邮件。 移动可以基于垃圾邮件筛选裁定操作将邮件移动到 *"垃圾邮件*"文件夹，或基于邮箱上的"阻止的发件人"列表。 禁用垃圾邮件规则可阻止根据邮箱上的"安全发件人"列表将邮件发送到"垃圾邮件"文件夹。
    - 在邮箱上禁用垃圾邮件规则后，EOP 无法根据垃圾邮件筛选裁定操作将邮件移动到"垃圾邮件"文件夹或邮箱的安全列表集合，将邮件移动到"垃圾邮件"文件夹。
    
- *批量合规级别 (BCL) ：* 邮件的批量投诉 (BCL) 级别。 BCL 越高，表明如果邮件可能是垃圾邮件，则 (产生投诉的可能性更大。) 。
    
- *SCL (可信度) ：* 邮件的垃圾邮件可信度 (SCL) 。 值越高，邮件是垃圾邮件的可能性就越大。

- *域名：* 是发件人域名。
    
- *域所有者*：指定发送域的所有者。
    
- *域* 位置：指定发送域的位置。
    
- *域创建日期*：指定发送域的创建日期。 如果其他信号指示某些可疑行为，则新创建的域是一个你可以谨慎处理的问题。

*电子邮件身份验证*：Microsoft 365 使用的电子邮件身份验证方法包括 SPF、DKIM 和 DMARC。

- 发件人策略 (**SPF**) ：描述邮件的 SPF 检查结果。 可能的值可以是：
    - 传递 (IP 地址) ：通过邮件的 SPF 检查并包括发件人的 IP 地址。 已授权客户端代表发件人的域发送或中继电子邮件。
    - 无法 (IP 地址) ：邮件的 SPF 检查失败，包括发件人的 IP 地址。 有时也称其为硬失败。
    - Softfail (原因) ：SPF 记录将主机指定为不允许发送但正在转换。
    - 中性：SPF 记录明确声明它不断言 IP 地址是否有权发送。
    - 无：域没有 SPF 记录，或者 SPF 记录未计算结果。
    - 恢复器：已发生临时错误。 例如，DNS 错误。 相同的检查稍后可能会成功。
    - Permerror：发生永久性错误。 例如，域的 SPF 记录格式不正确。

- 域密钥标识的邮件 (**DKIM**) ：
    - Pass： Indicates the DKIM check for the message passed.
    - 失败 (原因) ：指示邮件的 DKIM 检查失败以及原因。 例如，如果邮件未签名或签名未经验证。
    - 无：指示邮件未签名。 这可能表示或不表示域存在 DKIM 记录或 DKIM 记录未生成结果，仅表示该邮件未签名。

- 基于域的邮件身份验证、报告和一致性 (**DMARC**) ：
    - Pass： Indicates the DMARC check for the message passed.
    - 失败：指示邮件的 DMARC 检查失败。
    - Bestguesspass：指示不存在域的 DMARC TXT 记录，但如果已存在，则邮件的 DMARC 检查已经通过。
    - 无：指示 DNS 中不存在发送域的 DMARC TXT 记录。

*复合身份验证*：这是 Microsoft 365 用于合并电子邮件身份验证（如 SPF、DKIM 和 DMARC）的值，以确定邮件是否可信。 它使用 *邮件的 From：* 域作为评估的基础。
