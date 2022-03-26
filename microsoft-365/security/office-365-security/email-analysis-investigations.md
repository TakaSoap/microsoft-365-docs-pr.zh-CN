---
title: Microsoft Defender for Office 365 调查的电子邮件分析
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: 自动事件响应， 调查， 修正， 威胁防护
description: 了解调查电子邮件分析在 Microsoft Defender for Office 365 中Office 365。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5c4d1be31742d21f6e7919a8db4a3d2aff75f66e
ms.sourcegitcommit: 9c8eca862a2f0fdca7a66c641e382e37fcaefa10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2022
ms.locfileid: "63775381"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 调查的电子邮件分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在警报自动调查期间，Microsoft Defender for Office 365分析原始电子邮件中的威胁，并确定与原始电子邮件相关的其他电子邮件以及可能属于攻击的一部分。 此分析非常重要，因为电子邮件攻击很少包含一封电子邮件。

自动调查的电子邮件分析使用原始电子邮件中的属性识别电子邮件群集，以查询您的组织发送和接收的电子邮件。 这类似于安全操作分析师在资源管理器或高级搜寻中搜寻相关电子邮件。 多个查询用于标识匹配的电子邮件，因为攻击者通常会更改电子邮件参数以避免安全检测。 群集分析执行以下检查以确定如何处理调查所涉及的电子邮件：

