---
title: 还原已删除的 Office 365 组
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: '了解如何使用 Exchange 管理中心还原已删除的 Office 365 组。 '
ms.openlocfilehash: 98eb00d90f5b607a58cd32728ce43cb4a1de1ff5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238438"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="efec8-103">还原已删除的 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="efec8-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="efec8-104">如果您是 Office 365 组的所有者，则可以通过执行以下步骤自己还原组。</span><span class="sxs-lookup"><span data-stu-id="efec8-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="efec8-105">在 "[已删除的组" 页](https://outlook.office.com/people/group/deleted)上，选择 "**组**" 节点下的 "**管理组**" 选项，然后选择 "**已删除**"。</span><span class="sxs-lookup"><span data-stu-id="efec8-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="efec8-106">单击要还原的组旁边的 "**还原**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="efec8-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="efec8-107">如果此处未显示已删除的组，请与管理员联系。</span><span class="sxs-lookup"><span data-stu-id="efec8-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="efec8-108">如果您是要还原 Office 365 组的用户，请管理员为您执行这些步骤或与您的技术支持人员联系。</span><span class="sxs-lookup"><span data-stu-id="efec8-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="efec8-109">如果已删除某个组，默认情况下它将保留30天。</span><span class="sxs-lookup"><span data-stu-id="efec8-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="efec8-110">这30天的期限被视为 "软删除"，因为您仍可以还原组。</span><span class="sxs-lookup"><span data-stu-id="efec8-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="efec8-111">30天后，该组及其关联的内容将被永久删除且无法还原。</span><span class="sxs-lookup"><span data-stu-id="efec8-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="efec8-112">在 "软删除" 时间段内，如果用户尝试访问该网站，将获得 404_禁止_访问的消息。</span><span class="sxs-lookup"><span data-stu-id="efec8-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="efec8-113">在此时间段后，如果用户尝试访问该网站，将收到 404_未找到_的消息。</span><span class="sxs-lookup"><span data-stu-id="efec8-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="efec8-114">还原组时，还可还原以下内容：</span><span class="sxs-lookup"><span data-stu-id="efec8-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="efec8-115">Azure Active Directory （AD） Office 365 组对象、属性和成员。</span><span class="sxs-lookup"><span data-stu-id="efec8-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="efec8-116">组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="efec8-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="efec8-117">Exchange Online 共享的收件箱和日历。</span><span class="sxs-lookup"><span data-stu-id="efec8-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="efec8-118">SharePoint Online 团队网站和文件。</span><span class="sxs-lookup"><span data-stu-id="efec8-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="efec8-119">OneNote 笔记本</span><span class="sxs-lookup"><span data-stu-id="efec8-119">OneNote notebook</span></span>
    
- <span data-ttu-id="efec8-120">Planner</span><span class="sxs-lookup"><span data-stu-id="efec8-120">Planner</span></span>
    
- <span data-ttu-id="efec8-121">Teams</span><span class="sxs-lookup"><span data-stu-id="efec8-121">Teams</span></span>

- <span data-ttu-id="efec8-122">Yammer 组和组内容（如果已从 Yammer 创建了 Office 365 组）</span><span class="sxs-lookup"><span data-stu-id="efec8-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="efec8-123">如果等不及在 30 天的保留期过期后再删除内容，也可选择[永久删除 Office 365 组](#permanently-delete-an-office-365-group)。</span><span class="sxs-lookup"><span data-stu-id="efec8-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="efec8-124">已删除的 Office 365 组的所有者也能够还原该组。</span><span class="sxs-lookup"><span data-stu-id="efec8-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="efec8-125">若要在不具有管理员权限的情况下使用 owner 权限还原 office 365 组，请参阅[使用 PowerShell 还原 office 365 组](#restore-an-office-365-group-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="efec8-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="efec8-126">使用 Exchange 管理中心还原 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="efec8-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="efec8-127">您必须拥有 Office 365 全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="efec8-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="efec8-128">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="efec8-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="efec8-129">在 Exchange 管理中心，选择" **收件人**"，然后选择" **组**"。</span><span class="sxs-lookup"><span data-stu-id="efec8-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="efec8-130">您可以查看该组是否处于活动状态或软删除。</span><span class="sxs-lookup"><span data-stu-id="efec8-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="efec8-131">如果该组已被永久删除，则不会将其列出。</span><span class="sxs-lookup"><span data-stu-id="efec8-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="efec8-132">若要查看软删除该组的确切时间，请选择该组并在右侧窗格中查看信息。</span><span class="sxs-lookup"><span data-stu-id="efec8-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="efec8-133">选择要还原的组，然后选择 "还原" 图标。</span><span class="sxs-lookup"><span data-stu-id="efec8-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![选择要还原的组，然后选择 "还原" 图标。](../media/restore-group.png)
  
5. <span data-ttu-id="efec8-135">选择 "刷新"</span><span class="sxs-lookup"><span data-stu-id="efec8-135">Select refresh</span></span> !['刷新'图标](../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="efec8-137">以更新页面上的信息。</span><span class="sxs-lookup"><span data-stu-id="efec8-137">to update the information on the page.</span></span> <span data-ttu-id="efec8-138">组将显示为活动状态。</span><span class="sxs-lookup"><span data-stu-id="efec8-138">Your group will show as Active.</span></span> <span data-ttu-id="efec8-139">与您的组关联的任何窗体和窗体数据也将还原。</span><span class="sxs-lookup"><span data-stu-id="efec8-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="efec8-140">使用 PowerShell 还原 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="efec8-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="efec8-141">您必须拥有 Office 365 全局管理员权限，或者是已删除的 Office 365 组的前一个所有者。</span><span class="sxs-lookup"><span data-stu-id="efec8-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efec8-142">如果使用 PowerShell 中的 MsolGroup 删除组，这将永久删除该组。</span><span class="sxs-lookup"><span data-stu-id="efec8-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="efec8-143">使用 PowerShell 删除组时，最佳做法是使用" **Remove-AzureADMSGroup**"软删除 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="efec8-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="efec8-144">这样可在需要时对其进行还原。</span><span class="sxs-lookup"><span data-stu-id="efec8-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="efec8-145">安装预览版的 Azure Active Directory PowerShell Graph</span><span class="sxs-lookup"><span data-stu-id="efec8-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="efec8-146">无法同时在同一台计算机上安装预览版本和 GA 版本。</span><span class="sxs-lookup"><span data-stu-id="efec8-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="efec8-147">作为一种最佳做法，我们建议*始终*保持最新，即卸载旧的 AzureADPreview 或旧的 AzureAD 版本并获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="efec8-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="efec8-148">在搜索栏中，键入 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="efec8-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="efec8-149">右键单击 **Windows PowerShell**，然后选择" **以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="efec8-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="efec8-150">查看已安装的模块：</span><span class="sxs-lookup"><span data-stu-id="efec8-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="efec8-151">3.要卸载早期版本的 AzureADPreview 或 AzureAD，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="efec8-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="efec8-152">或者</span><span class="sxs-lookup"><span data-stu-id="efec8-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="efec8-153">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="efec8-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="efec8-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="efec8-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="efec8-155">还原已删除的组</span><span class="sxs-lookup"><span data-stu-id="efec8-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="efec8-156">您是否按照 previoius 部分 "安装用于 Windows PowerShell 的 Azure Active Directory 模块的预览版本" 中的说明，安装了**AzureADPreview**模块？</span><span class="sxs-lookup"><span data-stu-id="efec8-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="efec8-157">这些步骤不起作用的首要原因是未安装最新的 **预览** 版。</span><span class="sxs-lookup"><span data-stu-id="efec8-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="efec8-158">如果尚未执行此操作，打开计算机上的 Windows PowerShell 窗口（可以是普通 Windows PowerShell 窗口，也可以是通过选择" **以管理员身份运行**"打开的窗口）。</span><span class="sxs-lookup"><span data-stu-id="efec8-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="efec8-159">在每个命令后按**enter** ，以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="efec8-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="efec8-160">在打开的 "**登录到帐户**" 屏幕中，输入您的管理帐户的用户名和密码以连接到 Azure AD 服务，并选择 "**登录**"。</span><span class="sxs-lookup"><span data-stu-id="efec8-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="efec8-161">运行此命令可显示组织中所有软删除的 Office 365 组，这些组仍在30天软删除时段内：</span><span class="sxs-lookup"><span data-stu-id="efec8-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="efec8-162">记下要还原的一个或多个组的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="efec8-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="efec8-163">如果在此列表中看不到您要查找的组，则它可能已永久清除。</span><span class="sxs-lookup"><span data-stu-id="efec8-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="efec8-164">如果使用与被删除组相同的别名或 SMTP 地址创建了新组，则必须先删除该新组才能还原已删除的组。</span><span class="sxs-lookup"><span data-stu-id="efec8-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="efec8-165">若要还原该组，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="efec8-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="efec8-166">此过程通常只需要几分钟时间，但在极少数情况下，可能需要长达24小时才能完全还原。</span><span class="sxs-lookup"><span data-stu-id="efec8-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="efec8-167">若要验证是否已成功还原组，请在 PowerShell 中运行此命令：</span><span class="sxs-lookup"><span data-stu-id="efec8-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="efec8-p110">成功还原后，该组会重新出现在 Outlook 和 Outlook 网页版的导航窗格上，且组成员应该可再次使用还原的所有内容，包括 SharePoint 和 Planner。</span><span class="sxs-lookup"><span data-stu-id="efec8-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="efec8-170">永久删除 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="efec8-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="efec8-171">有时，您可能希望永久清除组，而无需等待30天软删除期过期。</span><span class="sxs-lookup"><span data-stu-id="efec8-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="efec8-172">若要执行此操作，启动 PowerShell 并运行此命令，获取组的对象 ID：</span><span class="sxs-lookup"><span data-stu-id="efec8-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="efec8-173">记下要永久删除的一个或几个组的对象 ID。</span><span class="sxs-lookup"><span data-stu-id="efec8-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="efec8-174">清除组后可永久删除该组及其数据。</span><span class="sxs-lookup"><span data-stu-id="efec8-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="efec8-175">若要清除组，请在 PowerShell 中运行此命令：</span><span class="sxs-lookup"><span data-stu-id="efec8-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="efec8-p112">若要确认是否成功清除该组，请再次运行  *Get-AzureADMSDeletedGroup*  cmdlet 以确认该组不再出现在软删除的组列表中。某些情况下，要永久删除该组及其所有数据可能需要长达 24 小时。</span><span class="sxs-lookup"><span data-stu-id="efec8-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="efec8-178">对 Office 365 组有疑问？</span><span class="sxs-lookup"><span data-stu-id="efec8-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="efec8-179">访问[Microsoft 技术社区](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以发布问题并参与有关 Office 365 组的对话。</span><span class="sxs-lookup"><span data-stu-id="efec8-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="efec8-180">相关文章</span><span class="sxs-lookup"><span data-stu-id="efec8-180">Related articles</span></span>

[<span data-ttu-id="efec8-181">使用 PowerShell 管理 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="efec8-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="efec8-182">使用 Remove-UnifiedGroup cmdlet 删除组</span><span class="sxs-lookup"><span data-stu-id="efec8-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="efec8-183">管理连接了组的团队网站设置</span><span class="sxs-lookup"><span data-stu-id="efec8-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="efec8-184">在 Outlook 中删除组</span><span class="sxs-lookup"><span data-stu-id="efec8-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
