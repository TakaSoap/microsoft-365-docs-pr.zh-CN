---
title: 在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南在 Microsoft 365 测试环境中注册设备，并远程管理这些设备。
ms.openlocfilehash: 0dde7acd10ad78327adb4862346639e05a276b4e
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981993"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0fa46-103">在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="0fa46-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0fa46-104">按照本文中提供的说明操作，您将能够在 Microsoft 365 企业版测试环境中注册和测试适用于 iOS 和 Android 设备的基本移动设备管理功能。</span><span class="sxs-lookup"><span data-stu-id="0fa46-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="0fa46-106">单击[此处](https://aka.ms/m365etlgstack)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="0fa46-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0fa46-107">第1阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="0fa46-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0fa46-108">如果只想使用最低要求以轻型方式注册 iOS 和 Android 设备，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0fa46-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0fa46-109">如果要在模拟企业版中注册 iOS 和 Android 设备，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0fa46-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fa46-110">测试自动许可和组成员身份不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="0fa46-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0fa46-111">此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="0fa46-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="0fa46-112">第2阶段：注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="0fa46-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="0fa46-113">首先，按照[安装和登录到公司门户应用](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)中的说明，为您的测试环境自定义 Microsoft Intune 公司门户应用程序。</span><span class="sxs-lookup"><span data-stu-id="0fa46-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="0fa46-114">接下来，按照设置对[贵公司资源的访问权限](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)注册 iOS 设备中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0fa46-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="0fa46-115">接下来，使用在[Intune 中注册 android 设备](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)注册 android 设备中的说明。</span><span class="sxs-lookup"><span data-stu-id="0fa46-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="0fa46-116">第3阶段：远程管理 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="0fa46-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="0fa46-117">Microsoft Intune 提供远程锁定和密码重置两种功能。</span><span class="sxs-lookup"><span data-stu-id="0fa46-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="0fa46-118">如果有人丢失了自己的设备，则可以远程锁定设备。</span><span class="sxs-lookup"><span data-stu-id="0fa46-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="0fa46-119">如果有人忘记了密码，你可以远程重置它。</span><span class="sxs-lookup"><span data-stu-id="0fa46-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="0fa46-120">远程锁定 iOS 或 Android 设备：</span><span class="sxs-lookup"><span data-stu-id="0fa46-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="0fa46-121">[https://portal.azure.com](https://portal.azure.com)使用全局管理员帐户的凭据登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="0fa46-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="0fa46-122">单击 "**所有服务**"，键入**Intune**，然后单击 " **intune**"。</span><span class="sxs-lookup"><span data-stu-id="0fa46-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="0fa46-123">单击 "**设备 > 所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="0fa46-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="0fa46-124">在设备列表中，单击一个 iOS 或 Android 设备，然后单击**远程锁定**操作。</span><span class="sxs-lookup"><span data-stu-id="0fa46-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="0fa46-125">远程重置密码：</span><span class="sxs-lookup"><span data-stu-id="0fa46-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="0fa46-126">如果需要，请[https://portal.azure.com](https://portal.azure.com)使用全局管理员帐户的凭据登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="0fa46-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="0fa46-127">单击 "**所有服务**"，键入**Intune**，然后单击 " **intune**"。</span><span class="sxs-lookup"><span data-stu-id="0fa46-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="0fa46-128">单击 "**设备 > 所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="0fa46-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="0fa46-129">从管理的设备列表中，单击 iOS 或 Android 设备，然后选择 **.。。更多**。</span><span class="sxs-lookup"><span data-stu-id="0fa46-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="0fa46-130">然后选择 "**删除密码**设备远程操作"。</span><span class="sxs-lookup"><span data-stu-id="0fa46-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="0fa46-131">有关其他实验，请参阅[可用设备操作](https://docs.microsoft.com/intune/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="0fa46-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="0fa46-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0fa46-132">Next step</span></span>

<span data-ttu-id="0fa46-133">在您的测试环境中探索其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="0fa46-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fa46-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fa46-134">See Also</span></span>

[<span data-ttu-id="0fa46-135">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="0fa46-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="0fa46-136">适用于 Microsoft 365 企业版测试环境的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="0fa46-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="0fa46-137">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="0fa46-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

