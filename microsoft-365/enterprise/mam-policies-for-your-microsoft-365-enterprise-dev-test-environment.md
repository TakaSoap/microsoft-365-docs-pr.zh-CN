---
title: 用于 Microsoft 365 企业版测试环境的 MAM 策略
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南添加到 Microsoft 365 企业版 Intune 移动应用程序管理 (MAM) 策略测试环境。
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866028"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ea3fb-103">用于 Microsoft 365 企业版测试环境的 MAM 策略</span><span class="sxs-lookup"><span data-stu-id="ea3fb-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ea3fb-104">使用本文中的说明，您添加到 Microsoft 365 企业版 Intune 移动应用程序管理 (MAM) 策略测试环境。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ea3fb-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ea3fb-107">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="ea3fb-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ea3fb-108">如果您只想要配置的最低硬件要求与轻型方式 MAM 策略，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ea3fb-109">如果您想要配置 MAM 策略模拟企业中，按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea3fb-p101">测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="ea3fb-112">第 2 阶段：为 iOS 和 Android 设备创建和部署 MAM 策略</span><span class="sxs-lookup"><span data-stu-id="ea3fb-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="ea3fb-113">在此阶段中，创建和部署两个不同的 MAM 策略：一个适用于 iOS 设备的策略和一个适用于 Android 设备的策略。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="ea3fb-114">转到 Office 365 门户: ([https://portal.office.com](https://portal.office.com)) 和 Office 365 试用版订阅与全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="ea3fb-115">在浏览器的新建选项卡上，打开 Azure 门户： [https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="ea3fb-116">Azure 门户选项卡在 Internet Explorer 中，在导航窗格中，单击**所有服务**，键入**Intune**，，然后都单击**Intune**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="ea3fb-p102">如果您看到**尚未启用尚未设备管理**消息**Microsoft Intune**刀片上，单击该选项。在**移动设备管理证书颁发机构**刀片中，单击**Intune MDM 证书颁发机构**，，然后单击**选择**。刷新您浏览器的选项卡。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="ea3fb-120">在左侧导航窗格中，单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="ea3fb-121">在**组所有组**刀片中，单击 **+ 新建组**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="ea3fb-122">在**组**刀片中，选择**Office 365** **组类型？**，请在**名称**框中，键入**托管 iOS 设备用户**在**成员资格类型**，选择**已分配**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="ea3fb-123">关闭**组**刀片。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="ea3fb-124">在**组所有组**刀片中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="ea3fb-125">在**组**刀片中，选择**Office 365** **组类型？**，请在**名称**框中，键入**托管 Android 设备用户**在**成员资格类型**，选择**已分配**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="ea3fb-126">关闭**组所有组**刀片。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="ea3fb-127">在**Intune**刀片，在**快速的任务**列表中，单击**创建合规性策略**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="ea3fb-128">在**合规性策略配置文件**刀片中，单击**创建策略**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="ea3fb-p103">在**创建策略**刀片，在**名称**框中，键入**iOS**。在**平台**中，选择**iOS**、 **iOS 合规性策略**刀片上, 单击**确定**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="ea3fb-131">在**合规性策略配置文件**刀片中，单击**创建策略**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="ea3fb-p104">在**创建策略**刀片，在**名称**框中，键入**Android**。**平台**中, 选择**Android**， **Android 合规性策略**刀片上, 单击**确定**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="ea3fb-134">在**合规性策略配置文件**刀片中，单击**Android**的策略名称。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="ea3fb-135">**Android-属性**刀片的左侧导航中，单击**分配**，，然后单击**选择组**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="ea3fb-136">**选择组**刀片上,**托管 Android 设备用户**的组中，单击，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="ea3fb-137">单击**保存**，然后关闭**Android-分配**刀片。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="ea3fb-138">在**合规性策略配置文件**刀片中，单击**iOS**策略名称。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="ea3fb-139">在**iOS-属性**刀片左侧导航窗格中，单击**工作分配**，然后单击**选择组**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="ea3fb-140">在**选择组**刀片中，单击**托管 iOS 设备用户**组中，，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="ea3fb-141">单击**保存**，然后关闭**iOS-分配**刀片。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="ea3fb-142">关闭**合规性策略配置文件**刀片。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="ea3fb-143">在**Intune**刀片，单击左侧导航窗格中的**管理应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="ea3fb-144">在**移动应用程序**刀片中，单击**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="ea3fb-145">在应用程序列表中，单击**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="ea3fb-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="ea3fb-p105">在**PowerPoint 概述**刀片中，单击**分配 > 选择组 > 托管 iOS 设备 > 选择**。在**类型**中，选择**有空**，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="ea3fb-148">对于以下应用程序重复步骤 29:</span><span class="sxs-lookup"><span data-stu-id="ea3fb-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="ea3fb-149">Outlook for Android</span><span class="sxs-lookup"><span data-stu-id="ea3fb-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="ea3fb-150">Word for iOS</span><span class="sxs-lookup"><span data-stu-id="ea3fb-150">Word for iOS</span></span>
    
    - <span data-ttu-id="ea3fb-151">Excel for iOS</span><span class="sxs-lookup"><span data-stu-id="ea3fb-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="ea3fb-152">Outlook iOS</span><span class="sxs-lookup"><span data-stu-id="ea3fb-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="ea3fb-153">适用于 iOS iPad 的 Microsoft Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="ea3fb-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="ea3fb-154">适用于 iOS iPhone 的 Microsoft Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="ea3fb-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="ea3fb-155">适用于 Android 手机的 Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="ea3fb-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="ea3fb-156">适用于 Android 平板电脑的 Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="ea3fb-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="ea3fb-157">Excel for Android</span><span class="sxs-lookup"><span data-stu-id="ea3fb-157">Excel for Android</span></span>
    
    - <span data-ttu-id="ea3fb-158">Word for Android</span><span class="sxs-lookup"><span data-stu-id="ea3fb-158">Word for Android</span></span>
    
    - <span data-ttu-id="ea3fb-159">OneNote for iOS</span><span class="sxs-lookup"><span data-stu-id="ea3fb-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="ea3fb-160">关闭**移动应用程序的应用程序**刀片。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="ea3fb-161">在**移动应用程序**刀片中，单击**应用程序保护策略**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="ea3fb-162">在**应用程序保护策略**刀片中，单击**添加策略**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="ea3fb-163">在**添加策略**刀片中，键入**iOS**，，然后单击**选择所需的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="ea3fb-164">在**应用程序**刀片， **PowerPoint**、 **iPhone 上的 Microsoft Dynamics CRM**、 **Excel**、 **iPhone 上的 Microsoft Dynamics CRM**、 **Word**、 **OneNote**和**Outlook**中，单击，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="ea3fb-165">在**添加策略**刀片中，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="ea3fb-166">在**应用程序保护策略**刀片中，单击**添加策略**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="ea3fb-167">**添加策略**刀片上, 键入**Android**，在**平台**选择**Android** ，然后单击**选择所需的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="ea3fb-168">在**应用程序**刀片中，单击**PowerPoint**、**平板电脑的 Dynamics CRM**、 **Excel**、 **Word**、 **Outlook**和**电话的 Dynamics CRM**、，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="ea3fb-169">在**添加策略**刀片中，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="ea3fb-170">现在你有两个 MAM 策略，一个适用于 iOS 设备的策略和一个适用于 Android 设备的策略，并已准备好对所选应用的测试设置进行测试。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="ea3fb-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ea3fb-171">Next step</span></span>

<span data-ttu-id="ea3fb-172">浏览您的测试环境中其他[移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea3fb-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea3fb-173">See also</span></span>

<span data-ttu-id="ea3fb-174">[Microsoft 365 Enterprise 测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="ea3fb-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="ea3fb-175">在 Microsoft 365 企业版测试环境中注册 iOS 和 Android 设备</span><span class="sxs-lookup"><span data-stu-id="ea3fb-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="ea3fb-176">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="ea3fb-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ea3fb-177">企业移动 + 安全 (EMS)</span><span class="sxs-lookup"><span data-stu-id="ea3fb-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
