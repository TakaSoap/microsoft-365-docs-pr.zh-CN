---
title: Microsoft Defender for Office 365 中的分步威胁防护堆栈
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
description: 通过 Microsoft Defender 中的威胁筛选堆栈跟踪传入邮件的路径，Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e883d4d6aea6af739a8156027ffa6968638ef4d
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962599"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的威胁防护步骤

Microsoft Defender Office 365保护或筛选堆栈可以分为 4 个阶段，如本文所介绍。 一般来说，传入邮件在传递之前会通过所有这些阶段，但实际路径电子邮件采用受组织的 Defender Office 365配置。

> [!TIP]
> 请继续关注到本文末尾，了解 Defender的所有 4 个阶段的统一图形，Office 365保护！

## <a name="phase-1---edge-protection"></a>第 1 阶段 - 边缘保护

遗憾的是，曾经至关重要 *的边缘块现在* 相对简单，让坏角色能够克服这些障碍。 随着时间的推移，此处阻止的流量较少，但它仍是堆栈的重要部分。  

边缘块设计为自动。 如果误报，将通知发件人并告知发件人如何处理其问题。 来自信誉有限的受信任合作伙伴的连接器可以确保可交付性，或在载入新终结点时可以设置临时替代。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="Defender for Office 365筛选的第 1 阶段是边缘保护。":::

1. 网络限制通过Office 365一组特定基础结构可以提交的消息数，保护基础结构和客户免受拒绝服务 (DOS) 攻击。

2. **IP 信誉和限制将** 阻止从已知的连接 IP 地址错误发送的邮件。 如果特定 IP 在短时间内发送许多邮件，则这些邮件将被限制。

3. **域信誉** 将阻止从已知错误域发送的任何邮件。

4. **基于目录的边缘筛选** 阻止尝试通过 SMTP 获取组织的目录信息。

5. **反散点检测** 可以防止组织受到无效的未送达报告 (NDR) 的攻击。

6. **连接器的增强** 筛选功能可保留身份验证信息，即使通信在到达其他设备之前通过Office 365。 这提高了筛选堆栈的准确性，包括启发式群集、反欺骗和防钓鱼机器学习模型，即使在复杂或混合路由方案中也可以。

## <a name="phase-2---sender-intelligence"></a>阶段 2 - 发件人智能

发件人智能中的功能对于捕获垃圾邮件、批量、模拟和未经授权的欺骗邮件至关重要，还会成为网络钓鱼检测的因素。 这些功能中的大多数是可单独配置的。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="Defender for Office 365筛选的第 2 阶段是发件人智能。":::

1. **帐户具有** 异常行为且与泄露一致时，会引发帐户泄露检测触发器和警报。 在某些情况下，用户帐户将被阻止并阻止发送任何进一步的电子邮件，直到组织的安全运营团队解决该问题为止。

2. **电子邮件** 身份验证涉及客户配置的方法和在云中设置的方法，旨在确保发件人得到授权，是可信的邮件发送者。 这些方法可抵御欺骗。
    - **SPF** 可以拒绝基于 DNS TXT 记录的邮件，这些记录列出允许代表组织发送邮件的 IP 地址和服务器。
    - **DKIM** 提供对发件人进行身份验证的加密签名。
    - **DMARC** 允许管理员按其域中的要求标记 SPF 和 DKIM，并强制在这两种技术的结果之间保持一致。
    - **ARC** 未进行客户配置，但基于 DMARC 构建，以用于邮件列表中的转发，同时记录身份验证链。

3. 欺骗智能能够筛选允许"欺骗" (即代表其他帐户发送邮件或从模仿组织或已知外部域的恶意发件人转发邮件列表) 的用户。 它将合法"代表"邮件与欺骗邮件传递垃圾邮件和网络钓鱼邮件的发件人分开。

    **组织内部欺骗智能** 检测和阻止来自组织内域的欺骗尝试。

4. **跨域欺骗智能** 检测和阻止来自组织外部域的欺骗尝试。

5. **批量筛选** 允许管理员配置批量可信度 (BCL) 指示邮件是否从批量发件人发送。 管理员可以使用反垃圾邮件策略中的批量滑块决定要视为垃圾邮件的批量邮件的级别。

6. **邮箱智能** 从标准用户电子邮件行为中学习。 它利用用户的通信图来检测发件人何时看起来只是用户通常通信但实际上是恶意的人。 此方法检测模拟。

7. **邮箱智能模拟** 基于每个用户的单个发件人映射启用或禁用增强的模拟结果。 启用后，此功能有助于识别模拟。

8. **用户模拟** 允许管理员创建可能模拟的高值目标列表。 如果邮件到达发件人看起来与受保护的高值帐户相同的名称和地址，则标记该邮件。  (例如 *，tr cye@contoso.com* for *tracye@contoso.com) 。*

9. **域模拟** 可检测类似于收件人域且尝试看起来像内部域的域。 例如，此模拟tracye@liw re.com tracye@litware.com。 

## <a name="phase-3---content-filtering"></a>阶段 3 - 内容筛选

