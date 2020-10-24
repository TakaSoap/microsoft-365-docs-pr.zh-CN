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
description: 摘要：了解为什么必须使用 PowerShell 来管理 Microsoft 365，在某些情况下，在某些情况下可以更有效地管理 Microsoft。
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754102"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a><span data-ttu-id="a823d-103">为什么需要使用 PowerShell for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a823d-103">Why you need to use PowerShell for Microsoft 365</span></span>

<span data-ttu-id="a823d-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="a823d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a823d-105">使用 Microsoft 365 管理中心，可以管理 Microsoft 365 用户帐户和许可证。</span><span class="sxs-lookup"><span data-stu-id="a823d-105">With the Microsoft 365 admin center, you can manage your Microsoft 365 user accounts and licenses.</span></span> <span data-ttu-id="a823d-106">您还可以管理 Microsoft 365 服务，例如 Exchange Online、团队和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="a823d-106">You can also manage your Microsoft 365 services, such as Exchange Online, Teams, and SharePoint Online.</span></span> <span data-ttu-id="a823d-107">[！注意] 如果改用 PowerShell 管理这些服务，则可以并利用命令行和脚本语言环境来实现速度、自动化和其他功能。</span><span class="sxs-lookup"><span data-stu-id="a823d-107">If you instead use PowerShell to manage these services, you can and take advantage of the command-line and scripting language environment for speed, automation, and additional capabilities.</span></span>
  
<span data-ttu-id="a823d-108">本文介绍如何使用 PowerShell 来管理 Microsoft 365，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a823d-108">This article shows how to use PowerShell to manage Microsoft 365 to:</span></span>
  
- <span data-ttu-id="a823d-109">显示您在 Microsoft 365 管理中心中无法看到的其他信息</span><span class="sxs-lookup"><span data-stu-id="a823d-109">Reveal additional information that you can't see in the Microsoft 365 admin center</span></span>
    
- <span data-ttu-id="a823d-110">仅配置 PowerShell 可能的功能和设置</span><span class="sxs-lookup"><span data-stu-id="a823d-110">Configure features and settings only possible with PowerShell</span></span>
    
- <span data-ttu-id="a823d-111">批量操作</span><span class="sxs-lookup"><span data-stu-id="a823d-111">Do bulk operations</span></span>
    
- <span data-ttu-id="a823d-112">筛选数据</span><span class="sxs-lookup"><span data-stu-id="a823d-112">Filter data</span></span>
    
- <span data-ttu-id="a823d-113">打印或保存数据</span><span class="sxs-lookup"><span data-stu-id="a823d-113">Print or save data</span></span>
    
- <span data-ttu-id="a823d-114">跨服务管理</span><span class="sxs-lookup"><span data-stu-id="a823d-114">Manage across services</span></span>
    
<span data-ttu-id="a823d-115">请注意，PowerShell for Microsoft 365 是一组用于 Windows PowerShell 的模块，这是一种适用于基于 Windows 的服务和平台的命令行环境。</span><span class="sxs-lookup"><span data-stu-id="a823d-115">Keep in mind that PowerShell for Microsoft 365 is a set of modules for Windows PowerShell, which is a command-line environment for Windows-based services and platforms.</span></span> <span data-ttu-id="a823d-116">此环境创建一种命令行管理程序语言，可使用其他模块进行扩展。</span><span class="sxs-lookup"><span data-stu-id="a823d-116">This environment creates a command-shell language that can be extended with additional modules.</span></span> <span data-ttu-id="a823d-117">它提供了一种执行简单或复杂命令或脚本的方法。</span><span class="sxs-lookup"><span data-stu-id="a823d-117">It provides a way to execute simple or complex commands or scripts.</span></span> <span data-ttu-id="a823d-118">例如，在安装适用于 Microsoft 365 模块的 PowerShell 并连接到 Microsoft 365 订阅后，可以运行以下命令来列出 Microsoft Exchange Online 的所有用户邮箱：</span><span class="sxs-lookup"><span data-stu-id="a823d-118">For example, after you install the PowerShell for Microsoft 365 modules and connect to your Microsoft 365 subscription, you can run the following command to list all the user mailboxes for Microsoft Exchange Online:</span></span>
  
```powershell
Get-Mailbox
```

<span data-ttu-id="a823d-119">您还可以使用 Microsoft 365 管理中心获取邮箱的列表，但对所有 web 应用程序的所有网站的所有列表中的项目进行计数并不简单。</span><span class="sxs-lookup"><span data-stu-id="a823d-119">You could also get the list of mailboxes by using the Microsoft 365 admin center but counting the items in all the lists for all the sites for all of your web apps isn't easy.</span></span>
  
<span data-ttu-id="a823d-120">PowerShell for Microsoft 365 旨在帮助您管理 Microsoft 365，而不是取代 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="a823d-120">PowerShell for Microsoft 365 is designed to help you manage Microsoft 365, not to replace the Microsoft 365 admin center.</span></span> <span data-ttu-id="a823d-121">管理员需要能够使用适用于 Microsoft 365 的 PowerShell，因为某些配置过程只能通过 PowerShell 为 Microsoft 365 命令完成。</span><span class="sxs-lookup"><span data-stu-id="a823d-121">Admins need to be able to use PowerShell for Microsoft 365 because there are some configuration procedures that can only be done through PowerShell for Microsoft 365 commands.</span></span> <span data-ttu-id="a823d-122">在这些情况下，您需要了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a823d-122">For these cases, you need to know how to:</span></span>
  
- <span data-ttu-id="a823d-123">为 Microsoft 365 模块安装 PowerShell (仅为每个管理员计算机) 执行一次。</span><span class="sxs-lookup"><span data-stu-id="a823d-123">Install the PowerShell for Microsoft 365 modules (done only one time for each administrator computer).</span></span>
    
- <span data-ttu-id="a823d-124">为每个 PowerShell 会话 (一次连接到 Microsoft 365 订阅) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-124">Connect to your Microsoft 365 subscription (one time for each PowerShell session).</span></span>
    
- <span data-ttu-id="a823d-125">收集运行所需的 PowerShell for Microsoft 365 命令所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-125">Gather the information needed to run the required PowerShell for Microsoft 365 commands.</span></span>
    
- <span data-ttu-id="a823d-126">为 Microsoft 365 命令运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a823d-126">Run PowerShell for Microsoft 365 commands.</span></span>
    
