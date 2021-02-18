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
# <a name="threat-trackers---new-and-noteworthy"></a><span data-ttu-id="eff2e-103">威胁跟踪器 - 新增的和值得注意的威胁</span><span class="sxs-lookup"><span data-stu-id="eff2e-103">Threat Trackers - New and Noteworthy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eff2e-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="eff2e-104">**Applies to**</span></span>
- [<span data-ttu-id="eff2e-105">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="eff2e-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="eff2e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eff2e-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="eff2e-107">[Office 365 威胁](office-365-ti.md) 调查和响应功能使组织的安全团队能够发现网络安全威胁并采取行动。</span><span class="sxs-lookup"><span data-stu-id="eff2e-107">[Office 365 Threat Investigation and Response](office-365-ti.md) capabilities enable your organization's security team to discover and take action against cybersecurity threats.</span></span> <span data-ttu-id="eff2e-108">Office 365 威胁调查和响应功能包括威胁跟踪程序功能，包括值得注意的跟踪器。</span><span class="sxs-lookup"><span data-stu-id="eff2e-108">Office 365 Threat Investigation and Response capabilities include Threat Tracker features, including Noteworthy trackers.</span></span> <span data-ttu-id="eff2e-109">阅读本文，大致了解这些新功能和下一步。</span><span class="sxs-lookup"><span data-stu-id="eff2e-109">Read this article to get an overview of these new features and next steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eff2e-110">Office 365 威胁智能现在是 Microsoft Defender for Office 365 计划 2，以及其他威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="eff2e-110">Office 365 Threat Intelligence is now Microsoft Defender for Office 365 Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="eff2e-111">若要了解的详细信息，请参阅 [Microsoft Defender for Office 365 计划和定价](https://products.office.com/exchange/advance-threat-protection) 以及 Microsoft Defender for Office [365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-111">To learn more, see [Microsoft Defender for Office 365 plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Microsoft Defender for Office 365 Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="what-are-threat-trackers"></a><span data-ttu-id="eff2e-112">什么是威胁跟踪器？</span><span class="sxs-lookup"><span data-stu-id="eff2e-112">What are Threat Trackers?</span></span>

<span data-ttu-id="eff2e-113">威胁跟踪器是信息小组件和视图，可针对可能会影响公司的不同网络安全问题提供情报。</span><span class="sxs-lookup"><span data-stu-id="eff2e-113">Threat Trackers are informative widgets and views that provide you with intelligence on different cybersecurity issues that might impact your company.</span></span> <span data-ttu-id="eff2e-114">例如，可以使用威胁跟踪器查看有关恶意软件活动趋势的信息。</span><span class="sxs-lookup"><span data-stu-id="eff2e-114">For example, you can view information about trending malware campaigns using Threat Trackers.</span></span>

![显示恶意软件活动的威胁跟踪程序示例](../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png)

<span data-ttu-id="eff2e-116">大多数跟踪器页面包括定期更新的趋势数字、帮助您了解问题最大或增长最多的小组件，以及"操作"列中的"操作"列中的一个快速链接（可在其中查看更多详细信息）。</span><span class="sxs-lookup"><span data-stu-id="eff2e-116">Most tracker pages include trending numbers that are updated periodically, widgets to help you understand which issues are the biggest or have grown the most, and a quick link in the **Actions** column that takes you to Explorer, where you can view more detailed information.</span></span>

![资源管理器中的市场活动信息示例](../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png)

<span data-ttu-id="eff2e-118">跟踪器只是使用 [Microsoft Defender for Office 365](office-365-ti.md)计划 2 获得的许多功能中的一些。</span><span class="sxs-lookup"><span data-stu-id="eff2e-118">Trackers are just a few of the many great features you get with [Microsoft Defender for Office 365 Plan 2](office-365-ti.md).</span></span> <span data-ttu-id="eff2e-119">威胁跟踪器包括 [笔记跟踪器](#noteworthy-trackers)、 [趋势跟踪](#trending-trackers)器、跟踪的 [查询](#tracked-queries)和 [保存的查询](#saved-queries)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-119">Threat Trackers include [Noteworth trackers](#noteworthy-trackers), [Trending trackers](#trending-trackers), [Tracked queries](#tracked-queries), and [Saved queries](#saved-queries).</span></span>

<span data-ttu-id="eff2e-120">若要查看和使用组织的威胁跟踪器，请转到安全与合规&中心 () 威胁 <https://protection.office.com>  \> **跟踪程序**。</span><span class="sxs-lookup"><span data-stu-id="eff2e-120">To view and use your Threat Trackers for your organization, go to the Security & Compliance Center (<https://protection.office.com>) and choose **Threat management** \> **Threat tracker**.</span></span>

> [!NOTE]
> <span data-ttu-id="eff2e-121">若要使用威胁跟踪器，您必须是全局管理员、安全管理员或安全读者。</span><span class="sxs-lookup"><span data-stu-id="eff2e-121">To use Threat Trackers, you must be a global administrator, security administrator, or security reader.</span></span> <span data-ttu-id="eff2e-122">请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-122">See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="noteworthy-trackers"></a><span data-ttu-id="eff2e-123">值得注意的跟踪器</span><span class="sxs-lookup"><span data-stu-id="eff2e-123">Noteworthy trackers</span></span>

<span data-ttu-id="eff2e-124">值得一提的跟踪器是一个值得关注的地方，你可以发现我们认为你应了解的较大和较小的威胁和风险。</span><span class="sxs-lookup"><span data-stu-id="eff2e-124">Noteworthy trackers are where you'll find big and smaller threats and risks that we think you should know about.</span></span> <span data-ttu-id="eff2e-125">值得注意的跟踪器可帮助你查找 Microsoft 365 环境中是否存在这些问题，以及指向文章 (（如本文章) ）的链接，这些链接提供有关发生的情况以及这些问题如何影响组织使用 Office 365 的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="eff2e-125">Noteworthy trackers help you find whether these issues exist in your Microsoft 365 environment, plus link to articles (like this one) that give you more details on what is happening, and how they'll impact your organization's use of Office 365.</span></span> <span data-ttu-id="eff2e-126">无论是新的重大威胁 (如 Wannacry、Petya) ，还是可能会带来一些新难题的现有威胁 (如我们的另一个新增项目 -Nemucod) ，你将在这里找到你和安全团队应定期查看和检查的重要新项。</span><span class="sxs-lookup"><span data-stu-id="eff2e-126">Whether it's a big new threat (e.g. Wannacry, Petya) or an existing threat that might create some new challenges (like our other inaugural Noteworthy item - Nemucod), this is where you'll find important new items you and your security team should review and examine periodically.</span></span>

<span data-ttu-id="eff2e-127">通常，当我们发现新威胁并认为你可能需要此功能提供的额外可见性时，值得注意的跟踪器将发布几周。</span><span class="sxs-lookup"><span data-stu-id="eff2e-127">Typically Noteworthy trackers will be posted for just a couple of weeks when we identify new threats and think you might need the extra visibility that this feature provides.</span></span> <span data-ttu-id="eff2e-128">威胁的最大风险一旦过去，我们将删除该值得注意的项目。</span><span class="sxs-lookup"><span data-stu-id="eff2e-128">Once the biggest risk for a threat has passed, we'll remove that Noteworthy item.</span></span> <span data-ttu-id="eff2e-129">这样，我们可以使用其他相关新项使列表保持最新。</span><span class="sxs-lookup"><span data-stu-id="eff2e-129">This way, we can keep the list fresh and up to date with other relevant new items.</span></span>

### <a name="trending-trackers"></a><span data-ttu-id="eff2e-130">趋势跟踪器</span><span class="sxs-lookup"><span data-stu-id="eff2e-130">Trending trackers</span></span>

<span data-ttu-id="eff2e-131">趋势跟踪 (以前称为) 活动，它突出显示了过去一周组织电子邮件中收到的新威胁。</span><span class="sxs-lookup"><span data-stu-id="eff2e-131">Trending trackers (formerly called Campaigns) highlight new threats received in your organization's email in the past week.</span></span>

![趋势恶意软件市场活动小组件示例](../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png)

<span data-ttu-id="eff2e-133">趋势跟踪器可让你了解应查看的新威胁，以确保更广泛的公司环境已做好抵御攻击的准备。</span><span class="sxs-lookup"><span data-stu-id="eff2e-133">Trending trackers give you an idea of new threats you should review to ensure your broader corporate environment is prepared against attacks.</span></span>

### <a name="tracked-queries"></a><span data-ttu-id="eff2e-134">跟踪的查询</span><span class="sxs-lookup"><span data-stu-id="eff2e-134">Tracked queries</span></span>

<span data-ttu-id="eff2e-135">跟踪的查询利用保存的查询定期评估组织中 Microsoft 365 活动。</span><span class="sxs-lookup"><span data-stu-id="eff2e-135">Tracked queries leverage your saved queries to periodically assess Microsoft 365 activity in your organization.</span></span> <span data-ttu-id="eff2e-136">这为你提供了事件趋势，未来几个月将有更多的事件趋势。</span><span class="sxs-lookup"><span data-stu-id="eff2e-136">This gives you event trending, with more to come in the coming months.</span></span> <span data-ttu-id="eff2e-137">跟踪的查询会自动运行，从而为您提供最新信息，而无需记住重新运行查询。</span><span class="sxs-lookup"><span data-stu-id="eff2e-137">Tracked queries run automatically, giving you up-to-date information without having to remember to re-run your queries.</span></span>

![已选定查询的跟踪查询示例](../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png)

### <a name="saved-queries"></a><span data-ttu-id="eff2e-139">已保存的查询</span><span class="sxs-lookup"><span data-stu-id="eff2e-139">Saved queries</span></span>

<span data-ttu-id="eff2e-140">保存的查询也位于"跟踪程序"部分。</span><span class="sxs-lookup"><span data-stu-id="eff2e-140">Saved queries are also found in the Trackers section.</span></span> <span data-ttu-id="eff2e-141">可以使用保存的查询来存储希望更快、重复地返回的常见 Explorer 搜索，而无需每次重新创建搜索。</span><span class="sxs-lookup"><span data-stu-id="eff2e-141">You can use Saved queries to store the common Explorer searches that you want to get back to quicker and repeatedly, without having to re-create the search every time.</span></span>

![已选定查询的已保存查询示例](../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png)

<span data-ttu-id="eff2e-143">始终可以使用资源管理器页面顶部的"保存查询"按钮保存值得注意的跟踪程序查询或您自己的任何资源管理器查询。</span><span class="sxs-lookup"><span data-stu-id="eff2e-143">You can always save a Noteworthy tracker query or any of your own Explorer queries using the **Save query** button at the top of the Explorer page.</span></span> <span data-ttu-id="eff2e-144">保存的内容都会显示在跟踪程序页面上的"已保存查询"列表中。</span><span class="sxs-lookup"><span data-stu-id="eff2e-144">Anything saved there will show up in the **Saved queries** list on the Tracker page.</span></span>

## <a name="trackers-and-explorer"></a><span data-ttu-id="eff2e-145">跟踪器和资源管理器</span><span class="sxs-lookup"><span data-stu-id="eff2e-145">Trackers and Explorer</span></span>

<span data-ttu-id="eff2e-146">无论你正在查看即将在) 即将 (的电子邮件、内容或 Office 活动，资源管理器和跟踪器都协同工作，以帮助您调查和跟踪安全风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="eff2e-146">Whether you're reviewing email, content, or Office activities (coming soon), Explorer and Trackers work together to help you investigate and track security risks and threats.</span></span> <span data-ttu-id="eff2e-147">跟踪器通过突出显示新的、值得注意的和经常搜索的问题，一起为您提供信息来保护用户 - 确保业务在移动到云时得到更好的保护。</span><span class="sxs-lookup"><span data-stu-id="eff2e-147">All together, Trackers provide you with information to protect your users by highlighting new, notable, and frequently searched issues - ensuring your business is better protected as it moves to the cloud.</span></span>

<span data-ttu-id="eff2e-148">请记住，你始终可以通过单击安全与合规中心概述右下角的"反馈"按钮，向我们提供有关此或其他Microsoft 365 安全功能[&反馈](https://support.microsoft.com/office/a5f2fd18-b029-4257-b5a8-ae83e7768c85)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-148">And remember that you can always provide us feedback on this or other Microsoft 365 security features by clicking on the **Feedback** button in the lower right corner of the [Overview of the Security & Compliance Center](https://support.microsoft.com/office/a5f2fd18-b029-4257-b5a8-ae83e7768c85).</span></span>

![安全与合规中心](../../media/86c330db-8132-4150-8475-220258fe04fb.png)

## <a name="trackers-and-microsoft-defender-for-office-365"></a><span data-ttu-id="eff2e-150">跟踪器和 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="eff2e-150">Trackers and Microsoft Defender for Office 365</span></span>

<span data-ttu-id="eff2e-151">借助我们值得注意的威胁，我们重点介绍安全附件检测到的高级 [恶意软件威胁](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-151">With our inaugural Noteworthy threat, we're highlighting advanced malware threats detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="eff2e-152">如果你是 Office 365 企业版 E5 客户，并且没有使用 [适用于 Office 365 的 Microsoft Defender，](office-365-atp.md)你应该已包含在订阅中。</span><span class="sxs-lookup"><span data-stu-id="eff2e-152">If you're an Office 365 Enterprise E5 customer and you're not using [Microsoft Defender for Office 365](office-365-atp.md), you should be - it's included in your subscription.</span></span> <span data-ttu-id="eff2e-153">Defender for Office 365 提供了价值，即使你有其他安全工具使用 Office 365 服务筛选电子邮件流。</span><span class="sxs-lookup"><span data-stu-id="eff2e-153">Defender for Office 365 provides value even if you have other security tools filtering email flow with your Office 365 services.</span></span> <span data-ttu-id="eff2e-154">但是，当主电子邮件安全[](atp-safe-links.md)解决方案通过 Office 365 时，反垃圾邮件和安全链接功能效果最佳。</span><span class="sxs-lookup"><span data-stu-id="eff2e-154">However, anti-spam and [Safe Links](atp-safe-links.md) features work best when your main email security solution is through Office 365.</span></span>

![安全与合规中心中的 Microsoft Defender & Office 365](../../media/cee70d07-f0c1-459b-843c-2d10c253349f.png)

<span data-ttu-id="eff2e-156">在当今的威胁威胁威胁的世界，仅运行传统的反恶意软件扫描意味着你没有足够的保护来抵御攻击。</span><span class="sxs-lookup"><span data-stu-id="eff2e-156">In today's threat-riddled world, running only traditional anti-malware scans means you are not protected well enough against attacks.</span></span> <span data-ttu-id="eff2e-157">当今更复杂的攻击者使用常用的工具创建新的、模糊化或延迟的攻击，而传统的基于签名的反恶意软件引擎无法识别这些攻击。</span><span class="sxs-lookup"><span data-stu-id="eff2e-157">Today's more sophisticated attackers use commonly available tools to create new, obfuscated, or delayed attacks that won't be recognized by traditional signature-based anti-malware engines.</span></span> <span data-ttu-id="eff2e-158">安全附件功能采用电子邮件附件，在虚拟环境中触发附件，以确定它们是安全附件还是恶意附件。</span><span class="sxs-lookup"><span data-stu-id="eff2e-158">The Safe Attachments feature takes email attachments and detonates them in a virtual environment to determine whether they're safe or malicious.</span></span> <span data-ttu-id="eff2e-159">此触发过程在虚拟计算机环境中打开每个文件，然后观察打开文件后会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="eff2e-159">This detonation process opens each file in a virtual computer environment, then watches what happens after the file is opened.</span></span> <span data-ttu-id="eff2e-160">无论是 PDF 文件、压缩文件还是 Office 文档，恶意代码都可以隐藏在文件中，仅在受攻击者打开其计算机后激活它。</span><span class="sxs-lookup"><span data-stu-id="eff2e-160">Whether it's a PDF, and compressed file, or an Office document, malicious code can be hidden in a file, activating only once the victim opens it on their computer.</span></span> <span data-ttu-id="eff2e-161">通过触发和分析电子邮件流中的文件，Defender for Office 365 功能根据行为、文件信誉和大量启发式规则找到这些威胁。</span><span class="sxs-lookup"><span data-stu-id="eff2e-161">By detonating and analyzing the file in the email flow, Defender for Office 365 capabilities finds these threats based on behaviors, file reputation, and a number of heuristic rules.</span></span>

<span data-ttu-id="eff2e-162">新的值得注意的威胁筛选器突出显示最近通过安全附件检测到的项目。</span><span class="sxs-lookup"><span data-stu-id="eff2e-162">The new Noteworthy threat filter highlights items that were recently detected through Safe Attachments.</span></span> <span data-ttu-id="eff2e-163">这些检测表示是新的恶意文件的项目，Microsoft 365 之前在您的电子邮件流或其他客户的电子邮件中找不到这些项目。</span><span class="sxs-lookup"><span data-stu-id="eff2e-163">These detections represent items that are new malicious files, not previously found by Microsoft 365 in either your email flow or other customers' email.</span></span> <span data-ttu-id="eff2e-164">注意值得注意的威胁跟踪器中的项目，查看他们的目标，并查看通过单击资源管理器) 中电子邮件的主题找到的"高级分析"选项卡 (上显示的触发详细信息。</span><span class="sxs-lookup"><span data-stu-id="eff2e-164">Pay attention to the items in the Noteworthy Threat Tracker, see who was targeted by them, and review the detonation details shown on the Advanced Analysis tab (found by clicking on the subject of the email in Explorer).</span></span> <span data-ttu-id="eff2e-165">请注意，你只能在安全附件功能检测到的电子邮件上找到此选项卡 - 此值得注意的跟踪器包含该筛选器，但您也可以在资源管理器中使用该筛选器进行其他搜索。</span><span class="sxs-lookup"><span data-stu-id="eff2e-165">Note you'll only find this tab on emails detected by the Safe Attachments capability - this Noteworthy tracker includes that filter, but you can also use that filter for other searches in Explorer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eff2e-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eff2e-166">Next steps</span></span>

- <span data-ttu-id="eff2e-167">如果你的组织还没有这些 Office 365 威胁调查和响应功能，请参阅如何 [获取 Office 365](office-365-ti.md)威胁调查和响应功能？。</span><span class="sxs-lookup"><span data-stu-id="eff2e-167">If your organization doesn't already have these Office 365 Threat Investigation and Response capabilities, see [How do we get Office 365 Threat Investigation and Response capabilities?](office-365-ti.md).</span></span>

- <span data-ttu-id="eff2e-168">确保安全团队分配了正确的角色和权限。</span><span class="sxs-lookup"><span data-stu-id="eff2e-168">Make sure that your security team has the correct roles and permissions assigned.</span></span> <span data-ttu-id="eff2e-169">您必须是全局管理员，或在安全与合规中心内分配了安全管理员&清除角色。</span><span class="sxs-lookup"><span data-stu-id="eff2e-169">You must be a global administrator, or have the Security Administrator or Search and Purge role assigned in the Security & Compliance Center.</span></span> <span data-ttu-id="eff2e-170">请参阅 [安全与合规中心&权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-170">See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="eff2e-171">观察新的跟踪器在 Microsoft 365 环境中显示。</span><span class="sxs-lookup"><span data-stu-id="eff2e-171">Watch for the new Trackers to show up in your Microsoft 365 environment.</span></span> <span data-ttu-id="eff2e-172">如果可用，你将在此处找到跟踪 [器](https://protection.office.com/)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-172">When available, you'll find your Trackers [here](https://protection.office.com/).</span></span> <span data-ttu-id="eff2e-173">转到 **威胁管理** \> **威胁跟踪程序**。</span><span class="sxs-lookup"><span data-stu-id="eff2e-173">Go to **Threat management** \> **Threat trackers**.</span></span>

- <span data-ttu-id="eff2e-174">如果尚未这样做，请详细了解和配置[适用于组织的 Microsoft Defender for Office 365，](office-365-atp.md)包括[安全链接](atp-safe-links.md)[和安全附件](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="eff2e-174">If you haven't already done so, learn more about and configure [Microsoft Defender for Office 365](office-365-atp.md) for your organization, including [Safe links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md).</span></span>
