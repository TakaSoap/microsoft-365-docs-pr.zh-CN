---
title: 了解 Microsoft 365 中的信息障碍
description: 使用信息屏障来确保在组织中使用 Microsoft Teams 的通信合规性。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 003347d46bed2529831a92681e73630d58a1f653
ms.sourcegitcommit: 8d28bce1a3445878b066864e766cf52cb83becd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50071267"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a><span data-ttu-id="9888e-103">了解 Microsoft 365 中的信息障碍</span><span class="sxs-lookup"><span data-stu-id="9888e-103">Learn about information barriers in Microsoft 365</span></span>

<span data-ttu-id="9888e-104">Microsoft 云服务包括强大的通信和协作功能。</span><span class="sxs-lookup"><span data-stu-id="9888e-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="9888e-105">但是，假设您要限制两个组之间的通信和协作，以避免在组织中发生利益冲突。</span><span class="sxs-lookup"><span data-stu-id="9888e-105">But suppose that you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="9888e-106">或者，您可能要限制组织内部某些人员之间的通信和协作，以保护内部信息。</span><span class="sxs-lookup"><span data-stu-id="9888e-106">Or, perhaps you want to restrict communication and collaboration between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="9888e-107">Microsoft 365 支持跨组和组织的通信和协作，因此是否在必要时限制特定用户组之间的通信和协作？</span><span class="sxs-lookup"><span data-stu-id="9888e-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communication and collaboration  among specific groups of users when necessary?</span></span> <span data-ttu-id="9888e-108">在信息屏障中，你可以！</span><span class="sxs-lookup"><span data-stu-id="9888e-108">With information barriers, you can!</span></span>

