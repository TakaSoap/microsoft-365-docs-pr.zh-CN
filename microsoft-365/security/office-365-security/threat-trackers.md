---
title: 威胁跟踪器 - 新增的和值得注意的威胁
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: a097f5ca-eac0-44a4-bbce-365f35b79ed1
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 了解威胁跟踪器（包括新的值得注意的跟踪器）以帮助组织解决安全问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a734085e9bc341424ee40757a21b855442605bcd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287385"
---
# <a name="threat-trackers---new-and-noteworthy"></a>威胁跟踪器 - 新增的和值得注意的威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[Office 365 威胁](office-365-ti.md) 调查和响应功能使组织的安全团队能够发现网络安全威胁并采取行动。 Office 365 威胁调查和响应功能包括威胁跟踪程序功能，包括值得注意的跟踪器。 阅读本文，大致了解这些新功能和下一步。

> [!IMPORTANT]
> Office 365 威胁智能现在是 Microsoft Defender for Office 365 计划 2，以及其他威胁防护功能。 若要了解的详细信息，请参阅 [Microsoft Defender for Office 365 计划和定价](https://products.office.com/exchange/advance-threat-protection) 以及 Microsoft Defender for Office [365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="what-are-threat-trackers"></a>什么是威胁跟踪器？

威胁跟踪器是信息小组件和视图，可针对可能会影响公司的不同网络安全问题提供情报。 例如，可以使用威胁跟踪器查看有关恶意软件活动趋势的信息。

![显示恶意软件活动的威胁跟踪程序示例](../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png)

大多数跟踪器页面包括定期更新的趋势数字、帮助您了解问题最大或增长最多的小组件，以及"操作"列中的"操作"列中的一个快速链接（可在其中查看更多详细信息）。

![资源管理器中的市场活动信息示例](../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png)

跟踪器只是使用 [Microsoft Defender for Office 365](office-365-ti.md)计划 2 获得的许多功能中的一些。 威胁跟踪器包括 [笔记跟踪器](#noteworthy-trackers)、 [趋势跟踪](#trending-trackers)器、跟踪的 [查询](#tracked-queries)和 [保存的查询](#saved-queries)。

若要查看和使用组织的威胁跟踪器，请转到安全与合规&中心 () 威胁 <https://protection.office.com>  \> **跟踪程序**。

> [!NOTE]
> 若要使用威胁跟踪器，您必须是全局管理员、安全管理员或安全读者。 请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="noteworthy-trackers"></a>值得注意的跟踪器

值得一提的跟踪器是一个值得关注的地方，你可以发现我们认为你应了解的较大和较小的威胁和风险。 值得注意的跟踪器可帮助你查找 Microsoft 365 环境中是否存在这些问题，以及指向文章 (（如本文章) ）的链接，这些链接提供有关发生的情况以及这些问题如何影响组织使用 Office 365 的更多详细信息。 无论是新的重大威胁 (如 Wannacry、Petya) ，还是可能会带来一些新难题的现有威胁 (如我们的另一个新增项目 -Nemucod) ，你将在这里找到你和安全团队应定期查看和检查的重要新项。

通常，当我们发现新威胁并认为你可能需要此功能提供的额外可见性时，值得注意的跟踪器将发布几周。 威胁的最大风险一旦过去，我们将删除该值得注意的项目。 这样，我们可以使用其他相关新项使列表保持最新。

### <a name="trending-trackers"></a>趋势跟踪器

趋势跟踪 (以前称为) 活动，它突出显示了过去一周组织电子邮件中收到的新威胁。

![趋势恶意软件市场活动小组件示例](../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png)

趋势跟踪器可让你了解应查看的新威胁，以确保更广泛的公司环境已做好抵御攻击的准备。

### <a name="tracked-queries"></a>跟踪的查询

跟踪的查询利用保存的查询定期评估组织中 Microsoft 365 活动。 这为你提供了事件趋势，未来几个月将有更多的事件趋势。 跟踪的查询会自动运行，从而为您提供最新信息，而无需记住重新运行查询。

![已选定查询的跟踪查询示例](../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png)

### <a name="saved-queries"></a>已保存的查询

保存的查询也位于"跟踪程序"部分。 可以使用保存的查询来存储希望更快、重复地返回的常见 Explorer 搜索，而无需每次重新创建搜索。

![已选定查询的已保存查询示例](../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png)

始终可以使用资源管理器页面顶部的"保存查询"按钮保存值得注意的跟踪程序查询或您自己的任何资源管理器查询。 保存的内容都会显示在跟踪程序页面上的"已保存查询"列表中。

## <a name="trackers-and-explorer"></a>跟踪器和资源管理器

无论你正在查看即将在) 即将 (的电子邮件、内容或 Office 活动，资源管理器和跟踪器都协同工作，以帮助您调查和跟踪安全风险和威胁。 跟踪器通过突出显示新的、值得注意的和经常搜索的问题，一起为您提供信息来保护用户 - 确保业务在移动到云时得到更好的保护。

请记住，你始终可以通过单击安全与合规中心概述右下角的"反馈"按钮，向我们提供有关此或其他Microsoft 365 安全功能[&反馈](https://support.microsoft.com/office/a5f2fd18-b029-4257-b5a8-ae83e7768c85)。

![安全与合规中心](../../media/86c330db-8132-4150-8475-220258fe04fb.png)

## <a name="trackers-and-microsoft-defender-for-office-365"></a>跟踪器和 Microsoft Defender for Office 365

借助我们值得注意的威胁，我们重点介绍安全附件检测到的高级 [恶意软件威胁](atp-safe-attachments.md)。 如果你是 Office 365 企业版 E5 客户，并且没有使用 [适用于 Office 365 的 Microsoft Defender，](office-365-atp.md)你应该已包含在订阅中。 Defender for Office 365 提供了价值，即使你有其他安全工具使用 Office 365 服务筛选电子邮件流。 但是，当主电子邮件安全[](atp-safe-links.md)解决方案通过 Office 365 时，反垃圾邮件和安全链接功能效果最佳。

![安全与合规中心中的 Microsoft Defender & Office 365](../../media/cee70d07-f0c1-459b-843c-2d10c253349f.png)

在当今的威胁威胁威胁的世界，仅运行传统的反恶意软件扫描意味着你没有足够的保护来抵御攻击。 当今更复杂的攻击者使用常用的工具创建新的、模糊化或延迟的攻击，而传统的基于签名的反恶意软件引擎无法识别这些攻击。 安全附件功能采用电子邮件附件，在虚拟环境中触发附件，以确定它们是安全附件还是恶意附件。 此触发过程在虚拟计算机环境中打开每个文件，然后观察打开文件后会发生什么情况。 无论是 PDF 文件、压缩文件还是 Office 文档，恶意代码都可以隐藏在文件中，仅在受攻击者打开其计算机后激活它。 通过触发和分析电子邮件流中的文件，Defender for Office 365 功能根据行为、文件信誉和大量启发式规则找到这些威胁。

新的值得注意的威胁筛选器突出显示最近通过安全附件检测到的项目。 这些检测表示是新的恶意文件的项目，Microsoft 365 之前在您的电子邮件流或其他客户的电子邮件中找不到这些项目。 注意值得注意的威胁跟踪器中的项目，查看他们的目标，并查看通过单击资源管理器) 中电子邮件的主题找到的"高级分析"选项卡 (上显示的触发详细信息。 请注意，你只能在安全附件功能检测到的电子邮件上找到此选项卡 - 此值得注意的跟踪器包含该筛选器，但您也可以在资源管理器中使用该筛选器进行其他搜索。

## <a name="next-steps"></a>后续步骤

- 如果你的组织还没有这些 Office 365 威胁调查和响应功能，请参阅如何 [获取 Office 365](office-365-ti.md)威胁调查和响应功能？。

- 确保安全团队分配了正确的角色和权限。 您必须是全局管理员，或在安全与合规中心内分配了安全管理员&清除角色。 请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。

- 观察新的跟踪器在 Microsoft 365 环境中显示。 如果可用，你将在此处找到跟踪 [器](https://protection.office.com/)。 转到 **威胁管理** \> **威胁跟踪程序**。

- 如果尚未这样做，请详细了解和配置[适用于组织的 Microsoft Defender for Office 365，](office-365-atp.md)包括[安全链接](atp-safe-links.md)[和安全附件](atp-safe-attachments.md)。
