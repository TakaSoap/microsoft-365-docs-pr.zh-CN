---
title: 使用 PowerShell 管理 Skype for Business Online 策略
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 摘要：使用 PowerShell 通过策略管理 Skype for Business Online 用户帐户属性。
ms.openlocfilehash: ca945bc05e76525b4b2df6fb0b982a8468d87810
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515048"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="4d215-103">使用 PowerShell 管理 Skype for Business Online 策略</span><span class="sxs-lookup"><span data-stu-id="4d215-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="4d215-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="4d215-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4d215-105">若要管理 Skype for Business Online 用户帐户的许多属性，必须使用 PowerShell for Microsoft 365 将其指定为策略的属性。</span><span class="sxs-lookup"><span data-stu-id="4d215-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4d215-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="4d215-106">Before you begin</span></span>

<span data-ttu-id="4d215-107">使用以下说明进行设置以运行命令 (跳过已完成) ：</span><span class="sxs-lookup"><span data-stu-id="4d215-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="4d215-108">Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="4d215-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="4d215-109">如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="4d215-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="4d215-110">安装 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="4d215-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="4d215-111">开启 Windows PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d215-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   <span data-ttu-id="4d215-112">系统提示时，输入 Skype for Business Online 管理员帐户名和密码。</span><span class="sxs-lookup"><span data-stu-id="4d215-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="4d215-113">管理用户帐户策略</span><span class="sxs-lookup"><span data-stu-id="4d215-113">Manage user account policies</span></span>

<span data-ttu-id="4d215-114">许多 Skype for Business Online 用户帐户属性都是使用策略配置的。</span><span class="sxs-lookup"><span data-stu-id="4d215-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="4d215-115">策略只是一组可应用于一个或多个用户的设置。</span><span class="sxs-lookup"><span data-stu-id="4d215-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="4d215-116">若要了解策略的配置方式，您可以为 FederationAndPICDefault 策略运行此示例命令：</span><span class="sxs-lookup"><span data-stu-id="4d215-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="4d215-117">反过来，应返回类似以下内容：</span><span class="sxs-lookup"><span data-stu-id="4d215-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="4d215-118">在此例中，此策略中的值确定在使用与联盟用户通信时可以或不能执行哪些功能。</span><span class="sxs-lookup"><span data-stu-id="4d215-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="4d215-119">例如，EnableOutsideAccess 属性必须设置为 True，用户才能与组织外部人员通信。</span><span class="sxs-lookup"><span data-stu-id="4d215-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="4d215-120">请注意，此属性不会显示在 Microsoft 365 管理中心中。</span><span class="sxs-lookup"><span data-stu-id="4d215-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4d215-121">而是根据你做出的其他选择自动将该属性设置为 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="4d215-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="4d215-122">其他两个关注属性是：</span><span class="sxs-lookup"><span data-stu-id="4d215-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="4d215-123">**EnableFederationAccess** 指示用户是否可以与联合域的用户通信。</span><span class="sxs-lookup"><span data-stu-id="4d215-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="4d215-124">**EnablePublicCloudAccess** 指示用户是否可以与 Windows Live 用户通信。</span><span class="sxs-lookup"><span data-stu-id="4d215-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="4d215-125">因此，不要直接更改用户帐户上的联合 (例如 **，Set-CsUser -EnableFederationAccess $True) 。**</span><span class="sxs-lookup"><span data-stu-id="4d215-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="4d215-126">而是为帐户分配一个预配置了所需属性值的外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="4d215-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="4d215-127">如果我们希望用户能够与联盟用户和Windows Live通信，则必须为用户帐户分配允许这些通信类型的策略。</span><span class="sxs-lookup"><span data-stu-id="4d215-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="4d215-128">如果您想了解某人是否可以与组织外部的用户通信，您必须：</span><span class="sxs-lookup"><span data-stu-id="4d215-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="4d215-129">确定为此用户分配的是哪种外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="4d215-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="4d215-130">确定此策略允许的许可范围。</span><span class="sxs-lookup"><span data-stu-id="4d215-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="4d215-131">例如，可以通过使用此命令来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="4d215-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="4d215-132">此命令查找分配给用户的策略，然后找到该策略中启用或禁用的功能。</span><span class="sxs-lookup"><span data-stu-id="4d215-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="4d215-133">若要使用 PowerShell 管理 Skype for Business Online 策略，请参阅以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4d215-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="4d215-134">[客户端策略](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4d215-134">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="4d215-135">[会议策略](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4d215-135">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="4d215-136">[移动策略](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4d215-136">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="4d215-137">[联机语音邮件策略](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4d215-137">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="4d215-138">[语音路由策略](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="4d215-138">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="4d215-139">Skype for Business Online 拨号计划是除名称之外的所有方面的策略。</span><span class="sxs-lookup"><span data-stu-id="4d215-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="4d215-140">为了提供与 Office Communications Server 和 Exchange 的向后兼容性，选择了名称"拨号计划"，而不是"拨号策略"。</span><span class="sxs-lookup"><span data-stu-id="4d215-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="4d215-141">例如，若要查看所有可用的语音策略，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d215-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="4d215-142">将返回所有可用的语音策略的列表。</span><span class="sxs-lookup"><span data-stu-id="4d215-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="4d215-143">但请记住，并非所有策略都可以分配给所有用户。</span><span class="sxs-lookup"><span data-stu-id="4d215-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="4d215-144">这是因为涉及许可和地理位置的各种限制。</span><span class="sxs-lookup"><span data-stu-id="4d215-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="4d215-145"> (所谓的"[使用位置"。](https://msdn.microsoft.com/library/azure/dn194136.aspx)) 如果您想要了解可分配给特定用户的外部访问策略和会议策略，请使用以下类似命令：</span><span class="sxs-lookup"><span data-stu-id="4d215-145">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="4d215-p107">ApplicableTo 参数可将返回的数据限制为可分配到特定用户的策略（例如，Alex Darrow）。根据不同的授权和使用位置限制，可能会代表所有可用策略的子集。</span><span class="sxs-lookup"><span data-stu-id="4d215-p107">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="4d215-148">在某些情况下，策略的属性不用于 Microsoft 365，而其他属性只能由 Microsoft 支持人员管理。</span><span class="sxs-lookup"><span data-stu-id="4d215-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="4d215-149">使用 Skype for Business Online，用户必须由某种类型的策略管理。</span><span class="sxs-lookup"><span data-stu-id="4d215-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="4d215-150">如果与策略相关的有效属性为空，则意味着相关用户由全局策略管理，全局策略是自动应用于用户的策略，除非专门为其分配了每用户策略。</span><span class="sxs-lookup"><span data-stu-id="4d215-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="4d215-151">由于未列出用户帐户的客户端策略，因此它由全局策略管理。</span><span class="sxs-lookup"><span data-stu-id="4d215-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="4d215-152">可以使用此命令确定全局客户端策略：</span><span class="sxs-lookup"><span data-stu-id="4d215-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="4d215-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d215-153">See also</span></span>

[<span data-ttu-id="4d215-154">使用 PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d215-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4d215-155">使用 PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d215-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4d215-156">PowerShell for Microsoft 365 入门</span><span class="sxs-lookup"><span data-stu-id="4d215-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