<span data-ttu-id="9888e-109">Microsoft Teams、SharePoint Online 和 OneDrive for Business 支持信息屏障。</span><span class="sxs-lookup"><span data-stu-id="9888e-109">Microsoft Teams, SharePoint Online, and OneDrive for Business support information barriers.</span></span> <span data-ttu-id="9888e-110">假定你的 [订阅](#required-licenses-and-permissions) 包含信息屏障，合规性管理员或信息屏障管理员可以定义策略，以允许或阻止 Microsoft Teams 中的用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="9888e-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator, or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="9888e-111">信息屏障策略可用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="9888e-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="9888e-112">日常通讯组的用户不应与营销团队通信或共享文件</span><span class="sxs-lookup"><span data-stu-id="9888e-112">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="9888e-113">处理机密公司信息的财务人员不应与组织内的某些组通信或共享文件</span><span class="sxs-lookup"><span data-stu-id="9888e-113">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="9888e-114">具有商业机密材料的内部团队不应与组织内某些组的人在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="9888e-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="9888e-115">研究团队应仅与产品开发团队在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="9888e-115">A research team should only call or chat online with a product development team</span></span>
- <span data-ttu-id="9888e-116">一天中每天的分组网站不应由日时小组之外的任何人共享或访问</span><span class="sxs-lookup"><span data-stu-id="9888e-116">A site for day trader group should not be shared or accessed by anyone outside the day trader group</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9888e-117">信息屏障 \***仅支持** _ 双向限制。</span><span class="sxs-lookup"><span data-stu-id="9888e-117">Information barriers \***only supports** _ two way restrictions.</span></span> <span data-ttu-id="9888e-118">单向限制（如营销）可以与日交易者进行通信和协作，但日交易者无法与营销 _\* 进行通信 _和协作不受_ 支持\*\*。</span><span class="sxs-lookup"><span data-stu-id="9888e-118">One way restrictions, such as marketing can communicate and collaborate with day traders, but day traders cannot communicate and collaborate with marketing _\*_is not supported_\*\*.</span></span>

<span data-ttu-id="9888e-119">对于上述所有示例方案 (更多) ，可以定义信息屏障策略来阻止或允许 Microsoft Teams、SharePoint Online 和 OneDrive 中的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="9888e-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications and collaboration in Microsoft Teams, SharePoint Online and OneDrive.</span></span> <span data-ttu-id="9888e-120">此类策略可以阻止用户呼叫或与不应联系的组聊天，或者使用户仅与 Microsoft Teams 中的特定组通信。</span><span class="sxs-lookup"><span data-stu-id="9888e-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="9888e-121">在信息屏障策略生效后，只要这些策略覆盖的用户尝试与 Microsoft Teams、SharePoint Online 或 OneDrive 中的其他人进行通信和协作，就会阻止 (或允许) 通信和协作 (，如信息屏障策略) 所定义。</span><span class="sxs-lookup"><span data-stu-id="9888e-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate and collaborate with others in Microsoft Teams, SharePoint Online or OneDrive checks are done to prevent (or allow) communication and collaboration (as defined by information barrier policies).</span></span>

<span data-ttu-id="9888e-122">若要了解有关具有信息障碍的用户体验详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="9888e-122">To learn more about the user experience with information barriers, see:</span></span>

- [<span data-ttu-id="9888e-123">Microsoft Teams 中的信息屏障</span><span class="sxs-lookup"><span data-stu-id="9888e-123">Information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="9888e-124">SharePoint Online 中的信息障碍</span><span class="sxs-lookup"><span data-stu-id="9888e-124">Information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="9888e-125">OneDrive 中的信息屏障</span><span class="sxs-lookup"><span data-stu-id="9888e-125">Information barriers in OneDrive</span></span>](/onedrive/information-barriers)

> [!IMPORTANT]
> <span data-ttu-id="9888e-126">目前，信息屏障不适用于电子邮件通信。</span><span class="sxs-lookup"><span data-stu-id="9888e-126">Currently, information barriers do not apply to email communications.</span></span> <span data-ttu-id="9888e-127">此外，信息屏障独立于合规性 [边界](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="9888e-127">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p> <span data-ttu-id="9888e-128">在定义和应用信息屏障策略之前，请确保您的组织没有 [生效的 Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 通讯簿策略。</span><span class="sxs-lookup"><span data-stu-id="9888e-128">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="9888e-129"> (信息屏障基于通讯簿策略。) </span><span class="sxs-lookup"><span data-stu-id="9888e-129">(Information barriers are based on address book policies.)</span></span>

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="9888e-130">信息屏障会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="9888e-130">What happens with information barriers</span></span>

<span data-ttu-id="9888e-131">信息屏障策略实施后，不应与其他特定用户通信或共享文件的用户将无法查找、选择、聊天或呼叫这些用户。</span><span class="sxs-lookup"><span data-stu-id="9888e-131">When information barrier policies are in place, people who should not communicate or share files with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="9888e-132">在信息屏障下，将进行检查以防止未经授权的通信和协作。</span><span class="sxs-lookup"><span data-stu-id="9888e-132">With information barriers, checks are in place to prevent unauthorized communication and collaboration.</span></span> 

<span data-ttu-id="9888e-133">信息屏障适用于 Microsoft Teams (、SharePoint Online 和 OneDrive) 聊天和频道。</span><span class="sxs-lookup"><span data-stu-id="9888e-133">Information barriers applies to Microsoft Teams (chats and channels), SharePoint Online and OneDrive.</span></span> <span data-ttu-id="9888e-134">在 Microsoft Teams 中，信息屏障策略确定并阻止以下类型的未经授权的通信：</span><span class="sxs-lookup"><span data-stu-id="9888e-134">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>

- <span data-ttu-id="9888e-135">搜索用户</span><span class="sxs-lookup"><span data-stu-id="9888e-135">Searching for a user</span></span>
- <span data-ttu-id="9888e-136">向团队添加成员</span><span class="sxs-lookup"><span data-stu-id="9888e-136">Adding a member to a team</span></span>
- <span data-ttu-id="9888e-137">开始与某人的聊天会话</span><span class="sxs-lookup"><span data-stu-id="9888e-137">Starting a chat session with someone</span></span>
- <span data-ttu-id="9888e-138">启动群聊</span><span class="sxs-lookup"><span data-stu-id="9888e-138">Starting a group chat</span></span>
- <span data-ttu-id="9888e-139">邀请某人加入会议</span><span class="sxs-lookup"><span data-stu-id="9888e-139">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="9888e-140">共享屏幕</span><span class="sxs-lookup"><span data-stu-id="9888e-140">Sharing a screen</span></span>
- <span data-ttu-id="9888e-141">发出呼叫</span><span class="sxs-lookup"><span data-stu-id="9888e-141">Placing a call</span></span>
- <span data-ttu-id="9888e-142">与其他用户共享文件</span><span class="sxs-lookup"><span data-stu-id="9888e-142">Sharing a file with another user</span></span>
- <span data-ttu-id="9888e-143">通过共享链接访问文件</span><span class="sxs-lookup"><span data-stu-id="9888e-143">Access to file through sharing link</span></span>

<span data-ttu-id="9888e-144">如果参与人员包含在信息屏障策略中以阻止活动，他们将无法继续。</span><span class="sxs-lookup"><span data-stu-id="9888e-144">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="9888e-145">此外，可能阻止信息屏障策略中包含的每个人与 Microsoft Teams 中的其他人通信。</span><span class="sxs-lookup"><span data-stu-id="9888e-145">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="9888e-146">当受信息屏障策略影响的人属于同一团队或群组聊天时，他们可能会从这些聊天会话中删除，并且可能不允许与组进一步通信。</span><span class="sxs-lookup"><span data-stu-id="9888e-146">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="9888e-147">若要了解有关具有信息障碍的用户体验详细信息，请参阅 Microsoft [Teams 中的信息屏障](/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="9888e-147">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams).</span></span>

<span data-ttu-id="9888e-148">在 SharePoint Online 和 OneDrive 中，信息屏障策略可确定并阻止以下类型的未经授权的协作：</span><span class="sxs-lookup"><span data-stu-id="9888e-148">In SharePoint Online and OneDrive, information barrier policies determine and prevent the following kinds of unauthorized collaborations:</span></span>

- <span data-ttu-id="9888e-149">向网站添加成员</span><span class="sxs-lookup"><span data-stu-id="9888e-149">Adding a member to a site</span></span>
- <span data-ttu-id="9888e-150">用户访问网站或内容</span><span class="sxs-lookup"><span data-stu-id="9888e-150">Accessing site or content by a user</span></span>
- <span data-ttu-id="9888e-151">与其他用户共享网站或内容</span><span class="sxs-lookup"><span data-stu-id="9888e-151">Sharing site or content with another user</span></span>
- <span data-ttu-id="9888e-152">搜索网站</span><span class="sxs-lookup"><span data-stu-id="9888e-152">Searching a site</span></span>

<span data-ttu-id="9888e-153">若要了解有关具有信息障碍的用户体验详细信息，请参阅 [SharePoint Online 中的信息屏障](/sharepoint/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="9888e-153">To learn more about the user experience with information barriers, see [information barriers in SharePoint Online](/sharepoint/information-barriers)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="9888e-154">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="9888e-154">Required licenses and permissions</span></span>

<span data-ttu-id="9888e-155">信息屏障现已推出，并包含在订阅中，例如：</span><span class="sxs-lookup"><span data-stu-id="9888e-155">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="9888e-156">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="9888e-156">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="9888e-157">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="9888e-157">Office 365 E5/A5</span></span>
- <span data-ttu-id="9888e-158">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="9888e-158">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="9888e-159">Microsoft 365 合规性 E5/A5</span><span class="sxs-lookup"><span data-stu-id="9888e-159">Microsoft 365 Compliance E5/A5</span></span>
- <span data-ttu-id="9888e-160">Microsoft 365 内部风险管理</span><span class="sxs-lookup"><span data-stu-id="9888e-160">Microsoft 365 Insider Risk Management</span></span>

<span data-ttu-id="9888e-161">有关详细信息，请参阅 [Microsoft 365 安全与合规&指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="9888e-161">For more information, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

<span data-ttu-id="9888e-162">若要 [定义或编辑信息屏障策略](information-barriers-policies.md)，必须分配有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="9888e-162">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="9888e-163">Microsoft 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="9888e-163">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="9888e-164">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="9888e-164">Office 365 global administrator</span></span>
- <span data-ttu-id="9888e-165">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="9888e-165">Compliance administrator</span></span>
- <span data-ttu-id="9888e-166">IBM 合规性管理</span><span class="sxs-lookup"><span data-stu-id="9888e-166">IB Compliance Management</span></span>

<span data-ttu-id="9888e-167"> (了解有关角色和权限的更多信息，请参阅 [Office 365](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)安全与合规&中的权限) </span><span class="sxs-lookup"><span data-stu-id="9888e-167">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="9888e-168">您必须熟悉 PowerShell cmdlet，才能定义、验证或编辑信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="9888e-168">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="9888e-169">尽管我们在操作方法文章中提供了 PowerShell cmdlet[](information-barriers-policies.md)的几个示例，但您需要了解组织的其他详细信息（如参数）。</span><span class="sxs-lookup"><span data-stu-id="9888e-169">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know other details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9888e-170">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9888e-170">Next steps</span></span>

- [<span data-ttu-id="9888e-171">了解有关 Microsoft Teams 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="9888e-171">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="9888e-172">了解有关 SharePoint Online 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="9888e-172">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="9888e-173">了解有关 OneDrive 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="9888e-173">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="9888e-174">查看可用于信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="9888e-174">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="9888e-175">定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9888e-175">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="9888e-176">编辑 (或删除) 信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9888e-176">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)