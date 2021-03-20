---
title: 在独立 EOP 中管理邮件用户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 了解如何在 Exchange Online Protection (EOP) 管理邮件用户，包括使用目录同步、EAC 和 PowerShell 管理用户。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910614"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="0d933-103">在独立 EOP 中管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d933-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="0d933-104">**Applies to**</span></span>
-  [<span data-ttu-id="0d933-105">独立 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0d933-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="0d933-106">在独立 Exchange Online Protection (EOP) 没有 Exchange Online 邮箱的组织，邮件用户是基本类型的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0d933-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="0d933-107">邮件用户在独立 EOP 组织中具有帐户凭据，并且可以访问 (分配有权限) 。</span><span class="sxs-lookup"><span data-stu-id="0d933-107">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="0d933-108">邮件用户的电子邮件地址是外部 (例如，在本地电子邮件环境中) 。</span><span class="sxs-lookup"><span data-stu-id="0d933-108">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="0d933-109">创建邮件用户时，相应的用户帐户在 Microsoft 365 管理中心可用。</span><span class="sxs-lookup"><span data-stu-id="0d933-109">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0d933-110">在 Microsoft 365 管理中心创建用户帐户时，该帐户不能用于创建邮件用户。</span><span class="sxs-lookup"><span data-stu-id="0d933-110">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="0d933-111">在独立 EOP 中创建和管理邮件用户的推荐方法是使用目录同步，如本文稍后的使用目录同步管理 [邮件](#use-directory-synchronization-to-manage-mail-users) 用户一节中所述。</span><span class="sxs-lookup"><span data-stu-id="0d933-111">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this article.</span></span>

<span data-ttu-id="0d933-112">对于具有少量用户的独立 EOP 组织，您可以在 Exchange 管理中心 (EAC) 或独立 EOP PowerShell 中添加和管理邮件用户，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="0d933-112">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0d933-113">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0d933-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0d933-114">若要打开 Exchange 管理中心 (EAC) ，请参阅独立 [EOP](exchange-admin-center-in-exchange-online-protection-eop.md)中的 Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0d933-114">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0d933-115">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0d933-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0d933-116">在 EOP PowerShell 中创建邮件用户时，可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="0d933-116">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="0d933-117">此外，EOP PowerShell cmdlet 使用批处理方法，该方法在命令结果可见之前导致传播延迟几分钟。</span><span class="sxs-lookup"><span data-stu-id="0d933-117">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="0d933-118">您需在 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="0d933-118">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="0d933-119">具体来说，您需要邮件收件人创建 **(** 创建) 和邮件收件人 **(** 修改) 角色，这些角色默认分配给组织管理 **(** 全局管理员) 和 **收件人** 管理角色组。</span><span class="sxs-lookup"><span data-stu-id="0d933-119">Specifically, you need the **Mail Recipient Creation** (create) and **Mail Recipients** (modify) roles, which are assigned to the **Organization Management** (global admins) and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="0d933-120">有关详细信息，请参阅 [Permissions in standalone EOP](feature-permissions-in-eop.md) 和 [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="0d933-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="0d933-121">有关可能适用于本文中的过程的键盘快捷方式的信息，请参阅[Keyboard shortcuts for the Exchange admin center in Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="0d933-121">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="0d933-122">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="0d933-122">Having problems?</span></span> <span data-ttu-id="0d933-123">在 Exchange 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="0d933-123">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="0d933-124">请访问 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 论坛。</span><span class="sxs-lookup"><span data-stu-id="0d933-124">Visit the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="0d933-125">使用 Exchange 管理中心管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-125">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="0d933-126">使用 EAC 创建邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-126">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="0d933-127">在 EAC 中，转到 **"收件人** \> **""联系人"**</span><span class="sxs-lookup"><span data-stu-id="0d933-127">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="0d933-128">单击 **"新建** ![ "图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="0d933-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="0d933-129">在打开 **的"新建** 邮件用户"页中，配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="0d933-129">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="0d933-130">标有 的 <sup>\*</sup> 设置是必需的。</span><span class="sxs-lookup"><span data-stu-id="0d933-130">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="0d933-131">**名**：使用此框可以键入用户的名。</span><span class="sxs-lookup"><span data-stu-id="0d933-131">**First name**</span></span>

   - <span data-ttu-id="0d933-132">**缩写**：人员中间名首字母。</span><span class="sxs-lookup"><span data-stu-id="0d933-132">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="0d933-133">**姓**：使用此框可以键入用户的姓。</span><span class="sxs-lookup"><span data-stu-id="0d933-133">**Last name**</span></span>

   - <span data-ttu-id="0d933-134"><sup>\*</sup>**显示名称**：默认情况下，此框显示"名字"、**缩写** 和姓氏 **框中** 的值。</span><span class="sxs-lookup"><span data-stu-id="0d933-134"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="0d933-135">可以接受或更改此值。</span><span class="sxs-lookup"><span data-stu-id="0d933-135">You can accept this value or change it.</span></span> <span data-ttu-id="0d933-136">该值应是唯一的，并且最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="0d933-136">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="0d933-137"><sup>\*</sup>**别名**：输入用户的唯一别名（最多使用 64 个字符）</span><span class="sxs-lookup"><span data-stu-id="0d933-137"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="0d933-138">**外部电子邮件地址**：输入用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0d933-138">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="0d933-139">域应在你的基于云的组织外部。</span><span class="sxs-lookup"><span data-stu-id="0d933-139">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="0d933-140"><sup>\*</sup>**用户 ID：** 输入用户将用于登录服务的帐户。</span><span class="sxs-lookup"><span data-stu-id="0d933-140"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="0d933-141">用户 ID 由位于 (@) 符号 (@) 左侧的用户名和右侧域组成。</span><span class="sxs-lookup"><span data-stu-id="0d933-141">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="0d933-142"><sup>\*</sup>**新密码** <sup>\*</sup> **和确认密码**：输入并重新输入帐户密码。</span><span class="sxs-lookup"><span data-stu-id="0d933-142"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="0d933-143">验证密码是否符合组织的密码长度、复杂性和历史记录要求。</span><span class="sxs-lookup"><span data-stu-id="0d933-143">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="0d933-144">完成后，请单击“保存”来创建邮件用户。</span><span class="sxs-lookup"><span data-stu-id="0d933-144">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="0d933-145">使用 EAC 修改邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-145">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="0d933-146">在 EAC 中，转到"**收件人** \> **""联系人"。**</span><span class="sxs-lookup"><span data-stu-id="0d933-146">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="0d933-147">选择要修改的邮件用户，然后单击"编辑 **编辑"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="0d933-147">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="0d933-148">在打开的邮件用户属性页上，单击下列选项卡之一以查看或更改属性。</span><span class="sxs-lookup"><span data-stu-id="0d933-148">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="0d933-149">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0d933-149">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="0d933-150">常规</span><span class="sxs-lookup"><span data-stu-id="0d933-150">General</span></span>

<span data-ttu-id="0d933-151">使用 **"常规** "选项卡可以查看或更改有关邮件用户的基本信息。</span><span class="sxs-lookup"><span data-stu-id="0d933-151">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="0d933-152">**名**</span><span class="sxs-lookup"><span data-stu-id="0d933-152">**First name**</span></span>

- <span data-ttu-id="0d933-153">**缩写**</span><span class="sxs-lookup"><span data-stu-id="0d933-153">**Initials**</span></span>

- <span data-ttu-id="0d933-154">**姓**</span><span class="sxs-lookup"><span data-stu-id="0d933-154">**Last name**</span></span>

- <span data-ttu-id="0d933-155">**显示名称**：此名称出现在组织的通讯簿中、电子邮件的"To："和"From："行以及 EAC 中的联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="0d933-155">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="0d933-156">此姓名不能在显示姓名之前或之后包含空格。</span><span class="sxs-lookup"><span data-stu-id="0d933-156">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="0d933-157">**用户 ID：** 这是 Microsoft 365 中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0d933-157">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="0d933-158">不能在此处修改此值。</span><span class="sxs-lookup"><span data-stu-id="0d933-158">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="0d933-159">联系人信息</span><span class="sxs-lookup"><span data-stu-id="0d933-159">Contact information</span></span>

<span data-ttu-id="0d933-160">使用 **"联系人信息** "选项卡可以查看或更改用户的联系信息。</span><span class="sxs-lookup"><span data-stu-id="0d933-160">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="0d933-161">该页上的信息显示在通讯簿中。</span><span class="sxs-lookup"><span data-stu-id="0d933-161">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="0d933-162">**Street**</span><span class="sxs-lookup"><span data-stu-id="0d933-162">**Street**</span></span>
- <span data-ttu-id="0d933-163">**市/县**</span><span class="sxs-lookup"><span data-stu-id="0d933-163">**City**</span></span>
- <span data-ttu-id="0d933-164">**省/市/自治区**</span><span class="sxs-lookup"><span data-stu-id="0d933-164">**State/Province**</span></span>
- <span data-ttu-id="0d933-165">**邮政编码**</span><span class="sxs-lookup"><span data-stu-id="0d933-165">**ZIP/Postal code**</span></span>
- <span data-ttu-id="0d933-166">**国家/地区**</span><span class="sxs-lookup"><span data-stu-id="0d933-166">**Country/Region**</span></span>
- <span data-ttu-id="0d933-167">**工作电话**</span><span class="sxs-lookup"><span data-stu-id="0d933-167">**Work phone**</span></span>
- <span data-ttu-id="0d933-168">**移动电话**</span><span class="sxs-lookup"><span data-stu-id="0d933-168">**Mobile phone**</span></span>
- <span data-ttu-id="0d933-169">**Fax**</span><span class="sxs-lookup"><span data-stu-id="0d933-169">**Fax**</span></span>
- <span data-ttu-id="0d933-170">**更多选项**</span><span class="sxs-lookup"><span data-stu-id="0d933-170">**More options**</span></span>

  - <span data-ttu-id="0d933-171">**Office**</span><span class="sxs-lookup"><span data-stu-id="0d933-171">**Office**</span></span>
  - <span data-ttu-id="0d933-172">**住宅电话**</span><span class="sxs-lookup"><span data-stu-id="0d933-172">**Home phone**</span></span>
  - <span data-ttu-id="0d933-173">**网页**</span><span class="sxs-lookup"><span data-stu-id="0d933-173">**Web page**</span></span>
  - <span data-ttu-id="0d933-174">**备注**</span><span class="sxs-lookup"><span data-stu-id="0d933-174">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="0d933-175">组织</span><span class="sxs-lookup"><span data-stu-id="0d933-175">Organization</span></span>

<span data-ttu-id="0d933-176">使用 **"** 组织"选项卡可以记录有关组织中用户角色的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0d933-176">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="0d933-177">**Title**</span><span class="sxs-lookup"><span data-stu-id="0d933-177">**Title**</span></span>
- <span data-ttu-id="0d933-178">**Department**</span><span class="sxs-lookup"><span data-stu-id="0d933-178">**Department**</span></span>
- <span data-ttu-id="0d933-179">**Company**</span><span class="sxs-lookup"><span data-stu-id="0d933-179">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="0d933-180">使用 EAC 删除邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-180">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="0d933-181">在 EAC 中，转到"**收件人** \> **""联系人"。**</span><span class="sxs-lookup"><span data-stu-id="0d933-181">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="0d933-182">选择要删除的邮件用户，然后单击"删除 **""删除** ![ "图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="0d933-182">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="0d933-183">使用 PowerShell 管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-183">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="0d933-184">使用独立 EOP PowerShell 查看邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-184">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="0d933-185">若要在独立 EOP PowerShell 中返回所有邮件用户的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0d933-185">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="0d933-186">若要查看有关特定邮件用户的详细信息，请将 替换为邮件用户的名称、别名或帐户名，然后 \<MailUserIdentity\> 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0d933-186">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="0d933-187">有关语法和参数的详细信息，请参阅[Get-Recipient](/powershell/module/exchange/get-recipient)和[Get-User。](/powershell/module/exchange/get-user)</span><span class="sxs-lookup"><span data-stu-id="0d933-187">For detailed syntax and parameter information, see [Get-Recipient](/powershell/module/exchange/get-recipient) and [Get-User](/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="0d933-188">使用独立 EOP PowerShell 创建邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-188">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="0d933-189">若要在独立 EOP PowerShell 中创建邮件用户，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0d933-189">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="0d933-190">**注意**：</span><span class="sxs-lookup"><span data-stu-id="0d933-190">**Notes**:</span></span>

- <span data-ttu-id="0d933-191">_Name_ 参数是必需的，最大长度为 64 个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0d933-191">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="0d933-192">如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。</span><span class="sxs-lookup"><span data-stu-id="0d933-192">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="0d933-193">如果不使用 _Alias_ 参数，则 _MicrosoftOnlineServicesID_ 参数的左侧将用于别名。</span><span class="sxs-lookup"><span data-stu-id="0d933-193">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="0d933-194">如果不使用 _ExternalEmailAddress_ 参数 _，MicrosoftOnlineServicesID_ 值将用于外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0d933-194">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="0d933-195">本示例创建一个具有以下设置的邮件用户：</span><span class="sxs-lookup"><span data-stu-id="0d933-195">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="0d933-196">姓名为 JeffreyZeng，显示名称 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="0d933-196">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="0d933-197">名是 Jeffrey，姓是 Zeng。</span><span class="sxs-lookup"><span data-stu-id="0d933-197">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="0d933-198">别名是 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="0d933-198">The alias is jeffreyz.</span></span>
- <span data-ttu-id="0d933-199">外部电子邮件地址是 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="0d933-199">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="0d933-200">帐户名称 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="0d933-200">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="0d933-201">密码为 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="0d933-201">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="0d933-202">有关语法和参数的详细信息，请参阅 [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="0d933-202">For detailed syntax and parameter information, see [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="0d933-203">使用独立 EOP PowerShell 修改邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-203">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="0d933-204">若要在独立 EOP PowerShell 中修改现有邮件用户，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="0d933-204">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="0d933-205">此示例将设置 Pilar Pinilla 的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0d933-205">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="0d933-206">此示例将所有邮件用户的"公司"属性设置为 Contoso。</span><span class="sxs-lookup"><span data-stu-id="0d933-206">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="0d933-207">有关语法和参数的详细信息，请参阅 [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="0d933-207">For detailed syntax and parameter information, see [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="0d933-208">使用独立 EOP PowerShell 删除邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-208">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="0d933-209">若要在独立 EOP PowerShell 中删除邮件用户，请将 替换为邮件用户的名称、别名或帐户名，然后 \<MailUserIdentity\> 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0d933-209">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="0d933-210">本示例删除 Jeffrey Zeng 的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="0d933-210">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="0d933-211">有关语法和参数的详细信息，请参阅 [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="0d933-211">For detailed syntax and parameter information, see [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0d933-212">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="0d933-212">How do you know these procedures worked?</span></span>

<span data-ttu-id="0d933-213">若要验证您是否已成功在独立 EOP 中创建、修改或删除邮件用户，请使用以下过程之一：</span><span class="sxs-lookup"><span data-stu-id="0d933-213">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="0d933-214">在 EAC 中，转到"**收件人** \> **""联系人"。**</span><span class="sxs-lookup"><span data-stu-id="0d933-214">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="0d933-215">验证邮件用户是否 (列出或未) 。</span><span class="sxs-lookup"><span data-stu-id="0d933-215">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="0d933-216">选择邮件用户，在"详细信息"窗格中查看信息，或单击"编辑 ![ 编辑"图标 ](../../media/ITPro-EAC-AddIcon.png) 查看设置。</span><span class="sxs-lookup"><span data-stu-id="0d933-216">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="0d933-217">在独立 EOP PowerShell 中，运行以下命令验证邮件用户是否 (列出或未) ：</span><span class="sxs-lookup"><span data-stu-id="0d933-217">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="0d933-218">将 替换为邮件用户的名称、别名或帐户名，并运行 \<MailUserIdentity\> 以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="0d933-218">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="0d933-219">使用目录同步管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="0d933-219">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="0d933-220">在独立 EOP 中，目录同步可用于具有本地 Active Directory 的客户。</span><span class="sxs-lookup"><span data-stu-id="0d933-220">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="0d933-221">可以将这些帐户同步到 Azure AD (Azure AD) Azure Active Directory，其中帐户的副本存储在云中。</span><span class="sxs-lookup"><span data-stu-id="0d933-221">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="0d933-222">将现有用户帐户同步到 Azure Active Directory 时，可以在 Exchange 管理中心 (EAC) 或独立 EOP PowerShell 的"收件人"窗格中查看这些用户。</span><span class="sxs-lookup"><span data-stu-id="0d933-222">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="0d933-223">**注意**：</span><span class="sxs-lookup"><span data-stu-id="0d933-223">**Notes**:</span></span>

- <span data-ttu-id="0d933-224">如果使用目录同步管理收件人，仍可以在 Microsoft 365 管理中心中添加和管理用户，但是用户不会与本地 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="0d933-224">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="0d933-225">这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。</span><span class="sxs-lookup"><span data-stu-id="0d933-225">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="0d933-226">建议将目录同步用于以下功能：</span><span class="sxs-lookup"><span data-stu-id="0d933-226">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="0d933-227">**Outlook 安全发件人列表和** 阻止发件人列表：当同步到服务时，这些列表将优先于服务中的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="0d933-227">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="0d933-228">这使用户可以使用单个发件人和域条目管理其自己的安全发件人列表和阻止发件人列表。</span><span class="sxs-lookup"><span data-stu-id="0d933-228">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="0d933-229">有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="0d933-229">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="0d933-230">**基于目录的边缘阻止 (DBEB) ：** 有关 DBEB 有关详细信息，请参阅使用基于目录的边缘阻止拒绝发送给 [无效收件人的邮件](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="0d933-230">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="0d933-231">**最终用户访问隔离**：若要访问其隔离邮件，收件人必须在服务中具有有效的用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="0d933-231">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="0d933-232">有关隔离功能详细信息，请参阅以用户模式查找并 [释放隔离邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="0d933-232">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="0d933-233">邮件流规则 (也称为传输规则 **) ：** 使用目录同步时，现有 Active Directory 用户和组将自动上载到云，然后可以创建面向特定用户和/或组的邮件流规则，而无需手动将它们添加到服务中。</span><span class="sxs-lookup"><span data-stu-id="0d933-233">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="0d933-234">请注意， [动态通讯组](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)无法通过目录同步进行同步。</span><span class="sxs-lookup"><span data-stu-id="0d933-234">Note that [dynamic distribution groups](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="0d933-235">获取必要的权限并准备目录同步，如什么是 Azure Active [Directory 混合标识？](/azure/active-directory/hybrid/whatis-hybrid-identity)中所述。</span><span class="sxs-lookup"><span data-stu-id="0d933-235">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="0d933-236">将目录与 Azure Active Directory Connect (AAD Connect) </span><span class="sxs-lookup"><span data-stu-id="0d933-236">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="0d933-237">激活目录同步，如 [Azure AD Connect sync： Understand and customize synchronization 中所述](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="0d933-237">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="0d933-238">安装和配置本地计算机以运行 AAD Connect，如 [Prerequisites for Azure AD Connect 中所述](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="0d933-238">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="0d933-239">[选择要用于 Azure AD Connect 的安装类型](/azure/active-directory/hybrid/how-to-connect-install-select-installation)：</span><span class="sxs-lookup"><span data-stu-id="0d933-239">[Select which installation type to use for Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="0d933-240">Express</span><span class="sxs-lookup"><span data-stu-id="0d933-240">Express</span></span>](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="0d933-241">自定义</span><span class="sxs-lookup"><span data-stu-id="0d933-241">Custom</span></span>](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="0d933-242">传递身份验证</span><span class="sxs-lookup"><span data-stu-id="0d933-242">Pass-through authentication</span></span>](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="0d933-243">完成 Azure Active Directory 同步工具配置向导后 **，MSOL_AD_SYNC** Active Directory 林中创建帐户。</span><span class="sxs-lookup"><span data-stu-id="0d933-243">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="0d933-244">此帐户用于读取和同步您的本地 Active Directory 信息。</span><span class="sxs-lookup"><span data-stu-id="0d933-244">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="0d933-245">为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="0d933-245">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="0d933-246">配置同步后，请确保验证 AAD Connect 是否正确同步。</span><span class="sxs-lookup"><span data-stu-id="0d933-246">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="0d933-247">在 EAC 中，转到"**收件人**""联系人"，并查看用户列表是否从本地环境 \> 正确同步。</span><span class="sxs-lookup"><span data-stu-id="0d933-247">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>