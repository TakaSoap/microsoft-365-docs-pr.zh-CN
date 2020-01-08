---
title: 信息屏障策略的属性
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
description: 使用本文作为对可在信息屏障策略中使用的各种属性的参考。
ms.openlocfilehash: 12acaa4fb8d6bcd6c660381b172703bd178af81f
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970780"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="caf44-103">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="caf44-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="caf44-104">Azure Active Directory 中的某些属性可用于分段用户。</span><span class="sxs-lookup"><span data-stu-id="caf44-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="caf44-105">在定义段之后，这些段可用作信息屏障策略的筛选器。</span><span class="sxs-lookup"><span data-stu-id="caf44-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="caf44-106">例如，您可以使用**部门**按组织中的部门定义用户的分段（假设没有一个员工同时适用于两个部门）。</span><span class="sxs-lookup"><span data-stu-id="caf44-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="caf44-107">本文介绍如何使用具有信息障碍的属性，并提供可使用的属性列表。</span><span class="sxs-lookup"><span data-stu-id="caf44-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="caf44-108">若要了解有关信息障碍的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="caf44-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="caf44-109">信息屏障</span><span class="sxs-lookup"><span data-stu-id="caf44-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="caf44-110">在 Microsoft 团队中定义信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="caf44-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="caf44-111">编辑（或删除）信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="caf44-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="caf44-112">如何在信息屏障策略中使用属性</span><span class="sxs-lookup"><span data-stu-id="caf44-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="caf44-113">本文中列出的属性可用于定义或编辑用户的各个部分。</span><span class="sxs-lookup"><span data-stu-id="caf44-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="caf44-114">在[信息屏障策略](information-barriers-policies.md)中，定义的段充当参数（称为*UserGroupFilter*值）。</span><span class="sxs-lookup"><span data-stu-id="caf44-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="caf44-115">确定要用于定义段的属性。</span><span class="sxs-lookup"><span data-stu-id="caf44-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="caf44-116">（请参阅本文中的[参考](#reference)部分。）</span><span class="sxs-lookup"><span data-stu-id="caf44-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="caf44-117">确保已为您在步骤1中选择的属性填写了用户帐户的值。</span><span class="sxs-lookup"><span data-stu-id="caf44-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="caf44-118">查看用户帐户详细信息，如有必要，请编辑用户帐户以包含属性值。</span><span class="sxs-lookup"><span data-stu-id="caf44-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="caf44-119">若要编辑多个帐户（或使用 PowerShell 编辑单个帐户），请参阅[Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="caf44-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

    - <span data-ttu-id="caf44-120">若要编辑单个帐户，请参阅[使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="caf44-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="caf44-121">[使用 PowerShell 定义分段](information-barriers-policies.md#define-segments-using-powershell)，类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="caf44-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="caf44-122">示例</span><span class="sxs-lookup"><span data-stu-id="caf44-122">Example</span></span>  |<span data-ttu-id="caf44-123">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="caf44-123">Cmdlet</span></span>  |
    |---------|---------|
    |<span data-ttu-id="caf44-124">使用部门属性定义名为 Segment1 的段</span><span class="sxs-lookup"><span data-stu-id="caf44-124">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |<span data-ttu-id="caf44-125">使用 MemberOf 属性定义名为 SegmentA 的段（假定此属性包含组名称，例如 "BlueGroup"）</span><span class="sxs-lookup"><span data-stu-id="caf44-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |<span data-ttu-id="caf44-126">使用 ExtensionAttribute1 定义名为 DayTraders 的段（假设此属性包含职务，如 "DayTrader"）</span><span class="sxs-lookup"><span data-stu-id="caf44-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="caf44-127">在定义段时，请对所有段使用相同的属性。</span><span class="sxs-lookup"><span data-stu-id="caf44-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="caf44-128">例如，如果使用*部门*定义一些分段，则使用*部门*定义所有分段。</span><span class="sxs-lookup"><span data-stu-id="caf44-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="caf44-129">请勿使用使用*MemberOf*的*部门*和其他部门定义某些分段。</span><span class="sxs-lookup"><span data-stu-id="caf44-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="caf44-130">请确保您的段不重叠;应将每个用户仅分配给一个分段。</span><span class="sxs-lookup"><span data-stu-id="caf44-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

## <a name="reference"></a><span data-ttu-id="caf44-131">参考</span><span class="sxs-lookup"><span data-stu-id="caf44-131">Reference</span></span>

<span data-ttu-id="caf44-132">下表列出了可用于信息障碍的属性。</span><span class="sxs-lookup"><span data-stu-id="caf44-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="caf44-133">Azure Active Directory 属性名称</span><span class="sxs-lookup"><span data-stu-id="caf44-133">Azure Active Directory property name</span></span><br/><span data-ttu-id="caf44-134">（LDAP 显示名称）</span><span class="sxs-lookup"><span data-stu-id="caf44-134">(LDAP display name)</span></span>  |<span data-ttu-id="caf44-135">Exchange 属性名称</span><span class="sxs-lookup"><span data-stu-id="caf44-135">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="caf44-136">合著</span><span class="sxs-lookup"><span data-stu-id="caf44-136">Co</span></span>       | <span data-ttu-id="caf44-137">合著</span><span class="sxs-lookup"><span data-stu-id="caf44-137">Co</span></span>        |
|<span data-ttu-id="caf44-138">Company</span><span class="sxs-lookup"><span data-stu-id="caf44-138">Company</span></span>     |<span data-ttu-id="caf44-139">公司</span><span class="sxs-lookup"><span data-stu-id="caf44-139">Company</span></span>         |
|<span data-ttu-id="caf44-140">Department</span><span class="sxs-lookup"><span data-stu-id="caf44-140">Department</span></span>     |<span data-ttu-id="caf44-141">Department</span><span class="sxs-lookup"><span data-stu-id="caf44-141">Department</span></span>         |
|<span data-ttu-id="caf44-142">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="caf44-142">ExtensionAttribute1</span></span> |<span data-ttu-id="caf44-143">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="caf44-143">CustomAttribute1</span></span>  |
|<span data-ttu-id="caf44-144">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="caf44-144">ExtensionAttribute2</span></span> |<span data-ttu-id="caf44-145">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="caf44-145">CustomAttribute2</span></span>  |
|<span data-ttu-id="caf44-146">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="caf44-146">ExtensionAttribute3</span></span> |<span data-ttu-id="caf44-147">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="caf44-147">CustomAttribute3</span></span>  |
|<span data-ttu-id="caf44-148">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="caf44-148">ExtensionAttribute4</span></span> |<span data-ttu-id="caf44-149">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="caf44-149">CustomAttribute4</span></span>  |
|<span data-ttu-id="caf44-150">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="caf44-150">ExtensionAttribute5</span></span> |<span data-ttu-id="caf44-151">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="caf44-151">CustomAttribute5</span></span>  |
|<span data-ttu-id="caf44-152">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="caf44-152">ExtensionAttribute6</span></span> |<span data-ttu-id="caf44-153">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="caf44-153">CustomAttribute6</span></span>  |
|<span data-ttu-id="caf44-154">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="caf44-154">ExtensionAttribute7</span></span> |<span data-ttu-id="caf44-155">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="caf44-155">CustomAttribute7</span></span>  |
|<span data-ttu-id="caf44-156">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="caf44-156">ExtensionAttribute8</span></span> |<span data-ttu-id="caf44-157">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="caf44-157">CustomAttribute8</span></span>  |
|<span data-ttu-id="caf44-158">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="caf44-158">ExtensionAttribute9</span></span> |<span data-ttu-id="caf44-159">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="caf44-159">CustomAttribute9</span></span>  |
|<span data-ttu-id="caf44-160">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="caf44-160">ExtensionAttribute10</span></span> |<span data-ttu-id="caf44-161">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="caf44-161">CustomAttribute10</span></span>  |
|<span data-ttu-id="caf44-162">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="caf44-162">ExtensionAttribute11</span></span> |<span data-ttu-id="caf44-163">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="caf44-163">CustomAttribute11</span></span>  |
|<span data-ttu-id="caf44-164">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="caf44-164">ExtensionAttribute12</span></span> |<span data-ttu-id="caf44-165">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="caf44-165">CustomAttribute12</span></span>  |
|<span data-ttu-id="caf44-166">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="caf44-166">ExtensionAttribute13</span></span> |<span data-ttu-id="caf44-167">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="caf44-167">CustomAttribute13</span></span>  |
|<span data-ttu-id="caf44-168">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="caf44-168">ExtensionAttribute14</span></span> |<span data-ttu-id="caf44-169">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="caf44-169">CustomAttribute14</span></span>  |
|<span data-ttu-id="caf44-170">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="caf44-170">ExtensionAttribute15</span></span> |<span data-ttu-id="caf44-171">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="caf44-171">CustomAttribute15</span></span>  |
|<span data-ttu-id="caf44-172">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="caf44-172">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="caf44-173">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="caf44-173">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="caf44-174">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="caf44-174">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="caf44-175">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="caf44-175">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="caf44-176">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="caf44-176">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="caf44-177">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="caf44-177">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="caf44-178">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="caf44-178">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="caf44-179">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="caf44-179">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="caf44-180">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="caf44-180">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="caf44-181">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="caf44-181">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="caf44-182">MailNickname</span><span class="sxs-lookup"><span data-stu-id="caf44-182">MailNickname</span></span> |<span data-ttu-id="caf44-183">别名</span><span class="sxs-lookup"><span data-stu-id="caf44-183">Alias</span></span> |
|<span data-ttu-id="caf44-184">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="caf44-184">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="caf44-185">Office</span><span class="sxs-lookup"><span data-stu-id="caf44-185">Office</span></span> |
|<span data-ttu-id="caf44-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="caf44-186">PostalCode</span></span> |<span data-ttu-id="caf44-187">PostalCode</span><span class="sxs-lookup"><span data-stu-id="caf44-187">PostalCode</span></span> |
|<span data-ttu-id="caf44-188">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="caf44-188">ProxyAddresses</span></span> |<span data-ttu-id="caf44-189">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="caf44-189">EmailAddresses</span></span> |
|<span data-ttu-id="caf44-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="caf44-190">StreetAddress</span></span> |<span data-ttu-id="caf44-191">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="caf44-191">StreetAddress</span></span> |
|<span data-ttu-id="caf44-192">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="caf44-192">TargetAddress</span></span> |<span data-ttu-id="caf44-193">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="caf44-193">ExternalEmailAddress</span></span> |
|<span data-ttu-id="caf44-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="caf44-194">UsageLocation</span></span> |<span data-ttu-id="caf44-195">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="caf44-195">UsageLocation</span></span> |
|<span data-ttu-id="caf44-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="caf44-196">UserPrincipalName</span></span>  |<span data-ttu-id="caf44-197">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="caf44-197">UserPrincipalName</span></span>  |
|<span data-ttu-id="caf44-198">邮件</span><span class="sxs-lookup"><span data-stu-id="caf44-198">Mail</span></span>   |<span data-ttu-id="caf44-199">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="caf44-199">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="caf44-200">说明</span><span class="sxs-lookup"><span data-stu-id="caf44-200">Description</span></span>    |<span data-ttu-id="caf44-201">说明</span><span class="sxs-lookup"><span data-stu-id="caf44-201">Description</span></span>    |
|<span data-ttu-id="caf44-202">MemberOf</span><span class="sxs-lookup"><span data-stu-id="caf44-202">MemberOf</span></span>   |<span data-ttu-id="caf44-203">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="caf44-203">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="caf44-204">相关主题</span><span class="sxs-lookup"><span data-stu-id="caf44-204">Related topics</span></span>

[<span data-ttu-id="caf44-205">在 Microsoft 团队中定义信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="caf44-205">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)

[<span data-ttu-id="caf44-206">信息屏障疑难解答</span><span class="sxs-lookup"><span data-stu-id="caf44-206">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="caf44-207">信息屏障</span><span class="sxs-lookup"><span data-stu-id="caf44-207">Information barriers</span></span>](information-barriers.md)



