---
title: 设备的 Microsoft 365 企业版的合规性策略测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南添加到 Microsoft 365 企业版 Intune 设备合规性策略测试环境。
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866028"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b43f2-103">设备的 Microsoft 365 企业版的合规性策略测试环境</span><span class="sxs-lookup"><span data-stu-id="b43f2-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b43f2-104">使用本文中的说明，Intune 设备合规性策略添加到 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="b43f2-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b43f2-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="b43f2-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b43f2-107">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="b43f2-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b43f2-108">如果您只想要配置的最低硬件要求与轻型方式 MAM 策略，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="b43f2-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b43f2-109">如果您想要配置 MAM 策略模拟企业中，按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="b43f2-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b43f2-p101">测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="b43f2-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="b43f2-112">阶段 2： 创建 Windows 10 设备的设备合规性策略</span><span class="sxs-lookup"><span data-stu-id="b43f2-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="b43f2-113">在此阶段中，您将创建 Windows 10 设备的设备合规性策略。</span><span class="sxs-lookup"><span data-stu-id="b43f2-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="b43f2-114">转到 Office 门户: ([https://office.com](https://office.com)) 和 Office 365 试用版订阅与全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b43f2-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="b43f2-115">在浏览器的新建选项卡上，打开 Azure 门户： [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="b43f2-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="b43f2-116">在浏览器中，在导航窗格中，Azure 门户选项卡上单击**所有服务**，键入**Intune**，，然后都单击**Intune**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="b43f2-p102">如果您看到**尚未启用尚未设备管理**消息**Microsoft Intune**刀片上，单击该选项。在**移动设备管理证书颁发机构**刀片中，单击**Intune MDM 证书颁发机构**，，然后单击**选择**。刷新您浏览器的选项卡。</span><span class="sxs-lookup"><span data-stu-id="b43f2-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="b43f2-120">在左侧导航窗格中，单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b43f2-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="b43f2-121">在**组所有组**刀片中，单击 **+ 新建组**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="b43f2-122">在**组**刀片中，选择**Office 365** **组类型？**，请在**名称**框中，键入**托管 Windows 10 设备用户**在**成员资格类型**，选择**已分配**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="b43f2-123">关闭**组**刀片。</span><span class="sxs-lookup"><span data-stu-id="b43f2-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="b43f2-124">关闭**组所有组**刀片。</span><span class="sxs-lookup"><span data-stu-id="b43f2-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="b43f2-125">在**Microsoft Intune**刀片，在**快速的任务**列表中，单击**创建合规性策略**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="b43f2-126">在**合规性策略配置文件**刀片中，单击**创建策略**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="b43f2-p103">在**创建策略**刀片，在**名称**框中，键入**Windows 10**。**平台**中, 选择**10 及更高版本的 Windows**，在**Windows 10 合规性策略**刀片中，单击**确定**，然后单击**创建**。关闭**Windows 10**刀片。</span><span class="sxs-lookup"><span data-stu-id="b43f2-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="b43f2-130">在**合规性策略配置文件**刀片中，单击**Windows 10**策略名称。</span><span class="sxs-lookup"><span data-stu-id="b43f2-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="b43f2-131">在**Windows 10**刀片中，单击**分配**，，然后单击**选择要包括的组**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="b43f2-132">**选择要包括的组**刀片上, 单击**托管 Windows 10 设备用户**组中，，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="b43f2-133">单击**保存**，然后关闭**Windows 10-分配**刀片。</span><span class="sxs-lookup"><span data-stu-id="b43f2-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="b43f2-134">关闭**合规性策略配置文件**刀片。</span><span class="sxs-lookup"><span data-stu-id="b43f2-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="b43f2-135">在**Microsoft Intune**刀片中，单击左侧导航窗格中**客户端应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="b43f2-136">在**客户端应用程序**刀片中，单击**应用程序**，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="b43f2-137">在**添加应用程序**刀片中，选择**应用程序类型**，，然后选择**Office 365 套件**下**Windows 10** 。</span><span class="sxs-lookup"><span data-stu-id="b43f2-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="b43f2-138">**配置应用程序套件**，请单击，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="b43f2-139">单击**应用程序套件信息**、 键入**套件名称**，在**套件说明**框中， **Office 应用程序的 Windows 10** **Office 应用程序的 Windows 10** ，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="b43f2-140">单击**应用程序套件设置**，在**更新通道**中，选择**半年**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="b43f2-141">在**添加应用程序**刀片中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b43f2-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="b43f2-142">现在，您具有设备合规性策略测试**Windows 10**设备合规性策略中选定的应用程序和**托管 Windows 10 设备用户**组的成员。</span><span class="sxs-lookup"><span data-stu-id="b43f2-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="b43f2-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b43f2-143">Next step</span></span>

<span data-ttu-id="b43f2-144">浏览您的测试环境中其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="b43f2-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b43f2-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b43f2-145">See also</span></span>

<span data-ttu-id="b43f2-146">[Microsoft 365 Enterprise 测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="b43f2-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="b43f2-147">在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="b43f2-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="b43f2-148">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b43f2-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b43f2-149">企业移动 + 安全 (EMS)</span><span class="sxs-lookup"><span data-stu-id="b43f2-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
