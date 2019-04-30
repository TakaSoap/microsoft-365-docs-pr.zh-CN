---
title: 适用于 Microsoft 365 企业版测试环境的设备合规性策略
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南将 Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境中。
ms.openlocfilehash: b8c2fbe437362f72effd5ba550817f847ccbbf74
ms.sourcegitcommit: e15cf5d0d8ff3dfdc457b469992d72ac802e6434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467730"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="57abd-103">适用于 Microsoft 365 企业版测试环境的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="57abd-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="57abd-104">使用本文中的说明, 可以向 Microsoft 365 企业版测试环境中添加 Intune 设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="57abd-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="57abd-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="57abd-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="57abd-107">第1阶段: 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="57abd-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="57abd-108">如果只想使用最低要求以轻型方式配置 MAM 策略, 请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="57abd-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="57abd-109">如果要在模拟的企业中配置 MAM 策略, 请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="57abd-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="57abd-110">测试自动许可和组成员身份不需要模拟企业测试环境, 其中包括连接到 Internet 的模拟 intranet 和 Active directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="57abd-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="57abd-111">此处提供了此选项, 以便您可以测试自动授权和组成员身份, 并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="57abd-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="57abd-112">第2阶段: 为 Windows 10 设备创建设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="57abd-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="57abd-113">在此阶段中, 将为 Windows 10 设备创建设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="57abd-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="57abd-114">转到 office 365 门户 ([https://portal.office.com](https://portal.office.com)), 并使用全局管理员帐户登录到你的 office 365 测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="57abd-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="57abd-115">在浏览器的新选项卡上, 在上打开 Azure [https://portal.azure.com](https://portal.azure.com)门户。</span><span class="sxs-lookup"><span data-stu-id="57abd-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="57abd-116">在浏览器中的 "Azure 门户" 选项卡上, 在导航窗格中, 单击 "**所有服务**", 键入**Intune**, 然后单击 " **intune**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="57abd-117">如果您在**Microsoft Intune**边栏上发现**尚未启用 "设备管理**" 消息, 请单击它。</span><span class="sxs-lookup"><span data-stu-id="57abd-117">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="57abd-118">在 "**移动设备管理机构**" 边栏选项卡上, 单击 " **Intune MDM 颁发机构**", 然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-118">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="57abd-119">刷新浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="57abd-119">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="57abd-120">在左侧导航窗格中，单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57abd-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="57abd-121">在 "**组-所有组**" 边栏选项卡上, 单击 " **+ 新建组**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="57abd-122">在**组**边栏上, 选择 **"组类型**的**Office 365**或**安全性**？", 在 "**名称**" 中键入**托管 Windows 10 设备用户**, 在 "**成员身份类型**" 中选择 "**已分配**", 然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-122">On the **Group** blade, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="57abd-123">关闭“组”\*\*\*\* 边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="57abd-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="57abd-124">关闭 "**组-所有组**" 边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="57abd-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="57abd-125">在**Microsoft Intune**边栏上的 "**快速任务**" 列表中, 单击 "**创建合规性策略**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="57abd-126">在“符合性策略配置文件”\*\*\*\* 边栏选项卡上，单击“创建策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="57abd-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="57abd-127">在 "**创建策略**" 边栏上的 "**名称**" 中, 键入**Windows 10**。</span><span class="sxs-lookup"><span data-stu-id="57abd-127">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="57abd-128">在 "**平台**" 中, 选择 " **windows 10 及更高版本**", 在**windows 10 合规性策略**边栏上单击 **"确定**", 然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-128">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="57abd-129">关闭**Windows 10**边栏。</span><span class="sxs-lookup"><span data-stu-id="57abd-129">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="57abd-130">在 "**合规性策略配置文件**" 边栏选项卡上, 单击**Windows 10**策略名称。</span><span class="sxs-lookup"><span data-stu-id="57abd-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="57abd-131">在**Windows 10**边栏上, 单击 "**分配**", 然后单击 "**选择要包含的组**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="57abd-132">在 "**选择要包括的组**" 边栏选项卡上, 单击 "**托管 Windows 10 设备用户**" 组, 然后单击 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="57abd-133">单击 "**保存**", 然后关闭 " **Windows 10 工作分配**" 边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="57abd-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="57abd-134">关闭“符合性策略配置文件”\*\*\*\* 边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="57abd-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="57abd-135">在**Microsoft Intune**边栏上, 单击左侧导航栏中的 "**客户端应用**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="57abd-136">在**客户端应用程序**边栏中, 单击 "**应用程序**", 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="57abd-137">在 "**添加应用程序**" 边栏选项卡上, 选择 "**应用类型**", 然后选择 " **Office 365 套件**下的**Windows 10** "。</span><span class="sxs-lookup"><span data-stu-id="57abd-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="57abd-138">单击 "**配置应用程序套件**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="57abd-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="57abd-139">单击 "**应用套件信息**", 在 "**套件名称**" 中键入**office apps for** windows 10, 在**套件**中键入适用于**windows 10 的 office 应用程序**, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="57abd-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="57abd-140">单击 "**应用套件设置**", 选择 "**半年\*\*\*\*更新频道**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="57abd-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="57abd-141">在 "**添加应用程序**" 边栏选项卡上, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="57abd-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="57abd-142">现在, 你已拥有设备合规性策略, 用于测试**Windows 10**设备合规性策略中的所选应用和**托管 windows 10 设备用户**组的成员。</span><span class="sxs-lookup"><span data-stu-id="57abd-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="57abd-143">请注意, 选择 "Office 365" 作为组类型将会创建其他资源。</span><span class="sxs-lookup"><span data-stu-id="57abd-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="57abd-144">下一步骤</span><span class="sxs-lookup"><span data-stu-id="57abd-144">Next step</span></span>

<span data-ttu-id="57abd-145">在您的测试环境中探索其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="57abd-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="57abd-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57abd-146">See also</span></span>

<span data-ttu-id="57abd-147">[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="57abd-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="57abd-148">在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="57abd-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="57abd-149">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="57abd-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="57abd-150">企业移动性 + 安全性 (EMS)</span><span class="sxs-lookup"><span data-stu-id="57abd-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
