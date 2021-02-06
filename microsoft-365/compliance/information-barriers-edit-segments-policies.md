---
title: 管理信息屏障策略
description: 了解如何编辑或删除信息屏障策略。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.openlocfilehash: 0d46459f61b29c6bdb457c7e0c82e9147e7709ba
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126137"
---
# <a name="manage-information-barrier-policies"></a><span data-ttu-id="9b7e0-103">管理信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-103">Manage information barrier policies</span></span>

<span data-ttu-id="9b7e0-104">定义信息[屏障](information-barriers-policies.md)策略后，可能需要更改这些策略或用户区段，作为故障排除或定期维护的一部分。 [](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="9b7e0-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="9b7e0-105">使用本文作为指南。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="9b7e0-106">要执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="9b7e0-106">What do you want to do?</span></span>

|<span data-ttu-id="9b7e0-107">**操作**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-107">**Action**</span></span>|<span data-ttu-id="9b7e0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-108">**Description**</span></span>|
|:---------|:--------------|
| [<span data-ttu-id="9b7e0-109">编辑用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="9b7e0-109">Edit user account attributes</span></span>](#edit-user-account-attributes) | <span data-ttu-id="9b7e0-110">填写 Azure Active Directory 中可用于定义线段的属性。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="9b7e0-111">在用户未包含在用户应包含的分段中时编辑用户帐户属性，更改用户所参与的分段，或者使用不同的属性定义分段。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span> |
| [<span data-ttu-id="9b7e0-112">编辑线段</span><span class="sxs-lookup"><span data-stu-id="9b7e0-112">Edit a segment</span></span>](#edit-a-segment) | <span data-ttu-id="9b7e0-113">在想要更改线段的定义时编辑线段。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="9b7e0-114">例如，你可能最初使用 *Department* 定义分段，现在想要使用另一个属性，如 *MemberOf。*</span><span class="sxs-lookup"><span data-stu-id="9b7e0-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span> |
| [<span data-ttu-id="9b7e0-115">编辑策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-115">Edit a policy</span></span>](#edit-a-policy) | <span data-ttu-id="9b7e0-116">在想要更改策略的工作方式时编辑信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="9b7e0-117">例如，你可能决定只允许某些分段之间发生通信，而不是阻止两个分段之间的通信。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span> |
| [<span data-ttu-id="9b7e0-118">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="9b7e0-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status) |<span data-ttu-id="9b7e0-119">在想要更改策略或不希望策略生效时，将策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span> |
| [<span data-ttu-id="9b7e0-120">删除策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-120">Remove a policy</span></span>](#remove-a-policy) | <span data-ttu-id="9b7e0-121">如果不再需要特定策略，请删除信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span> |
| [<span data-ttu-id="9b7e0-122">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="9b7e0-122">Stop a policy application</span></span>](#stop-a-policy-application) | <span data-ttu-id="9b7e0-123">若要停止应用信息屏障策略的过程，请执行该操作。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-123">Take this action when you want to stop the process of applying information barrier policies.</span></span><br/> <span data-ttu-id="9b7e0-124">停止策略应用程序不是即时的，它不会撤消已应用于用户的策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-124">Stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span> |
| [<span data-ttu-id="9b7e0-125">定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-125">Define policies for information barriers</span></span>](information-barriers-policies.md) | <span data-ttu-id="9b7e0-126">如果尚未制定信息屏障策略，并且必须限制或限制特定用户组之间的通信，请定义信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span> |
| [<span data-ttu-id="9b7e0-127">信息屏障疑难解答</span><span class="sxs-lookup"><span data-stu-id="9b7e0-127">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md) | <span data-ttu-id="9b7e0-128">当您遇到信息障碍的意外问题时，请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-128">Refer to this article when you run into unexpected issues with information barriers.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="9b7e0-129">若要执行本文中所述的任务，必须分配有适当的角色，例如以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="9b7e0-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="9b7e0-130">- Microsoft 365 企业版全局管理员</span><span class="sxs-lookup"><span data-stu-id="9b7e0-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="9b7e0-131">- 全局管理员</span><span class="sxs-lookup"><span data-stu-id="9b7e0-131">- Global Administrator</span></span><br/><span data-ttu-id="9b7e0-132">- 合规性管理员</span><span class="sxs-lookup"><span data-stu-id="9b7e0-132">- Compliance Administrator</span></span><br/><span data-ttu-id="9b7e0-133">- IBM 合规性管理 (这是一个新角色！) </span><span class="sxs-lookup"><span data-stu-id="9b7e0-133">- IB Compliance Management (this is a new role!)</span></span><br><br><span data-ttu-id="9b7e0-134">若要了解有关信息屏障的先决条件详细信息，请参阅 ([策略的先决条件 ](information-barriers-policies.md#prerequisites)) 。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><br><br> <span data-ttu-id="9b7e0-135">确保连接到[安全与合规& PowerShell。](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="9b7e0-135">Make sure to [connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="9b7e0-136">编辑用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="9b7e0-136">Edit user account attributes</span></span>

<span data-ttu-id="9b7e0-137">使用此过程可编辑用于分段用户的属性。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> <span data-ttu-id="9b7e0-138">例如，如果您使用的是 Department 属性，并且一个或多个用户帐户当前没有为"部门"列出的任何值，则必须编辑这些用户帐户以包含部门信息。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> <span data-ttu-id="9b7e0-139">用户帐户属性用于定义分段，以便可以分配信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="9b7e0-140">若要查看特定用户帐户的详细信息，例如属性值和分配段 (s) ，请使用带 Identity 参数的 **Get-InformationBarrierRecipientStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    |<span data-ttu-id="9b7e0-141">**语法**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-141">**Syntax**</span></span>|<span data-ttu-id="9b7e0-142">**示例**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-142">**Example**</span></span>|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> <span data-ttu-id="9b7e0-143">可以使用任何能够唯一标识每个用户的值，例如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p> <span data-ttu-id="9b7e0-144"> (还可以为单个用户使用此 cmdlet：) `Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> <span data-ttu-id="9b7e0-145">本示例中，我们引用了 Office 365 中的两个用户帐户 *：Meganb* for *Megan* 和 *alexw* for *Alex。*</span><span class="sxs-lookup"><span data-stu-id="9b7e0-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> |

2. <span data-ttu-id="9b7e0-146">确定要编辑用户帐户配置文件的属性 () 。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="9b7e0-147">有关详细信息，请参阅 ["属性"了解信息屏障策略](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-147">For more information, see [Attributes for information barrier policies](information-barriers-attributes.md).</span></span> 

3. <span data-ttu-id="9b7e0-148">编辑一个或多个用户帐户以包括上一步中所选的属性值。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="9b7e0-149">若要执行此操作，请使用以下过程之一：</span><span class="sxs-lookup"><span data-stu-id="9b7e0-149">To take this action, use one of the following procedures:</span></span>

    - <span data-ttu-id="9b7e0-150">若要编辑单个帐户，请参阅使用 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)添加或更新用户配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="9b7e0-151">若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户) ，请参阅"使用[Office 365 PowerShell 配置用户帐户属性"。](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="9b7e0-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="9b7e0-152">编辑线段</span><span class="sxs-lookup"><span data-stu-id="9b7e0-152">Edit a segment</span></span>

<span data-ttu-id="9b7e0-153">使用此过程可编辑用户区段的定义。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="9b7e0-154">例如，您可以更改线段的名称，或者更改用于确定该线段中包括哪些人使用的筛选器。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="9b7e0-155">若要查看所有现有分段，请使用 **Get-OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>

    <span data-ttu-id="9b7e0-156">语法： `Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="9b7e0-157">你将看到每个类别的列表和详细信息，如线段类型、其 UserGroupFilter 值、创建或上次修改它的用户、GUID 等。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="9b7e0-158">打印或保存分段列表，供以后参考。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="9b7e0-159">例如，如果要编辑线段，需要知道其名称或标识值 (Identity 参数参数) 。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="9b7e0-160">若要编辑段，请使用带 **Identity** 参数和相关详细信息的 **Set-OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span>

    |<span data-ttu-id="9b7e0-161">**语法**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-161">**Syntax**</span></span>|<span data-ttu-id="9b7e0-162">**示例**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-162">**Example**</span></span>|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> <span data-ttu-id="9b7e0-163">本示例中，对于 GUID *为 c96e0837-c232-4a8a-841e-ef45787d8fcd* 的段，我们将部门名称更新为"HRDept"。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span> |

<span data-ttu-id="9b7e0-164">为组织完成分段编辑后，可以[定义或](information-barriers-policies.md#part-2-define-information-barrier-policies)[编辑](#edit-a-policy)信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="9b7e0-165">编辑策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-165">Edit a policy</span></span>

1. <span data-ttu-id="9b7e0-166">若要查看当前信息屏障策略的列表，请使用 **Get-InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9b7e0-167">语法： `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9b7e0-168">在结果列表中，确定要更改的策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="9b7e0-169">请注意策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="9b7e0-170">将 **Set-InformationBarrierPolicy** cmdlet 与 **Identity** 参数一同使用，并指定要所做的更改。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="9b7e0-171">示例：假设定义了一个策略，以阻止 *Research* 部门与 *销售和* 市场营销部门进行通信 *。*</span><span class="sxs-lookup"><span data-stu-id="9b7e0-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="9b7e0-172">策略是使用此 cmdlet 定义的： `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>

    <span data-ttu-id="9b7e0-173">假设我们想要更改它，以便"研究"部门中的人员只能与 *人力资源* 部门中的人员通信。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="9b7e0-174">若要进行此更改，我们使用此 cmdlet： `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="9b7e0-175">本示例将"SegmentsBlocked"更改为"SegmentsAllowed"，并指定 *HR* 段。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="9b7e0-176">编辑完策略后，请确保应用更改。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="9b7e0-177"> (应用 [信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies).) </span><span class="sxs-lookup"><span data-stu-id="9b7e0-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="9b7e0-178">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="9b7e0-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="9b7e0-179">若要查看当前信息屏障策略的列表，请使用 **Get-InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9b7e0-180">语法： `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9b7e0-181">在结果列表中，确定要更改策略 (或删除) 。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="9b7e0-182">请注意策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="9b7e0-183">若要将策略的状态设置为非活动状态，请使用带 Identity 参数的 **Set-InformationBarrierPolicy** cmdlet，将 State 参数设置为"非活动"。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="9b7e0-184">**语法**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-184">**Syntax**</span></span>|<span data-ttu-id="9b7e0-185">**示例**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-185">**Example**</span></span>|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> <span data-ttu-id="9b7e0-186">本示例中，我们将 GUID *为 43c37853-ea10-4b90-a23d-ab8c9377247* 的信息屏障策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span> |

3. <span data-ttu-id="9b7e0-187">若要应用更改，请使用 **Start-InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="9b7e0-188">语法： `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="9b7e0-189">将按用户对组织应用更改。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="9b7e0-190">如果组织规模较大，可能需要 24 (或) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="9b7e0-191"> (一般来说，处理 5，000 个用户帐户大约需要一个小时) </span><span class="sxs-lookup"><span data-stu-id="9b7e0-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="9b7e0-192">此时，一个或多个信息屏障策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="9b7e0-193">在这里，你可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="9b7e0-193">From here, you can do any of the following actions:</span></span>

- <span data-ttu-id="9b7e0-194">保持它 (设置为非活动状态的策略对用户没有) </span><span class="sxs-lookup"><span data-stu-id="9b7e0-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="9b7e0-195">编辑策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="9b7e0-196">删除策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="9b7e0-197">删除策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-197">Remove a policy</span></span>

1. <span data-ttu-id="9b7e0-198">若要查看当前信息屏障策略的列表，请使用 **Get-InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9b7e0-199">语法： `Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9b7e0-200">在结果列表中，标识要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="9b7e0-201">请注意策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="9b7e0-202">确保策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="9b7e0-203">将 **Remove-InformationBarrierPolicy** cmdlet 与 Identity 参数一同使用。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="9b7e0-204">**语法**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-204">**Syntax**</span></span>|<span data-ttu-id="9b7e0-205">**示例**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-205">**Example**</span></span>|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> <span data-ttu-id="9b7e0-206">本示例中，我们将删除 GUID *为 43c37853-ea10-4b90-a23d-ab8c93772471* 的策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> |

    <span data-ttu-id="9b7e0-207">当系统提示时，确认更改。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="9b7e0-208">对要删除的每个策略重复步骤 1-2。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="9b7e0-209">删除完策略后，应用更改。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="9b7e0-210">若要执行此操作，请使用 **Start-InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-210">To take this action, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="9b7e0-211">语法： `Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="9b7e0-212">将按用户对组织应用更改。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="9b7e0-213">如果组织规模较大，可能需要 24 (或) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="9b7e0-214">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="9b7e0-214">Stop a policy application</span></span>

<span data-ttu-id="9b7e0-215">开始应用信息屏障策略后，如果要阻止应用这些策略，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-215">After you have started applying information barrier policies, if you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="9b7e0-216">此过程大约需要 30-35 分钟才能开始。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-216">It will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="9b7e0-217">若要查看最新信息屏障策略应用程序的状态，请使用 **Get-InformationBarrierPoliciesApplicationStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="9b7e0-218">语法： `Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="9b7e0-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="9b7e0-219">请注意应用程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="9b7e0-220">将 **Stop-InformationBarrierPoliciesApplication** cmdlet 与 Identity 参数一同使用。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="9b7e0-221">**语法**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-221">**Syntax**</span></span>|<span data-ttu-id="9b7e0-222">**示例**</span><span class="sxs-lookup"><span data-stu-id="9b7e0-222">**Example**</span></span>|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> <span data-ttu-id="9b7e0-223">本示例中，我们将阻止应用信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="9b7e0-223">In this example, we are stopping information barrier policies from being applied.</span></span> |

## <a name="resources"></a><span data-ttu-id="9b7e0-224">资源</span><span class="sxs-lookup"><span data-stu-id="9b7e0-224">Resources</span></span>

- [<span data-ttu-id="9b7e0-225">大致了解信息障碍</span><span class="sxs-lookup"><span data-stu-id="9b7e0-225">Get an overview of information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="9b7e0-226">定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9b7e0-226">Define policies for information barriers</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="9b7e0-227">了解有关 Microsoft Teams 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="9b7e0-227">Learn more about information barriers in Microsoft Teams</span></span>](/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="9b7e0-228">了解有关 SharePoint Online 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="9b7e0-228">Learn more about information barriers in SharePoint Online</span></span>](/sharepoint/information-barriers)
- [<span data-ttu-id="9b7e0-229">了解有关 OneDrive 中信息屏障的信息详细信息</span><span class="sxs-lookup"><span data-stu-id="9b7e0-229">Learn more about information barriers in OneDrive</span></span>](/onedrive/information-barriers)
- [<span data-ttu-id="9b7e0-230">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="9b7e0-230">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="9b7e0-231">信息屏障疑难解答</span><span class="sxs-lookup"><span data-stu-id="9b7e0-231">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
