---
title: 设置 Android 或 iOS 设备的应用保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、编辑或删除应用管理策略, 以及如何保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: e81ff8a4bd71dbbbf7ccc31249d450e03f4bd241
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277435"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="1d7f6-103">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="1d7f6-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="1d7f6-104">创建应用管理策略</span><span class="sxs-lookup"><span data-stu-id="1d7f6-104">Create an app management policy</span></span>

1. <span data-ttu-id="1d7f6-105">使用全局管理员凭据登录到[Microsoft 365 商业版管理员中心](https://go.microsoft.com/fwlink/p/?linkid=837890)。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-105">Sign in to [Microsoft 365 Business admin center ](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="1d7f6-106">在管理中心中, 选择 "**设备** \> **策略** \> " "**添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-106">In the admin center, choose **Devices** \> **Policies** \> **Add policy**.</span></span>
  
3. <span data-ttu-id="1d7f6-107">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-107">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="1d7f6-108">在" **策略类型**"下，根据要创建的策略集，选择" **适用于 Android 的应用程序管理**"或" **适用于 iOS 的应用程序管理**"。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-108">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="1d7f6-109">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="1d7f6-109">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="1d7f6-110">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span><span class="sxs-lookup"><span data-stu-id="1d7f6-110">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="1d7f6-111">有关详细信息, 请参阅[可用设置](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-111">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="1d7f6-112">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-112">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="1d7f6-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="1d7f6-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="1d7f6-116">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="1d7f6-117">编辑应用管理策略</span><span class="sxs-lookup"><span data-stu-id="1d7f6-117">Edit an app management policy</span></span>

1. <span data-ttu-id="1d7f6-118">在**策略**卡上, 选择 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-118">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="1d7f6-119">在" **编辑策略**"窗格中，选择要更改的策略</span><span class="sxs-lookup"><span data-stu-id="1d7f6-119">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="1d7f6-p103">选择每个设置旁边的" **编辑**"来更改策略中的值。更改值后，它将自动保存到该策略</span><span class="sxs-lookup"><span data-stu-id="1d7f6-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="1d7f6-122">完成操作后，关闭" **编辑策略**"窗格。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-122">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="1d7f6-123">删除应用管理策略</span><span class="sxs-lookup"><span data-stu-id="1d7f6-123">Delete an app management policy</span></span>

1. <span data-ttu-id="1d7f6-124">在" **策略**"卡中，选择" **删除策略**"。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-124">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="1d7f6-125">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span><span class="sxs-lookup"><span data-stu-id="1d7f6-125">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="1d7f6-126">可用设置</span><span class="sxs-lookup"><span data-stu-id="1d7f6-126">Available settings</span></span>

<span data-ttu-id="1d7f6-127">以下表格提供了有关用于保护设备上工作文件的可用设置以及控制用户如何从其移动设备访问 Office 文件的设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-127">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="1d7f6-128">有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-128">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="1d7f6-129">用于保护工作文件的设置</span><span class="sxs-lookup"><span data-stu-id="1d7f6-129">Settings that protect work files</span></span>

<span data-ttu-id="1d7f6-130">如果用户的设备丢失或被盗，以下设置可用于保护工作文件：</span><span class="sxs-lookup"><span data-stu-id="1d7f6-130">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1d7f6-131">Setting</span><span class="sxs-lookup"><span data-stu-id="1d7f6-131">Setting</span></span>  <br/> |<span data-ttu-id="1d7f6-132">说明</span><span class="sxs-lookup"><span data-stu-id="1d7f6-132">Description</span></span>  <br/> |
|<span data-ttu-id="1d7f6-133">在以下天数后，从非活动的设备删除工作文件</span><span class="sxs-lookup"><span data-stu-id="1d7f6-133">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="1d7f6-134">如果设备的未使用天数达到指定天数，则自动删除该设备上存储的任何工作文件。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-134">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="1d7f6-135">强制要求用户将所有的工作文件保存到 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1d7f6-135">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="1d7f6-136">如果此设置为" **打开**"，则工作文件的唯一可用保存位置是 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-136">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="1d7f6-137">对工作文件进行加密</span><span class="sxs-lookup"><span data-stu-id="1d7f6-137">Encrypt work files</span></span>  <br/> |<span data-ttu-id="1d7f6-p104">将此设置保持为" **打开**"，可通过加密保护工作文件。即使设备丢失或被盗，也没有人能够读取公司的数据。  </span><span class="sxs-lookup"><span data-stu-id="1d7f6-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="1d7f6-140">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="1d7f6-140">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="1d7f6-141">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="1d7f6-141">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1d7f6-142">Setting</span><span class="sxs-lookup"><span data-stu-id="1d7f6-142">Setting</span></span>  <br/> |<span data-ttu-id="1d7f6-143">说明</span><span class="sxs-lookup"><span data-stu-id="1d7f6-143">Description</span></span>  <br/> |
|<span data-ttu-id="1d7f6-144">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="1d7f6-144">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="1d7f6-145">如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-145">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="1d7f6-146">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="1d7f6-146">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="1d7f6-147">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-147">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="1d7f6-148">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="1d7f6-148">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="1d7f6-149">此设置确定用户保持空闲状态多久后系统会提示再次登录。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-149">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="1d7f6-150">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="1d7f6-150">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="1d7f6-p105">一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **打开**"，会阻止这些设备。  </span><span class="sxs-lookup"><span data-stu-id="1d7f6-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="1d7f6-154">允许用户从 Office 应用将内容复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="1d7f6-154">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="1d7f6-155">默认允许此设置，但如果设置为" **开**"，用户可将工作文件中的信息复制到个人文件。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-155">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="1d7f6-156">如果设置为" **关** "，用户无法将工作帐户中的信息复制到个人应用或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="1d7f6-156">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