<span data-ttu-id="a823d-127">了解这些基本技能之后，您无需使用 " **获取邮箱** " 命令列出邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="a823d-127">After you learn these basic skills, you don't have to list your mailbox users by using the **Get-Mailbox** command.</span></span> <span data-ttu-id="a823d-128">此外，您还无需了解如何创建新命令（如前面提到的命令），以便对所有 web 应用程序的所有网站的所有列表中的所有项进行计数。</span><span class="sxs-lookup"><span data-stu-id="a823d-128">You also don't have to understand how to create a new command like the command cited previously to count all the items in all the lists for all the sites for all of your web apps.</span></span> <span data-ttu-id="a823d-129">Microsoft 和管理员社区可在需要时帮助你执行此类任务。</span><span class="sxs-lookup"><span data-stu-id="a823d-129">Microsoft and the community of administrators can help you with such tasks as needed.</span></span>
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a><span data-ttu-id="a823d-130">PowerShell for Microsoft 365 可以显示你无法通过 Microsoft 365 管理中心看到的信息</span><span class="sxs-lookup"><span data-stu-id="a823d-130">PowerShell for Microsoft 365 can reveal information that you can't see with the Microsoft 365 admin center</span></span>

<span data-ttu-id="a823d-131">Microsoft 365 管理中心显示了许多有用的信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-131">The Microsoft 365 admin center displays many useful information.</span></span> <span data-ttu-id="a823d-132">但它不会显示 Microsoft 365 存储的有关用户、许可证、邮箱和网站的所有可能信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-132">But it doesn't display all the possible information that Microsoft 365 stores about users, licenses, mailboxes, and sites.</span></span> <span data-ttu-id="a823d-133">下面的示例展示了 Microsoft 365 管理中心中的 *用户和组* ：</span><span class="sxs-lookup"><span data-stu-id="a823d-133">Here's an example for *users and groups* in the Microsoft 365 admin center:</span></span>
  
![Microsoft 365 管理中心中的用户和组的显示示例。](../media/o365-powershell-users-and-groups.png)
  
<span data-ttu-id="a823d-135">此视图提供了在许多情况下所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-135">This view provides the information that you need in many cases.</span></span> <span data-ttu-id="a823d-136">但是，有时你需要了解更多。</span><span class="sxs-lookup"><span data-stu-id="a823d-136">However, there are times when you need more.</span></span> <span data-ttu-id="a823d-137">例如，Microsoft 365 许可 (和可用于用户) 的 Microsoft 365 功能取决于用户的地理位置。</span><span class="sxs-lookup"><span data-stu-id="a823d-137">For example, Microsoft 365 licensing (and the Microsoft 365 features available to a user) depends in part on the user's geographic location.</span></span> <span data-ttu-id="a823d-138">您可以扩展到美国居住的用户的策略和功能可能与您可以在印度或比利时的用户中扩展的策略和功能不同。</span><span class="sxs-lookup"><span data-stu-id="a823d-138">The policies and features that you can extend to a user who lives in the United States might not be the same as those that you can extend to a user in India or Belgium.</span></span> <span data-ttu-id="a823d-139">在 Microsoft 365 管理中心中执行以下步骤，以确定用户的地理位置：</span><span class="sxs-lookup"><span data-stu-id="a823d-139">Follow these steps in the Microsoft 365 admin center to determine a user's geographic location:</span></span>
  
1. <span data-ttu-id="a823d-140">双击用户的"显示名称"。</span><span class="sxs-lookup"><span data-stu-id="a823d-140">Double-click the user's **Display Name**.</span></span>
    
2. <span data-ttu-id="a823d-141">在用户属性显示窗格中，选择 " **详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="a823d-141">In the user properties display pane, select **details**.</span></span>
    
3. <span data-ttu-id="a823d-142">在详细信息显示中，选择 " **其他详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="a823d-142">In the details display, select **additional details**.</span></span>
    
4. <span data-ttu-id="a823d-143">向内滚动，直到找到 "标题" **国家或地区**：</span><span class="sxs-lookup"><span data-stu-id="a823d-143">Scroll until you find the heading **Country or region**:</span></span>
    
     ![Microsoft 365 管理中心中用户的区域信息示例。](../media/o365-powershell-usage-location.png)
  
5. <span data-ttu-id="a823d-145">在一张纸上记下用户的显示名称和位置，或将其复制并粘贴至记事本中。</span><span class="sxs-lookup"><span data-stu-id="a823d-145">Write the user's display name and location on a piece of paper, or copy and paste it into Notepad.</span></span>
    
