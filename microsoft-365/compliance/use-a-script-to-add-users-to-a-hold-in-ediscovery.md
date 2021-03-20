---
title: 使用脚本将用户添加到核心电子数据展示案例中的保留
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: 了解如何运行脚本，将 OneDrive for Business &邮箱添加到与 Microsoft 365 合规中心中的电子数据展示案例相关联的新保留中。
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909912"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="8797f-103">使用脚本将用户添加到核心电子数据展示案例中的保留</span><span class="sxs-lookup"><span data-stu-id="8797f-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="8797f-104">安全&中心 PowerShell 提供了 cmdlet，让你可以自动执行与创建和管理电子数据展示事例相关的耗时任务。</span><span class="sxs-lookup"><span data-stu-id="8797f-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="8797f-105">目前，使用安全与合规&核心电子数据展示案例将大量保管人内容位置放在保留状态需要时间和准备。</span><span class="sxs-lookup"><span data-stu-id="8797f-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="8797f-106">例如，创建保留之前，必须收集要保留的每个 OneDrive for Business 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="8797f-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="8797f-107">然后，对于要置于保留状态的每一位用户，您必须将其邮箱及其 OneDrive for Business 网站添加到保留状态。</span><span class="sxs-lookup"><span data-stu-id="8797f-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="8797f-108">您可以使用本文中的脚本自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="8797f-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="8797f-109">该脚本会提示您输入您组织的"我的网站"域 (的名称，例如，在 URL 中，现有电子数据展示案例的名称，与该案例关联的新保留的名称，要置于保留状态的用户的电子邮件地址列表，以及创建基于查询的保留时将使用的搜索查询。 `contoso` https://contoso-my.sharepoint.com)</span><span class="sxs-lookup"><span data-stu-id="8797f-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="8797f-110">然后，脚本为列表中的每个用户获取 OneDrive for Business 网站的 URL，创建新的保留，然后将列表中的每个用户的邮箱和 OneDrive for Business 网站添加到保留项。</span><span class="sxs-lookup"><span data-stu-id="8797f-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="8797f-111">该脚本还会生成包含有关新保留的信息的日志文件。</span><span class="sxs-lookup"><span data-stu-id="8797f-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="8797f-112">以下是实现此目标的步骤：</span><span class="sxs-lookup"><span data-stu-id="8797f-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="8797f-113">步骤 1：安装 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="8797f-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="8797f-114">步骤 2：生成用户列表</span><span class="sxs-lookup"><span data-stu-id="8797f-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="8797f-115">步骤 3：运行脚本以创建保留并添加用户</span><span class="sxs-lookup"><span data-stu-id="8797f-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="8797f-116">将用户添加到保留项之前</span><span class="sxs-lookup"><span data-stu-id="8797f-116">Before you add users to a hold</span></span>

