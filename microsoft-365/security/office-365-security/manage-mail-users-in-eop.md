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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 了解如何在 Exchange Online Protection (EOP) （包括使用目录同步、EAC 和 PowerShell 管理用户）中管理邮件用户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3c3e69def731a85c0dccffdcb5620560dcf00052
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356723"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="474a7-103">在独立 EOP 中管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-103">Manage mail users in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="474a7-104">在独立 Exchange Online Protection (EOP) 不含 Exchange Online 邮箱的组织中，邮件用户是用户帐户的基本类型。</span><span class="sxs-lookup"><span data-stu-id="474a7-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="474a7-105">邮件用户在独立 EOP 组织中具有帐户凭据，并且可以访问) 分配权限的资源 (。</span><span class="sxs-lookup"><span data-stu-id="474a7-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="474a7-106">邮件用户的电子邮件地址是外部 (例如，在本地电子邮件环境) 中。</span><span class="sxs-lookup"><span data-stu-id="474a7-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="474a7-107">当您创建邮件用户时，相应的用户帐户在 Microsoft 365 管理中心中可用。</span><span class="sxs-lookup"><span data-stu-id="474a7-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="474a7-108">在 Microsoft 365 管理中心创建用户帐户时，不能使用该帐户来创建邮件用户。</span><span class="sxs-lookup"><span data-stu-id="474a7-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="474a7-109">在独立 EOP 中创建和管理邮件用户的建议方法是使用目录同步，如本主题后面的 [使用目录同步管理邮件用户](#use-directory-synchronization-to-manage-mail-users) 一节中所述。</span><span class="sxs-lookup"><span data-stu-id="474a7-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="474a7-110">对于具有少量用户的独立 EOP 组织，可以在 Exchange 管理中心 (EAC) 或独立 EOP PowerShell 中添加和管理邮件用户，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="474a7-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="474a7-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="474a7-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="474a7-112">若要打开 Exchange 管理中心 (EAC) ，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="474a7-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="474a7-113">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="474a7-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="474a7-114">当您在 EOP PowerShell 中创建邮件用户时，您可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="474a7-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="474a7-115">此外，EOP PowerShell cmdlet 使用一种批处理方法，该方法会导致几分钟的传播延迟，然后才会显示命令的结果。</span><span class="sxs-lookup"><span data-stu-id="474a7-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="474a7-116">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="474a7-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="474a7-117">具体来说，您需要创建邮件收件人 (创建) 和邮件收件人 (修改) 角色，默认情况下这些角色分配给 OrganizationManagement (全局管理员) 和 RecipientManagement 角色组。</span><span class="sxs-lookup"><span data-stu-id="474a7-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="474a7-118">有关详细信息，请参阅 [独立 EOP 中的权限](feature-permissions-in-eop.md) 和 [使用 EAC 修改角色组中的成员列表](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="474a7-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="474a7-119">有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="474a7-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="474a7-120">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="474a7-120">Having problems?</span></span> <span data-ttu-id="474a7-121">在 Exchange 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="474a7-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="474a7-122">访问 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 论坛。</span><span class="sxs-lookup"><span data-stu-id="474a7-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="474a7-123">使用 Exchange 管理中心管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="474a7-124">使用 EAC 创建邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="474a7-125">在 EAC 中，转到 "**收件人**" " \> **联系人**"</span><span class="sxs-lookup"><span data-stu-id="474a7-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="474a7-126">单击 " **新建** ![ 新图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="474a7-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="474a7-127">在打开的 " **新建邮件用户** " 页上，配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="474a7-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="474a7-128">使用标记为的设置 <sup>\*</sup> 是必需的。</span><span class="sxs-lookup"><span data-stu-id="474a7-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="474a7-129">**名**：使用此框可以键入用户的名。</span><span class="sxs-lookup"><span data-stu-id="474a7-129">**First name**</span></span>

   - <span data-ttu-id="474a7-130">**缩写**：人员的中间名首字母。</span><span class="sxs-lookup"><span data-stu-id="474a7-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="474a7-131">**姓**：使用此框可以键入用户的姓。</span><span class="sxs-lookup"><span data-stu-id="474a7-131">**Last name**</span></span>

   - <span data-ttu-id="474a7-132"><sup>\*</sup>**显示名称**：默认情况下，此框显示 " **名字**"、" **缩写**" 和 " **姓氏** " 框中的值。</span><span class="sxs-lookup"><span data-stu-id="474a7-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="474a7-133">您可以接受此值，也可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="474a7-133">You can accept this value or change it.</span></span> <span data-ttu-id="474a7-134">该值应是唯一的，并且最大长度为64个字符。</span><span class="sxs-lookup"><span data-stu-id="474a7-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="474a7-135"><sup>\*</sup>**别名**：为用户输入一个唯一的别名，最长为64个字符</span><span class="sxs-lookup"><span data-stu-id="474a7-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="474a7-136">**外部电子邮件地址**：输入用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="474a7-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="474a7-137">域应位于基于云的组织外部。</span><span class="sxs-lookup"><span data-stu-id="474a7-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="474a7-138"><sup>\*</sup>**用户 ID**：输入此人将用于登录服务的帐户。</span><span class="sxs-lookup"><span data-stu-id="474a7-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="474a7-139">用户 ID 由位于 ( @ ) 符号 ( @ ) 的左侧的用户名和右侧的域组成。</span><span class="sxs-lookup"><span data-stu-id="474a7-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="474a7-140"><sup>\*</sup>"**新密码**" 和 " <sup>\*</sup> **确认密码**"：输入并重新输入帐户密码。</span><span class="sxs-lookup"><span data-stu-id="474a7-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="474a7-141">验证密码是否符合组织的密码长度、复杂性和历史要求。</span><span class="sxs-lookup"><span data-stu-id="474a7-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="474a7-142">完成后，请单击“保存”来创建邮件用户。</span><span class="sxs-lookup"><span data-stu-id="474a7-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="474a7-143">使用 EAC 修改邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="474a7-144">在 EAC 中，转到 " **收件人**" " \> **联系人**"。</span><span class="sxs-lookup"><span data-stu-id="474a7-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="474a7-145">选择要修改的邮件用户，然后单击 " **编辑** ![ 编辑图标" ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="474a7-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="474a7-146">在打开的 "邮件用户属性" 页上，单击下列选项卡之一以查看或更改属性。</span><span class="sxs-lookup"><span data-stu-id="474a7-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="474a7-147">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="474a7-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="474a7-148">常规</span><span class="sxs-lookup"><span data-stu-id="474a7-148">General</span></span>

<span data-ttu-id="474a7-149">使用 " **常规** " 选项卡可以查看或更改有关邮件用户的基本信息。</span><span class="sxs-lookup"><span data-stu-id="474a7-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="474a7-150">**名**</span><span class="sxs-lookup"><span data-stu-id="474a7-150">**First name**</span></span>

- <span data-ttu-id="474a7-151">**缩写**</span><span class="sxs-lookup"><span data-stu-id="474a7-151">**Initials**</span></span>

- <span data-ttu-id="474a7-152">**姓**</span><span class="sxs-lookup"><span data-stu-id="474a7-152">**Last name**</span></span>

- <span data-ttu-id="474a7-153">**显示名称**：此名称显示在组织的通讯簿中、电子邮件的 "To：" 和 "发件人：" 行和 EAC 中的联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="474a7-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="474a7-154">此姓名不能在显示姓名之前或之后包含空格。</span><span class="sxs-lookup"><span data-stu-id="474a7-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="474a7-155">**用户 ID**：这是 Microsoft 365 中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="474a7-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="474a7-156">您不能在此处修改此值。</span><span class="sxs-lookup"><span data-stu-id="474a7-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="474a7-157">联系人信息</span><span class="sxs-lookup"><span data-stu-id="474a7-157">Contact information</span></span>

<span data-ttu-id="474a7-158">使用 " **联系人信息** " 选项卡查看或更改用户的联系信息。</span><span class="sxs-lookup"><span data-stu-id="474a7-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="474a7-159">该页上的信息显示在通讯簿中。</span><span class="sxs-lookup"><span data-stu-id="474a7-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="474a7-160">**地址**</span><span class="sxs-lookup"><span data-stu-id="474a7-160">**Street**</span></span>
- <span data-ttu-id="474a7-161">**市/县**</span><span class="sxs-lookup"><span data-stu-id="474a7-161">**City**</span></span>
- <span data-ttu-id="474a7-162">**省/市/自治区**</span><span class="sxs-lookup"><span data-stu-id="474a7-162">**State/Province**</span></span>
- <span data-ttu-id="474a7-163">**邮政编码**</span><span class="sxs-lookup"><span data-stu-id="474a7-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="474a7-164">**国家/地区**</span><span class="sxs-lookup"><span data-stu-id="474a7-164">**Country/Region**</span></span>
- <span data-ttu-id="474a7-165">**工作电话**</span><span class="sxs-lookup"><span data-stu-id="474a7-165">**Work phone**</span></span>
- <span data-ttu-id="474a7-166">**移动电话**</span><span class="sxs-lookup"><span data-stu-id="474a7-166">**Mobile phone**</span></span>
- <span data-ttu-id="474a7-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="474a7-167">**Fax**</span></span>
- <span data-ttu-id="474a7-168">**更多选项**</span><span class="sxs-lookup"><span data-stu-id="474a7-168">**More options**</span></span>

  - <span data-ttu-id="474a7-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="474a7-169">**Office**</span></span>
  - <span data-ttu-id="474a7-170">**住宅电话**</span><span class="sxs-lookup"><span data-stu-id="474a7-170">**Home phone**</span></span>
  - <span data-ttu-id="474a7-171">**网页**</span><span class="sxs-lookup"><span data-stu-id="474a7-171">**Web page**</span></span>
  - <span data-ttu-id="474a7-172">**备注**</span><span class="sxs-lookup"><span data-stu-id="474a7-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="474a7-173">组织</span><span class="sxs-lookup"><span data-stu-id="474a7-173">Organization</span></span>

<span data-ttu-id="474a7-174">使用 " **组织** " 选项卡可以记录有关组织中用户角色的详细信息。</span><span class="sxs-lookup"><span data-stu-id="474a7-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="474a7-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="474a7-175">**Title**</span></span>
- <span data-ttu-id="474a7-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="474a7-176">**Department**</span></span>
- <span data-ttu-id="474a7-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="474a7-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="474a7-178">使用 EAC 删除邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="474a7-179">在 EAC 中，转到 " **收件人**" " \> **联系人**"。</span><span class="sxs-lookup"><span data-stu-id="474a7-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="474a7-180">选择要删除的邮件用户，然后单击 " **删除** ![ 删除图标" ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="474a7-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="474a7-181">使用 PowerShell 管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="474a7-182">使用独立 EOP PowerShell 查看邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="474a7-183">若要返回独立 EOP PowerShell 中所有邮件用户的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="474a7-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="474a7-184">若要查看有关特定邮件用户的详细信息，请将 \<MailUserIdentity\> 其替换为邮件用户的名称、别名或帐户名称，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="474a7-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="474a7-185">有关语法和参数的详细信息，请参阅 " [获取-收件人](https://docs.microsoft.com/powershell/module/exchange/get-recipient) " 和 " [获取用户](https://docs.microsoft.com/powershell/module/exchange/get-user)"。</span><span class="sxs-lookup"><span data-stu-id="474a7-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="474a7-186">使用独立的 EOP PowerShell 创建邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="474a7-187">若要在独立 EOP PowerShell 中创建邮件用户，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="474a7-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="474a7-188">**注意**：</span><span class="sxs-lookup"><span data-stu-id="474a7-188">**Notes**:</span></span>

- <span data-ttu-id="474a7-189">_Name_ 参数是必需的，最大长度为64个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="474a7-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="474a7-190">如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。</span><span class="sxs-lookup"><span data-stu-id="474a7-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="474a7-191">如果不使用 _alias_ 参数，则 _MicrosoftOnlineServicesID_ 参数的左侧将用于别名。</span><span class="sxs-lookup"><span data-stu-id="474a7-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="474a7-192">如果不使用 _ExternalEmailAddress_ 参数，则 _MicrosoftOnlineServicesID_ 值将用于外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="474a7-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="474a7-193">本示例将创建具有下列设置的邮件用户：</span><span class="sxs-lookup"><span data-stu-id="474a7-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="474a7-194">名称为 JeffreyZeng，显示名称为 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="474a7-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="474a7-195">名是 Jeffrey，姓是 Zeng。</span><span class="sxs-lookup"><span data-stu-id="474a7-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="474a7-196">别名是 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="474a7-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="474a7-197">外部电子邮件地址是 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="474a7-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="474a7-198">帐户名称为 jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="474a7-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="474a7-199">密码为 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="474a7-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="474a7-200">有关语法和参数的详细信息，请参阅 [new-eopmailuser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="474a7-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="474a7-201">使用独立 EOP PowerShell 修改邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="474a7-202">若要修改独立 EOP PowerShell 中的现有邮件用户，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="474a7-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="474a7-203">此示例将设置 Pilar Pinilla 的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="474a7-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="474a7-204">此示例将所有邮件用户的"公司"属性设置为 Contoso。</span><span class="sxs-lookup"><span data-stu-id="474a7-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="474a7-205">有关语法和参数的详细信息，请参阅 [new-eopmailuser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="474a7-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="474a7-206">使用独立 EOP PowerShell 删除邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="474a7-207">若要删除独立 EOP PowerShell 中的邮件用户，请将 \<MailUserIdentity\> 其替换为邮件用户的名称、别名或帐户名称，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="474a7-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="474a7-208">本示例删除 Jeffrey Zeng 的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="474a7-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="474a7-209">有关语法和参数的详细信息，请参阅 [new-eopmailuser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)。</span><span class="sxs-lookup"><span data-stu-id="474a7-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="474a7-210">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="474a7-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="474a7-211">若要验证您是否已成功创建、修改或删除了独立 EOP 中的邮件用户，请使用以下任一过程：</span><span class="sxs-lookup"><span data-stu-id="474a7-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="474a7-212">在 EAC 中，转到 " **收件人**" " \> **联系人**"。</span><span class="sxs-lookup"><span data-stu-id="474a7-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="474a7-213">验证邮件用户是否列出 (或是否未列出) 。</span><span class="sxs-lookup"><span data-stu-id="474a7-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="474a7-214">选择邮件用户并查看详细信息窗格中的信息，或单击 " **编辑** ![ 编辑图标 ](../../media/ITPro-EAC-AddIcon.png) " 以查看设置。</span><span class="sxs-lookup"><span data-stu-id="474a7-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="474a7-215">在独立 EOP PowerShell 中，运行以下命令来验证邮件用户是否 (列出，或者是否未列出) ：</span><span class="sxs-lookup"><span data-stu-id="474a7-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="474a7-216">将替换 \<MailUserIdentity\> 为邮件用户的名称、别名或帐户名称，然后运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="474a7-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="474a7-217">使用目录同步管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="474a7-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="474a7-218">在独立 EOP 中，目录同步适用于具有本地 Active Directory 的客户。</span><span class="sxs-lookup"><span data-stu-id="474a7-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="474a7-219">你可以将这些帐户同步到 Azure Active Directory (Azure AD) ，其中，帐户副本存储在云中。</span><span class="sxs-lookup"><span data-stu-id="474a7-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="474a7-220">将现有用户帐户同步到 Azure Active Directory 时，可以在 Exchange 管理中心的 " **收件人** " 窗格中 (EAC) 或独立 EOP PowerShell 中查看这些用户。</span><span class="sxs-lookup"><span data-stu-id="474a7-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="474a7-221">**注意**：</span><span class="sxs-lookup"><span data-stu-id="474a7-221">**Notes**:</span></span>

- <span data-ttu-id="474a7-222">如果使用目录同步来管理收件人，您仍可以在 Microsoft 365 管理中心中添加和管理用户，但不会将其与本地 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="474a7-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="474a7-223">这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。</span><span class="sxs-lookup"><span data-stu-id="474a7-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="474a7-224">建议将目录同步用于以下功能：</span><span class="sxs-lookup"><span data-stu-id="474a7-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="474a7-225">**Outlook 安全发件人列表和阻止的发件人列表**：当同步到服务时，这些列表将优先于服务中的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="474a7-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="474a7-226">这使用户可以管理其自己的安全发件人列表和阻止的发件人列表和单个发件人和域条目。</span><span class="sxs-lookup"><span data-stu-id="474a7-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="474a7-227">有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="474a7-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="474a7-228">**基于目录的边缘阻止 (DBEB)**：有关 DBEB 的详细信息，请参阅 [使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="474a7-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="474a7-229">**最终用户对隔离的访问权限**：若要访问其隔离邮件，收件人必须在服务中具有有效的用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="474a7-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="474a7-230">有关隔离的详细信息，请参阅 [以用户的方式查找和释放隔离的邮件](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="474a7-230">For more information about quarantine, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  - <span data-ttu-id="474a7-231">**邮件流规则 (也称为传输规则)**：使用目录同步时，会自动将现有的 Active directory 用户和组上载到云，然后您可以创建针对特定用户和/或组的邮件流规则，而无需手动将其添加到服务中。</span><span class="sxs-lookup"><span data-stu-id="474a7-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="474a7-232">请注意， [动态通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)无法通过目录同步进行同步。</span><span class="sxs-lookup"><span data-stu-id="474a7-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="474a7-233">获取必要的权限并准备目录同步，如 ["使用 Azure Active directory 的混合标识是什么？"](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)中所述。</span><span class="sxs-lookup"><span data-stu-id="474a7-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="474a7-234">将目录与 Azure Active Directory Connect (AAD Connect) 同步</span><span class="sxs-lookup"><span data-stu-id="474a7-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="474a7-235">按照 Azure AD Connect 同步中所述激活目录同步 [：了解和自定义同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="474a7-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="474a7-236">按照 [AZURE AD connect 的先决条件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)中所述，安装和配置内部部署计算机以运行 AAD Connect。</span><span class="sxs-lookup"><span data-stu-id="474a7-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="474a7-237">[选择要用于 AZURE AD Connect 的安装类型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)：</span><span class="sxs-lookup"><span data-stu-id="474a7-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="474a7-238">Express 版</span><span class="sxs-lookup"><span data-stu-id="474a7-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="474a7-239">自定义</span><span class="sxs-lookup"><span data-stu-id="474a7-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="474a7-240">传递身份验证</span><span class="sxs-lookup"><span data-stu-id="474a7-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="474a7-241">当您完成 Azure Active Directory 同步工具配置向导时，将在 Active Directory 林中创建 **MSOL_AD_SYNC** 帐户。</span><span class="sxs-lookup"><span data-stu-id="474a7-241">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="474a7-242">此帐户用于读取和同步您的本地 Active Directory 信息。</span><span class="sxs-lookup"><span data-stu-id="474a7-242">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="474a7-243">为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="474a7-243">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="474a7-244">配置同步之后，请务必验证 AAD 连接是否正确同步。</span><span class="sxs-lookup"><span data-stu-id="474a7-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="474a7-245">在 EAC 中，转到 " **收件人** \> " " **联系人** "，并查看从您的本地环境中正确同步的用户列表。</span><span class="sxs-lookup"><span data-stu-id="474a7-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
