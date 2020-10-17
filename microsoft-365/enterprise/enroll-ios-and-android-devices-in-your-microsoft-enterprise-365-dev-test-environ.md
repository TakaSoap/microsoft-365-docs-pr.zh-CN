---
title: 在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南在 Microsoft 365 测试环境中注册设备，并远程管理这些设备。
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487692"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84052-103">在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="84052-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84052-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="84052-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="84052-105">本文介绍了如何为 Microsoft 365 企业版测试环境中的 iOS 和 Android 设备注册和测试基本移动设备管理功能。</span><span class="sxs-lookup"><span data-stu-id="84052-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="84052-106">在测试环境中注册 iOS 和 Android 设备涉及三个阶段：</span><span class="sxs-lookup"><span data-stu-id="84052-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="84052-107">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="84052-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="84052-108">第2阶段：注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="84052-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="84052-109">第3阶段：远程管理 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="84052-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="84052-111">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="84052-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84052-112">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="84052-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84052-113">如果要使用最低要求以轻型方式注册 iOS 和 Android 设备，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="84052-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="84052-114">如果要在模拟企业版中注册 iOS 和 Android 设备，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="84052-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="84052-115">测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="84052-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="84052-116">它作为选项提供，以便您可以测试自动授权和组成员身份，并且可以在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="84052-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="84052-117">第2阶段：注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="84052-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="84052-118">首先，按照 [安装和登录到公司门户应用](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) 中的说明，为您的测试环境自定义 Microsoft Intune 公司门户应用程序。</span><span class="sxs-lookup"><span data-stu-id="84052-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="84052-119">接下来，按照设置对 [贵公司资源的访问权限](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 注册 iOS 设备中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="84052-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="84052-120">接下来，使用在 [Intune 中注册 android 设备](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) 注册 android 设备中的说明。</span><span class="sxs-lookup"><span data-stu-id="84052-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="84052-121">第3阶段：远程管理 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="84052-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="84052-122">Microsoft Intune 提供远程锁定和密码重置两种功能。</span><span class="sxs-lookup"><span data-stu-id="84052-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="84052-123">如果某人丢失了设备，则可以远程锁定设备。</span><span class="sxs-lookup"><span data-stu-id="84052-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="84052-124">如果有人忘记了密码，可以对其进行远程重置。</span><span class="sxs-lookup"><span data-stu-id="84052-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="84052-125">若要远程锁定 iOS 或 Android 设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84052-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="84052-126">[https://portal.azure.com](https://portal.azure.com)使用全局管理员帐户的凭据登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="84052-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="84052-127">在 Azure 门户中，在搜索框中输入 **intune** ，然后选择 **intune**。</span><span class="sxs-lookup"><span data-stu-id="84052-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="84052-128">单击 " **设备 > 所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="84052-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="84052-129">在设备列表中，选择一个 iOS 或 Android 设备，然后选择 **远程锁定** 操作。</span><span class="sxs-lookup"><span data-stu-id="84052-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="84052-130">若要远程重置密码，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84052-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="84052-131">如果需要，请 [https://portal.azure.com](https://portal.azure.com) 使用全局管理员帐户的凭据登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="84052-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="84052-132">在 Azure 门户中，在搜索框中输入 **intune** ，然后选择 **intune**。</span><span class="sxs-lookup"><span data-stu-id="84052-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="84052-133">选择 "**设备**  >  **所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="84052-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="84052-134">从所管理的设备列表中，选择 iOS 或 Android 设备，选择 " **..."详细信息**，然后选择 " **删除密码** 设备远程操作"。</span><span class="sxs-lookup"><span data-stu-id="84052-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="84052-135">有关其他实验，请参阅 [可用设备操作](https://docs.microsoft.com/intune/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="84052-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="84052-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="84052-136">Next step</span></span>

<span data-ttu-id="84052-137">在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。</span><span class="sxs-lookup"><span data-stu-id="84052-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="84052-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84052-138">See Also</span></span>

[<span data-ttu-id="84052-139">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="84052-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="84052-140">适用于 Microsoft 365 企业版测试环境的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="84052-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="84052-141">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="84052-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
