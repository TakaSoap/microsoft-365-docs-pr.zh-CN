---
title: 使用 PowerShell 为 Microsoft 365 分配每用户 Skype for Business Online 策略
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 摘要：使用 PowerShell for Microsoft 365 通过 Skype for Business Online 策略分配每用户通信设置。
ms.openlocfilehash: 6ee237e5d2ee0c9f472f372a6aa66c9612336265
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514976"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="32f42-103">使用 PowerShell 为 Microsoft 365 分配每用户 Skype for Business Online 策略</span><span class="sxs-lookup"><span data-stu-id="32f42-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="32f42-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="32f42-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="32f42-105">使用适用于 Microsoft 365 的 PowerShell 是使用 Skype for Business Online 策略分配每用户通信设置的一种有效方法。</span><span class="sxs-lookup"><span data-stu-id="32f42-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="32f42-106">准备运行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="32f42-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="32f42-107">使用以下说明进行设置以运行命令 (跳过已完成) ：</span><span class="sxs-lookup"><span data-stu-id="32f42-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="32f42-108">Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="32f42-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="32f42-109">如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="32f42-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="32f42-110">安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="32f42-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="32f42-111">开启 Windows PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="32f42-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="32f42-112">系统提示时，输入 Skype for Business Online 管理员帐户名和密码。</span><span class="sxs-lookup"><span data-stu-id="32f42-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="32f42-113">更新用户帐户的外部通信设置</span><span class="sxs-lookup"><span data-stu-id="32f42-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="32f42-114">假设您要更改用户帐户上的外部通信设置。</span><span class="sxs-lookup"><span data-stu-id="32f42-114">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="32f42-115">例如，您希望允许 Alex 与联盟用户通信 (EnableFederationAccess 等于 True) 但不与 Windows Live 用户 (EnablePublicCloudAccess 等于 False) 。</span><span class="sxs-lookup"><span data-stu-id="32f42-115">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="32f42-116">为此，需要执行两项操作：</span><span class="sxs-lookup"><span data-stu-id="32f42-116">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="32f42-117">找到符合我们的条件的外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="32f42-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="32f42-118">将该外部访问策略分配给 Alex。</span><span class="sxs-lookup"><span data-stu-id="32f42-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="32f42-119">如何确定要分配 Alex 的外部访问策略？</span><span class="sxs-lookup"><span data-stu-id="32f42-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="32f42-120">以下命令返回在 EnableFederationAccess 设置为 True 且 EnablePublicCloudAccess 设置为 False 时的所有外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="32f42-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="32f42-121">除非您已创建 ExternalAccessPolicy 的任何自定义实例，否则该命令将返回一个符合 FederationOnly (条件) 。</span><span class="sxs-lookup"><span data-stu-id="32f42-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="32f42-122">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="32f42-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="32f42-123">现在，你已知道要分配给 Alex 的策略，我们可以使用 [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) cmdlet 分配该策略。</span><span class="sxs-lookup"><span data-stu-id="32f42-123">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) cmdlet.</span></span> <span data-ttu-id="32f42-124">如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="32f42-124">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="32f42-125">分配策略非常简单：只需指定用户的标识和要分配的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="32f42-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="32f42-126">对于策略和策略分配，不限于一次使用一个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="32f42-126">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="32f42-127">例如，假设您需要获得可与联盟伙伴和 Windows Live 用户通信的所有用户的列表。</span><span class="sxs-lookup"><span data-stu-id="32f42-127">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="32f42-128">我们已经知道，这些用户已分配有外部用户访问策略 FederationAndPICDefault。</span><span class="sxs-lookup"><span data-stu-id="32f42-128">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="32f42-129">因为我们知道，您可以通过运行一个简单的命令来显示所有这些用户的列表。</span><span class="sxs-lookup"><span data-stu-id="32f42-129">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="32f42-130">命令如下：</span><span class="sxs-lookup"><span data-stu-id="32f42-130">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="32f42-131">换句话说，向我们显示 ExternalAccessPolicy 属性设置为 FederationAndPICDefault 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="32f42-131">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="32f42-132"> (，为了限制屏幕上显示的信息量，请使用 Select-Object cmdlet 向我们仅显示每个用户的 显示名称.) </span><span class="sxs-lookup"><span data-stu-id="32f42-132">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="32f42-133">若要配置所有用户帐户以使用同一策略，请使用此命令：</span><span class="sxs-lookup"><span data-stu-id="32f42-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="32f42-134">此命令使用 Get-CsOnlineUser 返回已启用 Lync 的所有用户的集合，然后将所有这些信息发送到 Grant-CsExternalAccessPolicy，该策略将 FederationAndPICDefault 策略分配给集合中的每个用户。</span><span class="sxs-lookup"><span data-stu-id="32f42-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="32f42-135">再举一个示例，假设您之前为 Alex 分配了 FederationAndPICDefault 策略，但现在改变了主意，希望他受全局外部访问策略的管理。</span><span class="sxs-lookup"><span data-stu-id="32f42-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="32f42-136">无法将全局策略显式分配给任何人。</span><span class="sxs-lookup"><span data-stu-id="32f42-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="32f42-137">相反，如果没有为给定用户分配每用户策略，则全局策略用于该用户。</span><span class="sxs-lookup"><span data-stu-id="32f42-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="32f42-138">因此，如果我们希望 Alex 由全局策略管理，则需要取消分配之前分配给他的任何每用户策略。</span><span class="sxs-lookup"><span data-stu-id="32f42-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="32f42-139">下面是一个示例命令：</span><span class="sxs-lookup"><span data-stu-id="32f42-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="32f42-140">此命令将分配给 Alex 的外部访问策略的名称设置为空值 ($Null) 。</span><span class="sxs-lookup"><span data-stu-id="32f42-140">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="32f42-141">Null 表示"nothing"。</span><span class="sxs-lookup"><span data-stu-id="32f42-141">Null means "nothing".</span></span> <span data-ttu-id="32f42-142">换句话说，没有为 Alex 分配任何外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="32f42-142">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="32f42-143">未向用户分配外部访问策略时，该用户随后会由全局策略管理。</span><span class="sxs-lookup"><span data-stu-id="32f42-143">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="32f42-144">管理大量用户</span><span class="sxs-lookup"><span data-stu-id="32f42-144">Managing large numbers of users</span></span>

<span data-ttu-id="32f42-145">若要管理 1000 (或 1000) 的用户，您需要使用 [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet 通过脚本块批处理命令。</span><span class="sxs-lookup"><span data-stu-id="32f42-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="32f42-146">在之前的示例中，每次执行 cmdlet 时，它必须设置调用，然后等待结果再发送回。</span><span class="sxs-lookup"><span data-stu-id="32f42-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="32f42-147">使用脚本块时，这允许远程执行 cmdlet，一旦完成，将数据发送回。</span><span class="sxs-lookup"><span data-stu-id="32f42-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="32f42-148">这将一次查找 500 个没有客户端策略的用户。</span><span class="sxs-lookup"><span data-stu-id="32f42-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="32f42-149">它将授予他们客户端策略"ClientPolicyNoIMURL"和外部访问策略"FederationAndPicDefault"。</span><span class="sxs-lookup"><span data-stu-id="32f42-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="32f42-150">结果分批分为 50 个组，然后每批 50 个结果发送到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="32f42-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="32f42-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32f42-151">See also</span></span>

[<span data-ttu-id="32f42-152">使用 PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="32f42-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="32f42-153">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32f42-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="32f42-154">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="32f42-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
