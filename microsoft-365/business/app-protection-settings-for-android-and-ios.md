---
title: 设置 Android 或 iOS 设备的应用保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、编辑或删除应用管理策略，以及如何保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: 68a338ffb4f9b6cab16c677f80d27481ccec4bd8
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287687"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="1797a-103">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="1797a-103">Set app protection settings for Android or iOS devices</span></span>

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="1797a-105">创建应用管理策略</span><span class="sxs-lookup"><span data-stu-id="1797a-105">Create an app management policy</span></span>

1. <span data-ttu-id="1797a-106">转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="1797a-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="1797a-107">在左侧导航中，选择 "**设备** \> **策略** \> " "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="1797a-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="1797a-108">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="1797a-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="1797a-109">在" **策略类型**"下，根据要创建的策略集，选择" **适用于 Android 的应用程序管理**"或" **适用于 iOS 的应用程序管理**"。</span><span class="sxs-lookup"><span data-stu-id="1797a-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="1797a-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="1797a-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="1797a-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span><span class="sxs-lookup"><span data-stu-id="1797a-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="1797a-112">有关详细信息，请参阅[可用设置](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="1797a-112">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="1797a-113">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="1797a-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="1797a-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="1797a-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="1797a-117">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="1797a-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="1797a-118">编辑应用管理策略</span><span class="sxs-lookup"><span data-stu-id="1797a-118">Edit an app management policy</span></span>

1. <span data-ttu-id="1797a-119">在**策略**卡上，选择 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="1797a-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="1797a-120">在" **编辑策略**"窗格中，选择要更改的策略</span><span class="sxs-lookup"><span data-stu-id="1797a-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="1797a-p103">选择每个设置旁边的" **编辑**"来更改策略中的值。更改值后，它将自动保存到该策略</span><span class="sxs-lookup"><span data-stu-id="1797a-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="1797a-123">完成操作后，关闭" **编辑策略**"窗格。</span><span class="sxs-lookup"><span data-stu-id="1797a-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="1797a-124">删除应用管理策略</span><span class="sxs-lookup"><span data-stu-id="1797a-124">Delete an app management policy</span></span>

1. <span data-ttu-id="1797a-125">在 "**策略**" 页上，选择策略，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="1797a-125">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="1797a-126">在 "**删除策略**" 窗格中，选择 "**确认**" 以删除所选的策略或策略。</span><span class="sxs-lookup"><span data-stu-id="1797a-126">On the **Delete policy** pane choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="1797a-127">可用设置</span><span class="sxs-lookup"><span data-stu-id="1797a-127">Available settings</span></span>

<span data-ttu-id="1797a-128">以下表格提供了有关用于保护设备上工作文件的可用设置以及控制用户如何从其移动设备访问 Office 文件的设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1797a-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="1797a-129">有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="1797a-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="1797a-130">用于保护工作文件的设置</span><span class="sxs-lookup"><span data-stu-id="1797a-130">Settings that protect work files</span></span>

<span data-ttu-id="1797a-131">如果用户的设备丢失或被盗，以下设置可用于保护工作文件：</span><span class="sxs-lookup"><span data-stu-id="1797a-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1797a-132">设置</span><span class="sxs-lookup"><span data-stu-id="1797a-132">Setting</span></span>  <br/> |<span data-ttu-id="1797a-133">说明</span><span class="sxs-lookup"><span data-stu-id="1797a-133">Description</span></span>  <br/> |
|<span data-ttu-id="1797a-134">在以下天数后，从非活动的设备删除工作文件</span><span class="sxs-lookup"><span data-stu-id="1797a-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="1797a-135">如果设备的未使用天数达到指定天数，则自动删除该设备上存储的任何工作文件。</span><span class="sxs-lookup"><span data-stu-id="1797a-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="1797a-136">强制要求用户将所有的工作文件保存到 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1797a-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="1797a-137">如果此设置为" **打开**"，则工作文件的唯一可用保存位置是 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="1797a-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="1797a-138">对工作文件进行加密</span><span class="sxs-lookup"><span data-stu-id="1797a-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="1797a-p104">将此设置保持为" **打开**"，可通过加密保护工作文件。即使设备丢失或被盗，也没有人能够读取公司的数据。  </span><span class="sxs-lookup"><span data-stu-id="1797a-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="1797a-141">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="1797a-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="1797a-142">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="1797a-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1797a-143">设置</span><span class="sxs-lookup"><span data-stu-id="1797a-143">Setting</span></span>  <br/> |<span data-ttu-id="1797a-144">说明</span><span class="sxs-lookup"><span data-stu-id="1797a-144">Description</span></span>  <br/> |
|<span data-ttu-id="1797a-145">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="1797a-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="1797a-146">如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="1797a-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="1797a-147">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="1797a-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="1797a-148">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="1797a-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="1797a-149">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="1797a-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="1797a-150">此设置确定用户保持空闲状态多久后系统会提示再次登录。</span><span class="sxs-lookup"><span data-stu-id="1797a-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="1797a-151">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="1797a-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="1797a-p105">一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **打开**"，会阻止这些设备。  </span><span class="sxs-lookup"><span data-stu-id="1797a-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="1797a-155">允许用户从 Office 应用将内容复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="1797a-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="1797a-156">默认允许此设置，但如果设置为" **开**"，用户可将工作文件中的信息复制到个人文件。</span><span class="sxs-lookup"><span data-stu-id="1797a-156">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="1797a-157">如果设置为" **关** "，用户无法将工作帐户中的信息复制到个人应用或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="1797a-157">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