- <span data-ttu-id="8797f-117">您必须是安全与合规中心内电子数据展示管理员角色组的成员& SharePoint Online 管理员才能运行步骤 3 中的脚本。</span><span class="sxs-lookup"><span data-stu-id="8797f-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="8797f-118">有关详细信息，请参阅在 [Office 365](assign-ediscovery-permissions.md)安全与合规中心&电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="8797f-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="8797f-119">在安全与合规中心内，最多可以将 1，000 个邮箱和 100 个网站添加到与电子数据展示&保留。</span><span class="sxs-lookup"><span data-stu-id="8797f-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="8797f-120">假设你想要保留的每个用户都有一个 OneDrive for Business 网站，则使用本文中的脚本最多可将 100 个用户添加到保留中。</span><span class="sxs-lookup"><span data-stu-id="8797f-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="8797f-121">请确保将步骤 2 中创建的用户列表和步骤 3 中的脚本保存到同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8797f-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="8797f-122">这样更易于运行脚本。</span><span class="sxs-lookup"><span data-stu-id="8797f-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="8797f-123">该脚本将用户列表添加到与现有案例关联的新保留中。</span><span class="sxs-lookup"><span data-stu-id="8797f-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="8797f-124">在运行脚本之前，请确保已创建要与保留关联的案例。</span><span class="sxs-lookup"><span data-stu-id="8797f-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="8797f-125">本文中的脚本支持在连接到安全与合规中心 PowerShell & SharePoint Online 命令行管理程序时进行新式验证。</span><span class="sxs-lookup"><span data-stu-id="8797f-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="8797f-126">如果你是 Microsoft 365 或 Microsoft 365 GCC 组织，你可以像现在一样使用脚本。</span><span class="sxs-lookup"><span data-stu-id="8797f-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="8797f-127">如果您是 Office 365 Germany 组织、Microsoft 365 GCC High 组织或 Microsoft 365 DoD 组织，您必须编辑脚本以成功运行它。</span><span class="sxs-lookup"><span data-stu-id="8797f-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="8797f-128">具体而言，您必须编辑行，并使用 `Connect-IPPSSession` *ConnectionUri* 和 *AzureADAuthorizationEndpointUri* 参数 (以及组织类型) 的适当值连接到安全 & 合规中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8797f-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="8797f-129">有关详细信息，请参阅 Connect to [Security & Compliance Center PowerShell 中的示例](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)。</span><span class="sxs-lookup"><span data-stu-id="8797f-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="8797f-130">该脚本会自动从安全与合规& PowerShell 和 SharePoint Online 命令行管理程序断开连接。</span><span class="sxs-lookup"><span data-stu-id="8797f-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="8797f-131">该脚本包括最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="8797f-131">The script includes minimal error handling.</span></span> <span data-ttu-id="8797f-132">其主要用途是快速轻松地将每个用户的邮箱和 OneDrive for Business 网站置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="8797f-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="8797f-p109">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="8797f-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="8797f-138">步骤 1：安装 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="8797f-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="8797f-139">第一步是在本地计算机上安装 SharePoint Online 命令行管理程序（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="8797f-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="8797f-140">不必在此过程中使用命令行管理程序，但必须安装它，因为它包含步骤 3 中运行的脚本所需的先决条件。</span><span class="sxs-lookup"><span data-stu-id="8797f-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="8797f-141">这些先决条件允许脚本与 SharePoint Online 通信，获取 OneDrive for Business 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="8797f-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="8797f-142">转到设置 [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 命令行管理程序 Windows PowerShell 环境，并执行步骤 1 和步骤 2 以在本地计算机上安装 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="8797f-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="8797f-143">步骤 2：生成用户列表</span><span class="sxs-lookup"><span data-stu-id="8797f-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="8797f-144">步骤 3 中的脚本将创建与电子数据展示案例关联的保留，并添加用户列表的邮箱和 OneDrive for Business 网站。</span><span class="sxs-lookup"><span data-stu-id="8797f-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="8797f-145">只需在文本文件中键入电子邮件地址，或者可以在 Windows PowerShell 中运行命令，获取电子邮件地址列表并将其保存到位于步骤 3) 中将脚本保存到的同一文件夹中的 (文件中。</span><span class="sxs-lookup"><span data-stu-id="8797f-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="8797f-146">下面是一个 PowerShell 命令 (，通过使用连接到 Exchange Online 组织的远程 PowerShell) 获取组织中所有用户的电子邮件地址列表，并将其保存到名为 HoldUsers.txt 的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="8797f-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="8797f-147">运行此命令后，打开文本文件并删除包含属性名称 的 标头  `PrimarySmtpAddress` 。</span><span class="sxs-lookup"><span data-stu-id="8797f-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="8797f-148">然后删除除要添加到将在步骤 3 创建的保留中的用户的电子邮件地址之外的所有电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8797f-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="8797f-149">确保电子邮件地址列表之前或之后没有空行。</span><span class="sxs-lookup"><span data-stu-id="8797f-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="8797f-150">步骤 3：运行脚本以创建保留并添加用户</span><span class="sxs-lookup"><span data-stu-id="8797f-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="8797f-151">在此步骤中运行脚本时，它将提示您输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="8797f-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="8797f-152">在运行脚本之前，请务必准备好此信息。</span><span class="sxs-lookup"><span data-stu-id="8797f-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="8797f-153">**你的用户凭据：** 该脚本将使用你的凭据通过 PowerShell &安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="8797f-153">**Your user credentials:** The script will use your credentials to connect to Security & Compliance Center with PowerShell.</span></span> <span data-ttu-id="8797f-154">它还将使用这些凭据访问 SharePoint Online，获取用户列表的 OneDrive for Business URL。</span><span class="sxs-lookup"><span data-stu-id="8797f-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="8797f-155">**SharePoint 域的名称：** 脚本会提示你输入此名称，以便可以连接到 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="8797f-155">**Name of your SharePoint domain:** The script prompts you to enter this name so it can connect to the SharePoint admin center.</span></span> <span data-ttu-id="8797f-156">它还使用组织中 OneDrive URL 的域名。</span><span class="sxs-lookup"><span data-stu-id="8797f-156">It also uses the domain name for the OneDrive URLs in your organization.</span></span> <span data-ttu-id="8797f-157">例如，如果管理中心的 URL 为 ，OneDrive 的 URL 为 ，则当脚本提示你输入域名时 `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` ，将输入 。</span><span class="sxs-lookup"><span data-stu-id="8797f-157">For example, if the URL for your admin center is `https://contoso-admin.sharepoint.com` and the URL for OneDrive is `https://contoso-my.sharepoint.com`, then you would enter `contoso` when the script prompts you for your domain name.</span></span>

- <span data-ttu-id="8797f-158">**案例名称：** 现有案例的名称。</span><span class="sxs-lookup"><span data-stu-id="8797f-158">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="8797f-159">脚本将创建与这种情况相关联的新保留。</span><span class="sxs-lookup"><span data-stu-id="8797f-159">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="8797f-160">**保留的名称：** 脚本将创建并关联到指定案例的保留名称。</span><span class="sxs-lookup"><span data-stu-id="8797f-160">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="8797f-161">**基于查询的保留的搜索查询：** 您可以创建基于查询的保留，以便仅将满足指定搜索条件的内容置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="8797f-161">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="8797f-162">若要保留所有内容 **，只需在** 系统提示您进行搜索查询时按 Enter。</span><span class="sxs-lookup"><span data-stu-id="8797f-162">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="8797f-163">**是否打开保留：** 可以在脚本创建后将其打开，也可以让脚本在不启用保留的情况下创建保留。</span><span class="sxs-lookup"><span data-stu-id="8797f-163">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="8797f-164">如果脚本尚未打开，可以在安全与合规中心稍后或运行以下 PowerShell 命令&启用脚本：</span><span class="sxs-lookup"><span data-stu-id="8797f-164">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="8797f-165">**包含用户列表的** 文本文件的名称 - 步骤 2 中包含要添加到保留项的用户列表的文本文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8797f-165">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="8797f-166">如果此文件与脚本位于同一文件夹中，只需键入该文件的名称 (例如，HoldUsers.txt) 。</span><span class="sxs-lookup"><span data-stu-id="8797f-166">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="8797f-167">如果文本文件位于另一个文件夹中，请键入该文件的完整路径名。</span><span class="sxs-lookup"><span data-stu-id="8797f-167">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="8797f-168">收集脚本将提示您输入的信息后，最后一步是运行脚本以创建新保留并添加用户。</span><span class="sxs-lookup"><span data-stu-id="8797f-168">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="8797f-169">使用 文件名后缀将以下Windows PowerShell保存到脚本文件中 `.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="8797f-169">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="8797f-170">例如，`AddUsersToHold.ps1`。</span><span class="sxs-lookup"><span data-stu-id="8797f-170">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="8797f-171">在本地计算机上，打开Windows PowerShell转到保存脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8797f-171">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="8797f-172">运行脚本;例如：</span><span class="sxs-lookup"><span data-stu-id="8797f-172">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="8797f-173">输入脚本提示您输入的信息。</span><span class="sxs-lookup"><span data-stu-id="8797f-173">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="8797f-174">该脚本连接到安全&合规中心 PowerShell，然后在电子数据展示案例中创建新的保留，并将邮箱和 OneDrive for Business 添加到列表中的用户。</span><span class="sxs-lookup"><span data-stu-id="8797f-174">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="8797f-175">你可以转到安全与合规中心的" **电子** 数据展示"页面上&查看新保留。</span><span class="sxs-lookup"><span data-stu-id="8797f-175">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="8797f-176">脚本运行完成后，它会创建以下日志文件，并保存到脚本所在的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8797f-176">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="8797f-177">**LocationsOnHold.txt：** 包含脚本成功置于保留的邮箱和 OneDrive for Business 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="8797f-177">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="8797f-178">**LocationsNotOnHold.txt：** 包含脚本未置于保留的邮箱和 OneDrive for Business 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="8797f-178">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="8797f-179">如果用户有邮箱，但没有 OneDrive for Business 网站，该用户将包含在未置于保留的 OneDrive for Business 网站列表中。</span><span class="sxs-lookup"><span data-stu-id="8797f-179">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="8797f-180">**GetCaseHoldPolicy.txt：** 包含新保留的 **Get-CaseHoldPolicy** cmdlet 的输出，脚本将在创建新保留后运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8797f-180">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="8797f-181">此 cmdlet 返回的信息包括其邮箱和 OneDrive for Business 网站处于保留状态的用户列表，以及是启用还是禁用保留。</span><span class="sxs-lookup"><span data-stu-id="8797f-181">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="8797f-182">**GetCaseHoldRule.txt：** 包含新保留的 **Get-CaseHoldRule** cmdlet 的输出，脚本将在创建新保留后运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8797f-182">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="8797f-183">如果您使用脚本创建基于查询的保留，此 cmdlet 返回的信息将包含搜索查询。</span><span class="sxs-lookup"><span data-stu-id="8797f-183">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>