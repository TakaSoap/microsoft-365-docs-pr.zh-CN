---
title: 使用 PowerShell Microsoft 365组
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BSA160
- BCS160
ms.assetid: aeb669aa-1770-4537-9de2-a82ac11b0540
description: 本文将了解如何在 PowerShell 中为 Microsoft 365组执行常见管理任务。
ms.openlocfilehash: adf796ad2f2ee7a304c578cd42c700f2b44e7a5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911046"
---
# <a name="manage-microsoft-365-groups-with-powershell"></a><span data-ttu-id="a7331-103">使用 PowerShell Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="a7331-103">Manage Microsoft 365 Groups with PowerShell</span></span>

<span data-ttu-id="a7331-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="a7331-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a7331-105">本文提供了在 Microsoft PowerShell 中为组执行常见管理任务的步骤。</span><span class="sxs-lookup"><span data-stu-id="a7331-105">This article provides the steps for doing common management tasks for Groups in Microsoft PowerShell.</span></span> <span data-ttu-id="a7331-106">它还列出了组的 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a7331-106">It also lists the PowerShell cmdlets for Groups.</span></span> <span data-ttu-id="a7331-107">有关管理网站SharePoint，请参阅[使用 PowerShell SharePoint Online 网站](/sharepoint/manage-team-and-communication-sites-in-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a7331-107">For info about managing SharePoint sites, see [Manage SharePoint Online sites using PowerShell](/sharepoint/manage-team-and-communication-sites-in-powershell).</span></span>

## <a name="link-to-your-microsoft-365-groups-usage-guidelines"></a><span data-ttu-id="a7331-108">链接到你的Microsoft 365组使用准则</span><span class="sxs-lookup"><span data-stu-id="a7331-108">Link to your Microsoft 365 Groups usage guidelines</span></span>
<span data-ttu-id="a7331-109"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="a7331-109"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="a7331-110">当用户[在组织中创建或编辑Outlook，](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx)您可以向用户显示指向组织使用准则的链接。</span><span class="sxs-lookup"><span data-stu-id="a7331-110">When users [create or edit a group in Outlook](https://support.office.com/article/04d0c9cf-6864-423c-a380-4fa858f27102.aspx), you can show them a link to your organization's usage guidelines.</span></span> <span data-ttu-id="a7331-111">例如，如果需要将特定前缀或后缀添加到组名称中。</span><span class="sxs-lookup"><span data-stu-id="a7331-111">For example, if you require a specific prefix or suffix to be added to a group name.</span></span>

<span data-ttu-id="a7331-112">使用 Azure Active Directory (Azure AD) PowerShell 将用户指向组织针对组Microsoft 365准则。</span><span class="sxs-lookup"><span data-stu-id="a7331-112">Use the Azure Active Directory (Azure AD) PowerShell to point your users to your organization's usage guidelines for Microsoft 365 groups.</span></span> <span data-ttu-id="a7331-113">请查看[Azure Active Directory组设置的 cmdlet，](/azure/active-directory/enterprise-users/groups-settings-cmdlets)并按照在目录级别创建设置中的步骤定义使用指南超链接。</span><span class="sxs-lookup"><span data-stu-id="a7331-113">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/enterprise-users/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the usage guideline hyperlink.</span></span> <span data-ttu-id="a7331-114">运行 AAD cmdlet 后，用户将在用户创建或编辑 Outlook 中的组时看到指向你的Outlook。</span><span class="sxs-lookup"><span data-stu-id="a7331-114">Once you run the AAD cmdlet, user's will see the link to your guidelines when they create or edit a group in Outlook.</span></span>

![使用使用指南链接创建新组](../media/3f74463f-3448-4f24-a0ec-086d9aa95caa.png)

![单击"组使用指南"查看组织Office 365组指南](../media/d0d54ace-f0ec-4946-b2de-50ce23f17765.png)

## <a name="allow-users-to-send-as-the-microsoft-365-group"></a><span data-ttu-id="a7331-117">允许用户作为组Microsoft 365发送</span><span class="sxs-lookup"><span data-stu-id="a7331-117">Allow users to Send as the Microsoft 365 Group</span></span>
<span data-ttu-id="a7331-118"><a name="BK_LinkToGuideLines"> </a></span><span class="sxs-lookup"><span data-stu-id="a7331-118"><a name="BK_LinkToGuideLines"> </a></span></span>

<span data-ttu-id="a7331-119">如果要使组组Microsoft 365"发送方式"，请使用[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)和[Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="a7331-119">If you want to enable your Microsoft 365 groups to "Send As", use the [Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission) and [Get-RecipientPermission](/powershell/module/exchange/get-recipientpermission) cmdlets to configure this.</span></span> <span data-ttu-id="a7331-120">启用此设置后，Microsoft 365组用户就可以使用 Outlook 或 Outlook web 以组用户Microsoft 365和回复电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a7331-120">Once you enable this setting, Microsoft 365 group users can use Outlook or Outlook on the web to send and reply to email as the Microsoft 365 group.</span></span> <span data-ttu-id="a7331-121">用户可以转到组、创建新电子邮件，并将"发送为"字段更改为组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a7331-121">Users can go to the group, create a new email, and change the "Send As" field to the group's email address.</span></span>

<span data-ttu-id="a7331-122"> ([您还可以在管理中心 Exchange .) ](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group)</span><span class="sxs-lookup"><span data-stu-id="a7331-122">([You can also do this in the Exchange Admin Center](/office365/admin/create-groups/allow-members-to-send-as-or-send-on-behalf-of-group).)</span></span>

<span data-ttu-id="a7331-123">使用以下脚本，将 替换为要更新的组的别名以及要授予权限的用户 *\<GroupAlias\>* *\<UserAlias\>* 的别名。</span><span class="sxs-lookup"><span data-stu-id="a7331-123">Use the following script, replacing *\<GroupAlias\>* with the alias of the group that you want to update, and *\<UserAlias\>* with the alias of the user to whom you want to grant permissions.</span></span> <span data-ttu-id="a7331-124">[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="a7331-124">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to run this script.</span></span>

```PowerShell
$groupAlias = "<GroupAlias>"
$userAlias = "<UserAlias>"
$groupsRecipientDetails = Get-Recipient -RecipientTypeDetails groupmailbox -Identity $groupAlias

Add-RecipientPermission -Identity $groupsRecipientDetails.Name -Trustee $userAlias -AccessRights SendAs
```

<span data-ttu-id="a7331-125">执行 cmdlet 后，用户可以通过将组电子邮件地址添加到"发送Outlook或Outlook Web 上转到组以作为 **组发送。**</span><span class="sxs-lookup"><span data-stu-id="a7331-125">Once the cmdlet is executed, users can go to Outlook or Outlook on the web to send as the group, by adding the group email address to the **From** field.</span></span>

## <a name="create-classifications-for-microsoft-365-groups-in-your-organization"></a><span data-ttu-id="a7331-126">为贵Microsoft 365组创建分类</span><span class="sxs-lookup"><span data-stu-id="a7331-126">Create classifications for Microsoft 365 Groups in your organization</span></span>

<span data-ttu-id="a7331-127">可以创建组织中用户在创建组时设置的敏感度Microsoft 365标签。</span><span class="sxs-lookup"><span data-stu-id="a7331-127">You can create sensitivity labels that the users in your organization can set when they create a Microsoft 365 Group.</span></span> <span data-ttu-id="a7331-128">如果要对组进行分类，我们建议使用敏感度标签，而不是以前的组分类功能。</span><span class="sxs-lookup"><span data-stu-id="a7331-128">If you want to classify groups, we recommend using sensitivity labels instead of the previous groups classification feature.</span></span> <span data-ttu-id="a7331-129">有关使用敏感度标签的信息，请参阅使用敏感度标签来保护网站Microsoft Teams、Microsoft 365[组SharePoint内容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="a7331-129">For information about using sensitivity labels, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7331-130">如果当前正在使用分类标签，则启用敏感度标签后，创建组的用户将不再可以使用分类标签。</span><span class="sxs-lookup"><span data-stu-id="a7331-130">If you are currently using classification labels, they will no longer be available to users who create groups once sensitivity labels are enabled.</span></span>

<span data-ttu-id="a7331-131">您仍可以使用以前的组分类功能。</span><span class="sxs-lookup"><span data-stu-id="a7331-131">You can still use the previous groups classification feature.</span></span> <span data-ttu-id="a7331-132">可以创建组织中用户在创建组组时可设置的Microsoft 365分类。</span><span class="sxs-lookup"><span data-stu-id="a7331-132">You can create classifications that the users in your organization can set when they create an Microsoft 365 Group.</span></span> <span data-ttu-id="a7331-133">例如，可以允许用户在创建的组上设置"标准"、"机密"和"顶级密码"。</span><span class="sxs-lookup"><span data-stu-id="a7331-133">For example, you can allow users to set "Standard", "Secret", and "Top Secret" on groups they create.</span></span> <span data-ttu-id="a7331-134">默认情况下不会设置组分类，你需要创建它，以便用户进行设置。</span><span class="sxs-lookup"><span data-stu-id="a7331-134">Group classifications aren't set by default and you need to create it in order for your users to set it.</span></span> <span data-ttu-id="a7331-135">使用 Azure Active Directory PowerShell 将用户指向组织针对组Microsoft 365准则。</span><span class="sxs-lookup"><span data-stu-id="a7331-135">Use Azure Active Directory PowerShell to point your users to your organization's usage guidelines for Microsoft 365 Groups.</span></span>

<span data-ttu-id="a7331-136">请查看[Azure Active Directory组设置的 cmdlet，](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)并按照在目录级别创建设置中的步骤定义组Microsoft 365分类。</span><span class="sxs-lookup"><span data-stu-id="a7331-136">Check out [Azure Active Directory cmdlets for configuring group settings](/azure/active-directory/users-groups-roles/groups-settings-cmdlets) and follow the steps in the **Create settings at the directory level** to define the classification for Microsoft 365 Groups.</span></span>

```powershell
$setting["ClassificationList"] = "Low Impact, Medium Impact, High Impact"
```

<span data-ttu-id="a7331-137">若要将说明与每个分类关联，可以使用 settings 属性  *ClassificationDescriptions* 进行定义。</span><span class="sxs-lookup"><span data-stu-id="a7331-137">In order to associate a description to each classification you can use the settings attribute  *ClassificationDescriptions* to define.</span></span>

```powershell
$setting["ClassificationDescriptions"] ="Classification:Description,Classification:Description"
```

<span data-ttu-id="a7331-138">其中 Classification 与 ClassificationList 中的字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="a7331-138">where Classification matches the strings in the ClassificationList.</span></span>

<span data-ttu-id="a7331-139">示例：</span><span class="sxs-lookup"><span data-stu-id="a7331-139">Example:</span></span>

```powershell
$setting["ClassificationDescriptions"] = "Low Impact: General communication, Medium Impact: Company internal data , High Impact: Data that has regulatory requirements"
```

<span data-ttu-id="a7331-140">在运行上述 Azure Active Directory cmdlet 设置分类后，如果要为特定组设置分类，请运行[Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a7331-140">After you run the above Azure Active Directory cmdlet to set your classification, run the [Set-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet if you want to set the classification for a specific group.</span></span>

```powershell
Set-UnifiedGroup <LowImpactGroup@constoso.com> -Classification <LowImpact>
```

<span data-ttu-id="a7331-141">或者创建一个分类的新组。</span><span class="sxs-lookup"><span data-stu-id="a7331-141">Or create a new group with a classification.</span></span>

```powershell
New-UnifiedGroup <HighImpactGroup@constoso.com> -Classification <HighImpact> -AccessType <Public>
```

<span data-ttu-id="a7331-142">请参阅将[PowerShell](/powershell/exchange/exchange-online-powershell)与 Exchange Online 一连接 Exchange Online [PowerShell，](/powershell/exchange/connect-to-exchange-online-powershell)详细了解如何Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a7331-142">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for more details on using Exchange Online PowerShell.</span></span>

<span data-ttu-id="a7331-143">启用这些设置后，组所有者将能够从 Outlook 网页版和 Outlook 中的下拉菜单中选择分类，然后从"编辑组 **"页保存** 它。</span><span class="sxs-lookup"><span data-stu-id="a7331-143">Once these settings are enabled, the group owner will be able to choose a classification from the drop down menu in Outlook on the Web and Outlook, and save it from the **Edit** group page.</span></span>

![选择Microsoft 365组分类](../media/f8d4219a-6180-491d-b0e1-4313ac83998b.png)

## <a name="hide-microsoft-365-groups-from-the-global-address-list"></a><span data-ttu-id="a7331-145">从Microsoft 365地址列表中隐藏组。</span><span class="sxs-lookup"><span data-stu-id="a7331-145">Hide Microsoft 365 Groups from the global address list.</span></span>
<span data-ttu-id="a7331-146"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a7331-146"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a7331-147">可以指定组是否Microsoft 365 GAL 地址列表 (GAL) 组织的其他列表中显示。</span><span class="sxs-lookup"><span data-stu-id="a7331-147">You can specify whether a Microsoft 365 Group appears in the global address list (GAL) and other lists in your organization.</span></span> <span data-ttu-id="a7331-148">例如，如果您具有不希望在地址列表中显示的法律部门组，您可以阻止该组显示在 GAL 中。</span><span class="sxs-lookup"><span data-stu-id="a7331-148">For example, if you have a legal department group that you don't want to show up in the address list, you can stop that group from appearing in the GAL.</span></span> <span data-ttu-id="a7331-149">运行 Set-Unified Group cmdlet，将组从地址列表中隐藏，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a7331-149">Run the Set-Unified Group cmdlet to hide the group from the address list like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Legal Department" -HiddenFromAddressListsEnabled $true
```

## <a name="allow-only-internal-users-to-send-message-to-microsoft-365-groups"></a><span data-ttu-id="a7331-150">仅允许内部用户向组Microsoft 365邮件</span><span class="sxs-lookup"><span data-stu-id="a7331-150">Allow only internal users to send message to Microsoft 365 Groups</span></span>
<span data-ttu-id="a7331-151"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a7331-151"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a7331-152">如果您不希望其他组织的用户向组组Microsoft 365，您可以更改该组的设置。</span><span class="sxs-lookup"><span data-stu-id="a7331-152">If you don't want users from other organizations to send emails to a Microsoft 365 Group, you can change the settings for that group.</span></span> <span data-ttu-id="a7331-153">它将仅允许内部用户向你的组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a7331-153">It will allow only internal users to send an email to your group.</span></span> <span data-ttu-id="a7331-154">如果外部用户尝试向该组发送邮件，邮件将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="a7331-154">If an external user tries to send a message to that group, it will be rejected.</span></span>

<span data-ttu-id="a7331-155">运行 Set-UnifiedGroup cmdlet 以更新此设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a7331-155">Run the Set-UnifiedGroup cmdlet to update this setting, like this:</span></span>

```powershell
Set-UnifiedGroup -Identity "Internal senders only" -RequireSenderAuthenticationEnabled $true
```

## <a name="add-mailtips-to-microsoft-365-groups"></a><span data-ttu-id="a7331-156">将邮件提示添加到Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="a7331-156">Add MailTips to Microsoft 365 Groups</span></span>
<span data-ttu-id="a7331-157"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a7331-157"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a7331-158">每当发件人尝试向 Microsoft 365 发送电子邮件时，都会向用户显示邮件提示。</span><span class="sxs-lookup"><span data-stu-id="a7331-158">Whenever a sender tries to send an email to a Microsoft 365 Group, a MailTip can be shown to them.</span></span>

<span data-ttu-id="a7331-159">运行 Set-Unified 组 cmdlet 将邮件提示添加到组：</span><span class="sxs-lookup"><span data-stu-id="a7331-159">Run the Set-Unified Group cmdlet to add a mailTip to the group:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailTip Group" -MailTip "This group has a MailTip"
```

<span data-ttu-id="a7331-160">除了邮件提示，还可以设置 MailTipTranslations，它指定邮件提示的其他语言。</span><span class="sxs-lookup"><span data-stu-id="a7331-160">Along with MailTip, you can also set MailTipTranslations, which specifies additional languages for the MailTip.</span></span> <span data-ttu-id="a7331-161">假设你想要使用西班牙语翻译，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a7331-161">Suppose you want to have the Spanish translation, then run the following command:</span></span>

```powershell
Set-UnifiedGroup -Identity "MailaTip Group" -MailTip "This group has a MailTip" -MailTipTranslations "@{Add="ES:Esta caja no se supervisa."
```

## <a name="change-the-display-name-of-the-microsoft-365-group"></a><span data-ttu-id="a7331-162">更改显示名称组Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7331-162">Change the display name of the Microsoft 365 Group</span></span>

<span data-ttu-id="a7331-163">the 显示名称 specifies the name of the Microsoft 365 Group.</span><span class="sxs-lookup"><span data-stu-id="a7331-163">The display name specifies the name of the Microsoft 365 Group.</span></span> <span data-ttu-id="a7331-164">您可以在 Exchange 管理中心或管理中心Microsoft 365此名称。</span><span class="sxs-lookup"><span data-stu-id="a7331-164">You can see this name in your exchange admin center or Microsoft 365 admin center.</span></span> <span data-ttu-id="a7331-165">可以通过运行 显示名称 命令，编辑显示名称组或显示名称组Microsoft 365组Set-UnifiedGroup组：</span><span class="sxs-lookup"><span data-stu-id="a7331-165">You can edit the display name of the group or assign a display name to an existing Microsoft 365 Group by running the Set-UnifiedGroup command:</span></span>

```powershell
Set-UnifiedGroup -Identity "mygroup@contoso.com" -DisplayName "My new group"
```

## <a name="change-the-default-setting-of-microsoft-365-groups-for-outlook-to-public-or-private"></a><span data-ttu-id="a7331-166">将组的默认Microsoft 365更改为Outlook"或"专用"</span><span class="sxs-lookup"><span data-stu-id="a7331-166">Change the default setting of Microsoft 365 Groups for Outlook to Public or Private</span></span>
<span data-ttu-id="a7331-167"><a name="BKMK_CreateClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a7331-167"><a name="BKMK_CreateClassification"> </a></span></span>

<span data-ttu-id="a7331-168">Microsoft 365默认情况下，Outlook中的组创建为专用组。</span><span class="sxs-lookup"><span data-stu-id="a7331-168">Microsoft 365 Groups in Outlook are created as Private by default.</span></span> <span data-ttu-id="a7331-169">如果组织希望Microsoft 365组默认创建为公用组或 (私有) ，请使用以下 PowerShell cmdlet 语法：</span><span class="sxs-lookup"><span data-stu-id="a7331-169">If your organization wants Microsoft 365 Groups to be created as Public by default (or back to Private), use this PowerShell cmdlet syntax:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Public`

<span data-ttu-id="a7331-170">若要设置为专用：</span><span class="sxs-lookup"><span data-stu-id="a7331-170">To set to Private:</span></span>

 `Set-OrganizationConfig -DefaultGroupAccessType Private`

<span data-ttu-id="a7331-171">验证设置：</span><span class="sxs-lookup"><span data-stu-id="a7331-171">To verify the setting:</span></span>

 `Get-OrganizationConfig | ft DefaultGroupAccessType`

<span data-ttu-id="a7331-172">若要了解更多信息，请参阅[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)和[Get-OrganizationConfig。](/powershell/module/exchange/get-organizationconfig)</span><span class="sxs-lookup"><span data-stu-id="a7331-172">To learn more, see [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) and [Get-OrganizationConfig](/powershell/module/exchange/get-organizationconfig).</span></span>

## <a name="microsoft-365-groups-cmdlets"></a><span data-ttu-id="a7331-173">Microsoft 365组 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a7331-173">Microsoft 365 Groups cmdlets</span></span>

<span data-ttu-id="a7331-174">以下 cmdlet 可用于组Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="a7331-174">The following cmdlets can be used with Microsoft 365 Groups.</span></span>

|<span data-ttu-id="a7331-175">**Cmdlet 名称**</span><span class="sxs-lookup"><span data-stu-id="a7331-175">**Cmdlet name**</span></span>|<span data-ttu-id="a7331-176">**说明**</span><span class="sxs-lookup"><span data-stu-id="a7331-176">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a7331-177">Get-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a7331-177">Get-UnifiedGroup</span></span>](/powershell/module/exchange/get-unifiedgroup) <br/> |<span data-ttu-id="a7331-178">使用此 cmdlet 查找现有Microsoft 365组，并查看组对象的属性</span><span class="sxs-lookup"><span data-stu-id="a7331-178">Use this cmdlet to look up existing Microsoft 365 Groups, and to view properties of the group object</span></span>  <br/> |
|[<span data-ttu-id="a7331-179">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a7331-179">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup) <br/> |<span data-ttu-id="a7331-180">更新特定组Microsoft 365属性</span><span class="sxs-lookup"><span data-stu-id="a7331-180">Update the properties of a specific Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a7331-181">New-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a7331-181">New-UnifiedGroup</span></span>](/powershell/module/exchange/new-unifiedgroup) <br/> |<span data-ttu-id="a7331-182">创建新的组Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="a7331-182">Create a new Microsoft 365 Group.</span></span> <span data-ttu-id="a7331-183">此 cmdlet 提供最少的一组参数。</span><span class="sxs-lookup"><span data-stu-id="a7331-183">This cmdlet provides a minimal set of parameters.</span></span> <span data-ttu-id="a7331-184">若要设置扩展属性的值，请使用Set-UnifiedGroup组后使用</span><span class="sxs-lookup"><span data-stu-id="a7331-184">To set values for extended properties, use Set-UnifiedGroup after creating the new group</span></span>  <br/> |
|[<span data-ttu-id="a7331-185">Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="a7331-185">Remove-UnifiedGroup</span></span>](/powershell/module/exchange/remove-unifiedgroup) <br/> |<span data-ttu-id="a7331-186">删除现有 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="a7331-186">Delete an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a7331-187">Get-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="a7331-187">Get-UnifiedGroupLinks</span></span>](/powershell/module/exchange/get-unifiedgrouplinks) <br/> |<span data-ttu-id="a7331-188">检索组成员身份和所有者Microsoft 365信息</span><span class="sxs-lookup"><span data-stu-id="a7331-188">Retrieve membership and owner information for a Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a7331-189">Add-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="a7331-189">Add-UnifiedGroupLinks</span></span>](/powershell/module/exchange/add-unifiedgrouplinks) <br/> |<span data-ttu-id="a7331-190">将成员、所有者和订阅者添加到现有 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="a7331-190">Add members, owners, and subscribers to an existing Microsoft 365 Group</span></span> <br/> |
|[<span data-ttu-id="a7331-191">Remove-UnifiedGroupLinks</span><span class="sxs-lookup"><span data-stu-id="a7331-191">Remove-UnifiedGroupLinks</span></span>](/powershell/module/exchange/remove-unifiedgrouplinks) <br/> |<span data-ttu-id="a7331-192">从现有组中删除所有者Microsoft 365成员</span><span class="sxs-lookup"><span data-stu-id="a7331-192">Remove owners and members from an existing Microsoft 365 Group</span></span>  <br/> |
|[<span data-ttu-id="a7331-193">Get-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="a7331-193">Get-UserPhoto</span></span>](/powershell/module/exchange/get-userphoto) <br/> |<span data-ttu-id="a7331-194">用于查看有关与帐户关联的用户照片的信息。</span><span class="sxs-lookup"><span data-stu-id="a7331-194">Used to view information about the user photo associated with an account.</span></span> <span data-ttu-id="a7331-195">用户照片存储在 Active Directory 中</span><span class="sxs-lookup"><span data-stu-id="a7331-195">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="a7331-196">Set-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="a7331-196">Set-UserPhoto</span></span>](/powershell/module/exchange/set-userphoto) <br/> |<span data-ttu-id="a7331-197">用于将用户照片与帐户关联。</span><span class="sxs-lookup"><span data-stu-id="a7331-197">Used to associate a user photo with an account.</span></span> <span data-ttu-id="a7331-198">用户照片存储在 Active Directory 中</span><span class="sxs-lookup"><span data-stu-id="a7331-198">User photos are stored in Active Directory</span></span>  <br/> |
|[<span data-ttu-id="a7331-199">Remove-UserPhoto</span><span class="sxs-lookup"><span data-stu-id="a7331-199">Remove-UserPhoto</span></span>](/powershell/module/exchange/remove-userphoto) <br/> |<span data-ttu-id="a7331-200">删除组Microsoft 365照片</span><span class="sxs-lookup"><span data-stu-id="a7331-200">Remove the photo for an Microsoft 365 Group</span></span>  <br/> |

## <a name="related-topics"></a><span data-ttu-id="a7331-201">相关主题</span><span class="sxs-lookup"><span data-stu-id="a7331-201">Related topics</span></span>

[<span data-ttu-id="a7331-202">将通讯组列表升级到Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="a7331-202">Upgrade distribution lists to Microsoft 365 Groups</span></span>](/office365/admin/manage/upgrade-distribution-lists)

[<span data-ttu-id="a7331-203">管理可创建 Microsoft 365 组的人员</span><span class="sxs-lookup"><span data-stu-id="a7331-203">Manage who can create Microsoft 365 Groups</span></span>](/office365/admin/create-groups/manage-creation-of-groups)

[<span data-ttu-id="a7331-204">管理来宾对组Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="a7331-204">Manage guest access to Microsoft 365 Groups</span></span>](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[<span data-ttu-id="a7331-205">将静态组成员身份更改为 dynamic in</span><span class="sxs-lookup"><span data-stu-id="a7331-205">Change static group membership to dynamic in</span></span>](/azure/active-directory/users-groups-roles/groups-change-type)