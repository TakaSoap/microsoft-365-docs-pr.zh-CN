---
title: 了解 Microsoft 365 中的信息障碍
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: 使用信息屏障来确保在组织中使用 Microsoft Teams 的通信合规性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73a76e67fdb96f89dbd11daf4b2ef12f6590f92a
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701001"
---
# <a name="learn-about-information-barriers-in-microsoft-365"></a><span data-ttu-id="032f9-103">了解 Microsoft 365 中的信息障碍</span><span class="sxs-lookup"><span data-stu-id="032f9-103">Learn about information barriers in Microsoft 365</span></span>

<span data-ttu-id="032f9-104">Microsoft 云服务包括强大的通信和协作功能。</span><span class="sxs-lookup"><span data-stu-id="032f9-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="032f9-105">但是，假设您要限制两个组之间的通信和协作，以避免在组织中发生利益冲突。</span><span class="sxs-lookup"><span data-stu-id="032f9-105">But suppose that you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="032f9-106">或者，您可能要限制组织内部某些人员之间的通信和协作，以保护内部信息。</span><span class="sxs-lookup"><span data-stu-id="032f9-106">Or, perhaps you want to restrict communication and collaboration between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="032f9-107">Microsoft 365 支持跨组和组织的通信和协作，因此是否在必要时限制特定用户组之间的通信和协作？</span><span class="sxs-lookup"><span data-stu-id="032f9-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communication and collaboration  among specific groups of users when necessary?</span></span> <span data-ttu-id="032f9-108">在信息屏障中，你可以！</span><span class="sxs-lookup"><span data-stu-id="032f9-108">With information barriers, you can!</span></span> 

