---
title: 为实现到 Microsoft 365 的目录同步做好准备
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 介绍如何准备通过使用目录Microsoft 365设置用户，以及使用此方法的长期好处。
ms.openlocfilehash: 7f701bf0a8b165323f7fd61b50b41fb5e18268a6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259555"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="8f566-103">为实现到 Microsoft 365 的目录同步做好准备</span><span class="sxs-lookup"><span data-stu-id="8f566-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="8f566-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="8f566-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8f566-105">混合标识和目录同步的好处包括：</span><span class="sxs-lookup"><span data-stu-id="8f566-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="8f566-106">减少贵组织的管理程序</span><span class="sxs-lookup"><span data-stu-id="8f566-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="8f566-107">（可选）启用单一登录方案</span><span class="sxs-lookup"><span data-stu-id="8f566-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="8f566-108">自动执行帐户中的帐户Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8f566-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="8f566-109">有关使用目录同步的优势详细信息，请参阅 Azure [AD](/azure/active-directory/hybrid/whatis-hybrid-identity) Azure Active Directory (的混合标识) 混合标识[Microsoft 365。](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="8f566-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="8f566-110">但是，目录同步需要规划和准备，以确保 Active Directory 域服务 (AD DS) 与 Microsoft 365 订阅的 Azure AD 租户同步，并且最少出现错误。</span><span class="sxs-lookup"><span data-stu-id="8f566-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="8f566-111">请按照以下步骤操作，以便获得最佳结果。</span><span class="sxs-lookup"><span data-stu-id="8f566-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="8f566-112">1. 目录清理任务</span><span class="sxs-lookup"><span data-stu-id="8f566-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="8f566-113">在将 AD DS 同步到 Azure AD 租户之前，需要清理 AD DS。</span><span class="sxs-lookup"><span data-stu-id="8f566-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f566-114">如果在同步之前不执行 AD DS 清理，则会导致对部署过程产生显著负面影响。</span><span class="sxs-lookup"><span data-stu-id="8f566-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="8f566-115">可能需要几天甚至数周的时间才能完成目录同步、识别错误和重新同步的周期。</span><span class="sxs-lookup"><span data-stu-id="8f566-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="8f566-116">在 AD DS 中，为每个将分配有许可证的用户帐户完成以下Microsoft 365任务：</span><span class="sxs-lookup"><span data-stu-id="8f566-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="8f566-117">确保 **proxyAddresses 属性中具有有效且唯一** 的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8f566-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="8f566-118">删除 **proxyAddresses 属性中任何重复** 的值。</span><span class="sxs-lookup"><span data-stu-id="8f566-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="8f566-119">如果可能，请确保用户用户对象中的 **userPrincipalName** 属性具有有效且 **唯** 一的值。</span><span class="sxs-lookup"><span data-stu-id="8f566-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="8f566-120">为了获得最佳同步体验，请确保 AD DS UPN 与 Azure AD UPN 匹配。</span><span class="sxs-lookup"><span data-stu-id="8f566-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="8f566-121">如果用户没有 **userPrincipalName** 属性的值，则用户对象必须包含 **sAMAccountName** 属性的有效唯一值。 </span><span class="sxs-lookup"><span data-stu-id="8f566-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="8f566-122">删除 **userPrincipalName 属性中任何重复** 的值。</span><span class="sxs-lookup"><span data-stu-id="8f566-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="8f566-123">为了充分利用全局地址列表 (GAL) ，请确保 AD DS 用户帐户的以下属性中的信息正确：</span><span class="sxs-lookup"><span data-stu-id="8f566-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="8f566-124">givenName</span><span class="sxs-lookup"><span data-stu-id="8f566-124">givenName</span></span>
   - <span data-ttu-id="8f566-125">surname</span><span class="sxs-lookup"><span data-stu-id="8f566-125">surname</span></span>
   - <span data-ttu-id="8f566-126">displayName</span><span class="sxs-lookup"><span data-stu-id="8f566-126">displayName</span></span>
   - <span data-ttu-id="8f566-127">职务</span><span class="sxs-lookup"><span data-stu-id="8f566-127">Job Title</span></span>
   - <span data-ttu-id="8f566-128">部门</span><span class="sxs-lookup"><span data-stu-id="8f566-128">Department</span></span>
   - <span data-ttu-id="8f566-129">办公室</span><span class="sxs-lookup"><span data-stu-id="8f566-129">Office</span></span>
   - <span data-ttu-id="8f566-130">办公室电话</span><span class="sxs-lookup"><span data-stu-id="8f566-130">Office Phone</span></span>
   - <span data-ttu-id="8f566-131">移动电话</span><span class="sxs-lookup"><span data-stu-id="8f566-131">Mobile Phone</span></span>
   - <span data-ttu-id="8f566-132">传真号码</span><span class="sxs-lookup"><span data-stu-id="8f566-132">Fax Number</span></span>
   - <span data-ttu-id="8f566-133">街道地址</span><span class="sxs-lookup"><span data-stu-id="8f566-133">Street Address</span></span>
   - <span data-ttu-id="8f566-134">市/县</span><span class="sxs-lookup"><span data-stu-id="8f566-134">City</span></span>
   - <span data-ttu-id="8f566-135">省/自治区/直辖市</span><span class="sxs-lookup"><span data-stu-id="8f566-135">State or Province</span></span>
   - <span data-ttu-id="8f566-136">邮政编码</span><span class="sxs-lookup"><span data-stu-id="8f566-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="8f566-137">国家或地区</span><span class="sxs-lookup"><span data-stu-id="8f566-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="8f566-138">2. 目录对象和属性准备</span><span class="sxs-lookup"><span data-stu-id="8f566-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="8f566-139">AD DS 与 Microsoft 365之间的成功目录同步要求正确准备 AD DS 属性。</span><span class="sxs-lookup"><span data-stu-id="8f566-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="8f566-140">例如，您需要确保特定字符不用于与自定义环境同步的某些Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f566-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="8f566-141">意外字符不会导致目录同步失败，但可能会返回警告。</span><span class="sxs-lookup"><span data-stu-id="8f566-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="8f566-142">无效字符将导致目录同步失败。</span><span class="sxs-lookup"><span data-stu-id="8f566-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="8f566-143">如果某些 AD DS 用户具有一个或多个重复属性，目录同步也将失败。</span><span class="sxs-lookup"><span data-stu-id="8f566-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="8f566-144">每个用户都必须具有唯一的属性。</span><span class="sxs-lookup"><span data-stu-id="8f566-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="8f566-145">下面列出了需要准备的属性：</span><span class="sxs-lookup"><span data-stu-id="8f566-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="8f566-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="8f566-146">**displayName**</span></span>

  - <span data-ttu-id="8f566-147">如果属性存在于 user 对象中，它将与 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f566-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="8f566-148">如果此属性存在于用户对象中，则必须有一个值。</span><span class="sxs-lookup"><span data-stu-id="8f566-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="8f566-149">也就是说，属性不得为空。</span><span class="sxs-lookup"><span data-stu-id="8f566-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="8f566-150">最大字符数：256</span><span class="sxs-lookup"><span data-stu-id="8f566-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="8f566-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="8f566-151">**givenName**</span></span>

  - <span data-ttu-id="8f566-152">如果属性存在于用户对象中，它将与Microsoft 365同步，Microsoft 365不需要也不使用它。</span><span class="sxs-lookup"><span data-stu-id="8f566-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="8f566-153">最大字符数：64</span><span class="sxs-lookup"><span data-stu-id="8f566-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="8f566-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="8f566-154">**mail**</span></span>

  - <span data-ttu-id="8f566-155">属性值在目录中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8f566-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f566-156">如果存在重复值，则同步具有值的第一个用户。</span><span class="sxs-lookup"><span data-stu-id="8f566-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="8f566-157">后续用户将不会显示在Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f566-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="8f566-158">必须修改 AD DS 中的Microsoft 365或修改这两个值，以便两个用户都显示在 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f566-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="8f566-159">**mailNickname** (Exchange别名) </span><span class="sxs-lookup"><span data-stu-id="8f566-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="8f566-160">属性值不能以 (.) 开头。</span><span class="sxs-lookup"><span data-stu-id="8f566-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="8f566-161">属性值在目录中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8f566-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f566-162">同步 ("_") 中的下划线表示此属性的原始值包含无效字符。</span><span class="sxs-lookup"><span data-stu-id="8f566-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="8f566-163">有关此属性详细信息，请参阅Exchange[别名属性](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="8f566-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="8f566-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="8f566-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="8f566-165">多值属性</span><span class="sxs-lookup"><span data-stu-id="8f566-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="8f566-166">每个值的最大字符数：256</span><span class="sxs-lookup"><span data-stu-id="8f566-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="8f566-167">属性值不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="8f566-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="8f566-168">属性值在目录中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8f566-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="8f566-169">无效字符： \< \> ( ) ; ， [ ] "</span><span class="sxs-lookup"><span data-stu-id="8f566-169">Invalid characters: \< \> ( ) ; , [ ] "</span></span>

    <span data-ttu-id="8f566-170">请注意，无效字符适用于类型分隔符和"："后的字符，SMTP:User@contso.com，但不允许 SMTP:user:M@contoso.com 字符。</span><span class="sxs-lookup"><span data-stu-id="8f566-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8f566-171">所有简单邮件传输协议 (SMTP) 地址应符合电子邮件标准。</span><span class="sxs-lookup"><span data-stu-id="8f566-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="8f566-172">删除重复或不需要的地址（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="8f566-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="8f566-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="8f566-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="8f566-174">最大字符数：20</span><span class="sxs-lookup"><span data-stu-id="8f566-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="8f566-175">属性值在目录中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8f566-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="8f566-176">无效字符： [ \ " | ， / ： \< \> + = ; ？</span><span class="sxs-lookup"><span data-stu-id="8f566-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="8f566-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="8f566-177">\* ']</span></span>
  - <span data-ttu-id="8f566-178">如果用户具有无效 **的 sAMAccountName** 属性，但具有有效的 **userPrincipalName** 属性，则用户帐户是在 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f566-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="8f566-179">如果 **sAMAccountName** 和 **userPrincipalName** 均无效，则必须更新 AD DS **userPrincipalName** 属性。</span><span class="sxs-lookup"><span data-stu-id="8f566-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="8f566-180">**sn** (surname) </span><span class="sxs-lookup"><span data-stu-id="8f566-180">**sn** (surname)</span></span>

  - <span data-ttu-id="8f566-181">如果属性存在于用户对象中，它将与Microsoft 365同步，Microsoft 365不需要也不使用它。</span><span class="sxs-lookup"><span data-stu-id="8f566-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="8f566-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="8f566-182">**targetAddress**</span></span>

    <span data-ttu-id="8f566-183">例如 **，targetAddress** 属性必须 (，SMTP:tom@contoso.com) 填充的用户属性必须显示在 Microsoft 365 GAL 中。</span><span class="sxs-lookup"><span data-stu-id="8f566-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="8f566-184">在第三方邮件迁移方案中，这需要Microsoft 365 AD DS 的架构扩展。</span><span class="sxs-lookup"><span data-stu-id="8f566-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="8f566-185">该Microsoft 365架构扩展还将添加其他有用的属性，以管理Microsoft 365 AD DS 中的目录同步工具填充的对象。</span><span class="sxs-lookup"><span data-stu-id="8f566-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="8f566-186">例如，将添加用于管理隐藏邮箱或通讯组的 **msExchHideFromAddressLists** 属性。</span><span class="sxs-lookup"><span data-stu-id="8f566-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="8f566-187">最大字符数：256</span><span class="sxs-lookup"><span data-stu-id="8f566-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="8f566-188">属性值不能包含空格。</span><span class="sxs-lookup"><span data-stu-id="8f566-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="8f566-189">属性值在目录中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8f566-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="8f566-190">无效字符： \ \< \> ( ) ; ， [ ] "</span><span class="sxs-lookup"><span data-stu-id="8f566-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="8f566-191">所有简单邮件传输协议 (SMTP) 地址应符合电子邮件标准。</span><span class="sxs-lookup"><span data-stu-id="8f566-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="8f566-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="8f566-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="8f566-193">**userPrincipalName** 属性必须是 Internet 样式的登录格式，其中用户名后跟 at 符号 (@) 和域名：例如 user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="8f566-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="8f566-194">所有简单邮件传输协议 (SMTP) 地址应符合电子邮件标准。</span><span class="sxs-lookup"><span data-stu-id="8f566-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="8f566-195">**userPrincipalName** 属性的最大字符数为 113。</span><span class="sxs-lookup"><span data-stu-id="8f566-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="8f566-196">at 符号之前和之后允许特定数量的字符 (@) ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f566-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="8f566-197">位于 at 符号前面的用户名的最大字符数 (@) ：64</span><span class="sxs-lookup"><span data-stu-id="8f566-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="8f566-198">@ (@) 符号后面的域名的最大字符数：48</span><span class="sxs-lookup"><span data-stu-id="8f566-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="8f566-199">无效字符： \ % &amp; \* + / = ？</span><span class="sxs-lookup"><span data-stu-id="8f566-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="8f566-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="8f566-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="8f566-201">允许的字符：A – Z、a - z、0 – 9、' 。</span><span class="sxs-lookup"><span data-stu-id="8f566-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="8f566-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="8f566-202">- _ !</span></span> <span data-ttu-id="8f566-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="8f566-203"># ^ ~</span></span>
  - <span data-ttu-id="8f566-204">带音调符号的字母（如 umlauts、accents 和 tildes）是无效字符。</span><span class="sxs-lookup"><span data-stu-id="8f566-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="8f566-205">每个 **userPrincipalName** 值中都需要 @ 字符。</span><span class="sxs-lookup"><span data-stu-id="8f566-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="8f566-206">@ 符在每个 **userPrincipalName** 值中不能作为第一个字符。</span><span class="sxs-lookup"><span data-stu-id="8f566-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="8f566-207">用户名不得以带符号 (.) 、与号 () 、空格或 at 符号 &amp; (@) 。</span><span class="sxs-lookup"><span data-stu-id="8f566-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="8f566-208">用户名不能包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="8f566-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="8f566-209">必须使用可路由域;例如，不能使用本地或内部域。</span><span class="sxs-lookup"><span data-stu-id="8f566-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="8f566-210">Unicode 将转换为下划线字符。</span><span class="sxs-lookup"><span data-stu-id="8f566-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="8f566-211">**userPrincipalName** 不能包含目录中的任何重复值。</span><span class="sxs-lookup"><span data-stu-id="8f566-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="8f566-212">3. 准备 userPrincipalName 属性</span><span class="sxs-lookup"><span data-stu-id="8f566-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="8f566-213">Active Directory 旨在允许贵组织的最终用户使用 **sAMAccountName** 或 **userPrincipalName** 登录目录。</span><span class="sxs-lookup"><span data-stu-id="8f566-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="8f566-214">同样，最终用户可以使用用户主体名称Microsoft 365工作或学校帐户的 UPN (UPN) 登录到网站。</span><span class="sxs-lookup"><span data-stu-id="8f566-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="8f566-215">目录同步尝试使用与 AD DS Azure Active Directory UPN 在目录同步中创建新用户。</span><span class="sxs-lookup"><span data-stu-id="8f566-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="8f566-216">UPN 的格式与电子邮件地址类似。</span><span class="sxs-lookup"><span data-stu-id="8f566-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="8f566-217">在Microsoft 365中，UPN 是用于生成电子邮件地址的默认属性。</span><span class="sxs-lookup"><span data-stu-id="8f566-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="8f566-218">很容易在 AD DS 和 Azure AD (获取 **userPrincipalName** **) ，proxyAddresses** 中的主电子邮件地址将设置为不同的值。</span><span class="sxs-lookup"><span data-stu-id="8f566-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="8f566-219">当它们设置为不同的值时，管理员和最终用户可能会混淆。</span><span class="sxs-lookup"><span data-stu-id="8f566-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="8f566-220">最好对齐这些属性以减少混淆。</span><span class="sxs-lookup"><span data-stu-id="8f566-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="8f566-221">若要满足使用 Active Directory 联合身份验证服务 (AD FS) 2.0 单一登录的要求，您需要确保 Azure Active Directory 中的 UPN 与 AD DS 匹配且正在使用有效的域命名空间。</span><span class="sxs-lookup"><span data-stu-id="8f566-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="8f566-222">4. 向 AD DS 添加备用 UPN 后缀</span><span class="sxs-lookup"><span data-stu-id="8f566-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="8f566-223">您可能需要添加备用 UPN 后缀，以将用户的公司凭据与Microsoft 365关联。</span><span class="sxs-lookup"><span data-stu-id="8f566-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="8f566-224">UPN 后缀是 @ 字符右侧的 UPN 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8f566-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="8f566-225">用于单一登录的 UPN 可能包含字母、数字、句点、短划线和下划线，但不包含任何其他类型的字符。</span><span class="sxs-lookup"><span data-stu-id="8f566-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="8f566-226">若要详细了解如何将备用 UPN 后缀添加到 Active Directory，请参阅准备 [目录同步]( https://go.microsoft.com/fwlink/p/?LinkId=525430)。</span><span class="sxs-lookup"><span data-stu-id="8f566-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="8f566-227">5. 将 AD DS UPN 与 MICROSOFT 365 UPN 匹配</span><span class="sxs-lookup"><span data-stu-id="8f566-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="8f566-228">如果已设置目录同步，则用户的 Microsoft 365 UPN 可能与在 AD DS 中定义的用户的 AD DS UPN 不匹配。</span><span class="sxs-lookup"><span data-stu-id="8f566-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="8f566-229">如果在验证域前已为用户分配了许可证，则可能发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="8f566-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="8f566-230">若要解决此问题，请使用 PowerShell 修复重复[UPN，](https://go.microsoft.com/fwlink/p/?LinkId=396730)以更新用户的 UPN，以确保 Microsoft 365 UPN 与公司用户名和域匹配。</span><span class="sxs-lookup"><span data-stu-id="8f566-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="8f566-231">如果要更新 AD DS 中的 UPN，并且希望它与 Azure Active Directory 标识同步，则需要在 Microsoft 365 中删除用户的许可证，然后在 AD DS 中进行更改。</span><span class="sxs-lookup"><span data-stu-id="8f566-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="8f566-232">另 [请参阅如何准备不可路由的域 (.local domain) 进行目录同步](prepare-a-non-routable-domain-for-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="8f566-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f566-233">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8f566-233">Next steps</span></span>

<span data-ttu-id="8f566-234">如果已完成上述步骤 1 至 5，请参阅 [设置目录同步](set-up-directory-synchronization.md)。</span><span class="sxs-lookup"><span data-stu-id="8f566-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
