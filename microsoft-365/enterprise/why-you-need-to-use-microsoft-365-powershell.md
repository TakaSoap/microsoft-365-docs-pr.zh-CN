---
title: 为什么需要使用 PowerShell for Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 摘要：了解为什么必须使用 PowerShell 管理 Microsoft 365，在某些情况下可以更高效地管理 Microsoft 365，而在某些情况下，必须这样管理。
ms.openlocfilehash: a60220001a148b3a24a996bb6e0154f80214b019
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924584"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="6baea-103">为什么需要使用 PowerShell for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6baea-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="6baea-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="6baea-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6baea-105">使用 Microsoft 365 管理中心，可以管理 Microsoft 365 用户帐户和许可证。</span><span class="sxs-lookup"><span data-stu-id="6baea-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="6baea-106">还可以管理 Microsoft 365 服务，如 Exchange Online、Teams 和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="6baea-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="6baea-107">如果您改为使用 PowerShell 来管理这些服务，您可以利用命令行和脚本语言环境实现速度、自动化和其他功能。</span><span class="sxs-lookup"><span data-stu-id="6baea-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="6baea-108">本文演示如何使用 PowerShell 管理 Microsoft 365 以：</span><span class="sxs-lookup"><span data-stu-id="6baea-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="6baea-109">显示你在 Microsoft 365 管理中心看不到的其他信息</span><span class="sxs-lookup"><span data-stu-id="6baea-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="6baea-110">仅能使用 PowerShell 配置功能和设置</span><span class="sxs-lookup"><span data-stu-id="6baea-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="6baea-111">执行批量操作</span><span class="sxs-lookup"><span data-stu-id="6baea-111">Do bulk operations</span></span>
    
- <span data-ttu-id="6baea-112">筛选数据</span><span class="sxs-lookup"><span data-stu-id="6baea-112">Filter data</span></span>
    
- <span data-ttu-id="6baea-113">打印或保存数据</span><span class="sxs-lookup"><span data-stu-id="6baea-113">Print or save data</span></span>
    
- <span data-ttu-id="6baea-114">跨服务管理</span><span class="sxs-lookup"><span data-stu-id="6baea-114">Manage across services</span></span>
    
