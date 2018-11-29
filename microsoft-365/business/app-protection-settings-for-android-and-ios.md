---
title: 设置 Android 或 iOS 设备的应用保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、 编辑或删除应用程序管理策略，和保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865969"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="70ffc-103">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="70ffc-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="70ffc-104">创建应用管理策略</span><span class="sxs-lookup"><span data-stu-id="70ffc-104">Create an app management policy</span></span>

1. <span data-ttu-id="70ffc-105">使用全局管理员凭据登录 [Microsoft 365 商业版](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="70ffc-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="70ffc-106">在管理中心内的" **设备策略**"卡上，选择" **添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="70ffc-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="70ffc-108">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="70ffc-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="70ffc-109">在" **策略类型**"下，根据要创建的策略集，选择" **适用于 Android 的应用程序管理**"或" **适用于 iOS 的应用程序管理**"。</span><span class="sxs-lookup"><span data-stu-id="70ffc-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="70ffc-p101">展开**保护工作文件时丢失或被盗设备**和**管理用户如何访问移动设备上的 Office 文件**\>配置方式的设置。默认情况下**管理用户如何访问移动设备上的 Office 文件**处于**关闭状态**，但建议您**将其打开**，并接受默认值。有关详细信息，请参阅[可用的设置](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings)。</span><span class="sxs-lookup"><span data-stu-id="70ffc-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="70ffc-113">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="70ffc-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="70ffc-p102">接下来决定**用户会收到这些设置？** 如果您不希望使用默认的**所有用户**安全组，选择**更改**、 选择用户会收到这些设置的安全组\>**选择**。</span><span class="sxs-lookup"><span data-stu-id="70ffc-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="70ffc-117">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="70ffc-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="70ffc-118">编辑应用管理策略</span><span class="sxs-lookup"><span data-stu-id="70ffc-118">Edit an app management policy</span></span>

1. <span data-ttu-id="70ffc-119">在**策略**卡片中，选择**编辑策略**。</span><span class="sxs-lookup"><span data-stu-id="70ffc-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="70ffc-120">在" **编辑策略**"窗格中，选择要更改的策略</span><span class="sxs-lookup"><span data-stu-id="70ffc-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="70ffc-p103">选择每个设置旁边的" **编辑**"来更改策略中的值。更改值后，它将自动保存到该策略</span><span class="sxs-lookup"><span data-stu-id="70ffc-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="70ffc-123">完成操作后，关闭" **编辑策略**"窗格。</span><span class="sxs-lookup"><span data-stu-id="70ffc-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="70ffc-124">删除应用管理策略</span><span class="sxs-lookup"><span data-stu-id="70ffc-124">Delete an app management policy</span></span>

1. <span data-ttu-id="70ffc-125">在" **策略**"卡中，选择" **删除策略**"。</span><span class="sxs-lookup"><span data-stu-id="70ffc-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="70ffc-126">在**删除策略**窗格中，选择您要删除的策略\>**选择**，然后**确认**删除的策略或您选择的策略。</span><span class="sxs-lookup"><span data-stu-id="70ffc-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="70ffc-127">可用设置</span><span class="sxs-lookup"><span data-stu-id="70ffc-127">Available settings</span></span>

<span data-ttu-id="70ffc-128">以下表格提供了有关用于保护设备上工作文件的可用设置以及控制用户如何从其移动设备访问 Office 文件的设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="70ffc-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="70ffc-129">有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="70ffc-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="70ffc-130">用于保护工作文件的设置</span><span class="sxs-lookup"><span data-stu-id="70ffc-130">Settings that protect work files</span></span>

<span data-ttu-id="70ffc-131">如果用户的设备丢失或被盗，以下设置可用于保护工作文件：</span><span class="sxs-lookup"><span data-stu-id="70ffc-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="70ffc-132">设置</span><span class="sxs-lookup"><span data-stu-id="70ffc-132">Setting</span></span>  <br/> |<span data-ttu-id="70ffc-133">说明</span><span class="sxs-lookup"><span data-stu-id="70ffc-133">Description</span></span>  <br/> |
|<span data-ttu-id="70ffc-134">在以下天数后，从非活动的设备删除工作文件</span><span class="sxs-lookup"><span data-stu-id="70ffc-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="70ffc-135">如果设备的未使用天数达到指定天数，则自动删除该设备上存储的任何工作文件。</span><span class="sxs-lookup"><span data-stu-id="70ffc-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="70ffc-136">强制要求用户将所有的工作文件保存到 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="70ffc-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="70ffc-137">如果此设置为" **开**"，则工作文件的唯一可用保存位置是 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="70ffc-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="70ffc-138">对工作文件进行加密</span><span class="sxs-lookup"><span data-stu-id="70ffc-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="70ffc-p104">将此设置保持为" **开**"，可通过加密保护工作文件。即使设备丢失或被盗，也没有人能够读取公司的数据。  </span><span class="sxs-lookup"><span data-stu-id="70ffc-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="70ffc-141">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="70ffc-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="70ffc-142">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="70ffc-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="70ffc-143">设置</span><span class="sxs-lookup"><span data-stu-id="70ffc-143">Setting</span></span>  <br/> |<span data-ttu-id="70ffc-144">说明</span><span class="sxs-lookup"><span data-stu-id="70ffc-144">Description</span></span>  <br/> |
|<span data-ttu-id="70ffc-145">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="70ffc-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="70ffc-146">如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="70ffc-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="70ffc-147">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="70ffc-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="70ffc-148">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="70ffc-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="70ffc-149">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="70ffc-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="70ffc-150">此设置确定用户保持空闲状态多久后系统会提示再次登录。</span><span class="sxs-lookup"><span data-stu-id="70ffc-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="70ffc-151">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="70ffc-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="70ffc-p105">一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **开** "，会阻止这些设备。  </span><span class="sxs-lookup"><span data-stu-id="70ffc-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="70ffc-155">允许用户从 Office 应用将内容复制到个人应用</span><span class="sxs-lookup"><span data-stu-id="70ffc-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="70ffc-p106">我们执行允许此默认情况下，但如果设置为**上**，用户无法复制信息中工作文件到个人文件。如果设置为**关闭**，用户将无法从工作帐户的信息复制到的个人的应用程序或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="70ffc-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

