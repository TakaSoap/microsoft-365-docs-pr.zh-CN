---
title: 设置 Android 或 iOS 设备的应用保护设置
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、编辑或删除应用管理策略，并保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580286"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="3d799-103">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="3d799-103">Set app protection settings for Android or iOS devices</span></span>

<span data-ttu-id="3d799-104">本文适用于Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="3d799-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="3d799-105">创建应用管理策略</span><span class="sxs-lookup"><span data-stu-id="3d799-105">Create an app management policy</span></span>

1. <span data-ttu-id="3d799-106">转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。</span><span class="sxs-lookup"><span data-stu-id="3d799-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="3d799-107">在左侧导航中，选择 **"设备策略** \>  \> **""添加"。**</span><span class="sxs-lookup"><span data-stu-id="3d799-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="3d799-108">在" **添加策略**"窗格中，输入此策略的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3d799-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="3d799-109">在 **"策略类型**"下，选择 **"Android** 应用程序管理"或" **适用于 iOS** 的应用程序管理"，具体取决于要创建的策略集。</span><span class="sxs-lookup"><span data-stu-id="3d799-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="3d799-110">Expand **Protect work files when devices are lost or stolen** and Manage how users access Office files on mobile **devices**.</span><span class="sxs-lookup"><span data-stu-id="3d799-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="3d799-111">配置您喜欢的设置。</span><span class="sxs-lookup"><span data-stu-id="3d799-111">Configure the settings how you would like.</span></span> <span data-ttu-id="3d799-112">**管理用户在移动设备上** Office访问文件方式默认为"关闭"，但我们建议你将其打开并接受默认值。 </span><span class="sxs-lookup"><span data-stu-id="3d799-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="3d799-113">有关详细信息，请参阅可用 [设置](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="3d799-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="3d799-114">始终可使用" **重置默认设置**"链接返回到默认设置。</span><span class="sxs-lookup"><span data-stu-id="3d799-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="3d799-116">Next decide **Who will get these settings?**</span><span class="sxs-lookup"><span data-stu-id="3d799-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="3d799-117">如果不想使用默认的"所有用户"安全组，请选择"更改"，选择获取这些设置的安全组" \> **选择"。**</span><span class="sxs-lookup"><span data-stu-id="3d799-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="3d799-118">最后，选择" **完成**"以保存该策略，并将其分配到设备。</span><span class="sxs-lookup"><span data-stu-id="3d799-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="3d799-119">编辑应用管理策略</span><span class="sxs-lookup"><span data-stu-id="3d799-119">Edit an app management policy</span></span>

1. <span data-ttu-id="3d799-120">在"**策略"** 卡上，选择"**编辑策略"。**</span><span class="sxs-lookup"><span data-stu-id="3d799-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="3d799-121">在" **编辑策略**"窗格中，选择要更改的策略</span><span class="sxs-lookup"><span data-stu-id="3d799-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="3d799-122">选择每个设置旁边的" **编辑**"来更改策略中的值。</span><span class="sxs-lookup"><span data-stu-id="3d799-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="3d799-123">更改值时，它会自动保存在策略中。</span><span class="sxs-lookup"><span data-stu-id="3d799-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="3d799-124">完成后，关闭"编辑 **策略"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="3d799-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="3d799-125">删除应用管理策略</span><span class="sxs-lookup"><span data-stu-id="3d799-125">Delete an app management policy</span></span>

1. <span data-ttu-id="3d799-126">在"**策略"** 页上，选择一个策略，然后选择"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="3d799-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="3d799-127">在" **删除策略"** 窗格中，选择" **确认** "以删除你选择的策略。</span><span class="sxs-lookup"><span data-stu-id="3d799-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="3d799-128">可用设置</span><span class="sxs-lookup"><span data-stu-id="3d799-128">Available settings</span></span>

