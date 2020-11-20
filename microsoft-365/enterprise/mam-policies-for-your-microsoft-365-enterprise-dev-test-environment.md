---
title: 适用于 Microsoft 365 企业版测试环境的设备合规性策略
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南将 Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境中。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367091"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ead80-103">适用于 Microsoft 365 企业版测试环境的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="ead80-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ead80-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="ead80-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ead80-105">本文介绍如何将适用于企业的 Windows 10 设备和 Microsoft 365 应用程序的 Intune 设备合规性策略添加到 Microsoft 365 for 企业测试环境。</span><span class="sxs-lookup"><span data-stu-id="ead80-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="ead80-106">添加 Intune 设备合规性策略涉及两个阶段：</span><span class="sxs-lookup"><span data-stu-id="ead80-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="ead80-107">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="ead80-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ead80-108">第2阶段：为 Windows 10 设备创建设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="ead80-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ead80-110">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ead80-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ead80-111">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="ead80-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ead80-112">如果您想要仅使用最低要求以轻量方式配置 MAM 策略，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ead80-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ead80-113">如果要在模拟的企业中配置 MAM 策略，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ead80-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ead80-114">测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="ead80-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ead80-115">它作为选项提供，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="ead80-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="ead80-116">第2阶段：为 Windows 10 设备创建设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="ead80-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="ead80-117">在此阶段中，将为 Windows 10 设备创建设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="ead80-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="ead80-118">此阶段使用 Microsoft Intune 和 [Microsoft 终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431) 添加组，并创建合规性策略。</span><span class="sxs-lookup"><span data-stu-id="ead80-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="ead80-119">转到 [microsoft 365 管理中心](https://admin.microsoft.com)，并使用全局管理员帐户登录到你的 microsoft 365 测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="ead80-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="ead80-120">选择 " **终结点管理器** " 管理中心。</span><span class="sxs-lookup"><span data-stu-id="ead80-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="ead80-121">[终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)将打开。</span><span class="sxs-lookup"><span data-stu-id="ead80-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="ead80-122">如果未 **启用 "设备管理尚未启用** " 的邮件，则选择 "Intune" 作为 MDM 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="ead80-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="ead80-123">有关具体步骤，请参阅 [设置移动设备管理机构](/mem/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="ead80-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="ead80-124">终结点管理器管理中心侧重于设备管理和应用管理。</span><span class="sxs-lookup"><span data-stu-id="ead80-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="ead80-125">有关此管理中心的教程，请参阅 [教程：演练 Intune In Microsoft 终结点管理器](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。</span><span class="sxs-lookup"><span data-stu-id="ead80-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="ead80-126">在 **"组**" 中，添加一个名为 "**托管 Windows 10 设备用户**" 的新 **Microsoft 365** 或 **安全** 组，其中包含 **已分配** 的成员身份类型。</span><span class="sxs-lookup"><span data-stu-id="ead80-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="ead80-127">在接下来的步骤中，你将向此组分配合规性策略。</span><span class="sxs-lookup"><span data-stu-id="ead80-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="ead80-128">有关具体步骤，以及有关 **Microsoft 365** 或 **安全** 组的信息，请参阅 [添加组以组织用户和设备](/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="ead80-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="ead80-129">在 " **设备**" 中，创建 Windows 10 合规性策略。</span><span class="sxs-lookup"><span data-stu-id="ead80-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="ead80-130">将此策略分配给您创建的 **托管 Windows 10 设备用户** 组。</span><span class="sxs-lookup"><span data-stu-id="ead80-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="ead80-131">在策略中，您可以阻止简单密码、需要防火墙、需要运行 Microsoft Defender 反恶意软件服务，等等。</span><span class="sxs-lookup"><span data-stu-id="ead80-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="ead80-132">合规性策略通常包括基本设置或每个设备应具有的最低基本设置。</span><span class="sxs-lookup"><span data-stu-id="ead80-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="ead80-133">有关具体步骤，以及可以配置的可用合规性设置的信息，请参阅 [使用合规性策略设置管理的设备的规则](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="ead80-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="ead80-134">完成后，你将拥有设备合规性策略，用于测试 **托管 Windows 10 设备用户** 组中的成员。</span><span class="sxs-lookup"><span data-stu-id="ead80-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="ead80-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ead80-135">Next step</span></span>

<span data-ttu-id="ead80-136">在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。</span><span class="sxs-lookup"><span data-stu-id="ead80-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ead80-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ead80-137">See also</span></span>

<span data-ttu-id="ead80-138">[适用于企业测试实验室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="ead80-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="ead80-139">在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="ead80-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="ead80-140">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="ead80-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ead80-141">企业移动性 + 安全性 (EMS)</span><span class="sxs-lookup"><span data-stu-id="ead80-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
