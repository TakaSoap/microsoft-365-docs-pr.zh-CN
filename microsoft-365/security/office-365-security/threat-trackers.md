---
title: 威胁跟踪器 - 新增的和值得注意的威胁
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: a097f5ca-eac0-44a4-bbce-365f35b79ed1
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: 了解威胁跟踪器，包括新的值得注意的跟踪器，以帮助组织随时了解安全问题。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba038f94e711470242995a8ea0f082cd6d82dcda
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663239"
---
# <a name="threat-trackers---new-and-noteworthy"></a>威胁跟踪器 - 新增的和值得注意的威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365威胁调查和响应](office-365-ti.md)功能，组织的安全团队可以发现网络安全威胁并采取措施。 Office 365威胁调查和响应功能包括威胁跟踪器功能，包括值得注意的跟踪器。 阅读本文，大致了解这些新功能和后续步骤。

> [!IMPORTANT]
> Office 365威胁情报现在Microsoft Defender for Office 365计划 2，以及额外的威胁防护功能。 若要了解详细信息，请参阅[Microsoft Defender for Office 365计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Microsoft Defender for Office 365服务说明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

## <a name="what-are-threat-trackers"></a>什么是威胁跟踪器？

威胁跟踪器是信息丰富的小组件和视图，可为你提供有关可能影响公司的不同网络安全问题的智能。 例如，可以使用威胁跟踪器查看有关热门恶意软件活动的信息。

:::image type="content" source="../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png" alt-text="显示恶意软件市场活动的威胁跟踪器示例" lightbox="../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png":::

大多数跟踪器页面包括定期更新的趋势数字、帮助你了解哪些问题最大或增长最多的小组件，以及将你带到资源管理器的 **"操作** "列中的快速链接，可在其中查看更详细的信息。

:::image type="content" source="../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png" alt-text="资源管理器中市场活动信息的示例" lightbox="../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png":::

跟踪器只是Microsoft Defender for Office 365[计划 2](office-365-ti.md) 中获得的许多出色功能中的一些。 威胁跟踪器包括 [值得注意的跟踪器](#noteworthy-trackers)、 [趋势跟踪器](#trending-trackers)、 [跟踪查询](#tracked-queries)和 [已保存的查询](#saved-queries)。

若要查看和使用组织的威胁跟踪器，请打开<https://security.microsoft.com>Microsoft 365 Defender门户，然后转到 **电子邮件&协作** \> **威胁跟踪器**。 若要直接转到 **"威胁跟踪器** "页，请使用 <https://security.microsoft.com/threattrackerv2>。

> [!NOTE]
> 若要使用威胁跟踪器，必须是全局管理员、安全管理员或安全读取者。 请参阅[Microsoft 365 Defender门户中的权限](permissions-microsoft-365-security-center.md)。

### <a name="noteworthy-trackers"></a>值得注意的跟踪器

值得注意的跟踪器是你会发现大和小的威胁和风险，我们认为你应该知道。 值得注意的跟踪器可帮助你查找这些问题是否存在于Microsoft 365环境中，以及指向此类文章的链接 () ，这些文章提供有关正在发生情况的更多详细信息，以及这些问题将如何影响组织对Office 365的使用。 无论是万纳克里、Petya () 等重大新威胁，还是现有威胁，都可能 (其他首要值得注意的项目（Nemucod) ）带来一些新的挑战，你都会发现你和安全团队应定期查看和检查的重要新项目。

通常，当我们识别新威胁并认为您可能需要此功能提供的额外可见性时，值得注意的跟踪器将只发布几个星期。 威胁的最大风险通过后，我们将删除该值得注意的项目。 这样，我们就可以将列表保持最新，并使用其他相关新项。

### <a name="trending-trackers"></a>趋势跟踪器

趋势跟踪器 (以前称为市场活动) 突出显示过去一周在组织电子邮件中收到的新威胁。 "趋势跟踪器"视图提供对影响组织Office 365环境的电子邮件威胁的动态评估。 此视图显示租户级恶意软件趋势，识别正在上升、平整或下降的恶意软件系列，使管理员更深入地了解哪些威胁需要进一步关注。

:::image type="content" source="../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png" alt-text="热门恶意软件市场活动小组件的示例" lightbox="../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png":::

趋势跟踪器可让你了解应查看的新威胁，以确保更广泛的企业环境已准备好应对攻击。

### <a name="tracked-queries"></a>跟踪的查询

跟踪的查询利用保存的查询定期评估组织中的Microsoft 365活动。 这为你提供了事件趋势，未来几个月将推出更多活动。 跟踪的查询会自动运行，无需记住重新运行查询即可提供最新信息。

:::image type="content" source="../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png" alt-text="已选中一个查询的跟踪查询示例" lightbox="../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png":::

### <a name="saved-queries"></a>已保存的查询

还可在"跟踪器"部分找到已保存的查询。 可以使用保存的查询来存储要更快、更重复地恢复的常见资源管理器搜索，而无需每次重新创建搜索。

:::image type="content" source="../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png" alt-text="已选中一个已跟踪查询的列表" lightbox="../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png":::

始终可以使用资源管理器页面顶部的 **"保存查询** "按钮保存值得注意的跟踪器查询或任何自己的资源管理器查询。 保存在那里的任何内容都将显示在"跟踪器"页上的 **"已保存的查询** "列表中。

## <a name="trackers-and-explorer"></a>跟踪器和资源管理器

无论是查看电子邮件、内容还是Office活动 (即将) ，资源管理器和跟踪器都会协同工作，帮助你调查和跟踪安全风险和威胁。 跟踪器一起提供信息，通过突出显示新的、值得注意且经常搜索的问题来保护用户 - 确保业务在迁移到云时得到更好的保护。

请记住，您始终可以通过单击右下角的"**反馈**"按钮向我们提供有关此功能或其他Microsoft 365安全功能的反馈。

:::image type="content" source="../../media/microsoft-365-defender-portal.png" alt-text="Microsoft 365 Defender 门户" lightbox="../../media/microsoft-365-defender-portal.png":::

## <a name="trackers-and-microsoft-defender-for-office-365"></a>跟踪器和Microsoft Defender for Office 365

通过我们的首次值得注意的威胁，我们将突出显示[保险箱附件](safe-attachments.md)检测到的高级恶意软件威胁。 如果你是一个Office 365 企业版 E5 客户，而你没有使用[Microsoft Defender for Office 365](defender-for-office-365.md)，你应该是 - 它包含在你的订阅中。 Defender for Office 365提供价值，即使你有其他安全工具通过Office 365服务筛选电子邮件流。 但是，当你的主要电子邮件安全解决方案通过Office 365时，反垃圾邮件和[保险箱链接](safe-links.md)功能效果最佳。

:::image type="content" source="../../media/policies.png" alt-text="Microsoft 365 Defender门户中的Microsoft Defender for Office 365" lightbox="../../media/policies.png":::

在当今充满威胁的世界中，仅运行传统的反恶意软件扫描意味着你受到的保护不够好，无法抵御攻击。 当今更复杂的攻击者使用常用工具来创建新的、模糊不清或延迟的攻击，而传统基于签名的反恶意软件引擎无法识别这些攻击。 保险箱附件功能获取电子邮件附件，并在虚拟环境中引爆它们，以确定它们是安全还是恶意。 此引爆过程在虚拟计算机环境中打开每个文件，然后监视打开文件后会发生什么情况。 无论是 PDF 和压缩文件，还是Office文档，恶意代码都可以隐藏在文件中，仅当受害者在其计算机上打开恶意代码后才激活。 通过在电子邮件流中引爆和分析文件，Defender for Office 365功能根据行为、文件信誉和一些启发性规则来查找这些威胁。

新的"值得注意的威胁"筛选器突出显示了最近通过保险箱附件检测到的项。 这些检测表示新恶意文件的项目，以前在电子邮件流或其他客户的电子邮件中Microsoft 365未找到这些项目。 请注意"值得注意的威胁跟踪器"中的项目，查看它们的目标，并查看"高级分析"选项卡上显示的爆炸详细信息 (单击资源管理器) 中的电子邮件主题找到。 请注意，你只会在保险箱附件功能检测到的电子邮件上找到此选项卡 - 此值得注意的跟踪器包含该筛选器，但你也可以将该筛选器用于资源管理器中的其他搜索。

## <a name="next-steps"></a>后续步骤

- 如果你的组织还没有这些Office 365威胁调查和响应功能，[请参阅如何Office 365威胁调查和响应功能？](office-365-ti.md)

- 确保安全团队分配了正确的角色和权限。 你必须是全局管理员，或者在Microsoft 365 Defender门户中分配安全管理员或搜索和清除角色。 请参阅[Microsoft 365 Defender门户中的权限](permissions-microsoft-365-security-center.md)。

- 监视新的跟踪器显示在Microsoft 365环境中。 如果可用，你将在Microsoft 365 Defender门户<https://security.microsoft.com/threattracker>的 **"威胁跟踪器**"页上找到跟踪器。

- 如果尚未这样做，请详细了解和配置组织[Microsoft Defender for Office 365](defender-for-office-365.md)，包括[保险箱链接](safe-links.md)和[保险箱附件](safe-attachments.md)。
