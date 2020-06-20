---
title: 了解信息障碍
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用信息障碍以确保在组织内使用 Microsoft 团队进行通信合规性。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5bd922bee0808262b297245340a2dd641f44018f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817531"
---
# <a name="information-barriers"></a><span data-ttu-id="b8bee-103">信息屏障</span><span class="sxs-lookup"><span data-stu-id="b8bee-103">Information barriers</span></span>

<span data-ttu-id="b8bee-104">Microsoft 云服务包括强大的通信和协作功能。</span><span class="sxs-lookup"><span data-stu-id="b8bee-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="b8bee-105">但假设您要限制两个组之间的通信，以避免组织中发生利益冲突。</span><span class="sxs-lookup"><span data-stu-id="b8bee-105">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="b8bee-106">或者，您可能希望限制组织内的某些人之间的通信，以便保护内部信息。</span><span class="sxs-lookup"><span data-stu-id="b8bee-106">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="b8bee-107">Microsoft 365 支持跨组和组织进行通信和协作，因此有一种方法可以在必要时限制特定用户组之间的通信吗？</span><span class="sxs-lookup"><span data-stu-id="b8bee-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="b8bee-108">通过信息障碍，你可以！</span><span class="sxs-lookup"><span data-stu-id="b8bee-108">With information barriers, you can!</span></span> 

