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
ms.openlocfilehash: 5ef39310ff74e5d5a38e8a5dd8c7ca24a126af58
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679022"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fb6c9-103">适用于 Microsoft 365 企业版测试环境的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="fb6c9-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fb6c9-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="fb6c9-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="fb6c9-105">使用本文中的说明，可以向 Microsoft 365 企业版测试环境中添加适用于企业的 Windows 10 设备和 Microsoft 365 应用程序的 Intune 设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="fb6c9-107">单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fb6c9-108">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fb6c9-109">如果只想使用最低要求以轻型方式配置 MAM 策略，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fb6c9-110">如果要在模拟的企业中配置 MAM 策略，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb6c9-111">测试自动许可和组成员身份不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="fb6c9-112">此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="fb6c9-113">第2阶段：为 Windows 10 设备创建设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="fb6c9-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="fb6c9-114">在此阶段中，将为 Windows 10 设备创建设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="fb6c9-115">转到 Office 365 门户（ [https://portal.office.com](https://portal.office.com) ），并使用全局管理员帐户登录到你的 office 365 测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="fb6c9-116">在浏览器的新选项卡上，在上打开 Azure 门户 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="fb6c9-117">从浏览器的 "Azure 门户" 选项卡中，在搜索框中键入**Intune** ，然后单击 " **intune**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="fb6c9-118">如果您在 " **Microsoft Intune** " 窗格中看到 "**尚未启用设备管理**" 消息，请单击它。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="fb6c9-119">在 "**移动设备管理机构**" 窗格中，单击 " **Intune MDM 颁发机构**"，然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="fb6c9-120">刷新浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="fb6c9-121">在左侧导航窗格中，单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="fb6c9-122">在 "**组-所有组**" 窗格中，单击 " **+ 新建组**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="fb6c9-123">在**组**窗格中，选择 **"组类型**的**Office 365**或**安全性**？"，在 "**名称**" 中键入**托管 Windows 10 设备用户**，在 "**成员资格类型**" 中选择 "**已分配**"，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="fb6c9-124">单击 " **Microsoft Intune**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="fb6c9-125">在 " **Microsoft Intune** " 窗格中的 "**快速任务**" 列表中，单击 "**创建合规性策略**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="fb6c9-126">在 "**合规性策略配置文件**" 窗格中，单击 "**创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="fb6c9-127">在 "**创建策略**" 窗格中的 "**名称**" 中，键入**Windows 10**。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="fb6c9-128">在 "**平台**" 中，选择 " **windows 10 及更高版本**"，在**windows 10 合规性策略**窗格中单击 **"确定"** ，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="fb6c9-129">单击 "**合规性策略配置文件**"，然后单击**Windows 10**策略名称。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="fb6c9-130">在 " **Windows 10** " 窗格中，单击 "**分配**"，然后单击 "**选择要包含的组**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="fb6c9-131">在 "**选择要包含的组**" 窗格中，单击 "**托管 Windows 10 设备用户**" 组，然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="fb6c9-132">单击 "**保存**"，再单击 " **Microsoft Intune-概述**"，然后单击左侧导航栏中的 "**客户端应用**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="fb6c9-133">在 "**客户端应用程序**" 窗格中，单击 "**应用**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="fb6c9-134">在 "**添加应用程序**" 窗格中，选择 "**应用程序类型**"，然后选择 " **Office 365 套件**下的**Windows 10** "。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="fb6c9-135">在 "**添加应用程序**" 窗格中，选择 "**应用程序套件信息**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="fb6c9-136">在 "**应用程序套件信息**" 窗格中，在 "**套件名称**" 和 "**套件说明**" 中键入**适用于企业的 Microsoft 365 应用**。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="fb6c9-137">单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-137">Click OK.</span></span>

19. <span data-ttu-id="fb6c9-138">在 "**添加应用程序**" 窗格中，选择 "**配置应用程序套件**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="fb6c9-139">在 "**添加应用程序**" 窗格中，选择 "**应用程序套件设置**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="fb6c9-140">对于 "**更新频道**"，选择 "**半年企业**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="fb6c9-141">在 "**添加应用程序**" 窗格中，单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="fb6c9-142">现在，你已拥有设备合规性策略，用于测试**Windows 10**设备合规性策略中的所选应用和**托管 windows 10 设备用户**组的成员。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="fb6c9-143">请注意，选择 "Office 365" 作为组类型将会创建其他资源。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="fb6c9-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fb6c9-144">Next step</span></span>

<span data-ttu-id="fb6c9-145">在您的测试环境中探索其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb6c9-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb6c9-146">See also</span></span>

<span data-ttu-id="fb6c9-147">[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6c9-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="fb6c9-148">在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="fb6c9-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="fb6c9-149">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="fb6c9-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fb6c9-150">企业移动性 + 安全性 (EMS)</span><span class="sxs-lookup"><span data-stu-id="fb6c9-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