在此阶段，筛选堆栈开始处理邮件的特定内容，包括其超链接和附件。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="MDO 中的筛选阶段 3 是内容筛选。":::

1. 传输 **(规则** 也称为邮件流规则或 Exchange 传输规则) 当邮件满足同样广泛的条件时，管理员可采取各种操作。 根据已启用的邮件流规则/传输规则评估通过组织传递的所有邮件。

2. **Microsoft Defender 防病毒** 和两个 *第三方防病毒引擎* 用于检测附件中的所有已知的恶意软件。

3. 防病毒 (AV) 引擎还用于真正键入所有附件，以便类型阻止可以阻止管理员指定类型的所有附件。 

4. 每当 Microsoft Defender for Office 365检测到恶意附件时，文件的哈希及其活动内容的哈希都会添加到 EOP Exchange Online Protection (信誉) 中。 **附件信誉阻止** 会通过 MSAV 云Office 365在终结点上阻止该文件。

5. **启发式聚类分析** 可以根据传递启发确定文件可疑。 当发现可疑附件时，整个市场活动将暂停，文件将沙盒。 如果发现该文件是恶意的，将阻止整个市场活动。

6. **机器学习模型** 作用于邮件的标头、正文内容和 URL，以检测网络钓鱼尝试。

7. Microsoft 使用来自 URL 沙盒的信誉以及 URL 信誉阻止中第三方源的 **URL** 信誉来阻止任何包含已知恶意 URL 的邮件。

8. **内容启发** 可以使用机器学习模型根据消息正文中的结构和单词频率检测出可疑消息。

9. **保险箱附件** 沙盒中为 Office 365 客户的 Defender 添加每个附件，使用动态分析检测之前未发现的威胁。

10. **链接内容爆炸** 将电子邮件中链接到文件的每个 URL 作为附件处理，在发送时对文件进行异步沙盒处理。

11. **当上游防钓鱼技术发现消息或 URL 可疑时，会发生 URL 爆炸**。 URL 触发在传递时对邮件中的 URL 进行沙盒化。

## <a name="phase-4---post-delivery-protection"></a>第 4 阶段 - 传递后保护

最后一个阶段发生在邮件或文件传递之后，对各种邮箱中的邮件以及显示在客户端（如 Microsoft Teams）中的文件和链接Microsoft Teams。

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="Defender for Office 365筛选的第 4 阶段是传递后保护。":::

1. **安全链接** 是 Defender for Office 365 的点击时间保护。 每封邮件中的每个 URL 都打包为指向 Microsoft 保险箱链接服务器。 单击 URL 时，将针对最新信誉检查 URL，然后用户重定向到目标网站。 URL 是异步沙盒，用于更新其信誉。

2. **针对网络钓鱼的零时** 差自动清除 (ZAP) 可主动检测并中性化已传递到 Exchange Online 邮箱的恶意网络钓鱼邮件。

3. **针对恶意软件的 ZAP** 可以追溯性地检测和消除已经传递到 Exchange Online 邮箱的 恶意软件 邮件。

4. **针对垃圾邮件的 ZAP** 可以追溯检测和中和已传递到 Exchange Online 邮箱的恶意 垃圾 邮件。

5. **与没有** 自动化的任何团队一样，市场活动视图使管理员能够更快、更完整地查看攻击的全局信息。 Microsoft 利用整个服务中的大量反网络钓鱼、反垃圾邮件和反恶意软件数据来帮助识别活动，然后允许管理员从头到尾调查它们，包括目标、影响和流，这些对象、影响和流也可在可下载的活动写入中提供。

6. 通过报告邮件外接程序，用户可以轻松地向 Microsoft 报告误报 (错误标记为错误 *)* 或误报 (错误电子邮件标记为) 错误电子邮件，以便进一步分析。 

7. **保险箱** Office 客户端的链接在 Office 客户端（如 Word、PowerPoint 和 Excel）内部提供相同的 保险箱 链接单击时间保护。

8. **对 OneDrive、SharePoint** 和 Teams 的保护提供了相同的 保险箱 附件保护，以抵御本地 OneDrive、SharePoint 和 Microsoft Teams 内的恶意文件。

9. 当选择指向文件的 URL 后，链接内容触发将显示一个警告页面，直到文件的沙盒完成，并且发现该 URL 是安全的。

## <a name="the-filtering-stack-diagram"></a>筛选堆栈图

最后一 (图表的所有部分一样，) 随着产品的增长和开发而 *更改*。 如果更新后需要 **询问** ，请为此页面添加书签，并使用底部的反馈选项。 对于记录，这是按顺序排列的所有阶段的堆栈：

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Defender 中筛选的所有阶段Office 365顺序为 1 到 4。":::

## <a name="more-information"></a>更多信息

是否需要为 Microsoft Defender 设置 Office 365 ***现在** _？ 使用此堆栈_now*，通过此分步操作开始[](protect-against-threats.md)保护你的组织。

*特别感谢 MSFTTracyP 和编写团队的文档向 Giulian Garruba 提供此内容*。
