---
title: 在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南注册 Microsoft 365 测试环境中的设备和远程管理它们。
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865536"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="384f4-103">在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="384f4-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="384f4-104">按照本文中提供的说明进行操作，您将能够注册和 Microsoft 365 企业版测试环境中测试用于 iOS 和 Android 设备的基本的移动设备管理功能。</span><span class="sxs-lookup"><span data-stu-id="384f4-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="384f4-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="384f4-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="384f4-107">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="384f4-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="384f4-108">如果您只想要注册的最低硬件要求与轻型方式的 iOS 和 Android 设备，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="384f4-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="384f4-109">如果您想要注册 iOS 和 Android 设备模拟企业中的，按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="384f4-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="384f4-p101">测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="384f4-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="384f4-112">阶段 2： 注册您的 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="384f4-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="384f4-113">首先，使用中的说明[安装和登录到的公司门户应用程序](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)自定义 Microsoft Intune 的公司门户应用程序的测试环境。</span><span class="sxs-lookup"><span data-stu-id="384f4-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="384f4-114">注册 iOS 设备，接下来，使用[设置访问公司资源](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)中的说明。</span><span class="sxs-lookup"><span data-stu-id="384f4-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="384f4-115">注册 Android 设备，接下来，使用[注册中 Intune Android 设备](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)中的说明。</span><span class="sxs-lookup"><span data-stu-id="384f4-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="384f4-116">第 3 阶段： 远程管理您的 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="384f4-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="384f4-p102">Microsoft Intune 提供远程锁定和密码重置功能。如果某人丢失其设备，您可以远程锁定设备。如果某人忘记其密码，您可以重置密码远程。</span><span class="sxs-lookup"><span data-stu-id="384f4-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="384f4-120">远程锁定 iOS 或 Android 设备：</span><span class="sxs-lookup"><span data-stu-id="384f4-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="384f4-121">登录到 Azure 门户在[https://portal.azure.com](https://portal.azure.com)的全局管理员帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="384f4-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="384f4-122">单击**所有服务**，键入**Intune**，，然后都单击**Intune**。</span><span class="sxs-lookup"><span data-stu-id="384f4-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="384f4-123">单击**设备 > 所有设备**。</span><span class="sxs-lookup"><span data-stu-id="384f4-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="384f4-124">在设备的列表中，单击 iOS 或 Android 设备，然后单击**远程锁定**操作。</span><span class="sxs-lookup"><span data-stu-id="384f4-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="384f4-125">远程重置密码：</span><span class="sxs-lookup"><span data-stu-id="384f4-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="384f4-126">如果需要登录到 Azure 门户在[https://portal.azure.com](https://portal.azure.com)的全局管理员帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="384f4-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="384f4-127">单击**所有服务**，键入**Intune**，，然后都单击**Intune**。</span><span class="sxs-lookup"><span data-stu-id="384f4-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="384f4-128">单击**设备 > 所有设备**。</span><span class="sxs-lookup"><span data-stu-id="384f4-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="384f4-p103">从设备列表中，您将管理、 单击 iOS 或 Android 设备，并选择 **...更多**。然后选择**删除密码**设备远程操作。</span><span class="sxs-lookup"><span data-stu-id="384f4-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="384f4-131">有关其他实验，请参阅[可用设备操作](https://docs.microsoft.com/intune/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="384f4-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="384f4-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="384f4-132">Next step</span></span>

<span data-ttu-id="384f4-133">浏览您的测试环境中其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="384f4-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="384f4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="384f4-134">See Also</span></span>

[<span data-ttu-id="384f4-135">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="384f4-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="384f4-136">用于 Microsoft 365 企业版测试环境的 MAM 策略</span><span class="sxs-lookup"><span data-stu-id="384f4-136">MAM policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="384f4-137">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="384f4-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="384f4-138">企业移动 + 安全 (EMS)</span><span class="sxs-lookup"><span data-stu-id="384f4-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
