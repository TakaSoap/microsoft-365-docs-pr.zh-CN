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
description: 了解 Exchange Online Protection (EOP) （包括使用目录同步、EAC 和 PowerShell 管理用户）中的邮件用户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827071"
---
# <a name="manage-mail-users-in-standalone-eop"></a><span data-ttu-id="67570-103">在独立 EOP 中管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-103">Manage mail users in standalone EOP</span></span>

<span data-ttu-id="67570-104">在没有 Exchange Online 邮箱 (独立的 Exchange Online Protection) 组织上，邮件用户是用户帐户的基本类型。</span><span class="sxs-lookup"><span data-stu-id="67570-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, mail users are the fundamental type of user account.</span></span> <span data-ttu-id="67570-105">邮件用户在独立 EOP 组织中拥有帐户凭据，并且可访问资源 (分配) 。</span><span class="sxs-lookup"><span data-stu-id="67570-105">A mail user has account credentials in your standalone EOP organization, and can access resources (have permissions assigned).</span></span> <span data-ttu-id="67570-106">邮件用户的电子邮件地址是外部 (例如，在您的内部部署电子邮件环境中) 。</span><span class="sxs-lookup"><span data-stu-id="67570-106">A mail user's email address is external (for example, in your on-premises email environment).</span></span>

> [!NOTE]
> <span data-ttu-id="67570-107">创建邮件用户时，Microsoft 365 管理中心会提供相应的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="67570-107">When you create a mail user, the corresponding user account is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="67570-108">在 Microsoft 365 管理中心创建用户帐户时，无法使用该帐户来创建邮件用户。</span><span class="sxs-lookup"><span data-stu-id="67570-108">When you create a user account in the Microsoft 365 admin center, you can't use that account to create a mail user.</span></span>

