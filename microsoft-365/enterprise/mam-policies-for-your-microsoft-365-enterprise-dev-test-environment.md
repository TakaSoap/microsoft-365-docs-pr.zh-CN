---
title: 适用于企业测试Microsoft 365的设备合规性策略
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
description: 使用此测试实验室指南将 Intune 设备合规性策略Microsoft 365企业测试环境。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367091"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3ba53-103">适用于企业测试Microsoft 365的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="3ba53-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3ba53-104">*本测试实验室指南只能用于Microsoft 365测试环境。*</span><span class="sxs-lookup"><span data-stu-id="3ba53-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3ba53-105">本文介绍如何为企业测试环境Windows 10 Intune Microsoft 365 企业应用版和Microsoft 365 Intune 设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="3ba53-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="3ba53-106">添加 Intune 设备合规性策略涉及两个阶段：</span><span class="sxs-lookup"><span data-stu-id="3ba53-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="3ba53-107">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="3ba53-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="3ba53-108">阶段 2：为设备创建Windows 10策略</span><span class="sxs-lookup"><span data-stu-id="3ba53-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="3ba53-110">有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365[企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3ba53-111">第 1 阶段：构建Microsoft 365测试环境</span><span class="sxs-lookup"><span data-stu-id="3ba53-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3ba53-112">如果你希望仅采用满足最低要求的轻型方式配置 MAM 策略，请按照轻型基本配置 [中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3ba53-113">如果要在模拟的企业中配置 MAM 策略，请按照传递 [身份验证 中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3ba53-114">测试自动许可和组成员身份不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="3ba53-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3ba53-115">它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="3ba53-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="3ba53-116">阶段 2：为设备创建Windows 10策略</span><span class="sxs-lookup"><span data-stu-id="3ba53-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="3ba53-117">在此阶段中，为设备创建Windows 10策略。</span><span class="sxs-lookup"><span data-stu-id="3ba53-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="3ba53-118">此阶段Microsoft Intune和Microsoft Endpoint Manager管理中心添加[](https://go.microsoft.com/fwlink/?linkid=2109431)组，并创建合规性策略。</span><span class="sxs-lookup"><span data-stu-id="3ba53-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="3ba53-119">转到["Microsoft 365](https://admin.microsoft.com)中心"，然后使用全局管理员Microsoft 365登录到你的测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="3ba53-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="3ba53-120">选择 **"Endpoint Manager** 管理中心"。</span><span class="sxs-lookup"><span data-stu-id="3ba53-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="3ba53-121">将[Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="3ba53-122">如果显示类似于 **你尚未启用设备** 管理的消息，则选择 Intune 作为 MDM 颁发机构。</span><span class="sxs-lookup"><span data-stu-id="3ba53-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="3ba53-123">有关具体步骤，请参阅 [设置移动设备管理机构](/mem/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="3ba53-124">管理Endpoint Manager中心侧重于设备管理和应用管理。</span><span class="sxs-lookup"><span data-stu-id="3ba53-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="3ba53-125">有关此管理中心的教程，请参阅[教程：Microsoft Endpoint Manager 中的演练 Intune。](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)</span><span class="sxs-lookup"><span data-stu-id="3ba53-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="3ba53-126">在 **"组**"中，Microsoft 365"已分配成员身份"类型的名为"托管Windows 10 **组或**"安全"组。 </span><span class="sxs-lookup"><span data-stu-id="3ba53-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="3ba53-127">在以下步骤中，将合规性策略分配给该组。</span><span class="sxs-lookup"><span data-stu-id="3ba53-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="3ba53-128">有关特定步骤，以及 **有关Microsoft 365\*\*\*\*组** 的信息，请参阅添加 [组以组织用户和设备](/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="3ba53-129">在 **"设备"** 中，创建Windows 10合规性策略。</span><span class="sxs-lookup"><span data-stu-id="3ba53-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="3ba53-130">将此策略分配给Windows 10 **托管设备** 用户组。</span><span class="sxs-lookup"><span data-stu-id="3ba53-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="3ba53-131">在你的策略中，可以阻止简单密码、需要防火墙、要求运行 Microsoft Defender 反恶意软件服务等。</span><span class="sxs-lookup"><span data-stu-id="3ba53-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="3ba53-132">合规性策略通常包括基本设置，或每个设备应具有的最低设置。</span><span class="sxs-lookup"><span data-stu-id="3ba53-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="3ba53-133">有关特定步骤以及可配置的可用合规性设置的信息，请参阅使用合规性策略为管理的设备 [设置规则](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="3ba53-134">完成后，你有一个设备合规性策略，用于测试托管Windows 10 **组的成员**。</span><span class="sxs-lookup"><span data-stu-id="3ba53-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="3ba53-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3ba53-135">Next step</span></span>

<span data-ttu-id="3ba53-136">探索 [测试环境中](m365-enterprise-test-lab-guides.md#mobile-device-management) 的其他移动设备管理功能。</span><span class="sxs-lookup"><span data-stu-id="3ba53-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ba53-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ba53-137">See also</span></span>

<span data-ttu-id="3ba53-138">[Microsoft 365测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="3ba53-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="3ba53-139">在适用于企业测试Microsoft 365注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="3ba53-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="3ba53-140">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="3ba53-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3ba53-141">企业移动性 + 安全性 (EMS)</span><span class="sxs-lookup"><span data-stu-id="3ba53-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