<span data-ttu-id="b8bee-109">现在，信息障碍即将推出，从 Microsoft 团队开始。</span><span class="sxs-lookup"><span data-stu-id="b8bee-109">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="b8bee-110">假定你的[订阅](#required-licenses-and-permissions)包括信息障碍，合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft 团队中的用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="b8bee-110">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="b8bee-111">信息屏障策略可用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="b8bee-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="b8bee-112">第一天的用户 trader 组不应与市场营销团队进行通信</span><span class="sxs-lookup"><span data-stu-id="b8bee-112">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="b8bee-113">从事机密公司信息的财务人员不应与组织内的特定组进行通信</span><span class="sxs-lookup"><span data-stu-id="b8bee-113">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="b8bee-114">具有贸易秘密材料的内部团队不应与组织内特定组中的人员进行呼叫或联机聊天</span><span class="sxs-lookup"><span data-stu-id="b8bee-114">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="b8bee-115">研究团队应仅与产品开发团队进行在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="b8bee-115">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8bee-116">信息障碍***仅支持***双向限制。</span><span class="sxs-lookup"><span data-stu-id="b8bee-116">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="b8bee-117">一种方法限制（如 "营销"）可以与日贸易贸易通信，但***不支持将***day 商贸与营销进行通信。</span><span class="sxs-lookup"><span data-stu-id="b8bee-117">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="b8bee-118">对于所有这些示例方案（及更多），可以将信息屏障策略定义为阻止或允许在 Microsoft 团队中进行通信。</span><span class="sxs-lookup"><span data-stu-id="b8bee-118">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="b8bee-119">此类策略可以阻止用户不应对其进行呼叫或聊天，或使用户只能与 Microsoft 团队中的特定组进行通信。</span><span class="sxs-lookup"><span data-stu-id="b8bee-119">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="b8bee-120">在信息屏障策略生效时，只要这些策略涵盖的用户尝试与 Microsoft 团队中的其他人通信，就会执行检查以阻止（或允许）通信（由信息屏障策略定义）。</span><span class="sxs-lookup"><span data-stu-id="b8bee-120">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="b8bee-121">若要了解有关信息障碍的用户体验方面的详细信息，请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="b8bee-121">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8bee-122">目前，信息障碍不适用于电子邮件通信或通过 SharePoint Online 或 OneDrive 进行文件共享。</span><span class="sxs-lookup"><span data-stu-id="b8bee-122">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="b8bee-123">此外，信息障碍独立于[合规性边界](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="b8bee-123">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="b8bee-124">在定义和应用信息屏障策略之前，请确保您的组织没有有效的[Exchange 通讯簿策略](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="b8bee-124">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="b8bee-125">（信息障碍基于通讯簿策略。）</span><span class="sxs-lookup"><span data-stu-id="b8bee-125">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="b8bee-126">信息障碍发生的情况</span><span class="sxs-lookup"><span data-stu-id="b8bee-126">What happens with information barriers</span></span>

<span data-ttu-id="b8bee-127">在信息屏障策略就绪后，不应与其他特定用户通信的人员将无法找到、选择、聊天或呼叫这些用户。</span><span class="sxs-lookup"><span data-stu-id="b8bee-127">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="b8bee-128">通过信息障碍，检查措施可防止未经授权的通信。</span><span class="sxs-lookup"><span data-stu-id="b8bee-128">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="b8bee-129">最初，信息障碍仅适用于 Microsoft 团队聊天和频道。</span><span class="sxs-lookup"><span data-stu-id="b8bee-129">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="b8bee-130">在 Microsoft 团队中，信息障碍策略决定并阻止以下类型的未经授权的通信：</span><span class="sxs-lookup"><span data-stu-id="b8bee-130">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="b8bee-131">搜索用户</span><span class="sxs-lookup"><span data-stu-id="b8bee-131">Searching for a user</span></span>
- <span data-ttu-id="b8bee-132">向团队添加成员</span><span class="sxs-lookup"><span data-stu-id="b8bee-132">Adding a member to a team</span></span>
- <span data-ttu-id="b8bee-133">启动与某人的聊天会话</span><span class="sxs-lookup"><span data-stu-id="b8bee-133">Starting a chat session with someone</span></span>
- <span data-ttu-id="b8bee-134">启动群聊天</span><span class="sxs-lookup"><span data-stu-id="b8bee-134">Starting a group chat</span></span>
- <span data-ttu-id="b8bee-135">邀请某人加入会议</span><span class="sxs-lookup"><span data-stu-id="b8bee-135">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="b8bee-136">共享屏幕</span><span class="sxs-lookup"><span data-stu-id="b8bee-136">Sharing a screen</span></span>
- <span data-ttu-id="b8bee-137">发出呼叫</span><span class="sxs-lookup"><span data-stu-id="b8bee-137">Placing a call</span></span> 

<span data-ttu-id="b8bee-138">如果涉及的人员包含在信息屏障策略中以阻止活动，则无法继续。</span><span class="sxs-lookup"><span data-stu-id="b8bee-138">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="b8bee-139">此外，在信息屏障策略中包括的每个人都可以阻止与 Microsoft 团队中的其他人通信。</span><span class="sxs-lookup"><span data-stu-id="b8bee-139">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="b8bee-140">当受信息障碍策略影响的人员是同一个团队或组聊天的一部分时，他们可能会从这些聊天会话中删除，并且可能不允许与组进行进一步通信。</span><span class="sxs-lookup"><span data-stu-id="b8bee-140">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="b8bee-141">若要了解有关信息障碍的用户体验方面的详细信息，请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="b8bee-141">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="b8bee-142">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="b8bee-142">Required licenses and permissions</span></span>

<span data-ttu-id="b8bee-143">信息屏障现在正在推出，并包含在订阅中，如：</span><span class="sxs-lookup"><span data-stu-id="b8bee-143">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="b8bee-144">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b8bee-144">Microsoft 365 E5</span></span>
- <span data-ttu-id="b8bee-145">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="b8bee-145">Office 365 E5</span></span>
- <span data-ttu-id="b8bee-146">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="b8bee-146">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="b8bee-147">Microsoft 365 合规性 E5</span><span class="sxs-lookup"><span data-stu-id="b8bee-147">Microsoft 365 Compliance E5</span></span>

<span data-ttu-id="b8bee-148">有关更多详细信息，请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="b8bee-148">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="b8bee-149">若要[定义或编辑信息障碍策略](information-barriers-policies.md)，您必须分配有下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="b8bee-149">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="b8bee-150">Microsoft 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="b8bee-150">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="b8bee-151">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="b8bee-151">Office 365 global administrator</span></span>
- <span data-ttu-id="b8bee-152">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="b8bee-152">Compliance administrator</span></span>
- <span data-ttu-id="b8bee-153">IB 合规性管理（这是一个新角色！）</span><span class="sxs-lookup"><span data-stu-id="b8bee-153">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="b8bee-154">（若要了解有关角色和权限的详细信息，请参阅[Office 365 Security & 合规中心中的权限](../security/office-365-security/protect-against-threats.md)。）</span><span class="sxs-lookup"><span data-stu-id="b8bee-154">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="b8bee-155">您必须熟悉 PowerShell cmdlet，才能定义、验证或编辑信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="b8bee-155">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="b8bee-156">尽管我们在操作[方法一文](information-barriers-policies.md)中提供了几个 PowerShell cmdlet 示例，但你需要了解组织的其他详细信息，如参数。</span><span class="sxs-lookup"><span data-stu-id="b8bee-156">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b8bee-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b8bee-157">Next steps</span></span>

- [<span data-ttu-id="b8bee-158">了解有关 Microsoft 团队中的信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="b8bee-158">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="b8bee-159">请参阅可用于信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="b8bee-159">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="b8bee-160">定义信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="b8bee-160">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="b8bee-161">编辑（或删除）信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="b8bee-161">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 