<span data-ttu-id="67570-109">建议的在独立 EOP 中创建和管理邮件用户的方法是使用目录同步，如本主题 [后面的"使用目录同步管理邮件用户](#use-directory-synchronization-to-manage-mail-users) "部分所述。</span><span class="sxs-lookup"><span data-stu-id="67570-109">The recommended method to create and manage mail users in standalone EOP is to use directory synchronization as described in the [Use directory synchronization to manage mail users](#use-directory-synchronization-to-manage-mail-users) section later in this topic.</span></span>

<span data-ttu-id="67570-110">对于具有少量用户的独立 EOP 组织，您可以在 Exchange 管理中心 (EAC 或独立 EOP PowerShell 中添加) 和管理邮件用户，如本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="67570-110">For standalone EOP organizations with a small number of users, you can add and manage mail users in the Exchange admin center (EAC) or in standalone EOP PowerShell as described in this topic.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67570-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="67570-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="67570-112">要打开 Exchange 管理中心 (EAC) ，请参阅 [在独立 EOP 中部署 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="67570-112">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="67570-113">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="67570-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="67570-114">当您在 EOP PowerShell 中创建邮件用户时，可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="67570-114">When you create mail users in EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="67570-115">此外，EOP PowerShell cmdlet 还使用批处理方法，在显示命令结果之前，有几分钟的传播延迟。</span><span class="sxs-lookup"><span data-stu-id="67570-115">Also, the EOP PowerShell cmdlets use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="67570-116">必须先分配有权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="67570-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="67570-117">具体而说，需要"邮件收件人创建 (创建) 和 Mail Recipients (修改) 角色，默认情况下这些角色分配给 OrganizationManagement (全局管理员) 和 RecipientManagement 角色组。</span><span class="sxs-lookup"><span data-stu-id="67570-117">Specifically, you need the Mail Recipient Creation (create) and Mail Recipients (modify) roles, which are assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="67570-118">有关详细信息，请参阅独立[EOP 中的"权限](feature-permissions-in-eop.md)["和"使用 EAC 修改角色组中的成员列表"。](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="67570-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="67570-119">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 [Exchange Online 中 Exchange 管理中心的键盘快捷键](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="67570-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="67570-120">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="67570-120">Having problems?</span></span> <span data-ttu-id="67570-121">在 Exchange 论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="67570-121">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="67570-122">访问 [Exchange Online Protection 论](https://go.microsoft.com/fwlink/p/?linkId=285351) 坛。</span><span class="sxs-lookup"><span data-stu-id="67570-122">Visit the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a><span data-ttu-id="67570-123">使用 Exchange 管理中心管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-123">Use the Exchange admin center to manage mail users</span></span>

### <a name="use-the-eac-to-create-mail-users"></a><span data-ttu-id="67570-124">使用 EAC 创建邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-124">Use the EAC to create mail users</span></span>

1. <span data-ttu-id="67570-125">在 EAC 中， **转到收件人** \> **联系人**</span><span class="sxs-lookup"><span data-stu-id="67570-125">In the EAC, go to **Recipients** \> **Contacts**</span></span>

2. <span data-ttu-id="67570-126">单击 **"新建** ![ "图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="67570-126">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="67570-127">在打开 **的"新建** 邮件用户"页中，配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="67570-127">In the **New mail user** page that opens, configure the following settings.</span></span> <span data-ttu-id="67570-128">标记有需要的 <sup>\*</sup> 设置。</span><span class="sxs-lookup"><span data-stu-id="67570-128">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="67570-129">**名**：使用此框可以键入用户的名。</span><span class="sxs-lookup"><span data-stu-id="67570-129">**First name**</span></span>

   - <span data-ttu-id="67570-130">**缩**写：人员的中间名首字母。</span><span class="sxs-lookup"><span data-stu-id="67570-130">**Initials**: The person's middle initial.</span></span>

   - <span data-ttu-id="67570-131">**姓**：使用此框可以键入用户的姓。</span><span class="sxs-lookup"><span data-stu-id="67570-131">**Last name**</span></span>

   - <span data-ttu-id="67570-132"><sup>\*</sup>**显示名称**：默认情况下，此框显示"名字、**缩写\*\*\*\*"和"** 姓氏 **"框中**的值。</span><span class="sxs-lookup"><span data-stu-id="67570-132"><sup>\*</sup>**Display name**: By default, this box shows the values from the **First name**, **Initials**, and **Last name** boxes.</span></span> <span data-ttu-id="67570-133">可以接受此值或更改该值。</span><span class="sxs-lookup"><span data-stu-id="67570-133">You can accept this value or change it.</span></span> <span data-ttu-id="67570-134">该值应唯一，并且最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="67570-134">The value should be unique, and has a maximum length of 64 characters.</span></span>

   - <span data-ttu-id="67570-135"><sup>\*</sup>**别名**：为用户输入唯一别名，最多 64 个字符</span><span class="sxs-lookup"><span data-stu-id="67570-135"><sup>\*</sup>**Alias**: Enter a unique alias, using up to 64 characters, for the user</span></span>

   - <span data-ttu-id="67570-136">**外部电子邮件地址**：输入用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="67570-136">**External email address**: Enter the user's email address.</span></span> <span data-ttu-id="67570-137">该域应位于基于云的组织外部。</span><span class="sxs-lookup"><span data-stu-id="67570-137">The domain should be external to your cloud-based organization.</span></span>

   - <span data-ttu-id="67570-138"><sup>\*</sup>**用户 ID：** 输入用户将用于登录服务的帐户。</span><span class="sxs-lookup"><span data-stu-id="67570-138"><sup>\*</sup>**User ID**: Enter the account that the person will use to sign in to the service.</span></span> <span data-ttu-id="67570-139">用户 ID 由 (@) 符号 (@) 左侧的用户名和右侧的域和右侧的域所包含。</span><span class="sxs-lookup"><span data-stu-id="67570-139">The user ID consists of a username on the left side of the at (@) symbol (@) and a domain on the right side.</span></span>

   - <span data-ttu-id="67570-140"><sup>\*</sup>**新密码**和 <sup>\*</sup> **确认密码**：输入并重新输入帐户密码。</span><span class="sxs-lookup"><span data-stu-id="67570-140"><sup>\*</sup>**New password** and <sup>\*</sup>**Confirm password**: Enter and reenter the account password.</span></span> <span data-ttu-id="67570-141">验证密码是否符合您组织的密码长度、复杂性和历史要求。</span><span class="sxs-lookup"><span data-stu-id="67570-141">Verify that the password complies with the password length, complexity, and history requirements of your organization.</span></span>

3. <span data-ttu-id="67570-142">完成后，请单击“保存”\*\*\*\* 来创建邮件用户。</span><span class="sxs-lookup"><span data-stu-id="67570-142">When you've finished, click **Save** to create the mail user.</span></span>

### <a name="use-the-eac-to-modify-mail-users"></a><span data-ttu-id="67570-143">使用 EAC 修改邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-143">Use the EAC to modify mail users</span></span>

1. <span data-ttu-id="67570-144">在 EAC 中，转到"**收件人联系人** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="67570-144">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="67570-145">选择要修改的邮件用户，然后单击" **编辑"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="67570-145">Select the mail user that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="67570-146">在打开的邮件用户属性页中，单击以下选项卡之一以查看或更改属性。</span><span class="sxs-lookup"><span data-stu-id="67570-146">On the mail user properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="67570-147">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="67570-147">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="67570-148">常规</span><span class="sxs-lookup"><span data-stu-id="67570-148">General</span></span>

<span data-ttu-id="67570-149">使用" **常规** "选项卡可以查看或更改有关邮件用户的基本信息。</span><span class="sxs-lookup"><span data-stu-id="67570-149">Use the **General** tab to view or change basic information about the mail user.</span></span>

- <span data-ttu-id="67570-150">**名**</span><span class="sxs-lookup"><span data-stu-id="67570-150">**First name**</span></span>

- <span data-ttu-id="67570-151">**缩写**</span><span class="sxs-lookup"><span data-stu-id="67570-151">**Initials**</span></span>

- <span data-ttu-id="67570-152">**姓**</span><span class="sxs-lookup"><span data-stu-id="67570-152">**Last name**</span></span>

- <span data-ttu-id="67570-153">**显示名称**：此名称将会出现在组织通讯簿中的"收件人："和"发件人："电子邮件和 EAC 的联系人列表中的行。</span><span class="sxs-lookup"><span data-stu-id="67570-153">**Display name**: This name appears in your organization's address book, on the To: and From: lines in email, and in the list of contacts in the EAC.</span></span> <span data-ttu-id="67570-154">此姓名不能在显示姓名之前或之后包含空格。</span><span class="sxs-lookup"><span data-stu-id="67570-154">This name can't contain empty spaces before or after the display name.</span></span>

- <span data-ttu-id="67570-155">**用户 ID：** 这是 Microsoft 365 中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="67570-155">**User ID**: This is the user's account in Microsoft 365.</span></span> <span data-ttu-id="67570-156">你无法在此处修改该值。</span><span class="sxs-lookup"><span data-stu-id="67570-156">You can't modify this value here.</span></span>

#### <a name="contact-information"></a><span data-ttu-id="67570-157">联系人信息</span><span class="sxs-lookup"><span data-stu-id="67570-157">Contact information</span></span>

<span data-ttu-id="67570-158">使用 **"联系人信息** "选项卡来查看或更改用户联系信息。</span><span class="sxs-lookup"><span data-stu-id="67570-158">Use the **Contact information** tab to view or change the user's contact information.</span></span> <span data-ttu-id="67570-159">该页上的信息显示在通讯簿中。</span><span class="sxs-lookup"><span data-stu-id="67570-159">The information on this page is displayed in the address book.</span></span>

- <span data-ttu-id="67570-160">**Street**</span><span class="sxs-lookup"><span data-stu-id="67570-160">**Street**</span></span>
- <span data-ttu-id="67570-161">**市/县**</span><span class="sxs-lookup"><span data-stu-id="67570-161">**City**</span></span>
- <span data-ttu-id="67570-162">**省/市/自治区**</span><span class="sxs-lookup"><span data-stu-id="67570-162">**State/Province**</span></span>
- <span data-ttu-id="67570-163">**邮政编码**</span><span class="sxs-lookup"><span data-stu-id="67570-163">**ZIP/Postal code**</span></span>
- <span data-ttu-id="67570-164">**国家/地区**</span><span class="sxs-lookup"><span data-stu-id="67570-164">**Country/Region**</span></span>
- <span data-ttu-id="67570-165">**工作电话**</span><span class="sxs-lookup"><span data-stu-id="67570-165">**Work phone**</span></span>
- <span data-ttu-id="67570-166">**移动电话**</span><span class="sxs-lookup"><span data-stu-id="67570-166">**Mobile phone**</span></span>
- <span data-ttu-id="67570-167">**Fax**</span><span class="sxs-lookup"><span data-stu-id="67570-167">**Fax**</span></span>
- <span data-ttu-id="67570-168">**更多选项**</span><span class="sxs-lookup"><span data-stu-id="67570-168">**More options**</span></span>

  - <span data-ttu-id="67570-169">**Office**</span><span class="sxs-lookup"><span data-stu-id="67570-169">**Office**</span></span>
  - <span data-ttu-id="67570-170">**住宅电话**</span><span class="sxs-lookup"><span data-stu-id="67570-170">**Home phone**</span></span>
  - <span data-ttu-id="67570-171">**网页**</span><span class="sxs-lookup"><span data-stu-id="67570-171">**Web page**</span></span>
  - <span data-ttu-id="67570-172">**备注**</span><span class="sxs-lookup"><span data-stu-id="67570-172">**Notes**</span></span>

#### <a name="organization"></a><span data-ttu-id="67570-173">组织</span><span class="sxs-lookup"><span data-stu-id="67570-173">Organization</span></span>

<span data-ttu-id="67570-174">使用 **"** 组织"选项卡可以记录有关组织中用户的角色的详细信息。</span><span class="sxs-lookup"><span data-stu-id="67570-174">Use the **Organization** tab to record detailed information about the user's role in the organization.</span></span>

- <span data-ttu-id="67570-175">**Title**</span><span class="sxs-lookup"><span data-stu-id="67570-175">**Title**</span></span>
- <span data-ttu-id="67570-176">**Department**</span><span class="sxs-lookup"><span data-stu-id="67570-176">**Department**</span></span>
- <span data-ttu-id="67570-177">**Company**</span><span class="sxs-lookup"><span data-stu-id="67570-177">**Company**</span></span>

### <a name="use-the-eac-to-remove-mail-users"></a><span data-ttu-id="67570-178">使用 EAC 删除邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-178">Use the EAC to remove mail users</span></span>

1. <span data-ttu-id="67570-179">在 EAC 中，转到"**收件人联系人** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="67570-179">In the EAC, go to **Recipients** \> **Contacts**.</span></span>

2. <span data-ttu-id="67570-180">选择要删除的邮件用户，然后单击 **"删除"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。</span><span class="sxs-lookup"><span data-stu-id="67570-180">Select the mail user that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-mail-users"></a><span data-ttu-id="67570-181">使用 PowerShell 管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-181">Use PowerShell to manage mail users</span></span>

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a><span data-ttu-id="67570-182">使用独立 EOP PowerShell 查看邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-182">Use standalone EOP PowerShell to view mail users</span></span>

<span data-ttu-id="67570-183">若要返回独立 EOP PowerShell 中所有邮件用户的摘要列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="67570-183">To return a summary list of all mail users in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

<span data-ttu-id="67570-184">若要查看特定邮件用户的详细信息，请 \<MailUserIdentity\> 将其替换为邮件用户的名称、别名或帐户名，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="67570-184">To view detailed information about a specific mail user, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands:</span></span>

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

<span data-ttu-id="67570-185">有关语法和参数的详细信息，请参阅[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient)和[Get-User。](https://docs.microsoft.com/powershell/module/exchange/get-user)</span><span class="sxs-lookup"><span data-stu-id="67570-185">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).</span></span>

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a><span data-ttu-id="67570-186">使用独立 EOP PowerShell 创建邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-186">Use standalone EOP PowerShell to create mail users</span></span>

<span data-ttu-id="67570-187">若要在独立 EOP PowerShell 中创建邮件用户，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="67570-187">To create mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

<span data-ttu-id="67570-188">**注意**：</span><span class="sxs-lookup"><span data-stu-id="67570-188">**Notes**:</span></span>

- <span data-ttu-id="67570-189">_Name 参数_必需，最大长度为 64 个字符，并且必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="67570-189">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="67570-190">如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。</span><span class="sxs-lookup"><span data-stu-id="67570-190">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>
- <span data-ttu-id="67570-191">如果您不使用 Alias 参数 _，_ 则会将 _MicrosoftOnlineServicesID 参数_ 左侧用于别名。</span><span class="sxs-lookup"><span data-stu-id="67570-191">If you don't use the _Alias_ parameter, the left side of the _MicrosoftOnlineServicesID_ parameter is used for the alias.</span></span>
- <span data-ttu-id="67570-192">如果您不使用 _ExternalEmailAddress 参数_ ， _则将 MicrosoftOnlineServicesID_ 值用于外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="67570-192">If you don't use the _ExternalEmailAddress_ parameter, the _MicrosoftOnlineServicesID_ value is used for the external email address.</span></span>

<span data-ttu-id="67570-193">此示例创建具有下列设置的邮件用户：</span><span class="sxs-lookup"><span data-stu-id="67570-193">This example creates a mail user with the following settings:</span></span>

- <span data-ttu-id="67570-194">名为 JeffreyZeng，显示显示名称 Jeffrey Zeng。</span><span class="sxs-lookup"><span data-stu-id="67570-194">The name is JeffreyZeng and the display name is Jeffrey Zeng.</span></span>
- <span data-ttu-id="67570-195">名是 Jeffrey，姓是 Zeng。</span><span class="sxs-lookup"><span data-stu-id="67570-195">The first name is Jeffrey and the last name is Zeng.</span></span>
- <span data-ttu-id="67570-196">别名是 jeffreyz。</span><span class="sxs-lookup"><span data-stu-id="67570-196">The alias is jeffreyz.</span></span>
- <span data-ttu-id="67570-197">外部电子邮件地址是 jzeng@tailspintoys.com。</span><span class="sxs-lookup"><span data-stu-id="67570-197">The external email address is jzeng@tailspintoys.com.</span></span>
- <span data-ttu-id="67570-198">帐户名称为"jeffreyz@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="67570-198">The account name is jeffreyz@contoso.onmicrosoft.com.</span></span>
- <span data-ttu-id="67570-199">密码为 Pa$$word1。</span><span class="sxs-lookup"><span data-stu-id="67570-199">The password is Pa$$word1.</span></span>

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

<span data-ttu-id="67570-200">有关语法和参数的详细信息，请参阅[New-EOPMailUser。](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="67570-200">For detailed syntax and parameter information, see [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a><span data-ttu-id="67570-201">使用独立 EOP PowerShell 修改邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-201">Use standalone EOP PowerShell to modify mail users</span></span>

<span data-ttu-id="67570-202">若要修改独立 EOP PowerShell 中的现有邮件用户，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="67570-202">To modify existing mail users in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

<span data-ttu-id="67570-203">此示例将设置 Pilar Pinilla 的外部电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="67570-203">This example sets the external email address for Pilar Pinilla.</span></span>

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="67570-204">此示例将所有邮件用户的"公司"属性设置为 Contoso。</span><span class="sxs-lookup"><span data-stu-id="67570-204">This example sets the Company property for all mail users to Contoso.</span></span>

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

<span data-ttu-id="67570-205">有关语法和参数的详细信息，请参阅[Set-EOPMailUser。](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="67570-205">For detailed syntax and parameter information, see [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a><span data-ttu-id="67570-206">使用独立 EOP PowerShell 删除邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-206">Use standalone EOP PowerShell to remove mail users</span></span>

<span data-ttu-id="67570-207">若要删除独立 EOP PowerShell 中的邮件用户，请 \<MailUserIdentity\> 替换为邮件用户的名称、别名或帐户名，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="67570-207">To remove mail users in standalone EOP PowerShell, replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following command:</span></span>

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

<span data-ttu-id="67570-208">本示例删除 Jeffrey Zeng 的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="67570-208">This example removes the mail user for Jeffrey Zeng.</span></span>

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

<span data-ttu-id="67570-209">有关语法和参数的详细信息，请参阅[Remove-EOPMailUser。](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)</span><span class="sxs-lookup"><span data-stu-id="67570-209">For detailed syntax and parameter information, see [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="67570-210">如何判断这些过程生效了？</span><span class="sxs-lookup"><span data-stu-id="67570-210">How do you know these procedures worked?</span></span>

<span data-ttu-id="67570-211">若要验证是否已在独立 EOP 中成功创建、修改或删除邮件用户，请使用以下任一过程：</span><span class="sxs-lookup"><span data-stu-id="67570-211">To verify that you've successfully created, modified, or removed mail users in standalone EOP, use any of the following procedures:</span></span>

- <span data-ttu-id="67570-212">在 EAC 中，转到"**收件人联系人** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="67570-212">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="67570-213">验证邮件用户是否在 (或未列出) 。</span><span class="sxs-lookup"><span data-stu-id="67570-213">Verify that the mail user is listed (or isn't listed).</span></span> <span data-ttu-id="67570-214">选择邮件用户并在"详细信息"窗格中查看信息，或单击"编辑 **"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 查看设置。</span><span class="sxs-lookup"><span data-stu-id="67570-214">Select the mail user and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="67570-215">在独立 EOP PowerShell 中，运行以下命令来验证邮件用户是否在未 (邮箱用户或未在) ：</span><span class="sxs-lookup"><span data-stu-id="67570-215">In standalone EOP PowerShell, run the following command to verify the mail user is listed (or isn't listed):</span></span>

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- <span data-ttu-id="67570-216">使用 \<MailUserIdentity\> 邮件用户的名称、别名或帐户名称替代，并运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="67570-216">Replace \<MailUserIdentity\> with the name, alias, or account name of the mail user, and run the following commands to verify the settings:</span></span>

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="67570-217">使用目录同步管理邮件用户</span><span class="sxs-lookup"><span data-stu-id="67570-217">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="67570-218">在独立 EOP 中，目录同步适用于具有本地 Active Directory 的客户。</span><span class="sxs-lookup"><span data-stu-id="67570-218">In standalone EOP, directory synchronization is available for customers with on-premises Active Directory.</span></span> <span data-ttu-id="67570-219">你可以将这些帐户同步到 Azure AD (应用程序中的 Azure Active Directory) ，其中，帐户的副本存储在云中。</span><span class="sxs-lookup"><span data-stu-id="67570-219">You can synchronize those accounts to Azure Active Directory (Azure AD), where copies of the accounts are stored in the cloud.</span></span> <span data-ttu-id="67570-220">将现有用户帐户同步到 Azure Active Directory 后，您可在 Exchange 管理中心 (EAC 网站的 **"收件人** "窗格中或独立 EOP PowerShell) 中查看这些用户。</span><span class="sxs-lookup"><span data-stu-id="67570-220">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC) or in standalone EOP PowerShell.</span></span>

<span data-ttu-id="67570-221">**注意**：</span><span class="sxs-lookup"><span data-stu-id="67570-221">**Notes**:</span></span>

- <span data-ttu-id="67570-222">如果您使用目录同步来管理收件人，则您仍然可以在 Microsoft 365 管理中心中添加和管理用户，但是他们无法与您的本地 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="67570-222">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="67570-223">这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。</span><span class="sxs-lookup"><span data-stu-id="67570-223">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span>

- <span data-ttu-id="67570-224">建议将目录同步用于以下功能：</span><span class="sxs-lookup"><span data-stu-id="67570-224">Using directory synchronization is recommended for use with the following features:</span></span>

  - <span data-ttu-id="67570-225">**Outlook 安全发件人列表和阻止发件人列表**：当同步到服务时，这些列表将优先于服务中的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="67570-225">**Outlook Safe Sender lists and Blocked Sender lists**: When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="67570-226">这允许用户使用单个发件人和域条目管理他们自己的安全发件人列表和阻止发件人列表。</span><span class="sxs-lookup"><span data-stu-id="67570-226">This lets users manage their own Safe Sender list and Blocked Sender list with individual sender and domain entries.</span></span> <span data-ttu-id="67570-227">有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="67570-227">For more information, see [Configure junk email settings on Exchange Online mailboxes](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).</span></span>

  - <span data-ttu-id="67570-228">\*\*基于目录的边缘 (DBEB) ： \*\*有关 DBEB 的详细信息，请参阅 [使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="67570-228">**Directory Based Edge Blocking (DBEB)**: For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

  - <span data-ttu-id="67570-229">**最终用户有权访问隔离**：若要访问隔离邮件，收件人必须在服务中具有有效的用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="67570-229">**End user access to quarantine**: To access their quarantined messages, recipients must have a valid user ID and password in the service.</span></span> <span data-ttu-id="67570-230">有关隔离的详细信息，请参阅以用户 [身份查找并释放隔离邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)。</span><span class="sxs-lookup"><span data-stu-id="67570-230">For more information about quarantine, see [Find and release quarantined messages as a user](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).</span></span>

  - <span data-ttu-id="67570-231">\*\*邮件流规则 (也称为传输规则) ： \*\*使用目录同步时，现有的 Active Directory 用户和组将自动上传到云，而且你可以随后创建面向特定用户和/或组的邮件流规则，无需在服务中手动添加它们。</span><span class="sxs-lookup"><span data-stu-id="67570-231">**Mail flow rules (also known as transport rules)**: When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules that target specific users and/or groups without having to manually add them in the service.</span></span> <span data-ttu-id="67570-232">请注意， [动态通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)无法通过目录同步进行同步。</span><span class="sxs-lookup"><span data-stu-id="67570-232">Note that [dynamic distribution groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) can't be synchronized via directory synchronization.</span></span>

<span data-ttu-id="67570-233">按 Azure Active Directory 混合标识的混合标识中所述，获取所需权限 [，并准备进行目录同步](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。</span><span class="sxs-lookup"><span data-stu-id="67570-233">Get the necessary permissions and prepare for directory synchronization, as described in [What is hybrid identity with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).</span></span>

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a><span data-ttu-id="67570-234">使用 Azure Active Directory Connect (AAD Connect 同步) </span><span class="sxs-lookup"><span data-stu-id="67570-234">Synchronize directories with Azure Active Directory Connect (AAD Connect)</span></span>

1. <span data-ttu-id="67570-235">按 Azure AD Connect 同步中所述 [激活目录同步：了解和自定义同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。</span><span class="sxs-lookup"><span data-stu-id="67570-235">Activate directory synchronization as described in [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

2. <span data-ttu-id="67570-236">安装和配置本地计算机以运行 AAD Connect，如 Azure AD Connect 系统必 [备中的所述](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="67570-236">Install and configure an on-premises computer to run AAD Connect as described in [Prerequisites for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span></span>

3. <span data-ttu-id="67570-237">[选择要用于 Azure AD Connect 的安装类型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)：</span><span class="sxs-lookup"><span data-stu-id="67570-237">[Select which installation type to use for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):</span></span>

   - [<span data-ttu-id="67570-238">Express</span><span class="sxs-lookup"><span data-stu-id="67570-238">Express</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [<span data-ttu-id="67570-239">自定义</span><span class="sxs-lookup"><span data-stu-id="67570-239">Custom</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [<span data-ttu-id="67570-240">传递身份验证</span><span class="sxs-lookup"><span data-stu-id="67570-240">Pass-through authentication</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> <span data-ttu-id="67570-241">完成 Azure Active Directory 同步工具配置向导后 **，MSOL_AD_SYNC** Active Directory 林中创建成员帐户。</span><span class="sxs-lookup"><span data-stu-id="67570-241">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest.</span></span> <span data-ttu-id="67570-242">此帐户用于读取和同步您的本地 Active Directory 信息。</span><span class="sxs-lookup"><span data-stu-id="67570-242">This account is used to read and synchronize your on-premises Active Directory information.</span></span> <span data-ttu-id="67570-243">为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="67570-243">In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span>

<span data-ttu-id="67570-244">配置同步后，请务必验证 AAD Connect 是否已正确同步。</span><span class="sxs-lookup"><span data-stu-id="67570-244">After configuring your sync, be sure to verify that AAD Connect is synchronizing correctly.</span></span> <span data-ttu-id="67570-245">在 EAC 中， **转到** \> **"收件人** 联系人"并查看用户列表是否已从本地环境中正确同步。</span><span class="sxs-lookup"><span data-stu-id="67570-245">In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span>
