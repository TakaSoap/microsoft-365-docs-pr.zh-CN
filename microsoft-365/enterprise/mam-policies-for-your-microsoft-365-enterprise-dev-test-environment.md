---
title: 适用于 Microsoft 365 企业版测试环境的设备合规性策略
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南将 Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境中。
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487408"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="bcc58-103">适用于 Microsoft 365 企业版测试环境的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="bcc58-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="bcc58-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="bcc58-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="bcc58-105">本文介绍如何将适用于企业的 Windows 10 设备和 Microsoft 365 应用程序的 Intune 设备合规性策略添加到 Microsoft 365 for 企业测试环境。</span><span class="sxs-lookup"><span data-stu-id="bcc58-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="bcc58-106">添加 Intune 设备合规性策略涉及两个阶段：</span><span class="sxs-lookup"><span data-stu-id="bcc58-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="bcc58-107">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="bcc58-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="bcc58-108">第2阶段：为 Windows 10 设备创建设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="bcc58-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="bcc58-110">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="bcc58-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="bcc58-111">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="bcc58-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="bcc58-112">如果您想要仅使用最低要求以轻量方式配置 MAM 策略，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="bcc58-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="bcc58-113">如果要在模拟的企业中配置 MAM 策略，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="bcc58-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bcc58-114">测试自动授权和组成员身份不需要模拟企业测试环境，其中包括连接到 internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="bcc58-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="bcc58-115">它作为选项提供，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="bcc58-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="bcc58-116">第2阶段：为 Windows 10 设备创建设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="bcc58-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="bcc58-117">在此阶段，为 Windows 10 设备创建设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="bcc58-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="bcc58-118">转到 [microsoft 365 管理中心](https://admin.microsoft.com) ，并使用全局管理员帐户登录 microsoft 365 测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="bcc58-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="bcc58-119">在浏览器的新选项卡上，在上打开 Azure 门户 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="bcc58-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="bcc58-120">在 Azure 门户的搜索框中，输入 **intune**，然后选择 **intune**。</span><span class="sxs-lookup"><span data-stu-id="bcc58-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="bcc58-121">如果您在 " **Microsoft Intune** " 窗格中看到 "**尚未启用设备管理**" 消息，请选择它。</span><span class="sxs-lookup"><span data-stu-id="bcc58-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="bcc58-122">在 " **移动设备管理机构** " 窗格中，选择 " **Intune MDM 颁发机构**"，然后选择 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="bcc58-123">刷新浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcc58-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="bcc58-124">在左侧导航窗格中，选择 " **组**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="bcc58-125">在 " **组-所有组** " 窗格中，选择 " **+ 新建组**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="bcc58-126">在**组**窗格中，选择 **"组类型**的**Microsoft 365** " 或 "**安全**"，在 "**名称**" 中输入**托管 Windows 10 设备用户**，在 "**成员身份类型**" 中选择 "**已分配**"，然后选择 "**创建**"</span><span class="sxs-lookup"><span data-stu-id="bcc58-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="bcc58-127">选择 " **Microsoft Intune**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="bcc58-128">在 " **Microsoft Intune** " 窗格中的 " **快速任务** " 列表中，选择 " **创建合规性策略**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="bcc58-129">在 " **合规性策略配置文件** " 窗格中，选择 " **创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="bcc58-130">在 " **创建策略** " 窗格中的 " **名称**" 中，输入 **Windows 10**。</span><span class="sxs-lookup"><span data-stu-id="bcc58-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="bcc58-131">在 "**平台**" 中，选择 " **windows 10 及更高版本**"，在**Windows 10 合规性策略**窗格中选择 **"确定"** ，然后选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="bcc58-132">选择 " **合规性策略配置文件**"，然后选择 **Windows 10** 策略名称。</span><span class="sxs-lookup"><span data-stu-id="bcc58-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="bcc58-133">在 " **Windows 10** " 窗格中，选择 " **分配**"，然后选择 " **选择要包含的组**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="bcc58-134">在 " **选择要包含的组** " 窗格中，选择 " **托管 Windows 10 设备用户** " 组，然后选择 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="bcc58-135">选择 " **保存**"，选择 " **Microsoft Intune-概述**"，然后在左侧导航中选择 " **客户端应用** "。</span><span class="sxs-lookup"><span data-stu-id="bcc58-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="bcc58-136">在 " **客户端应用** " 窗格中，选择 " **应用**"，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="bcc58-137">在 "**添加应用程序**" 窗格中，选择 "**应用程序类型**"，然后选择 " **Microsoft 365 套件**下的**Windows 10** "。</span><span class="sxs-lookup"><span data-stu-id="bcc58-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="bcc58-138">在 " **添加应用程序** " 窗格中，选择 " **应用程序套件信息**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="bcc58-139">在 "**应用套件信息**" 窗格中，在 "**套件名称**" 和 "**套件说明**" 中输入 "**适用于企业的 Microsoft 365 应用**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bcc58-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="bcc58-140">在 " **添加应用程序** " 窗格中，选择 " **配置应用程序套件**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bcc58-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="bcc58-141">在 " **添加应用程序** " 窗格中，选择 " **应用程序套件设置**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="bcc58-142">对于 " **更新频道**"，选择 " **半年企业**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bcc58-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="bcc58-143">在 " **添加应用程序** " 窗格中，选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="bcc58-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="bcc58-144">现在，你已拥有设备合规性策略，用于测试 **Windows 10** 设备合规性策略中的所选应用和 **托管 windows 10 设备用户** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="bcc58-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="bcc58-145">请注意，如果选择 **Microsoft 365** 作为组类型，则会创建其他资源。</span><span class="sxs-lookup"><span data-stu-id="bcc58-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="bcc58-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bcc58-146">Next step</span></span>

<span data-ttu-id="bcc58-147">在您的测试环境中探索其他 [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 特性和功能。</span><span class="sxs-lookup"><span data-stu-id="bcc58-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcc58-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc58-148">See also</span></span>

<span data-ttu-id="bcc58-149">[适用于企业测试实验室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc58-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="bcc58-150">在 Microsoft 365 for 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="bcc58-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="bcc58-151">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="bcc58-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="bcc58-152">企业移动性 + 安全性 (EMS)</span><span class="sxs-lookup"><span data-stu-id="bcc58-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