- 电子邮件分析使用原始电子邮件中的属性创建 (群集) 电子邮件的查询 - 发件人值 (IP 地址、发送域) 和内容 (主题、群集 ID) ，以便查找相关的电子邮件。
- 如果对原始电子邮件的 URL 和文件的分析发现某些是恶意 (，即恶意软件或网络钓鱼) ，则它还将创建包含恶意 URL 或文件的查询或电子邮件群集。
- 电子邮件群集分析对与群集中的匹配电子邮件关联的威胁进行计数，以确定电子邮件是恶意的、可疑的还是没有明确的威胁。 如果匹配查询的电子邮件群集具有足够的垃圾邮件、普通网络钓鱼、高可信度网络钓鱼或恶意软件威胁，则电子邮件群集将应用该威胁类型。
- 电子邮件群集分析还会检查原始电子邮件和电子邮件在电子邮件群集中的最新传递位置，以帮助确定电子邮件是否仍可能需要删除或已修正或阻止。 此分析非常重要，因为攻击者会更改恶意内容以及安全策略和保护，这两个邮箱可能会有所不同。 此功能会导致恶意内容仍位于邮箱中的情况，即使使用 ZAP 策略的零时差自动清除功能检测到并删除了一 (恶意) 。
- 如果由于恶意软件、高可信度钓鱼邮件、恶意文件或恶意 URL 威胁而被视为恶意的电子邮件群集，当云邮箱 (收件箱或垃圾邮件文件夹) 时，将获取软删除电子邮件的挂起操作。 如果恶意电子邮件或电子邮件群集仅"不在邮箱中" (阻止、隔离、失败、软删除等 ) 或"本地/外部"，在云邮箱中无，则将不会设置任何待处理操作来删除它们。
- 如果任何电子邮件群集被确定为恶意群集，则群集标识的威胁将应用到调查所涉及的原始电子邮件。 此行为类似于安全操作分析师使用电子邮件搜寻结果根据匹配电子邮件确定原始电子邮件裁定。 此结果可确保无论是否检测到原始电子邮件的 URL、文件或源电子邮件指示器，系统都可以识别通过个性化、变形、黑客或其他攻击者技术可能规避检测的恶意电子邮件。
- 在用户泄露调查中，会创建其他电子邮件群集，以确定邮箱创建的潜在电子邮件问题。 此过程包括干净电子邮件群集 (来自用户的良好电子邮件、潜在的数据窃取和潜在的命令/控制电子邮件) 、可疑电子邮件群集 (包含垃圾邮件或普通网络钓鱼) 的电子邮件以及包含恶意软件或高可信度网络钓鱼) 的恶意电子邮件群集 (电子邮件。 这些电子邮件群集提供安全操作分析师数据，以确定可能需要通过泄露解决哪些其他问题，以及哪些电子邮件已触发原始警报（例如 (触发用户发送限制的网络钓鱼/垃圾邮件）的可见性) 

通过相似性和恶意实体查询的电子邮件群集分析可确保完全识别并清理电子邮件问题，即使只识别出来自攻击的一封电子邮件。 可以使用电子邮件群集详细信息侧面板视图中的链接在资源管理器或高级搜寻中打开查询，以执行更深入的分析并根据需要更改查询。 如果你发现电子邮件群集的查询过窄或过宽，包括无关的电子邮件或电子邮件，此功能 (手动精简和) 。

下面是调查电子邮件分析的其他增强功能。

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>AIR 调查将忽略 SecOps (和 PhishEDU 邮件中的高级) 

在电子邮件群集分析过程中，所有群集查询将忽略在高级传递策略中设置为安全操作邮箱的安全邮箱。 同样，电子邮件群集查询将忽略高级 (策略) 邮件的网络钓鱼模拟电子邮件。 查询中既不显示 SecOps 值也不显示 PhishEdu 排除值，使群集属性更易于阅读。 此排除可确保威胁分析期间将忽略威胁智能 (SecOps 邮箱) 和网络钓鱼模拟 (PhishEdu) ，并且不会在任何修正过程中删除它们。

>[!Note]
>从电子邮件群集详细信息打开电子邮件群集以在资源管理器中查看它时，PhishEdu 和 SecOps 邮箱筛选器将在资源管理器中应用，但将不会显示。 如果更改"资源管理器"筛选器、日期或刷新页面中的查询，则 PhishEdu/SecOps 筛选器排除项将被删除，匹配这些筛选器的电子邮件将再次显示。 如果使用浏览器刷新函数刷新"资源管理器"页，将重新加载原始查询筛选器，包括 PhishEdu/SecOps 筛选器，但会删除您进行的任何后续更改。
>

## <a name="air-updates-pending-email-action-status"></a>AIR 更新挂起的电子邮件操作状态

调查电子邮件分析在调查时计算电子邮件威胁和位置，以创建调查证据和操作。 当调查之外的操作影响调查所涉及的电子邮件时，此数据可能会过期。 例如，安全操作手动搜寻和修正可能会清理调查中包含的电子邮件。 同样，在并行调查或零时差自动清除中批准的删除操作 (ZAP) 自动隔离操作可能已删除电子邮件。 此外，电子邮件传递后对威胁的延迟检测可能会更改调查的电子邮件查询/群集中包含的威胁数量。

为了确保调查操作是最新的，任何具有挂起操作的调查将定期重新运行电子邮件分析查询，以更新电子邮件位置和威胁。

- 当电子邮件群集数据发生更改时，它将更新威胁和最新的传递位置计数。
- 如果邮箱中不再包含挂起操作的电子邮件或电子邮件群集，则挂起的操作将被取消，恶意电子邮件/群集视为已修复。
- 如上所述，修正或取消所有调查的威胁后，调查将转换为修正状态，并解决原始警报。

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>显示电子邮件和电子邮件群集的事件证据

现在，在事件的"证据 **和** 响应"选项卡中，基于电子邮件的证据将显示以下信息。

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="证据和响应中的电子邮件分析信息示例。" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

从图中的编号标注：

1. 除了操作中心外，还可以执行 **修正操作**。
2. 你可以对具有恶意裁定的电子邮件群集采取修正 **(，但不能** 对可疑) 。
3. 对于垃圾邮件裁定，网络钓鱼被拆分为高可信度和普通网络钓鱼。

   对于恶意裁定，威胁类别为恶意软件、高可信度钓鱼邮件、恶意 URL 和恶意文件。

   对于"可疑"裁定，威胁类别为垃圾邮件和普通钓鱼邮件。

4. 电子邮件计数依据基于最新的传递位置，包括邮箱（而不是邮箱和本地）中的电子邮件计数器。
5. 包括查询的日期和时间，查询可能会针对最新数据进行更新。

对于事件"实体"选项卡中的电子邮件或电子邮件群集，"已阻止"表示邮箱中没有针对此项目的恶意电子邮件 (邮件或群集) 。 以下是示例。

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="阻止的电子邮件示例。" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

本示例中，电子邮件是恶意电子邮件，但不在邮箱中。

## <a name="next-steps"></a>后续步骤

- [查看挂起或已完成的修正操作](air-review-approve-pending-completed-actions.md)
