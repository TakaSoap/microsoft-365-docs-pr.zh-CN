---
title: 在 Microsoft 365 for 企业版测试环境中注册 iOS/iPadOS 和 Android 设备
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: 使用此测试实验室指南在 Microsoft 365 测试环境中注册设备，并远程管理这些设备。
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367079"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="eb988-103">在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="eb988-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="eb988-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="eb988-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="eb988-105">本文介绍如何在 Microsoft 365 for 企业测试环境中注册和测试适用于 iOS/iPadOS 和 Android 设备的基本移动设备管理功能。</span><span class="sxs-lookup"><span data-stu-id="eb988-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="eb988-106">在测试环境中注册 iOS/iPadOS 和 Android 设备涉及三个阶段：</span><span class="sxs-lookup"><span data-stu-id="eb988-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="eb988-107">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="eb988-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="eb988-108">第2阶段：注册 iOS/iPadOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="eb988-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="eb988-109">第3阶段：远程管理 iOS/iPadOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="eb988-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="eb988-111">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="eb988-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="eb988-112">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="eb988-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="eb988-113">如果要以使用最低要求的轻型方式注册 iOS/iPadOS 和 Android 设备，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="eb988-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="eb988-114">如果要在模拟的企业中注册 iOS/iPadOS 和 Android 设备，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="eb988-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb988-115">测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="eb988-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="eb988-116">它作为选项提供，以便您可以测试自动授权和组成员身份，并且可以在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="eb988-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="eb988-117">第2阶段：注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="eb988-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="eb988-118">如果你正在考虑移动设备管理 (MDM) 解决方案来管理设备，则可以使用 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="eb988-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="eb988-119">在使用任何 MDM 提供程序（包括 Intune）时，设备都将 "注册"。</span><span class="sxs-lookup"><span data-stu-id="eb988-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="eb988-120">注册后，他们会收到您配置的功能和设置。</span><span class="sxs-lookup"><span data-stu-id="eb988-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="eb988-121">在 Intune 中，有几种方法可以注册 iOS/iPadOS 和 Android 设备。</span><span class="sxs-lookup"><span data-stu-id="eb988-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="eb988-122">您可以选择最适合您的组织的注册选项。</span><span class="sxs-lookup"><span data-stu-id="eb988-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="eb988-123">有关详细信息和指导，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="eb988-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="eb988-124">部署指南：在 Microsoft Intune 中注册 iOS 和 iPadOS 设备</span><span class="sxs-lookup"><span data-stu-id="eb988-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="eb988-125">部署指南：在 Microsoft Intune 中注册 Android 设备</span><span class="sxs-lookup"><span data-stu-id="eb988-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="eb988-126">如果你已准备好使用 Intune 进行设备管理，并希望获得一些指导，以下信息可能会有所帮助：</span><span class="sxs-lookup"><span data-stu-id="eb988-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="eb988-127">设备管理概述</span><span class="sxs-lookup"><span data-stu-id="eb988-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="eb988-128">教程： Microsoft 终结点管理器中的演练 Intune</span><span class="sxs-lookup"><span data-stu-id="eb988-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="eb988-129">部署指南：设置或移动到 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eb988-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="eb988-130">第3阶段：远程管理 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="eb988-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="eb988-131">Microsoft Intune 提供远程锁定和密码重置功能。</span><span class="sxs-lookup"><span data-stu-id="eb988-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="eb988-132">如果某人丢失了设备，则可以远程锁定设备。</span><span class="sxs-lookup"><span data-stu-id="eb988-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="eb988-133">如果有人忘记了密码，可以对其进行远程重置。</span><span class="sxs-lookup"><span data-stu-id="eb988-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="eb988-134">若要远程锁定 iOS/iPadOS 或 Android 设备，请参阅 [使用 Intune 远程锁定设备](/mem/intune/remote-actions/device-remote-lock)。</span><span class="sxs-lookup"><span data-stu-id="eb988-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="eb988-135">若要远程重置密码，请参阅 [在 Intune 中重置或删除设备密码](/mem/intune/remote-actions/device-passcode-reset)。</span><span class="sxs-lookup"><span data-stu-id="eb988-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="eb988-136">有关可远程运行的其他任务，请参阅 [可用的设备操作](/mem/intune/remote-actions/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="eb988-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="eb988-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eb988-137">Next step</span></span>

<span data-ttu-id="eb988-138">在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。</span><span class="sxs-lookup"><span data-stu-id="eb988-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb988-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb988-139">See Also</span></span>

[<span data-ttu-id="eb988-140">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="eb988-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="eb988-141">适用于 Microsoft 365 企业版测试环境的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="eb988-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="eb988-142">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="eb988-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