<span data-ttu-id="a823d-146">您必须为每个用户重复此过程。</span><span class="sxs-lookup"><span data-stu-id="a823d-146">You must repeat this procedure for each user.</span></span> <span data-ttu-id="a823d-147">如果有多个用户，此过程可能很单调。</span><span class="sxs-lookup"><span data-stu-id="a823d-147">If you have many users, this process can be tedious.</span></span> <span data-ttu-id="a823d-148">对于适用于 Microsoft 365 的 PowerShell，可以使用以下命令为所有用户显示此信息：</span><span class="sxs-lookup"><span data-stu-id="a823d-148">With PowerShell for Microsoft 365, you can display this information for all of your users by using the following command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
><span data-ttu-id="a823d-149">PowerShell Core 不支持在其名称中包含 *Msol* 的 Windows PowerShell 模块和 Cmdlet 的 Microsoft Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="a823d-149">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="a823d-150">您必须从 Windows PowerShell 中运行这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a823d-150">You have to run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="a823d-151">下面是结果的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-151">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="a823d-152">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户 (**AzureADUser**) ，但仅显示每个用户的名称和位置 (**选择 "DisplayName"、"UsageLocation**) "。</span><span class="sxs-lookup"><span data-stu-id="a823d-152">The interpretation of this PowerShell command is: Get all of the users in the current Microsoft 365 subscription (**Get-AzureADUser**), but only display the name and location for each user (**Select DisplayName, UsageLocation**).</span></span>
  
<span data-ttu-id="a823d-153">由于适用于 Microsoft 365 的 PowerShell 支持命令行管理程序语言，因此您可以进一步操纵 **AzureADUser** 命令获取的信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-153">Because PowerShell for Microsoft 365 supports a command-shell language, you can further manipulate the information obtained by the **Get-AzureADUser** command.</span></span> <span data-ttu-id="a823d-154">例如，您可能希望按照用户的位置对这些用户进行排序，将所有巴西用户组合在一起，将所有美国用户组合在一起，等等。</span><span class="sxs-lookup"><span data-stu-id="a823d-154">For example, maybe you'd like to sort these users by their location, grouping all the Brazilian users together, all the United States users together, and so on.</span></span> <span data-ttu-id="a823d-155">以下命令如下所示：</span><span class="sxs-lookup"><span data-stu-id="a823d-155">Here's the command:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

<span data-ttu-id="a823d-156">下面是结果的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-156">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="a823d-157">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户，但仅显示每个用户的名称和位置，并按其位置和名称 (**Sort UsageLocation，DisplayName**) 对其进行排序。</span><span class="sxs-lookup"><span data-stu-id="a823d-157">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but only display the name and location for each user and sort them first by their location and then their name (**Sort UsageLocation, DisplayName**).</span></span>
  
<span data-ttu-id="a823d-158">您还可以使用其他筛选。</span><span class="sxs-lookup"><span data-stu-id="a823d-158">You can also use additional filtering.</span></span> <span data-ttu-id="a823d-159">例如，如果您只想查看有关巴西用户的信息，请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="a823d-159">For example, if you only want to see information about users based in Brazil, use this command:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

<span data-ttu-id="a823d-160">下面是结果的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-160">Here's an example of the results:</span></span>
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

<span data-ttu-id="a823d-161">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的位置是巴西的所有用户 **（在 {$ (其中，{$） \_ 。UsageLocation-eq "BR"}**) 然后显示每个用户的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="a823d-161">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription whose location is Brazil (**Where {$\_.UsageLocation -eq "BR"}**) and then display the name and location for each user.</span></span>
  
 <span data-ttu-id="a823d-162">**关于大型域的说明**</span><span class="sxs-lookup"><span data-stu-id="a823d-162">**A note about large domains**</span></span>
  
<span data-ttu-id="a823d-163">如果有成千上万个用户的大型域，请尝试在本文中介绍的一些示例将导致限制。</span><span class="sxs-lookup"><span data-stu-id="a823d-163">If you have a large domain with tens of thousands of users, trying some of the examples we show in this article could lead to throttling.</span></span> <span data-ttu-id="a823d-164">根据计算功率和可用网络带宽等因素，您可能尝试一次执行太多操作。</span><span class="sxs-lookup"><span data-stu-id="a823d-164">Based on factors like computing power and available network bandwidth, you may be trying to do too much at one time.</span></span> <span data-ttu-id="a823d-165">大型组织可能希望将其中一些 PowerShell 操作拆分成两个命令。</span><span class="sxs-lookup"><span data-stu-id="a823d-165">Large organizations might want to split some of these PowerShell operations into two commands.</span></span>

<span data-ttu-id="a823d-166">例如，以下命令返回所有用户帐户并显示每个帐户的名称和位置：</span><span class="sxs-lookup"><span data-stu-id="a823d-166">For example, the following command returns all the user accounts and shows the name and location for each:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

<span data-ttu-id="a823d-167">这对于较小的域非常有用。</span><span class="sxs-lookup"><span data-stu-id="a823d-167">That works great for smaller domains.</span></span> <span data-ttu-id="a823d-168">但在大型组织中，可能需要将该操作拆分为两个命令：一个命令，用于将用户帐户信息存储在一个变量中，另一个用于显示所需的信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-168">But in a large organization, you might want to split that operation into two commands: one command to store the user account information in a variable and another to display the needed information.</span></span> <span data-ttu-id="a823d-169">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-169">Here's an example:</span></span>
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

<span data-ttu-id="a823d-170">此 PowerShell 命令集的解释如下：</span><span class="sxs-lookup"><span data-stu-id="a823d-170">The interpretation of this set of PowerShell commands is:</span></span>
1. <span data-ttu-id="a823d-171">获取当前 Microsoft 365 订阅中的所有用户，并将信息存储在名为 $x (**$x = AzureADUser**) 的变量中。</span><span class="sxs-lookup"><span data-stu-id="a823d-171">Get all the users in the current Microsoft 365 subscription and store the information in a variable named $x (**$x = Get-AzureADUser**).</span></span>
1.  <span data-ttu-id="a823d-172">显示变量 *$x*的内容，但只包含每个用户的名称和位置 (**$x |选择 "DisplayName"、"UsageLocation) "** 。</span><span class="sxs-lookup"><span data-stu-id="a823d-172">Display the contents of the variable *$x*, but only include the name and location for each user (**$x | Select DisplayName, UsageLocation**).</span></span>
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a><span data-ttu-id="a823d-173">Microsoft 365 具有仅可为 Microsoft 365 配置 PowerShell 的功能</span><span class="sxs-lookup"><span data-stu-id="a823d-173">Microsoft 365 has features that you can only configure with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="a823d-174">Microsoft 365 管理中心旨在提供适用于大多数环境的常见、有用管理任务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a823d-174">The Microsoft 365 admin center is intended to provide access to common, useful administrative tasks that apply to most environments.</span></span> <span data-ttu-id="a823d-175">换句话说，Microsoft 365 管理中心的设计是为了使典型管理员可以执行最常见的管理任务。</span><span class="sxs-lookup"><span data-stu-id="a823d-175">In other words, the Microsoft 365 admin center was designed so that the typical administrator can carry out the most-common management tasks.</span></span> <span data-ttu-id="a823d-176">但有些任务无法在管理中心完成。</span><span class="sxs-lookup"><span data-stu-id="a823d-176">But there are some tasks that can't be done in the admin center.</span></span>
  
<span data-ttu-id="a823d-177">例如，Skype for Business Online 管理中心提供了用于创建自定义会议邀请的几个选项：</span><span class="sxs-lookup"><span data-stu-id="a823d-177">For example, the Skype for Business Online admin center provides a few options for creating custom meeting invitations:</span></span>
  
![用于在 Skype for Business Online 管理中心内显示自定义会议邀请的示例。](../media/o365-powershell-meeting-invitation.png)
  
<span data-ttu-id="a823d-179">借助这些设置，您可以为会议邀请添加少许个性化和专业化。</span><span class="sxs-lookup"><span data-stu-id="a823d-179">With these settings, you can add a touch of personalization and professionalism to meeting invitations.</span></span> <span data-ttu-id="a823d-180">但与简单地创建自定义会议邀请相比，会议配置设置更多。</span><span class="sxs-lookup"><span data-stu-id="a823d-180">But there's more to meeting-configuration settings than simply creating custom meeting invitations.</span></span> <span data-ttu-id="a823d-181">例如，默认情况下，会议允许：</span><span class="sxs-lookup"><span data-stu-id="a823d-181">For example, by default, meetings allow:</span></span>
  
- <span data-ttu-id="a823d-182">匿名用户获取自动参与每个会议的权限。</span><span class="sxs-lookup"><span data-stu-id="a823d-182">Anonymous users to gain automatic entrance to each meeting.</span></span>
    
- <span data-ttu-id="a823d-183">与会者记录会议。</span><span class="sxs-lookup"><span data-stu-id="a823d-183">Attendees to record the meeting.</span></span>
    
- <span data-ttu-id="a823d-184">您组织中的所有用户在加入会议时被指定为演示者。</span><span class="sxs-lookup"><span data-stu-id="a823d-184">All users from your organization to be designated as presenters when they join the meeting.</span></span>
    
<span data-ttu-id="a823d-185">这些设置在 Skype for Business Online 管理中心不可用。</span><span class="sxs-lookup"><span data-stu-id="a823d-185">These settings aren't available from the Skype for Business Online admin center.</span></span> <span data-ttu-id="a823d-186">你可以从 PowerShell for Microsoft 365 中控制它们。</span><span class="sxs-lookup"><span data-stu-id="a823d-186">You can control them from PowerShell for Microsoft 365.</span></span> <span data-ttu-id="a823d-187">以下是禁用这三个设置的命令：</span><span class="sxs-lookup"><span data-stu-id="a823d-187">Here's a command that disables these three settings:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> <span data-ttu-id="a823d-188">若要运行此命令，您必须安装 [Skype For Business Online PowerShell 模块 ](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="a823d-188">To run this command, you must install the [Skype for Business Online PowerShell Module ](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
  
<span data-ttu-id="a823d-189">此 PowerShell 命令的解释如下：</span><span class="sxs-lookup"><span data-stu-id="a823d-189">The interpretation of this PowerShell command is:</span></span>
 
1. <span data-ttu-id="a823d-190">在 "新 Skype for Business Online 会议的设置" (**get-csmeetingconfiguration**) 中，禁用允许匿名用户自动进入会议 (**-AdmitAnonymousUsersByDefault $False**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-190">In the settings for new Skype for Business Online meetings (**Set-CsMeetingConfiguration**), disable allowing anonymous users to gain automatic entrance to meetings (**-AdmitAnonymousUsersByDefault $False**).</span></span>
2.  <span data-ttu-id="a823d-191">禁用与会者 (**-AllowConferenceRecording $False**) 录制会议的功能。</span><span class="sxs-lookup"><span data-stu-id="a823d-191">Disable the ability for attendees to record meetings (**-AllowConferenceRecording $False**).</span></span>
3. <span data-ttu-id="a823d-192">请勿将组织中的所有用户指定为演示者 (**-DesignateAsPresenter "None"**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-192">Don't designate all users from your organization as presenters (**-DesignateAsPresenter "None"**).</span></span>
  
<span data-ttu-id="a823d-193">若要还原这些默认设置 (启用 "选项") ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a823d-193">To restore these default settings (enable the options), run this command:</span></span>
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

<span data-ttu-id="a823d-194">还有其他类似的方案，这也是为什么管理员应了解如何为 Microsoft 365 命令运行 PowerShell 的原因。</span><span class="sxs-lookup"><span data-stu-id="a823d-194">There are other similar scenarios as well, which is why administrators should know how to run PowerShell for Microsoft 365 commands.</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a><span data-ttu-id="a823d-195">适用于 Microsoft 365 的 PowerShell 非常适合用于批量操作</span><span class="sxs-lookup"><span data-stu-id="a823d-195">PowerShell for Microsoft 365 is great for bulk operations</span></span>

<span data-ttu-id="a823d-196">当您执行一个操作时，像 Microsoft 365 管理中心这样的可视界面是最有用的。</span><span class="sxs-lookup"><span data-stu-id="a823d-196">Visual interfaces like the Microsoft 365 admin center are most valuable when you have a single operation to do.</span></span> <span data-ttu-id="a823d-197">例如，如果您需要禁用一个用户帐户，则可以使用管理中心快速查找并清除复选框。</span><span class="sxs-lookup"><span data-stu-id="a823d-197">For example, if you need to disable one user account, you can use the admin center to quickly locate and clear a checkbox.</span></span> <span data-ttu-id="a823d-198">这可能比在 PowerShell 中执行类似的操作更容易。</span><span class="sxs-lookup"><span data-stu-id="a823d-198">This may be easier than performing a similar operation in PowerShell.</span></span>
  
<span data-ttu-id="a823d-199">但是，如果您必须在一大范围的其他内容中更改许多内容或所选内容，Microsoft 365 管理中心可能不是最佳工具。</span><span class="sxs-lookup"><span data-stu-id="a823d-199">But if you have to change many things or some selected things within a large set of other things, the Microsoft 365 admin center might not be the best tool.</span></span> <span data-ttu-id="a823d-200">例如，假设您必须更改成千上万个电话号码的前缀，或者从所有 SharePoint Online 网站中删除特定用户 *Ken Myer* 。</span><span class="sxs-lookup"><span data-stu-id="a823d-200">For example, say you have to change the prefix on thousands of phone numbers or remove the specific user *Ken Myer* from all your SharePoint Online sites.</span></span> <span data-ttu-id="a823d-201">如何在 Microsoft 365 管理中心中执行此操作？</span><span class="sxs-lookup"><span data-stu-id="a823d-201">How would you do that in the Microsoft 365 admin center?</span></span>
  
<span data-ttu-id="a823d-202">在最后一个示例中，假设您有几百个 SharePoint Online 网站，并且您不知道哪些 Ken Meyer 是其成员。</span><span class="sxs-lookup"><span data-stu-id="a823d-202">For the last example, say you have several hundred SharePoint Online sites, and you don't know which ones Ken Meyer is a member of.</span></span> <span data-ttu-id="a823d-203">您必须从 Microsoft 365 管理中心开始，然后对每个网站执行此过程：</span><span class="sxs-lookup"><span data-stu-id="a823d-203">You would have to start at the Microsoft 365 admin center and then perform this procedure for each site:</span></span>
  
1. <span data-ttu-id="a823d-204">选择网站的 **URL** 。</span><span class="sxs-lookup"><span data-stu-id="a823d-204">Select the **URL** of the site.</span></span>
    
2. <span data-ttu-id="a823d-205">在 " **网站集属性** " 框中，选择 "网站 **地址** " 链接以打开网站。</span><span class="sxs-lookup"><span data-stu-id="a823d-205">In the **site collection properties** box, select the **Web Site Address** link to open the site.</span></span>
    
3. <span data-ttu-id="a823d-206">在网站上，选择 " **共享**"。</span><span class="sxs-lookup"><span data-stu-id="a823d-206">On the site, select **Share**.</span></span>
    
4. <span data-ttu-id="a823d-207">在 " **共享** " 对话框中，选择显示有权访问该网站的所有用户的链接：</span><span class="sxs-lookup"><span data-stu-id="a823d-207">In the **Share** dialog box, select the link that shows all the users who have permissions to the site:</span></span>
    
     ![在 SharePoint Online 管理中心内查看 SharePoint Online 站点成员的示例。](../media/o365-powershell-view-permissions.png)
  
5. <span data-ttu-id="a823d-209">在 " **共享** " 对话框中，选择 " **高级**"。</span><span class="sxs-lookup"><span data-stu-id="a823d-209">In the **Shared With** dialog box, select **Advanced**.</span></span>
    
6. <span data-ttu-id="a823d-210">向下滚动用户列表，找到并选择 Ken Myer (如果他拥有对网站) 的权限，然后选择 " **删除用户权限**"。</span><span class="sxs-lookup"><span data-stu-id="a823d-210">Scroll down the list of users, find and select Ken Myer (assuming he has permissions to the site), and then select **Remove User Permissions**.</span></span>
    
<span data-ttu-id="a823d-211">对于几百个网站，这可能需要 *很长* 时间。</span><span class="sxs-lookup"><span data-stu-id="a823d-211">This would take a *long* time for several hundred sites.</span></span>
  
<span data-ttu-id="a823d-212">另一种方法是在 PowerShell for Microsoft 365 中运行以下命令，以从所有网站中删除 Ken Myer：</span><span class="sxs-lookup"><span data-stu-id="a823d-212">The alternative is to run the following command in PowerShell for Microsoft 365 to remove Ken Myer from all your sites:</span></span>
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> <span data-ttu-id="a823d-213">此命令要求您安装 [SharePoint Online PowerShell 模块](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="a823d-213">This command requires that you install the [SharePoint Online PowerShell module](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span> 
  
<span data-ttu-id="a823d-214">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有 SharePoint 网站 (**get-sposite**) 并为每个网站删除 Ken Meyer （从可访问它的用户列表 (**ForEach {remove-get-spouser-site $） \_ 。Url-Person.loginname "kenmyer \@ litwareinc.com"}**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-214">The interpretation of this PowerShell command is: Get all of the SharePoint sites in the current Microsoft 365 subscription (**Get-SPOSite**) and for each site remove Ken Meyer from the list of users who can access it (**ForEach {Remove-SPOUser -Site $\_.Url -LoginName "kenmyer\@litwareinc.com"}**).</span></span>
  
<span data-ttu-id="a823d-215">我们将告知 Microsoft 365 从每个站点中删除 Ken Meyer，包括他无权访问的所有站点。</span><span class="sxs-lookup"><span data-stu-id="a823d-215">We tell Microsoft 365 to remove Ken Meyer from every site, including those that he doesn't have access to.</span></span> <span data-ttu-id="a823d-216">因此，结果将显示他无权访问的那些网站的错误。</span><span class="sxs-lookup"><span data-stu-id="a823d-216">So the results will show errors for those sites that he doesn't have access to.</span></span> <span data-ttu-id="a823d-217">我们可以对此命令使用附加条件，以便仅从拥有他的登录列表的站点中删除 Ken Meyer。</span><span class="sxs-lookup"><span data-stu-id="a823d-217">We can use an additional condition on this command to remove Ken Meyer only from the sites that have him on their login list.</span></span> <span data-ttu-id="a823d-218">但返回的错误对网站本身不造成危害。</span><span class="sxs-lookup"><span data-stu-id="a823d-218">But the errors that are returned cause no harm to the sites themselves.</span></span> <span data-ttu-id="a823d-219">此命令可能需要几分钟的时间才能运行数百个网站，而不是通过 Microsoft 365 管理中心工作数小时。</span><span class="sxs-lookup"><span data-stu-id="a823d-219">This command might take a few minutes to run against hundreds of sites, rather than hours of working through the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="a823d-220">下面是另一个批量操作示例。</span><span class="sxs-lookup"><span data-stu-id="a823d-220">Here's another bulk operation example.</span></span> <span data-ttu-id="a823d-221">使用此命令将 *Bonnie Kearney*（一个新的 SharePoint 管理员）添加到组织中的所有网站：</span><span class="sxs-lookup"><span data-stu-id="a823d-221">Use this command to add *Bonnie Kearney*, a new SharePoint administrator, to all sites in the organization:</span></span>
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

<span data-ttu-id="a823d-222">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有 SharePoint 网站，并为每个网站提供 Bonnie Kearney access，具体方法是将其登录名添加到网站的成员组 (**ForEach {get-spouser-site $ \_ 。Url-Person.loginname "bkearney \@ litwareinc.com"-Group "Members"}**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-222">The interpretation of this PowerShell command is: Get all the SharePoint sites in the current Microsoft 365 subscription and for each site allow Bonnie Kearney access by adding her login name to the Members group of the site (**ForEach {Add-SPOUser -Site $\_.Url -LoginName "bkearney\@litwareinc.com" -Group "Members"}**).</span></span>
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a><span data-ttu-id="a823d-223">适用于 Microsoft 365 的 PowerShell 非常适合筛选数据</span><span class="sxs-lookup"><span data-stu-id="a823d-223">PowerShell for Microsoft 365 is great at filtering data</span></span>

<span data-ttu-id="a823d-224">Microsoft 365 管理中心提供了几种筛选数据的方法，以便轻松找到目标信息子集。</span><span class="sxs-lookup"><span data-stu-id="a823d-224">The Microsoft 365 admin center provides several ways to filter your data to easily locate a targeted subset of information.</span></span> <span data-ttu-id="a823d-225">例如，可以通过 Exchange 轻松筛选用户邮箱的几乎所有属性。</span><span class="sxs-lookup"><span data-stu-id="a823d-225">For example, Exchange makes it easy to filter on practically any property of a user mailbox.</span></span> <span data-ttu-id="a823d-226">例如，以下是居住在布卢明顿城市中的所有用户的邮箱列表：</span><span class="sxs-lookup"><span data-stu-id="a823d-226">For example, here's the list of mailboxes for all the users who live in the city of Bloomington:</span></span>
  
![在 Microsoft 365 管理中心中执行高级搜索的示例，用于居住在布卢明顿城市的所有用户的邮箱列表。](../media/o365-powershell-advanced-search.png)
  
<span data-ttu-id="a823d-228">Exchange 管理中心还允许您组合筛选条件。</span><span class="sxs-lookup"><span data-stu-id="a823d-228">The Exchange Admin center also lets you combine filter criteria.</span></span> <span data-ttu-id="a823d-229">例如，您可以查找居住在布卢明顿中的所有人的邮箱，并在财务部门工作。</span><span class="sxs-lookup"><span data-stu-id="a823d-229">For example, you can find the mailboxes for all the people who live in Bloomington and work in the Finance department.</span></span>
  
<span data-ttu-id="a823d-230">但您可以在 Exchange 管理中心中执行的操作有一些限制。</span><span class="sxs-lookup"><span data-stu-id="a823d-230">But there are limitations to what you can do in the Exchange Admin center.</span></span> <span data-ttu-id="a823d-231">例如，您无法轻松找到居住在布卢明顿 *或* 圣地亚哥的用户的邮箱，或者无法找到布卢明顿中未居住的所有用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a823d-231">For example, you couldn't as easily find the mailboxes of people who live in Bloomington *or* San Diego, or the mailboxes for all people who don't live in Bloomington.</span></span>
  
<span data-ttu-id="a823d-232">您可以使用以下 PowerShell for Microsoft 365 命令获取邮箱列表，以获取居住在布卢明顿或圣地亚哥的所有人员的邮箱列表：</span><span class="sxs-lookup"><span data-stu-id="a823d-232">You can use the following PowerShell for Microsoft 365 command to get a list of mailboxes for all the people who live in Bloomington or San Diego:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

<span data-ttu-id="a823d-233">下面是结果的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-233">Here's an example of the results:</span></span>
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

<span data-ttu-id="a823d-234">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户，这些用户在 San 圣地亚哥或布卢明顿的城市中拥有邮箱（ **其中 {$） (其中的邮箱 \_ 。RecipientTypeDetails-eq "UserMailbox"-和 ($ \_ 。City-eq "圣地亚哥"-或 $ \_ 。City-eq "布卢明顿" ) }**) ，然后显示每个 (的姓名和城市 **选择 "DisplayName"、"city**) "。</span><span class="sxs-lookup"><span data-stu-id="a823d-234">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox in the city of San Diego or Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**), and then display the name and city for each (**Select DisplayName, City**).</span></span>
  
<span data-ttu-id="a823d-235">下面的命令可列出除布卢明顿以外的生活在任何位置的用户的所有邮箱：</span><span class="sxs-lookup"><span data-stu-id="a823d-235">And here's the command to list all the mailboxes for people who live anywhere except Bloomington:</span></span>
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

<span data-ttu-id="a823d-236">下面是结果的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-236">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="a823d-237">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的邮箱不位于 (布卢明顿的城市中的所有用户 **{$ \_ 。RecipientTypeDetails-eq "UserMailbox" 和 $ \_ 。City-ne "布卢明顿"}**) ，然后显示每个城市的姓名和城市。</span><span class="sxs-lookup"><span data-stu-id="a823d-237">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription who have a mailbox not located in the city of Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_.City -ne "Bloomington"}**), and then display the name and city for each.</span></span>
  
### <a name="use-wildcards"></a><span data-ttu-id="a823d-238">使用通配符</span><span class="sxs-lookup"><span data-stu-id="a823d-238">Use wildcards</span></span>

<span data-ttu-id="a823d-239">您还可以在 PowerShell 筛选器中使用通配符，以匹配名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="a823d-239">You can also use wildcard characters in your PowerShell filters to match part of a name.</span></span> <span data-ttu-id="a823d-240">例如，假设您正在寻找用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a823d-240">For example, suppose you're looking for a user account.</span></span> <span data-ttu-id="a823d-241">您可以记住的是，用户的姓是 *Anderson* ，或者可能是 *Henderson* 或 *Jorgenson*。</span><span class="sxs-lookup"><span data-stu-id="a823d-241">All you can remember is that the user's last name was *Anderson* or maybe *Henderson* or *Jorgenson*.</span></span>
  
<span data-ttu-id="a823d-242">您可以使用搜索工具在 Microsoft 365 管理中心内跟踪该用户并执行三种不同的搜索：</span><span class="sxs-lookup"><span data-stu-id="a823d-242">You could track down that user in the Microsoft 365 admin center by using the search tool and carrying out three different searches:</span></span>
  
- <span data-ttu-id="a823d-243">一次是搜索  *Anderson*</span><span class="sxs-lookup"><span data-stu-id="a823d-243">One for  *Anderson*</span></span> 
    
- <span data-ttu-id="a823d-244">一次是搜索  *Henderson*</span><span class="sxs-lookup"><span data-stu-id="a823d-244">One for  *Henderson*</span></span> 
    
- <span data-ttu-id="a823d-245">一次是搜索  *Jorgenson*</span><span class="sxs-lookup"><span data-stu-id="a823d-245">One for  *Jorgenson*</span></span> 
    
<span data-ttu-id="a823d-246">由于所有这三个名称都以 "儿子" 结束，因此您可以告知 PowerShell 显示姓名以 "儿子" 结尾的所有用户。</span><span class="sxs-lookup"><span data-stu-id="a823d-246">Because all three of these names end in "son", you can tell PowerShell to display all the users whose name ends in "son".</span></span> <span data-ttu-id="a823d-247">以下命令如下所示：</span><span class="sxs-lookup"><span data-stu-id="a823d-247">Here's the command:</span></span>
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

<span data-ttu-id="a823d-248">此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户，但使用仅列出姓氏以 "儿子" 结尾的用户的筛选器 (**筛选器 "{LastName-like" 子 \* 儿子 "}"**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-248">The interpretation of this PowerShell command is: Get all the users in the current Microsoft 365 subscription, but use a filter that only lists the users whose last names end in "son" (**-Filter '{LastName -like "\*son"}'**).</span></span> <span data-ttu-id="a823d-249">\*代表任意一组字符，这些字符是用户的姓氏中的字母。</span><span class="sxs-lookup"><span data-stu-id="a823d-249">The \* stands for any set of characters, which are letters in the user's last name.</span></span>
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a><span data-ttu-id="a823d-250">适用于 Microsoft 365 的 PowerShell 可轻松打印或保存数据</span><span class="sxs-lookup"><span data-stu-id="a823d-250">PowerShell for Microsoft 365 makes it easy to print or save data</span></span>

<span data-ttu-id="a823d-251">Microsoft 365 管理中心允许你查看数据列表。</span><span class="sxs-lookup"><span data-stu-id="a823d-251">The Microsoft 365 admin center lets you view lists of data.</span></span> <span data-ttu-id="a823d-252">以下是 Skype for business Online 管理中心的示例，其中显示已为 Skype for business Online 启用的用户的列表：</span><span class="sxs-lookup"><span data-stu-id="a823d-252">Here's an example of the Skype for Business Online admin center displaying a list of users who have been enabled for Skype for Business Online:</span></span>
  
![用于显示已为 Skype for Business Online 启用的用户列表的 Skype for Business Online 管理中心的示例。](../media/o365-powershell-lync-users.png)
  
<span data-ttu-id="a823d-254">若要将该信息保存到文件中，则必须将其粘贴到文档或 Microsoft Excel 工作表中。</span><span class="sxs-lookup"><span data-stu-id="a823d-254">To save that information to a file, you must paste it into a document or Microsoft Excel worksheet.</span></span> <span data-ttu-id="a823d-255">任意一种情况都可能需要其他格式。</span><span class="sxs-lookup"><span data-stu-id="a823d-255">Either case might require additional formatting.</span></span> <span data-ttu-id="a823d-256">此外，Microsoft 365 管理中心不提供直接打印显示列表的方法。</span><span class="sxs-lookup"><span data-stu-id="a823d-256">Additionally, the Microsoft 365 admin center doesn't provide a way to directly print the displayed list.</span></span>
  
<span data-ttu-id="a823d-257">幸运的是，您可以使用 PowerShell 不仅显示列表，还可以将其保存到可轻松导入 Excel 的文件中。</span><span class="sxs-lookup"><span data-stu-id="a823d-257">Fortunately, you can use PowerShell to not only display the list but to save it to a file that can be easily imported into Excel.</span></span> <span data-ttu-id="a823d-258">下面的命令示例将 Skype for Business Online 用户数据保存为逗号分隔的值 (CSV) 文件，然后可以在 Excel 工作表中轻松地将其作为表导入：</span><span class="sxs-lookup"><span data-stu-id="a823d-258">Here's an example command to save Skype for Business Online user data to a comma-separated values (CSV) file, which can then be easily imported as a table in an Excel worksheet:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

<span data-ttu-id="a823d-259">下面是结果的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-259">Here's an example of the results:</span></span>
  
![为保存到逗号分隔值文件的 Skype for business Online 用户数据导入到 Excel 工作表中的表的示例。](../media/o365-powershell-data-in-excel.png)
  
<span data-ttu-id="a823d-261">此 PowerShell 命令的解释为：在当前 Microsoft 365 订阅中获取所有 Skype for Business Online 用户 (**get-csonlineuser**) ;仅获取用户名、UPN 和位置 (**选择 DisplayName、UserPrincipalName、UsageLocation**) ;，然后将该信息保存在名为 C： logsSfBUsers.csv 的 CSV 文件中 \\ \\ (**导出-CSV-路径 "C： \\ Logs \\SfBUsers.csv"-NoTypeInformation**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-261">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription (**Get-CsOnlineUser**); obtain only the user name, UPN, and location (**Select DisplayName, UserPrincipalName, UsageLocation**); and then save that information in a CSV file named C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\SfBUsers.csv" -NoTypeInformation**).</span></span>
  
<span data-ttu-id="a823d-262">您还可以使用选项将此列表另存为 XML 文件或 HTML 页面。</span><span class="sxs-lookup"><span data-stu-id="a823d-262">You can also use options to save this list as an XML file or an HTML page.</span></span> <span data-ttu-id="a823d-263">事实上，使用其他 PowerShell 命令，您可以将其直接保存为 Excel 文件，并使用所需的任何自定义格式。</span><span class="sxs-lookup"><span data-stu-id="a823d-263">In fact, with additional PowerShell commands, you could save it directly as an Excel file, with any custom formatting you want.</span></span>
  
<span data-ttu-id="a823d-264">您还可以向 Windows 中的默认打印机发送直接显示列表的 PowerShell 命令的输出。</span><span class="sxs-lookup"><span data-stu-id="a823d-264">You can also send the output of a PowerShell command that displays a list directly to the default printer in Windows.</span></span> <span data-ttu-id="a823d-265">下面是一个示例命令：</span><span class="sxs-lookup"><span data-stu-id="a823d-265">Here's an example command:</span></span>
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

<span data-ttu-id="a823d-266">打印的文档如下所示：</span><span class="sxs-lookup"><span data-stu-id="a823d-266">Here's what your printed document will look like:</span></span>
  
![在 Windows 中直接发送到默认打印机的 PowerShell 命令输出的打印文档的示例。](../media/o365-powershell-printed-data.png)
  
<span data-ttu-id="a823d-268">此 PowerShell 命令的解释为：在当前 Microsoft 365 订阅中获取所有 Skype for Business Online 用户;仅获取用户名称、UPN 和位置;，然后将该信息发送到默认的 Windows 打印机 (**打印机**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-268">The interpretation of this PowerShell command is: Get all the Skype for Business Online users in the current Microsoft 365 subscription; obtain only the user name, UPN, and location; and then send that information to the default Windows printer (**Out-Printer**).</span></span>
  
<span data-ttu-id="a823d-269">打印的文档与 PowerShell 命令窗口中显示的简单格式相同。</span><span class="sxs-lookup"><span data-stu-id="a823d-269">The printed document has the same simple formatting as the display in the PowerShell command window.</span></span> <span data-ttu-id="a823d-270">若要获取硬副本，只需添加 **|打印机** 到命令的末尾。</span><span class="sxs-lookup"><span data-stu-id="a823d-270">To get a hard copy, just add **| Out-Printer** to the end of the command.</span></span>
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a><span data-ttu-id="a823d-271">PowerShell for Microsoft 365 允许您跨服务器产品进行管理</span><span class="sxs-lookup"><span data-stu-id="a823d-271">PowerShell for Microsoft 365 lets you manage across server products</span></span>

<span data-ttu-id="a823d-272">组成 Microsoft 365 的组件旨在协同工作。</span><span class="sxs-lookup"><span data-stu-id="a823d-272">The components that make up Microsoft 365 are designed to work together.</span></span> <span data-ttu-id="a823d-273">例如，假设您将一个新用户添加到 Microsoft 365，并指定用户的部门和电话号码等信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-273">For example, suppose you add a new user to Microsoft 365, and you specify such information as the user's department and phone number.</span></span> <span data-ttu-id="a823d-274">如果您访问任何 Microsoft 365 服务中的用户信息，则该信息将可用： Skype for Business Online、Exchange 或 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a823d-274">That information will then be available if you access the user's information in any of the Microsoft 365 services: Skype for Business Online, Exchange, or SharePoint.</span></span>
  
<span data-ttu-id="a823d-275">不过，此规则适用于跨产品套件的一般信息。</span><span class="sxs-lookup"><span data-stu-id="a823d-275">But that's for common information that spans the suite of products.</span></span> <span data-ttu-id="a823d-276">特定于产品的信息（如有关用户的 Exchange 邮箱的信息）通常不在套件中提供。</span><span class="sxs-lookup"><span data-stu-id="a823d-276">Product-specific information, such as information about a user's Exchange mailbox, isn't typically available across the suite.</span></span> <span data-ttu-id="a823d-277">例如，有关是否启用了用户邮箱的信息仅适用于 Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="a823d-277">For example, information about whether a user's mailbox is enabled or not is available only in the Exchange admin center.</span></span>
  
<span data-ttu-id="a823d-278">假设您要为您的所有用户生成显示以下信息的报告：</span><span class="sxs-lookup"><span data-stu-id="a823d-278">Suppose you'd like to make a report that shows the following information for all your users:</span></span>
  
- <span data-ttu-id="a823d-279">用户的显示名称</span><span class="sxs-lookup"><span data-stu-id="a823d-279">The user's display name</span></span>
    
- <span data-ttu-id="a823d-280">用户是否已获得适用于 Microsoft 365 的许可</span><span class="sxs-lookup"><span data-stu-id="a823d-280">Whether the user is licensed for Microsoft 365</span></span>
    
- <span data-ttu-id="a823d-281">用户的 Exchange 邮箱是否已启用</span><span class="sxs-lookup"><span data-stu-id="a823d-281">Whether the user's Exchange mailbox has been enabled</span></span>
    
- <span data-ttu-id="a823d-282">用户是否已启用 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a823d-282">Whether the user is enabled for Skype for Business Online</span></span>
    
<span data-ttu-id="a823d-283">您无法轻松在 Microsoft 365 管理中心生成此类报告。</span><span class="sxs-lookup"><span data-stu-id="a823d-283">You can't easily produce such a report in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a823d-284">相反，您必须创建单独的文档来存储信息，例如 Excel 工作表。</span><span class="sxs-lookup"><span data-stu-id="a823d-284">Instead, you would have to create a separate document to store the information, such as an Excel worksheet.</span></span> <span data-ttu-id="a823d-285">然后，从 Microsoft 365 管理中心获取所有用户名和许可信息，从 Exchange 管理中心获取邮箱信息，从 Skype for business Online 管理中心获取 Skype for Business Online 信息，然后将这些信息组合在一起。</span><span class="sxs-lookup"><span data-stu-id="a823d-285">Then, get all the user names and licensing information from the Microsoft 365 admin center, get mailbox information from the Exchange Admin center, get Skype for Business Online information from the Skype for Business Online Admin center, and then combine that information.</span></span>
  
<span data-ttu-id="a823d-286">另一种方法是使用 PowerShell 脚本为您编译报告。</span><span class="sxs-lookup"><span data-stu-id="a823d-286">The alternative is to use a PowerShell script to compile the report for you.</span></span>
  
<span data-ttu-id="a823d-287">下面的示例脚本比您在本文中已看过的命令更复杂。</span><span class="sxs-lookup"><span data-stu-id="a823d-287">The following example script is more complicated than the commands you've seen so far in this article.</span></span> <span data-ttu-id="a823d-288">但是，它展示了使用 PowerShell 创建难以以其他方式获取的信息视图的可能性。</span><span class="sxs-lookup"><span data-stu-id="a823d-288">But, it shows the potential of using PowerShell to create information views that are difficult to get otherwise.</span></span> <span data-ttu-id="a823d-289">下面的脚本用于编译和显示所需的列表：</span><span class="sxs-lookup"><span data-stu-id="a823d-289">Here's the script to compile and display the list you need:</span></span>
  
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

<span data-ttu-id="a823d-290">下面是结果的一个示例：</span><span class="sxs-lookup"><span data-stu-id="a823d-290">Here's an example of the results:</span></span>
  
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

<span data-ttu-id="a823d-291">此 PowerShell 脚本的解释如下：</span><span class="sxs-lookup"><span data-stu-id="a823d-291">The interpretation of this PowerShell script is:</span></span>  

1. <span data-ttu-id="a823d-292">获取当前 Microsoft 365 订阅中的所有用户，并将信息存储在名为 *$x* (**$x = AzureADUser**) 的变量中。</span><span class="sxs-lookup"><span data-stu-id="a823d-292">Get all the users in the current Microsoft 365 subscription and store the information in a variable that's named *$x* (**$x = Get-AzureADUser**).</span></span>
1. <span data-ttu-id="a823d-293">启动在变量中的所有用户上运行的循环 $x (\*\*foreach ($i $x \*\*) ) 中。</span><span class="sxs-lookup"><span data-stu-id="a823d-293">Start a loop that runs over all the users in the variable $x (**foreach ($i in $x)**).</span></span>  
1. <span data-ttu-id="a823d-294">定义一个名为 *$y* 的变量，并将用户的邮箱信息存储在其中 (**$y = Get-Mailbox 标识 $i** 。</span><span class="sxs-lookup"><span data-stu-id="a823d-294">Define a variable named *$y* and store the user's mailbox information in it (**$y = Get-Mailbox -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="a823d-295">将新属性添加到名为 *IsMailBoxEnabled*的用户信息中。</span><span class="sxs-lookup"><span data-stu-id="a823d-295">Add a new property to the user information that's named *IsMailBoxEnabled*.</span></span> <span data-ttu-id="a823d-296">将其设置为用户邮箱的 IsMailBoxEnabled 属性的值 (**$i | Add-Member MemberType NoteProperty-Name IsMailBoxEnabled-value $Y IsMailBoxEnabled**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-296">Set it to the value of the IsMailBoxEnabled property of the user's mailbox (**$i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**).</span></span>
1. <span data-ttu-id="a823d-297">定义一个名为 *$y*的变量，并将用户的 Skype For business Online 信息存储在其中 (**$Y = Get-CsOnlineUser 身份 $i**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-297">Define a variable named *$y*, and store the user's Skype for Business Online information in it (**$y = Get-CsOnlineUser -Identity $i.UserPrincipalName**).</span></span>
1. <span data-ttu-id="a823d-298">将新属性添加到名为 *EnabledForSfB*的用户信息中。</span><span class="sxs-lookup"><span data-stu-id="a823d-298">Add a new property to the user information that's named *EnabledForSfB*.</span></span> <span data-ttu-id="a823d-299">将其设置为用户的 Skype for Business Online 信息的 Enabled 属性的值 (**$i | Add-Member-MemberType NoteProperty-Name EnabledForSfB-value $y。已启用**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-299">Set it to the value of the Enabled property of the user's Skype for Business Online information (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**).</span></span>
1. <span data-ttu-id="a823d-300">显示用户列表，但仅包括其名称、是否已获得许可，以及两个新属性，它们分别指示其邮箱是否已启用以及是否为 Skype for business Online 启用了这些用户 (**$x |选择 DisplayName、IsLicensed、IsMailboxEnabled、EnabledforSfB**) 。</span><span class="sxs-lookup"><span data-stu-id="a823d-300">Display the list of users, but include only their name, whether they are licensed, and the two new properties that indicate whether their mailbox is enabled and whether they are enabled for Skype for Business Online (**$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB**).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a823d-301">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a823d-301">See also</span></span>

[<span data-ttu-id="a823d-302">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="a823d-302">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a823d-303">使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组</span><span class="sxs-lookup"><span data-stu-id="a823d-303">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a823d-304">使用 Windows PowerShell 在 Microsoft 365 中创建报告</span><span class="sxs-lookup"><span data-stu-id="a823d-304">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