<span data-ttu-id="6baea-115">请记住，适用于 Microsoft 365 的 PowerShell 是一组适用于 Windows PowerShell 的模块，它是一个适用于基于 Windows 的服务和平台的命令行环境。</span><span class="sxs-lookup"><span data-stu-id="6baea-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="6baea-116">此环境创建一种命令行管理程序语言，该语言可以使用其他模块进行扩展。</span><span class="sxs-lookup"><span data-stu-id="6baea-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="6baea-117">它提供了一种执行简单或复杂的命令或脚本的方法。</span><span class="sxs-lookup"><span data-stu-id="6baea-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="6baea-118">例如，安装适用于 Microsoft 365 模块的 PowerShell 并连接到 Microsoft 365 订阅后，可以运行以下命令列出用户邮箱的Microsoft Exchange Online：</span><span class="sxs-lookup"><span data-stu-id="6baea-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="6baea-119">您还可以使用 Microsoft 365 管理中心获取邮箱列表，但无法轻松计算所有 Web 应用的所有网站的所有列表中的项目。</span><span class="sxs-lookup"><span data-stu-id="6baea-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="6baea-120">适用于 Microsoft 365 的 PowerShell 旨在帮助你管理 Microsoft 365，而不是替换 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6baea-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="6baea-121">管理员需要能够使用适用于 Microsoft 365 的 PowerShell，因为有些配置过程只能通过 PowerShell for Microsoft 365 命令完成。</span><span class="sxs-lookup"><span data-stu-id="6baea-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="6baea-122">在这些情况下，您需要了解如何：</span><span class="sxs-lookup"><span data-stu-id="6baea-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="6baea-123">安装 PowerShell for Microsoft 365 模块， (管理员计算机安装一次) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="6baea-124">针对每个 PowerShell 会话 (一次连接到 Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="6baea-125">收集运行 Microsoft 365 命令所需的 PowerShell 的信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="6baea-126">运行 PowerShell for Microsoft 365 命令。</span><span class="sxs-lookup"><span data-stu-id="6baea-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="6baea-127">了解这些基本技能后，不必使用 **Get-Mailbox** 命令列出邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="6baea-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="6baea-128">您也不必了解如何创建与前面引用的命令一样的新命令，以计算所有 Web 应用的所有网站的所有列表中的所有项数。</span><span class="sxs-lookup"><span data-stu-id="6baea-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="6baea-129">Microsoft 和管理员社区可根据需要帮助你完成此类任务。</span><span class="sxs-lookup"><span data-stu-id="6baea-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="6baea-130">适用于 Microsoft 365 的 PowerShell 可以显示你无法通过 Microsoft 365 管理中心看到的信息</span><span class="sxs-lookup"><span data-stu-id="6baea-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="6baea-131">Microsoft 365 管理中心显示许多有用的信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="6baea-132">但它不会显示 Microsoft 365 存储的有关用户、许可证、邮箱和网站的所有可能的信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="6baea-133">下面是 Microsoft 365 管理中心 *中* 用户和组的示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 管理中心中用户和组的显示示例。](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="6baea-135">此视图提供在许多情况下您需要的信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="6baea-136">但是，有时你需要了解更多。</span><span class="sxs-lookup"><span data-stu-id="6baea-136">However, there are times when you need more.</span></span> <span data-ttu-id="6baea-137">例如，Microsoft 365 授权 (以及可供用户使用的 Microsoft 365) 部分取决于用户的地理位置。</span><span class="sxs-lookup"><span data-stu-id="6baea-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="6baea-138">可以扩展到居住在美国的用户的策略和功能可能与可以扩展到印度或比利时的用户的策略和功能不同。</span><span class="sxs-lookup"><span data-stu-id="6baea-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="6baea-139">按照 Microsoft 365 管理中心中的以下步骤确定用户的地理位置：</span><span class="sxs-lookup"><span data-stu-id="6baea-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="6baea-140">双击用户的"显示名称"。</span><span class="sxs-lookup"><span data-stu-id="6baea-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="6baea-141">在用户属性显示窗格中， **选择详细信息**。</span><span class="sxs-lookup"><span data-stu-id="6baea-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="6baea-142">在详细信息显示中，选择 **其他详细信息**。</span><span class="sxs-lookup"><span data-stu-id="6baea-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="6baea-143">滚动，直到找到标题 **"国家/地区"：**</span><span class="sxs-lookup"><span data-stu-id="6baea-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Microsoft 365 管理中心中用户的区域信息示例。](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="6baea-145">在一张纸上记下用户的显示名称和位置，或将其复制并粘贴至记事本中。</span><span class="sxs-lookup"><span data-stu-id="6baea-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="6baea-146">您必须为每个用户重复此过程。</span><span class="sxs-lookup"><span data-stu-id="6baea-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="6baea-147">如果您有很多用户，此过程可能很繁琐。</span><span class="sxs-lookup"><span data-stu-id="6baea-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="6baea-148">通过适用于 Microsoft 365 的 PowerShell，可以使用以下命令为所有用户显示此信息：</span><span class="sxs-lookup"><span data-stu-id="6baea-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="6baea-149">PowerShell Core 不支持 Microsoft Azure Active Directory 模块，Windows PowerShell名称中具有 *Msol* 的模块和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6baea-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="6baea-150">您必须从应用程序运行这些 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6baea-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="6baea-151">下面是一个结果示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-151">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

<span data-ttu-id="6baea-152">此 PowerShell 命令的解释是：获取当前 Microsoft 365 订阅 (**Get-AzureADUser**) 中的所有用户，但仅显示每个用户的名称和位置 (**Select DisplayName， UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="6baea-153">因为 PowerShell for Microsoft 365 支持命令行管理程序语言，所以可以进一步操作 **Get-AzureADUser** 命令获取的信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="6baea-154">例如，也许你想按用户的位置对这些用户进行排序，将所有巴西用户分组在一起，将所有的美国用户组合在一起，等等。</span><span class="sxs-lookup"><span data-stu-id="6baea-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="6baea-155">下面是命令：</span><span class="sxs-lookup"><span data-stu-id="6baea-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="6baea-156">下面是一个结果示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-156">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

<span data-ttu-id="6baea-157">此 PowerShell 命令的解释是：在当前 Microsoft 365 订阅中获取所有用户，但仅显示每个用户的名称和位置，然后按用户的位置排序，然后按其名称 (**Sort UsageLocation， DisplayName**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="6baea-158">您还可以使用其他筛选。</span><span class="sxs-lookup"><span data-stu-id="6baea-158">You can also use additional filtering.</span></span> <span data-ttu-id="6baea-159">例如，如果您只想查看有关巴西用户的信息，请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="6baea-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="6baea-160">下面是一个结果示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="6baea-161">此 PowerShell 命令的解释是：获取当前 Microsoft 365 订阅中位置为 Brazil (**{$ 的所有用户 \_ 。UsageLocation -eq "BR"}**) ，然后显示每个用户的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="6baea-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="6baea-162">**有关大型域的注释**</span><span class="sxs-lookup"><span data-stu-id="6baea-162">**A note about large domains**</span></span>
  
<span data-ttu-id="6baea-163">如果您有一个拥有数万个用户的大型域，尝试本文中介绍的一些示例可能会导致限制。</span><span class="sxs-lookup"><span data-stu-id="6baea-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="6baea-164">根据计算能力和可用网络带宽等因素，您可能尝试一次执行太多。</span><span class="sxs-lookup"><span data-stu-id="6baea-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="6baea-165">大型组织可能希望将其中一些 PowerShell 操作拆分为两个命令。</span><span class="sxs-lookup"><span data-stu-id="6baea-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="6baea-166">例如，以下命令返回所有用户帐户，并显示每个帐户的名称和位置：</span><span class="sxs-lookup"><span data-stu-id="6baea-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="6baea-167">这对于较小的域非常有用。</span><span class="sxs-lookup"><span data-stu-id="6baea-167">That works great for smaller domains.</span></span> <span data-ttu-id="6baea-168">但在大型组织中，您可能需要将该操作拆分为两个命令：一个命令用于将用户帐户信息存储在变量中，另一个命令用于显示所需信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="6baea-169">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="6baea-170">这组 PowerShell 命令的解释是：</span><span class="sxs-lookup"><span data-stu-id="6baea-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="6baea-171">获取当前 Microsoft 365 订阅中的所有用户，将信息存储在名为 $x (**$x = Get-AzureADUser**) 的变量中。</span><span class="sxs-lookup"><span data-stu-id="6baea-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="6baea-172">显示变量的内容 *$x，但* 仅包括每个用户的用户名和 **($x |选择 DisplayName、UsageLocation**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="6baea-173">Microsoft 365 具有只能使用适用于 Microsoft 365 的 PowerShell 配置的功能</span><span class="sxs-lookup"><span data-stu-id="6baea-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="6baea-174">Microsoft 365 管理中心旨在提供对适用于大多数环境的常见、有用的管理任务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6baea-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="6baea-175">换句话说，Microsoft 365 管理中心的设计目的是让典型的管理员能够执行最常见的管理任务。</span><span class="sxs-lookup"><span data-stu-id="6baea-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="6baea-176">但有些任务无法通过管理中心完成。</span><span class="sxs-lookup"><span data-stu-id="6baea-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="6baea-177">例如，Skype for Business Online 管理中心提供了一些创建自定义会议邀请的选项：</span><span class="sxs-lookup"><span data-stu-id="6baea-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![用于在 Skype for Business Online 管理中心内显示自定义会议邀请的示例。](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="6baea-179">借助这些设置，您可以为会议邀请添加少许个性化和专业化。</span><span class="sxs-lookup"><span data-stu-id="6baea-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="6baea-180">但是，与仅创建自定义会议邀请一样，会议配置设置也更多。</span><span class="sxs-lookup"><span data-stu-id="6baea-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="6baea-181">例如，默认情况下，会议允许：</span><span class="sxs-lookup"><span data-stu-id="6baea-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="6baea-182">匿名用户获取自动参与每个会议的权限。</span><span class="sxs-lookup"><span data-stu-id="6baea-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="6baea-183">与会者记录会议。</span><span class="sxs-lookup"><span data-stu-id="6baea-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="6baea-184">您组织中的所有用户在加入会议时被指定为演示者。</span><span class="sxs-lookup"><span data-stu-id="6baea-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="6baea-185">这些设置不适用于 Skype for Business Online 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6baea-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="6baea-186">可以从适用于 Microsoft 365 的 PowerShell 控制它们。</span><span class="sxs-lookup"><span data-stu-id="6baea-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="6baea-187">下面是一个禁用这三个设置的命令：</span><span class="sxs-lookup"><span data-stu-id="6baea-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="6baea-188">若要运行此命令，必须安装 Skype [for Business Online PowerShell 模块 ](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="6baea-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="6baea-189">此 PowerShell 命令的解释为：</span><span class="sxs-lookup"><span data-stu-id="6baea-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="6baea-190">在 **Set-CsMeetingConfiguration**)  (的新 Skype for Business Online 会议设置中，禁用允许匿名用户自动进入会议 (**-AdmitAnonymousUsersByDefault** $False) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="6baea-191">禁止与会者在会议记录 (**-AllowConferenceRecording** $False) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="6baea-192">不要将您组织的所有用户指定为 (**-DesignateAsPresenter "None"**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="6baea-193">若要还原这些默认设置 (启用以下) ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6baea-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="6baea-194">还有一些类似的方案，这就是管理员应知道如何为 Microsoft 365 命令运行 PowerShell 的原因。</span><span class="sxs-lookup"><span data-stu-id="6baea-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="6baea-195">适用于 Microsoft 365 的 PowerShell 非常适用于批量操作</span><span class="sxs-lookup"><span data-stu-id="6baea-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="6baea-196">当你要执行一个操作时，Microsoft 365 管理中心等可视化界面最有价值。</span><span class="sxs-lookup"><span data-stu-id="6baea-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="6baea-197">例如，如果需要禁用一个用户帐户，可以使用管理中心快速找到并清除复选框。</span><span class="sxs-lookup"><span data-stu-id="6baea-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="6baea-198">这可能比在 PowerShell 中执行类似的操作要容易。</span><span class="sxs-lookup"><span data-stu-id="6baea-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="6baea-199">但是，如果你必须更改一大组其他内容中的许多内容或某些选定内容，Microsoft 365 管理中心可能不是最佳工具。</span><span class="sxs-lookup"><span data-stu-id="6baea-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="6baea-200">例如，假设必须更改数千个电话号码的前缀，或者从所有 SharePoint Online 网站中删除特定用户 *Ken Myer。*</span><span class="sxs-lookup"><span data-stu-id="6baea-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="6baea-201">如何在 Microsoft 365 管理中心中这样做？</span><span class="sxs-lookup"><span data-stu-id="6baea-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="6baea-202">对于最后一个示例，假设你拥有数百个 SharePoint Online 网站，而你不知道 Ken Meyer 是哪个网站的成员。</span><span class="sxs-lookup"><span data-stu-id="6baea-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="6baea-203">你必须从 Microsoft 365 管理中心开始，然后针对每个网站执行此过程：</span><span class="sxs-lookup"><span data-stu-id="6baea-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="6baea-204">选择 **网站的 URL。**</span><span class="sxs-lookup"><span data-stu-id="6baea-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="6baea-205">在 **"网站集属性"** 框中，选择" **网站地址** "链接以打开该网站。</span><span class="sxs-lookup"><span data-stu-id="6baea-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="6baea-206">在网站中，选择"共享 **"。**</span><span class="sxs-lookup"><span data-stu-id="6baea-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="6baea-207">在 **"共享** "对话框中，选择显示对网站具有权限的所有用户的链接：</span><span class="sxs-lookup"><span data-stu-id="6baea-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![在 SharePoint Online 管理中心内查看 SharePoint Online 站点成员的示例。](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="6baea-209">在"**共享对象"** 对话框中，选择"高级 **"。**</span><span class="sxs-lookup"><span data-stu-id="6baea-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="6baea-210">向下滚动用户列表，查找并选择 Ken Myer (假定他拥有访问网站) ，然后选择"删除 **用户权限"。**</span><span class="sxs-lookup"><span data-stu-id="6baea-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="6baea-211">对于几百 *个网站，* 这可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="6baea-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="6baea-212">另一个选择是在 PowerShell 中为 Microsoft 365 运行以下命令，以从所有网站中删除 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="6baea-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="6baea-213">此命令要求安装 [SharePoint Online PowerShell 模块](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="6baea-213">This command requires that you install the [SharePoint Online PowerShell module](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="6baea-214">此 PowerShell 命令的解释是：在当前 Microsoft 365 订阅 (**Get-SPOSite**) 中获取所有 SharePoint 网站，并针对每个网站从可以访问它的用户列表中删除 Ken Meyer (**ForEach {Remove-SPOUser -Site $ \_ 。Url -LoginName "kenmyer \@ litwareinc.com"}) 。**</span><span class="sxs-lookup"><span data-stu-id="6baea-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="6baea-215">我们告诉 Microsoft 365 从每个网站中删除 Ken Meyer，包括他无法访问的网站。</span><span class="sxs-lookup"><span data-stu-id="6baea-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="6baea-216">因此，结果将显示他无法访问的网站的错误。</span><span class="sxs-lookup"><span data-stu-id="6baea-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="6baea-217">我们可以在此命令上使用附加条件，以仅从登录列表中具有 Ken Meyer 的站点中删除 Ken Meyer。</span><span class="sxs-lookup"><span data-stu-id="6baea-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="6baea-218">但返回的错误不会损害网站本身。</span><span class="sxs-lookup"><span data-stu-id="6baea-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="6baea-219">此命令可能需要几分钟才能针对数百个网站运行，而不是在 Microsoft 365 管理中心中运行数小时。</span><span class="sxs-lookup"><span data-stu-id="6baea-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="6baea-220">下面是另一个批量操作示例。</span><span class="sxs-lookup"><span data-stu-id="6baea-220">Here's another bulk operation example.</span></span> <span data-ttu-id="6baea-221">使用此命令将新 SharePoint 管理员 *的一位用户将一位用户添加* 至组织的所有网站：</span><span class="sxs-lookup"><span data-stu-id="6baea-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="6baea-222">此 PowerShell 命令的解释是：在当前 Microsoft 365 订阅中获取所有 SharePoint 网站，并针对每个网站，通过将用户登录名添加到网站 (**ForEach {Add-SPOUser -Site $ 的 Members 组来允许其访问。 \_Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="6baea-223">适用于 Microsoft 365 的 PowerShell 非常出色的筛选数据</span><span class="sxs-lookup"><span data-stu-id="6baea-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="6baea-224">Microsoft 365 管理中心提供了几种筛选数据的方法，以轻松找到信息的目标子集。</span><span class="sxs-lookup"><span data-stu-id="6baea-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="6baea-225">例如，可以通过 Exchange 轻松筛选用户邮箱的几乎所有属性。</span><span class="sxs-lookup"><span data-stu-id="6baea-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="6baea-226">例如，下面是居住在布卢明顿市的所有用户的邮箱列表：</span><span class="sxs-lookup"><span data-stu-id="6baea-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![在 Microsoft 365 管理中心中为居住在布卢明顿市的所有用户执行邮箱列表的高级搜索的示例。](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="6baea-228">Exchange 管理中心还允许您组合筛选条件。</span><span class="sxs-lookup"><span data-stu-id="6baea-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="6baea-229">例如，您可以查找居住在布卢明顿且在财务部门工作的所有用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6baea-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="6baea-230">但是，您可以在 Exchange 管理中心中执行某些限制。</span><span class="sxs-lookup"><span data-stu-id="6baea-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="6baea-231">例如，找不到居住在布卢 *明顿或* 圣地亚哥的用户的邮箱，或者所有不居住在布卢明顿的用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="6baea-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="6baea-232">可以使用以下 PowerShell for Microsoft 365 命令获取居住在布卢明顿或圣地亚哥的所有用户的邮箱列表：</span><span class="sxs-lookup"><span data-stu-id="6baea-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="6baea-233">下面是一个结果示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="6baea-234">此 PowerShell 命令的解释是：在当前 Microsoft 365 订阅中获取在圣地亚哥或布卢明顿市拥有邮箱的所有用户 (**{$ \_ 。RecipientTypeDetails -eq "UserMailbox" -and ($ \_ .City -eq "San Diego" -or $ \_ .City -eq "Bloomington") }**) ，然后显示每个名称的名称和城市 (**选择 DisplayName， City**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="6baea-235">下面是为居住在布卢明顿以外的任何地方的用户列出所有邮箱的命令：</span><span class="sxs-lookup"><span data-stu-id="6baea-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="6baea-236">下面是一个结果示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-236">Here's an example of the results:</span></span>
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

<span data-ttu-id="6baea-237">此 PowerShell 命令的解释是：获取当前 Microsoft 365 订阅中邮箱未位于布卢明顿市 (**{$ 的所有用户 \_ 。RecipientTypeDetails -eq "UserMailbox" -and $ \_ .City -ne "Bloomington"}**) ，然后显示每个名称及城市。</span><span class="sxs-lookup"><span data-stu-id="6baea-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="6baea-238">使用通配符</span><span class="sxs-lookup"><span data-stu-id="6baea-238">Use wildcards</span></span>

<span data-ttu-id="6baea-239">您还可以在 PowerShell 筛选器中使用通配符来匹配部分名称。</span><span class="sxs-lookup"><span data-stu-id="6baea-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="6baea-240">例如，假设您要查找用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6baea-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="6baea-241">你只记得用户的姓氏是 *Anderson，* 也可能是 *Henderson* 或 *Jorgenson。*</span><span class="sxs-lookup"><span data-stu-id="6baea-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="6baea-242">通过使用搜索工具并执行三种不同的搜索，可以在 Microsoft 365 管理中心中跟踪该用户：</span><span class="sxs-lookup"><span data-stu-id="6baea-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="6baea-243">一次是搜索  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="6baea-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="6baea-244">一次是搜索  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="6baea-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="6baea-245">一次是搜索  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="6baea-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="6baea-246">由于所有这三个名称以"son"结尾，因此您可以告诉 PowerShell 显示其名称以"son"结尾的所有用户。</span><span class="sxs-lookup"><span data-stu-id="6baea-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="6baea-247">下面是命令：</span><span class="sxs-lookup"><span data-stu-id="6baea-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="6baea-248">此 PowerShell 命令的解释是：在当前 Microsoft 365 订阅中获取所有用户，但使用仅列出姓氏以"son"结尾的用户的筛选器 (**-Filter '{LastName -like " \* son"}'**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="6baea-249">\*代表任意一组字符，这些字符是用户姓氏中的字母。</span><span class="sxs-lookup"><span data-stu-id="6baea-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="6baea-250">PowerShell for Microsoft 365 使打印或保存数据变得简单</span><span class="sxs-lookup"><span data-stu-id="6baea-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="6baea-251">Microsoft 365 管理中心允许你查看数据列表。</span><span class="sxs-lookup"><span data-stu-id="6baea-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="6baea-252">下面是显示已启用 Skype for Business Online 的用户列表的 Skype for Business Online 管理中心的示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![用于显示已为 Skype for Business Online 启用的用户列表的 Skype for Business Online 管理中心的示例。](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="6baea-254">若要将该信息保存到文件中，必须将其粘贴到文档或 Microsoft Excel 工作表中。</span><span class="sxs-lookup"><span data-stu-id="6baea-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="6baea-255">这两种情况都可能需要其他格式。</span><span class="sxs-lookup"><span data-stu-id="6baea-255">Either case might require additional formatting.</span></span> <span data-ttu-id="6baea-256">此外，Microsoft 365 管理中心不提供直接打印显示的列表的方法。</span><span class="sxs-lookup"><span data-stu-id="6baea-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="6baea-257">幸运的是，您可以使用 PowerShell 不仅显示列表，还可以将其保存到可轻松导入 Excel 的文件。</span><span class="sxs-lookup"><span data-stu-id="6baea-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="6baea-258">下面是一个将 Skype for Business Online 用户数据保存到逗号分隔值 (CSV) 文件的示例命令，随后可以轻松地将这些值作为表导入 Excel 工作表中：</span><span class="sxs-lookup"><span data-stu-id="6baea-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="6baea-259">下面是一个结果示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-259">Here's an example of the results:</span></span>
  
![导入 Excel 工作表的表示例，用于保存到逗号分隔值文件的 Skype for Business Online 用户数据。](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="6baea-261">此 PowerShell 命令的解释是：使用 **Get-CsOnlineUser** (获取当前 Microsoft 365 订阅中所有 Skype for Business Online) ;仅获取 Select **DisplayName、UserPrincipalName、UsageLocation** (用户名、UPN 和位置) ;然后将该信息保存在名为 C： LogsSfBUsers.csv (\\ \\ **Export-Csv -Path "C： \\ Logs \\SfBUsers.csv" -NoTypeInformation**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="6baea-262">您还可以使用选项将此列表另存为 XML 文件或 HTML 页。</span><span class="sxs-lookup"><span data-stu-id="6baea-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="6baea-263">事实上，通过其他 PowerShell 命令，您可以直接将其另存为 Excel 文件，并设置任何自定义格式。</span><span class="sxs-lookup"><span data-stu-id="6baea-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="6baea-264">还可以将显示列表的 PowerShell 命令的输出直接发送到 Windows 中的默认打印机。</span><span class="sxs-lookup"><span data-stu-id="6baea-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="6baea-265">下面是一个示例命令：</span><span class="sxs-lookup"><span data-stu-id="6baea-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="6baea-266">打印的文档如下所示：</span><span class="sxs-lookup"><span data-stu-id="6baea-266">Here's what your printed document will look like:</span></span>
  
![打印文档的示例，该文档是直接发送到 Windows 中的默认打印机的 PowerShell 命令的输出。](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="6baea-268">此 PowerShell 命令的解释是：在当前 Microsoft 365 订阅中获取所有 Skype for Business Online 用户;仅获取用户名、UPN 和位置;然后将该信息发送到默认 Windows 打印机 (**打印机**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="6baea-269">打印的文档的格式与 PowerShell 命令窗口中的显示格式相同。</span><span class="sxs-lookup"><span data-stu-id="6baea-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="6baea-270">若要获取硬拷贝， **只需添加|命令末尾** 的打印机输出。</span><span class="sxs-lookup"><span data-stu-id="6baea-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="6baea-271">PowerShell for Microsoft 365 允许你跨服务器产品进行管理</span><span class="sxs-lookup"><span data-stu-id="6baea-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="6baea-272">组成 Microsoft 365 的组件旨在协同工作。</span><span class="sxs-lookup"><span data-stu-id="6baea-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="6baea-273">例如，假设您向 Microsoft 365 添加新用户，并指定了诸如该用户的部门和电话号码这样的信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="6baea-274">如果你在任何 Microsoft 365 服务（Skype for Business Online、Exchange 或 SharePoint）中访问用户信息，该信息将可用。</span><span class="sxs-lookup"><span data-stu-id="6baea-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="6baea-275">不过，此规则适用于跨产品套件的一般信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="6baea-276">特定于产品的信息（如有关用户的 Exchange 邮箱的信息）通常在整个套件中不可用。</span><span class="sxs-lookup"><span data-stu-id="6baea-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="6baea-277">例如，有关用户邮箱是否已启用的信息仅在 Exchange 管理中心可用。</span><span class="sxs-lookup"><span data-stu-id="6baea-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="6baea-278">假设您要为您的所有用户生成显示以下信息的报告：</span><span class="sxs-lookup"><span data-stu-id="6baea-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="6baea-279">用户的显示名称</span><span class="sxs-lookup"><span data-stu-id="6baea-279">The user's display name</span></span>
    
- <span data-ttu-id="6baea-280">用户是否获得 Microsoft 365 许可</span><span class="sxs-lookup"><span data-stu-id="6baea-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="6baea-281">用户的 Exchange 邮箱是否已启用</span><span class="sxs-lookup"><span data-stu-id="6baea-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="6baea-282">用户是否已启用 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6baea-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="6baea-283">你无法轻松地在 Microsoft 365 管理中心生成此类报告。</span><span class="sxs-lookup"><span data-stu-id="6baea-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6baea-284">相反，您必须创建单独的文档来存储信息，如 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="6baea-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="6baea-285">然后，从 Microsoft 365 管理中心获取所有用户名和许可信息，从 Exchange 管理中心获取邮箱信息，从 Skype for Business Online 管理中心获取 Skype for Business Online 信息，然后合并该信息。</span><span class="sxs-lookup"><span data-stu-id="6baea-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="6baea-286">替代方法是使用 PowerShell 脚本来编译报告。</span><span class="sxs-lookup"><span data-stu-id="6baea-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="6baea-287">以下示例脚本比到目前为止在本文看到的命令更复杂。</span><span class="sxs-lookup"><span data-stu-id="6baea-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="6baea-288">但是，它显示了使用 PowerShell 创建难以通过其他方式获取的信息视图的可能性。</span><span class="sxs-lookup"><span data-stu-id="6baea-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="6baea-289">下面是编译和显示所需的列表的脚本：</span><span class="sxs-lookup"><span data-stu-id="6baea-289">Here's the script to compile and display the list you need:</span></span>
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

<span data-ttu-id="6baea-290">下面是一个结果示例：</span><span class="sxs-lookup"><span data-stu-id="6baea-290">Here's an example of the results:</span></span>
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

<span data-ttu-id="6baea-291">此 PowerShell 脚本的解释为：</span><span class="sxs-lookup"><span data-stu-id="6baea-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="6baea-292">获取当前 Microsoft 365 订阅中的所有用户，将信息存储在名为 *$x* (**$x = Get-AzureADUser**) 的变量中。</span><span class="sxs-lookup"><span data-stu-id="6baea-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="6baea-293">启动一个循环，该循环在 $x (**foreach** ($i 中运行$x) ) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="6baea-294">定义一个名为 *$y* 的变量， ($y **= Get-Mailbox -Identity $i.UserPrincipalName) 。**</span><span class="sxs-lookup"><span data-stu-id="6baea-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="6baea-295">向名为 *IsMailBoxEnabled* 的用户信息添加新属性。</span><span class="sxs-lookup"><span data-stu-id="6baea-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="6baea-296">将此属性设置为用户邮箱 ($i | Add-Member **-MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled) 的 IsMailBoxEnabled** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="6baea-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="6baea-297">定义一个名为 *$y* 的变量，将用户的 Skype for Business Online 信息存储到 ($y **= Get-CsOnlineUser -Identity $i.UserPrincipalName**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="6baea-298">向名为 *EnabledForSfB* 的用户信息添加新属性。</span><span class="sxs-lookup"><span data-stu-id="6baea-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="6baea-299">将此属性设置为用户的 Skype for Business Online 信息 (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="6baea-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="6baea-300">显示用户列表，但仅包括其姓名、是否获得许可以及指示其邮箱是否已启用以及是否已启用 Skype for Business Online ($x | **选择 DisplayName、IsLicensed、IsMailboxEnabled、EnabledforSfB**) 。</span><span class="sxs-lookup"><span data-stu-id="6baea-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6baea-301">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6baea-301">See also</span></span>

[<span data-ttu-id="6baea-302">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="6baea-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6baea-303">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="6baea-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6baea-304">使用 Windows PowerShell 在 Microsoft 365 中创建报告</span><span class="sxs-lookup"><span data-stu-id="6baea-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)