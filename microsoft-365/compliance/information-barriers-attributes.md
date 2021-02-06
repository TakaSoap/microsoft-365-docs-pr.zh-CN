---
title: 信息屏障策略的属性
description: 本文引用了可用于定义信息屏障段的 Azure Active Directory 用户帐户属性。
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c45a2733c1fa7cf6d05cff747a9cfcdba1b124cc
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126159"
---
# <a name="attributes-for-information-barrier-policies"></a><span data-ttu-id="9d5b2-103">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="9d5b2-103">Attributes for information barrier policies</span></span>

<span data-ttu-id="9d5b2-104">Azure Active Directory 中的某些属性可用于划分用户。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="9d5b2-105">定义线段后，这些线段可以用作信息屏障策略的筛选器。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="9d5b2-106">例如，可以使用"部门"按组织内部的部门定义用户细分 (假定没有一名员工同时为两个部门) 。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span>

<span data-ttu-id="9d5b2-107">本文介绍如何将属性与信息障碍一同使用，并提供了可以使用的属性列表。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="9d5b2-108">若要了解有关信息屏障详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="9d5b2-108">To learn more about information barriers, see the following resources:</span></span>

- [<span data-ttu-id="9d5b2-109">信息屏障</span><span class="sxs-lookup"><span data-stu-id="9d5b2-109">Information barriers</span></span>](information-barriers.md)
- [<span data-ttu-id="9d5b2-110">在 Microsoft Teams 中定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9d5b2-110">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="9d5b2-111">编辑 (或删除) 信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9d5b2-111">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="9d5b2-112">如何在信息屏障策略中使用属性</span><span class="sxs-lookup"><span data-stu-id="9d5b2-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="9d5b2-113">本文中列出的属性可用于定义或编辑用户细分。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="9d5b2-114">你定义的区段用作 (策略中) *UserGroupFilter* [值的参数](information-barriers-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="9d5b2-115">确定要用于定义线段的属性。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="9d5b2-116"> ([请参阅本文中的](#reference) 参考部分。) </span><span class="sxs-lookup"><span data-stu-id="9d5b2-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="9d5b2-117">确保用户帐户已针对在步骤 1 中 () 属性填充了值。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="9d5b2-118">查看用户帐户详细信息，如有必要，编辑用户帐户以包含属性值。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="9d5b2-119">若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户) ，请参阅"使用[Office 365 PowerShell 配置用户帐户属性"。](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="9d5b2-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).</span></span>

    - <span data-ttu-id="9d5b2-120">若要编辑单个帐户，请参阅使用 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)添加或更新用户配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="9d5b2-121">[使用 PowerShell](information-barriers-policies.md#define-segments-using-powershell)定义线段，类似于以下示例：</span><span class="sxs-lookup"><span data-stu-id="9d5b2-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="9d5b2-122">**示例**</span><span class="sxs-lookup"><span data-stu-id="9d5b2-122">**Example**</span></span>|<span data-ttu-id="9d5b2-123">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="9d5b2-123">**Cmdlet**</span></span>|
    |:----------|:---------|
    | <span data-ttu-id="9d5b2-124">使用 Department 属性定义名为 Segment1 的线段</span><span class="sxs-lookup"><span data-stu-id="9d5b2-124">Define a segment called Segment1 using the Department attribute</span></span> | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | <span data-ttu-id="9d5b2-125">使用 MemberOf 属性定义名为 SegmentA 的 (假定此属性包含组名称，例如"BlueGroup") </span><span class="sxs-lookup"><span data-stu-id="9d5b2-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span> | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | <span data-ttu-id="9d5b2-126">使用 ExtensionAttribute1 定义名为 DayTraders 的 (假定此属性包含职务，例如"DayTrader") </span><span class="sxs-lookup"><span data-stu-id="9d5b2-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span> | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="9d5b2-127">定义线段时，请为所有线段使用相同的属性。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="9d5b2-128">例如，如果使用 Department 定义某些线 *段，则* 使用 Department 定义所有 *线段*。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="9d5b2-129">请勿使用 Department 定义某些 *分段，* 而使用 *MemberOf 定义其他分段*。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="9d5b2-130">确保线段不重叠;每个用户应只分配到一个区段。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span>

## <a name="reference"></a><span data-ttu-id="9d5b2-131">参考</span><span class="sxs-lookup"><span data-stu-id="9d5b2-131">Reference</span></span>

<span data-ttu-id="9d5b2-132">下表列出了可用于信息障碍的属性。</span><span class="sxs-lookup"><span data-stu-id="9d5b2-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="9d5b2-133">**AZURE Active Directory 属性名称 (<br/> LDAP 显示名称)**</span><span class="sxs-lookup"><span data-stu-id="9d5b2-133">**Azure Active Directory property name<br/>(LDAP display name)**</span></span>|<span data-ttu-id="9d5b2-134">**Exchange 属性名称**</span><span class="sxs-lookup"><span data-stu-id="9d5b2-134">**Exchange property name**</span></span>|
|:---------------------------------------------------------------|:-------------------------|
| <span data-ttu-id="9d5b2-135">Co</span><span class="sxs-lookup"><span data-stu-id="9d5b2-135">Co</span></span> | <span data-ttu-id="9d5b2-136">Co</span><span class="sxs-lookup"><span data-stu-id="9d5b2-136">Co</span></span> |
| <span data-ttu-id="9d5b2-137">Company</span><span class="sxs-lookup"><span data-stu-id="9d5b2-137">Company</span></span> | <span data-ttu-id="9d5b2-138">公司</span><span class="sxs-lookup"><span data-stu-id="9d5b2-138">Company</span></span> |
| <span data-ttu-id="9d5b2-139">Department</span><span class="sxs-lookup"><span data-stu-id="9d5b2-139">Department</span></span> | <span data-ttu-id="9d5b2-140">Department</span><span class="sxs-lookup"><span data-stu-id="9d5b2-140">Department</span></span> |
| <span data-ttu-id="9d5b2-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="9d5b2-141">ExtensionAttribute1</span></span> | <span data-ttu-id="9d5b2-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="9d5b2-142">CustomAttribute1</span></span> |
| <span data-ttu-id="9d5b2-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="9d5b2-143">ExtensionAttribute2</span></span> | <span data-ttu-id="9d5b2-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="9d5b2-144">CustomAttribute2</span></span> |
| <span data-ttu-id="9d5b2-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="9d5b2-145">ExtensionAttribute3</span></span> | <span data-ttu-id="9d5b2-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="9d5b2-146">CustomAttribute3</span></span> |
| <span data-ttu-id="9d5b2-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="9d5b2-147">ExtensionAttribute4</span></span> | <span data-ttu-id="9d5b2-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="9d5b2-148">CustomAttribute4</span></span> |
| <span data-ttu-id="9d5b2-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="9d5b2-149">ExtensionAttribute5</span></span> | <span data-ttu-id="9d5b2-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="9d5b2-150">CustomAttribute5</span></span> |
| <span data-ttu-id="9d5b2-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="9d5b2-151">ExtensionAttribute6</span></span> | <span data-ttu-id="9d5b2-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="9d5b2-152">CustomAttribute6</span></span> |
| <span data-ttu-id="9d5b2-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="9d5b2-153">ExtensionAttribute7</span></span> | <span data-ttu-id="9d5b2-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="9d5b2-154">CustomAttribute7</span></span> |
| <span data-ttu-id="9d5b2-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="9d5b2-155">ExtensionAttribute8</span></span> | <span data-ttu-id="9d5b2-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="9d5b2-156">CustomAttribute8</span></span> |
| <span data-ttu-id="9d5b2-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="9d5b2-157">ExtensionAttribute9</span></span> | <span data-ttu-id="9d5b2-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="9d5b2-158">CustomAttribute9</span></span> |
| <span data-ttu-id="9d5b2-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="9d5b2-159">ExtensionAttribute10</span></span> | <span data-ttu-id="9d5b2-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="9d5b2-160">CustomAttribute10</span></span> |
| <span data-ttu-id="9d5b2-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="9d5b2-161">ExtensionAttribute11</span></span> | <span data-ttu-id="9d5b2-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="9d5b2-162">CustomAttribute11</span></span> |
| <span data-ttu-id="9d5b2-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="9d5b2-163">ExtensionAttribute12</span></span> | <span data-ttu-id="9d5b2-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="9d5b2-164">CustomAttribute12</span></span> |
| <span data-ttu-id="9d5b2-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="9d5b2-165">ExtensionAttribute13</span></span> | <span data-ttu-id="9d5b2-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="9d5b2-166">CustomAttribute13</span></span> |
| <span data-ttu-id="9d5b2-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="9d5b2-167">ExtensionAttribute14</span></span> | <span data-ttu-id="9d5b2-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="9d5b2-168">CustomAttribute14</span></span> |
| <span data-ttu-id="9d5b2-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="9d5b2-169">ExtensionAttribute15</span></span> | <span data-ttu-id="9d5b2-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="9d5b2-170">CustomAttribute15</span></span> |
| <span data-ttu-id="9d5b2-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="9d5b2-171">MSExchExtensionCustomAttribute1</span></span> | <span data-ttu-id="9d5b2-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="9d5b2-172">ExtensionCustomAttribute1</span></span> |
| <span data-ttu-id="9d5b2-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="9d5b2-173">MSExchExtensionCustomAttribute2</span></span> | <span data-ttu-id="9d5b2-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="9d5b2-174">ExtensionCustomAttribute2</span></span> |
| <span data-ttu-id="9d5b2-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="9d5b2-175">MSExchExtensionCustomAttribute3</span></span> | <span data-ttu-id="9d5b2-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="9d5b2-176">ExtensionCustomAttribute3</span></span> |
| <span data-ttu-id="9d5b2-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="9d5b2-177">MSExchExtensionCustomAttribute4</span></span> | <span data-ttu-id="9d5b2-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="9d5b2-178">ExtensionCustomAttribute4</span></span> |
| <span data-ttu-id="9d5b2-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="9d5b2-179">MSExchExtensionCustomAttribute5</span></span> | <span data-ttu-id="9d5b2-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="9d5b2-180">ExtensionCustomAttribute5</span></span> |
| <span data-ttu-id="9d5b2-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="9d5b2-181">MailNickname</span></span> | <span data-ttu-id="9d5b2-182">Alias</span><span class="sxs-lookup"><span data-stu-id="9d5b2-182">Alias</span></span> |
| <span data-ttu-id="9d5b2-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="9d5b2-183">PhysicalDeliveryOfficeName</span></span> | <span data-ttu-id="9d5b2-184">Office</span><span class="sxs-lookup"><span data-stu-id="9d5b2-184">Office</span></span> |
| <span data-ttu-id="9d5b2-185">PostalCode</span><span class="sxs-lookup"><span data-stu-id="9d5b2-185">PostalCode</span></span> | <span data-ttu-id="9d5b2-186">PostalCode</span><span class="sxs-lookup"><span data-stu-id="9d5b2-186">PostalCode</span></span> |
| <span data-ttu-id="9d5b2-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9d5b2-187">ProxyAddresses</span></span> | <span data-ttu-id="9d5b2-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="9d5b2-188">EmailAddresses</span></span> |
| <span data-ttu-id="9d5b2-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="9d5b2-189">StreetAddress</span></span> | <span data-ttu-id="9d5b2-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="9d5b2-190">StreetAddress</span></span> |
| <span data-ttu-id="9d5b2-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="9d5b2-191">TargetAddress</span></span> | <span data-ttu-id="9d5b2-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="9d5b2-192">ExternalEmailAddress</span></span> |
| <span data-ttu-id="9d5b2-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="9d5b2-193">UsageLocation</span></span> | <span data-ttu-id="9d5b2-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="9d5b2-194">UsageLocation</span></span> |
| <span data-ttu-id="9d5b2-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9d5b2-195">UserPrincipalName</span></span> | <span data-ttu-id="9d5b2-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9d5b2-196">UserPrincipalName</span></span> |
| <span data-ttu-id="9d5b2-197">邮件</span><span class="sxs-lookup"><span data-stu-id="9d5b2-197">Mail</span></span> | <span data-ttu-id="9d5b2-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="9d5b2-198">WindowsEmailAddress</span></span> |
| <span data-ttu-id="9d5b2-199">说明</span><span class="sxs-lookup"><span data-stu-id="9d5b2-199">Description</span></span> | <span data-ttu-id="9d5b2-200">说明</span><span class="sxs-lookup"><span data-stu-id="9d5b2-200">Description</span></span> |
| <span data-ttu-id="9d5b2-201">MemberOf</span><span class="sxs-lookup"><span data-stu-id="9d5b2-201">MemberOf</span></span> | <span data-ttu-id="9d5b2-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="9d5b2-202">MemberOfGroup</span></span> |

## <a name="resources"></a><span data-ttu-id="9d5b2-203">资源</span><span class="sxs-lookup"><span data-stu-id="9d5b2-203">Resources</span></span>

- [<span data-ttu-id="9d5b2-204">在 Microsoft Teams 中定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="9d5b2-204">Define policies for information barriers in Microsoft Teams</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="9d5b2-205">信息屏障疑难解答</span><span class="sxs-lookup"><span data-stu-id="9d5b2-205">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
- [<span data-ttu-id="9d5b2-206">信息屏障</span><span class="sxs-lookup"><span data-stu-id="9d5b2-206">Information barriers</span></span>](information-barriers.md)