<span data-ttu-id="3d799-129">下表详细介绍了可用于保护设备上工作文件的设置，以及控制用户如何从Office访问工作文件的设置。</span><span class="sxs-lookup"><span data-stu-id="3d799-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="3d799-130">有关详细信息，请参阅如何将保护[功能Microsoft 365 商业高级版映射到 Intune 设置](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3d799-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="3d799-131">用户保护工作文件的设置</span><span class="sxs-lookup"><span data-stu-id="3d799-131">Settings that protect work files</span></span>

<span data-ttu-id="3d799-132">如果用户的设备丢失或被盗，以下设置可用于保护工作文件：</span><span class="sxs-lookup"><span data-stu-id="3d799-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3d799-133">设置</span><span class="sxs-lookup"><span data-stu-id="3d799-133">Setting</span></span>  <br/> |<span data-ttu-id="3d799-134">说明</span><span class="sxs-lookup"><span data-stu-id="3d799-134">Description</span></span>  <br/> |
|<span data-ttu-id="3d799-135">在以下天数后，从非活动的设备删除工作文件</span><span class="sxs-lookup"><span data-stu-id="3d799-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="3d799-136">如果设备不用于你在此处指定的天数，则将自动删除设备上存储的任何工作文件。</span><span class="sxs-lookup"><span data-stu-id="3d799-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="3d799-137">强制要求用户将所有的工作文件保存到 OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="3d799-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="3d799-138">如果此设置为 **"打开"，** 则工作文件的唯一可用保存位置OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="3d799-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="3d799-139">对工作文件进行加密</span><span class="sxs-lookup"><span data-stu-id="3d799-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="3d799-140">将此设置保持为" **打开**"，可通过加密保护工作文件。</span><span class="sxs-lookup"><span data-stu-id="3d799-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="3d799-141">即使设备丢失或被盗，也没有人可以读取你的公司数据。</span><span class="sxs-lookup"><span data-stu-id="3d799-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="3d799-142">用于控制用户如何在移动设备上访问 Office 文件的设置</span><span class="sxs-lookup"><span data-stu-id="3d799-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="3d799-143">以下设置可用于管理用户访问 Office 工作文件的方式：</span><span class="sxs-lookup"><span data-stu-id="3d799-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3d799-144">设置</span><span class="sxs-lookup"><span data-stu-id="3d799-144">Setting</span></span>  <br/> |<span data-ttu-id="3d799-145">说明</span><span class="sxs-lookup"><span data-stu-id="3d799-145">Description</span></span>  <br/> |
|<span data-ttu-id="3d799-146">需要 PIN 或指纹才能访问 Office 应用</span><span class="sxs-lookup"><span data-stu-id="3d799-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="3d799-147">如果此设置为 **"打开**"，则除了用户名和密码之外，用户还必须提供另一种形式的身份验证，然后才能在移动设备上Office应用。</span><span class="sxs-lookup"><span data-stu-id="3d799-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="3d799-148">登录失败以下次数后重置 PIN</span><span class="sxs-lookup"><span data-stu-id="3d799-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="3d799-149">若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。</span><span class="sxs-lookup"><span data-stu-id="3d799-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="3d799-150">要求用户在 Office 应用空闲以下时间后重新登录</span><span class="sxs-lookup"><span data-stu-id="3d799-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="3d799-151">此设置确定用户在系统提示重新登录之前可以处于空闲状态的时间。</span><span class="sxs-lookup"><span data-stu-id="3d799-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="3d799-152">在已越狱或取得 root 权限的设备上拒绝对工作文件的访问</span><span class="sxs-lookup"><span data-stu-id="3d799-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="3d799-p105">一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **打开**"，会阻止这些设备。  </span><span class="sxs-lookup"><span data-stu-id="3d799-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="3d799-156">不允许用户将内容从应用Office个人应用中</span><span class="sxs-lookup"><span data-stu-id="3d799-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="3d799-157">默认允许此设置，但如果设置为" **开**"，用户可将工作文件中的信息复制到个人文件。</span><span class="sxs-lookup"><span data-stu-id="3d799-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="3d799-158">如果设置为" **关** "，用户无法将工作帐户中的信息复制到个人应用或个人帐户。</span><span class="sxs-lookup"><span data-stu-id="3d799-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