<span data-ttu-id="032f9-109">Microsoft Teams、SharePoint Online 和 OneDrive for Business 现在支持信息屏障。</span><span class="sxs-lookup"><span data-stu-id="032f9-109">Information barriers is now supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="032f9-110">假定 [你的订阅](#required-licenses-and-permissions) 包含信息屏障，合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft Teams 中的用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="032f9-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="032f9-111">信息屏障策略可用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="032f9-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="032f9-112">一天中工作组中的用户不应与营销团队通信或共享文件</span><span class="sxs-lookup"><span data-stu-id="032f9-112">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="032f9-113">处理机密公司信息的财务人员不应与组织内的某些组通信或共享文件</span><span class="sxs-lookup"><span data-stu-id="032f9-113">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="032f9-114">具有商业机密材料的内部团队不应与组织内某些组的人在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="032f9-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="032f9-115">研究团队应仅与产品开发团队在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="032f9-115">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="032f9-116">信息屏障 \***仅支持** _ 双向限制。</span><span class="sxs-lookup"><span data-stu-id="032f9-116">Information barriers \***only supports** _ two way restrictions.</span></span> <span data-ttu-id="032f9-117">单向限制（如营销）可以与日交易者通信，但日交易者无法与营销 _\*_进行通信不受支持_\*\*。</span><span class="sxs-lookup"><span data-stu-id="032f9-117">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing _\*_is not supported_\*\*.</span></span>

<span data-ttu-id="032f9-118">对于上述所有示例方案 (更多) ，可以定义信息屏障策略来阻止或允许 Microsoft Teams 中的通信。</span><span class="sxs-lookup"><span data-stu-id="032f9-118">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="032f9-119">此类策略可以阻止用户呼叫或与不应联系的组聊天，或者使用户仅与 Microsoft Teams 中的特定组通信。</span><span class="sxs-lookup"><span data-stu-id="032f9-119">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="032f9-120">在信息屏障策略生效后，只要这些策略覆盖的用户尝试与 Microsoft Teams 中的其他人通信，就会进行检查以防止 (或允许) 通信 (如信息屏障策略) 。</span><span class="sxs-lookup"><span data-stu-id="032f9-120">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="032f9-121">若要了解有关具有信息障碍的用户体验详细信息，请参阅 Microsoft [Teams 中的信息屏障](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="032f9-121">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="032f9-122">目前，信息屏障不适用于电子邮件通信。</span><span class="sxs-lookup"><span data-stu-id="032f9-122">Currently, information barriers do not apply to email communications.</span></span> <span data-ttu-id="032f9-123">此外，信息屏障独立于合规性 [边界](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="032f9-123">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="032f9-124">在定义和应用信息屏障策略之前，请确保您的组织没有 [生效的 Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) 通讯簿策略。</span><span class="sxs-lookup"><span data-stu-id="032f9-124">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="032f9-125"> (信息屏障基于通讯簿策略。) </span><span class="sxs-lookup"><span data-stu-id="032f9-125">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="032f9-126">信息屏障会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="032f9-126">What happens with information barriers</span></span>

<span data-ttu-id="032f9-127">当信息屏障策略到位时，不应与其他特定用户通信或共享文件的用户将无法查找、选择、聊天或呼叫这些用户。</span><span class="sxs-lookup"><span data-stu-id="032f9-127">When information barrier policies are in place, people who should not communicate or share files with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="032f9-128">在信息屏障下，将进行检查以防止未经授权的通信。</span><span class="sxs-lookup"><span data-stu-id="032f9-128">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="032f9-129">最初，信息屏障仅适用于 Microsoft Teams 聊天和频道。</span><span class="sxs-lookup"><span data-stu-id="032f9-129">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="032f9-130">在 Microsoft Teams 中，信息屏障策略确定并阻止以下类型的未经授权的通信：</span><span class="sxs-lookup"><span data-stu-id="032f9-130">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>

- <span data-ttu-id="032f9-131">搜索用户</span><span class="sxs-lookup"><span data-stu-id="032f9-131">Searching for a user</span></span>
- <span data-ttu-id="032f9-132">向团队添加成员</span><span class="sxs-lookup"><span data-stu-id="032f9-132">Adding a member to a team</span></span>
- <span data-ttu-id="032f9-133">开始与某人的聊天会话</span><span class="sxs-lookup"><span data-stu-id="032f9-133">Starting a chat session with someone</span></span>
- <span data-ttu-id="032f9-134">启动群聊</span><span class="sxs-lookup"><span data-stu-id="032f9-134">Starting a group chat</span></span>
- <span data-ttu-id="032f9-135">邀请某人加入会议</span><span class="sxs-lookup"><span data-stu-id="032f9-135">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="032f9-136">共享屏幕</span><span class="sxs-lookup"><span data-stu-id="032f9-136">Sharing a screen</span></span>
- <span data-ttu-id="032f9-137">发出呼叫</span><span class="sxs-lookup"><span data-stu-id="032f9-137">Placing a call</span></span>
- <span data-ttu-id="032f9-138">与其他用户共享文件</span><span class="sxs-lookup"><span data-stu-id="032f9-138">Sharing a file with another user</span></span>
- <span data-ttu-id="032f9-139">通过共享链接访问文件</span><span class="sxs-lookup"><span data-stu-id="032f9-139">Access to file through sharing link</span></span> 

<span data-ttu-id="032f9-140">如果参与人员包含在信息屏障策略中以阻止活动，他们将不能继续。</span><span class="sxs-lookup"><span data-stu-id="032f9-140">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="032f9-141">此外，可能阻止信息屏障策略中包含的每个人与 Microsoft Teams 中的其他人通信。</span><span class="sxs-lookup"><span data-stu-id="032f9-141">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="032f9-142">当受信息屏障策略影响的人属于同一团队或群组聊天时，他们可能会从这些聊天会话中删除，并且可能不允许与组进一步通信。</span><span class="sxs-lookup"><span data-stu-id="032f9-142">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="032f9-143">若要了解有关具有信息障碍的用户体验详细信息，请参阅 Microsoft [Teams 中的信息屏障](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="032f9-143">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="032f9-144">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="032f9-144">Required licenses and permissions</span></span>

<span data-ttu-id="032f9-145">信息屏障现已推出，并包含在订阅中，例如：</span><span class="sxs-lookup"><span data-stu-id="032f9-145">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="032f9-146">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="032f9-146">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="032f9-147">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="032f9-147">Office 365 E5/A5</span></span>
- <span data-ttu-id="032f9-148">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="032f9-148">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="032f9-149">Microsoft 365 合规性 E5/A5</span><span class="sxs-lookup"><span data-stu-id="032f9-149">Microsoft 365 Compliance E5/A5</span></span>
- <span data-ttu-id="032f9-150">Microsoft 365 内部风险管理</span><span class="sxs-lookup"><span data-stu-id="032f9-150">Microsoft 365 Insider Risk Management</span></span>

<span data-ttu-id="032f9-151">有关详细信息，请参阅 [Microsoft 365 安全与合规&指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="032f9-151">For more details, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

<span data-ttu-id="032f9-152">若要 [定义或编辑信息屏障策略](information-barriers-policies.md)，必须分配有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="032f9-152">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="032f9-153">Microsoft 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="032f9-153">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="032f9-154">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="032f9-154">Office 365 global administrator</span></span>
- <span data-ttu-id="032f9-155">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="032f9-155">Compliance administrator</span></span>
- <span data-ttu-id="032f9-156">IBM 合规性管理 (这是一个新角色！) </span><span class="sxs-lookup"><span data-stu-id="032f9-156">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="032f9-157"> (详细了解角色和权限，请参阅 [Office 365](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)安全与合规中心&中的权限) </span><span class="sxs-lookup"><span data-stu-id="032f9-157">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="032f9-158">您必须熟悉 PowerShell cmdlet，才能定义、验证或编辑信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="032f9-158">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="032f9-159">尽管我们在操作方法文章中提供了 PowerShell cmdlet[](information-barriers-policies.md)的几个示例，但您需要了解组织的其他详细信息（如参数）。</span><span class="sxs-lookup"><span data-stu-id="032f9-159">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="032f9-160">后续步骤</span><span class="sxs-lookup"><span data-stu-id="032f9-160">Next steps</span></span>

- [<span data-ttu-id="032f9-161">了解有关 Microsoft Teams 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="032f9-161">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="032f9-162">查看可用于信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="032f9-162">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="032f9-163">定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="032f9-163">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="032f9-164">编辑 (或删除) 信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="032f9-164">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)
- [<span data-ttu-id="032f9-165">了解有关 SharePoint Online 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="032f9-165">Learn more about Information barriers in SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/information-barriers)
- [<span data-ttu-id="032f9-166">了解有关 OneDrive for Business 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="032f9-166">Learn more about Information barriers in OneDrive for Business</span></span>](https://docs.microsoft.com/onedrive/information-barriers)