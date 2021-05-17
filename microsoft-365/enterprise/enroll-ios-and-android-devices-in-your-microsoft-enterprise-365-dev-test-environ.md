---
title: 在企业测试环境中注册 iOS/iPadOS Microsoft 365 Android 设备
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
description: 使用此测试实验室指南在测试环境中注册Microsoft 365并远程管理设备。
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367079"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9747f-103">在适用于企业测试Microsoft 365注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="9747f-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9747f-104">*本测试实验室指南只能用于Microsoft 365测试环境。*</span><span class="sxs-lookup"><span data-stu-id="9747f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="9747f-105">本文介绍如何在适用于企业测试环境的 Microsoft 365 注册和测试 iOS/iPadOS 和 Android 设备的基本移动设备管理功能。</span><span class="sxs-lookup"><span data-stu-id="9747f-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="9747f-106">在测试环境中注册 iOS/iPadOS 和 Android 设备涉及三个阶段：</span><span class="sxs-lookup"><span data-stu-id="9747f-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="9747f-107">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="9747f-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="9747f-108">阶段 2：注册 iOS/iPadOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="9747f-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="9747f-109">第 3 阶段：远程管理 iOS/iPadOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="9747f-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="9747f-111">有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365[企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9747f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9747f-112">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="9747f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9747f-113">如果你想要按照最低要求以轻型方式注册 iOS/iPadOS 和 Android 设备，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="9747f-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9747f-114">如果要在模拟的企业中注册 iOS/iPadOS 和 Android 设备，请按照传递 [身份验证 中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="9747f-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9747f-115">测试自动许可和组成员身份不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="9747f-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9747f-116">它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并且可以在代表典型组织的环境中试验它。</span><span class="sxs-lookup"><span data-stu-id="9747f-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="9747f-117">阶段 2：注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="9747f-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="9747f-118">如果你正在考虑使用移动设备管理 (MDM) 解决方案来管理设备，可以使用Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="9747f-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="9747f-119">使用任意 MDM 提供程序（包括 Intune）时，设备将"注册"。</span><span class="sxs-lookup"><span data-stu-id="9747f-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="9747f-120">注册后，他们将收到你配置的功能和设置。</span><span class="sxs-lookup"><span data-stu-id="9747f-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="9747f-121">在 Intune 中，有一些注册 iOS/iPadOS 和 Android 设备的方法。</span><span class="sxs-lookup"><span data-stu-id="9747f-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="9747f-122">你可以选择最适合你的组织的注册选项。</span><span class="sxs-lookup"><span data-stu-id="9747f-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="9747f-123">有关详细信息和指导，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="9747f-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="9747f-124">部署指南：在部署中注册 iOS 和 iPadOS Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9747f-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="9747f-125">部署指南：在 Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9747f-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="9747f-126">如果你已准备好使用 Intune 进行设备管理，并且需要一些指南，则以下信息可能会有所帮助：</span><span class="sxs-lookup"><span data-stu-id="9747f-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="9747f-127">设备管理概述</span><span class="sxs-lookup"><span data-stu-id="9747f-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="9747f-128">教程：演练 Intune Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="9747f-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="9747f-129">部署指南：安装或移动到Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9747f-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="9747f-130">第 3 阶段：远程管理 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="9747f-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="9747f-131">Microsoft Intune远程锁定和密码重置功能。</span><span class="sxs-lookup"><span data-stu-id="9747f-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="9747f-132">如果有人丢失了设备，你可以远程锁定设备。</span><span class="sxs-lookup"><span data-stu-id="9747f-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="9747f-133">如果有人忘记了自己的密码，可以远程重置密码。</span><span class="sxs-lookup"><span data-stu-id="9747f-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="9747f-134">若要远程锁定 iOS/iPadOS 或 Android 设备，请参阅使用 [Intune 远程锁定设备](/mem/intune/remote-actions/device-remote-lock)。</span><span class="sxs-lookup"><span data-stu-id="9747f-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="9747f-135">若要远程重置密码，请参阅在 [Intune 中重置或删除设备密码](/mem/intune/remote-actions/device-passcode-reset)。</span><span class="sxs-lookup"><span data-stu-id="9747f-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="9747f-136">有关你可以远程运行的其他任务，请参阅 [可用的设备操作](/mem/intune/remote-actions/device-management#available-device-actions)。</span><span class="sxs-lookup"><span data-stu-id="9747f-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="9747f-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9747f-137">Next step</span></span>

<span data-ttu-id="9747f-138">探索 [测试环境中](m365-enterprise-test-lab-guides.md#mobile-device-management) 的其他移动设备管理功能。</span><span class="sxs-lookup"><span data-stu-id="9747f-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9747f-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9747f-139">See Also</span></span>

[<span data-ttu-id="9747f-140">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="9747f-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="9747f-141">适用于企业测试Microsoft 365的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="9747f-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="9747f-142">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="9747f-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
