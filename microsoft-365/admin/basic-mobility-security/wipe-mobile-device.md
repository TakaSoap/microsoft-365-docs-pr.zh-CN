---
title: 在基本移动性和安全性中擦除移动设备
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 使用内置的"基本移动性和安全性"从已注册的设备中删除信息。
ms.openlocfilehash: 8c873923505fe527f5a44df0e8b15d290e92023b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706138"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="98add-103">在基本移动性和安全性中擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="98add-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="98add-104">可以使用内置的 Microsoft 365 基本移动性和安全性来仅删除组织信息，或执行恢复出厂设置以从移动设备中删除所有信息，并还原到出厂设置。</span><span class="sxs-lookup"><span data-stu-id="98add-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="98add-105">准备工作</span><span class="sxs-lookup"><span data-stu-id="98add-105">Before you begin</span></span>

<span data-ttu-id="98add-106">移动设备可以存储敏感的组织信息，并提供对组织资源Microsoft 365的访问权限。</span><span class="sxs-lookup"><span data-stu-id="98add-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="98add-107">若要帮助保护组织的信息，可以执行"恢复出厂设置"或"删除公司数据"操作：</span><span class="sxs-lookup"><span data-stu-id="98add-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="98add-108">**恢复** 出厂设置：删除用户移动设备上的所有数据，包括已安装的应用程序、照片和个人信息。</span><span class="sxs-lookup"><span data-stu-id="98add-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="98add-109">擦除完成后，设备将还原到出厂设置。</span><span class="sxs-lookup"><span data-stu-id="98add-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="98add-110">**删除公司数据**：仅删除组织数据，并保留用户的移动设备上已安装的应用程序、照片和个人信息。</span><span class="sxs-lookup"><span data-stu-id="98add-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="98add-111">**当擦除设备 (重置** 或删除公司) 时，该设备将从托管设备列表中删除。</span><span class="sxs-lookup"><span data-stu-id="98add-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="98add-112">**自动重置设备**：可以设置基本移动性和安全策略，在用户尝试输入设备密码特定次数失败后自动恢复设备出厂设置。</span><span class="sxs-lookup"><span data-stu-id="98add-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="98add-113">为此，请按照创建基本移动性和安全性中的设备 [安全策略中的步骤操作](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="98add-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="98add-114">**如果你希望了解擦除** 其设备的用户体验，请参阅   [用户和设备的影响是什么？。](#whats-the-user-and-device-impact)</span><span class="sxs-lookup"><span data-stu-id="98add-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="98add-115">擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="98add-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="98add-116">转到管理 [Microsoft 365中心](../../admin/admin-overview/about-the-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="98add-116">Go to the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md).</span></span>

2. <span data-ttu-id="98add-117">在搜索字段中键入"移动设备管理"，然后从结果列表中选择"移动设备管理"。</span><span class="sxs-lookup"><span data-stu-id="98add-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本移动性和安全移动设备管理选项":::

3. <span data-ttu-id="98add-119">选择 **"管理设备"。**</span><span class="sxs-lookup"><span data-stu-id="98add-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="98add-120">选择要擦除的设备。</span><span class="sxs-lookup"><span data-stu-id="98add-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="98add-121">选择"**管理"。**</span><span class="sxs-lookup"><span data-stu-id="98add-121">Select **Manage**.</span></span>

6. <span data-ttu-id="98add-122">选择要执行的远程擦除类型。</span><span class="sxs-lookup"><span data-stu-id="98add-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="98add-123">若要执行完全擦除，将设备还原到出厂设置，请选择"恢复 **出厂设置"。**</span><span class="sxs-lookup"><span data-stu-id="98add-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="98add-124">若要执行选择性擦除并仅删除Microsoft 365，请选择"删除 **公司数据"。**</span><span class="sxs-lookup"><span data-stu-id="98add-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="98add-125">若要从组织中删除设备，请选择"**删除设备"。**</span><span class="sxs-lookup"><span data-stu-id="98add-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="98add-126">选择“**是**”进行确认。</span><span class="sxs-lookup"><span data-stu-id="98add-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="98add-127">我如何知道它有效？</span><span class="sxs-lookup"><span data-stu-id="98add-127">How do I know it worked?</span></span>

<span data-ttu-id="98add-128">您不再在托管设备列表中看到移动设备。</span><span class="sxs-lookup"><span data-stu-id="98add-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="98add-129">为什么你想要擦除设备？</span><span class="sxs-lookup"><span data-stu-id="98add-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="98add-130">由于以下原因，擦除设备：</span><span class="sxs-lookup"><span data-stu-id="98add-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="98add-131">智能手机和平板电脑等移动设备功能越来越全面。</span><span class="sxs-lookup"><span data-stu-id="98add-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="98add-132">这意味着用户能够更轻松地存储敏感的公司信息（如个人标识或机密通信）并同时访问这些信息。</span><span class="sxs-lookup"><span data-stu-id="98add-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="98add-133">如果其中一个移动设备丢失或被盗，则擦除设备有助于防止组织的信息最终被误用。</span><span class="sxs-lookup"><span data-stu-id="98add-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="98add-134">当用户使用注册基本移动性和安全性的个人设备离开组织时，可以通过执行出厂重置来帮助防止组织信息与该用户一起访问。</span><span class="sxs-lookup"><span data-stu-id="98add-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="98add-135">如果你的组织为用户提供移动设备，你可能需要时时重新分配设备。</span><span class="sxs-lookup"><span data-stu-id="98add-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="98add-136">在将设备分配给新用户之前，在设备上执行出厂重置可帮助确保删除以前所有者的任何敏感信息。</span><span class="sxs-lookup"><span data-stu-id="98add-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="98add-137">用户和设备有什么影响？</span><span class="sxs-lookup"><span data-stu-id="98add-137">What's the user and device impact?</span></span>

<span data-ttu-id="98add-138">擦除会立即发送到移动设备，并且设备在 Azure Active Directory 中标记为不兼容。</span><span class="sxs-lookup"><span data-stu-id="98add-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="98add-139">当设备重置为出厂默认设置时，会删除所有数据，但下表介绍了在设备删除公司数据时，将删除每种设备类型的内容。</span><span class="sxs-lookup"><span data-stu-id="98add-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="98add-140">**内容影响**</span><span class="sxs-lookup"><span data-stu-id="98add-140">**Content impact**</span></span>|<span data-ttu-id="98add-141">**iOS 10 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="98add-141">**iOS 10 and later**</span></span>|<span data-ttu-id="98add-142">**Android 5 及更高版本**</span><span class="sxs-lookup"><span data-stu-id="98add-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98add-143">Microsoft 365受 Intune 应用保护策略保护，则擦除应用数据。</span><span class="sxs-lookup"><span data-stu-id="98add-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="98add-144">不会删除这些应用。</span><span class="sxs-lookup"><span data-stu-id="98add-144">The apps aren't removed.</span></span> <span data-ttu-id="98add-145">对于不受移动应用程序管理保护的设备 (MAM) 策略，Outlook OneDrive不会删除缓存数据。</span><span class="sxs-lookup"><span data-stu-id="98add-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="98add-146">**注意** 要应用 Intune 应用保护策略，你必须拥有 Intune 许可证。</span><span class="sxs-lookup"><span data-stu-id="98add-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="98add-147">是</span><span class="sxs-lookup"><span data-stu-id="98add-147">Yes</span></span>|<span data-ttu-id="98add-148">是</span><span class="sxs-lookup"><span data-stu-id="98add-148">Yes</span></span>|
|<span data-ttu-id="98add-149">不再强制执行基本移动性和安全性应用于设备的策略设置;用户可以更改设置。</span><span class="sxs-lookup"><span data-stu-id="98add-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="98add-150">是</span><span class="sxs-lookup"><span data-stu-id="98add-150">Yes</span></span>|<span data-ttu-id="98add-151">是</span><span class="sxs-lookup"><span data-stu-id="98add-151">Yes</span></span>|
|<span data-ttu-id="98add-152">将删除由基本移动性和安全性创建的电子邮件配置文件，并删除设备上缓存的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="98add-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="98add-153">是</span><span class="sxs-lookup"><span data-stu-id="98add-153">Yes</span></span>|<span data-ttu-id="98add-154">不适用</span><span class="sxs-lookup"><span data-stu-id="98add-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="98add-155">公司门户应用在适用于 iOS 的应用商店和适用于 Android 设备的 Play 应用商店中提供。</span><span class="sxs-lookup"><span data-stu-id="98add-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>
