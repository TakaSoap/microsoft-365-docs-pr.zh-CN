---
title: 使用 Microsoft Endpoint Manager 载入
description: 了解如何使用 Microsoft Endpoint Manager 载入 Microsoft Defender for Endpoint
keywords: 载入， 配置， 部署， 部署， 终结点管理器， mdatp， 高级威胁防护， 集合创建， 终结点检测响应， 下一代保护， 攻击面减少， microsoft 终结点管理器
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4028fbaedd4e0b89b37a774b79ac5302d899ec3c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054651"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="5f177-104">使用 Microsoft Endpoint Manager 载入</span><span class="sxs-lookup"><span data-stu-id="5f177-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f177-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5f177-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f177-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5f177-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="5f177-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f177-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5f177-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5f177-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5f177-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="5f177-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5f177-110">本文是部署指南的一部分，并作为示例载入方法。</span><span class="sxs-lookup"><span data-stu-id="5f177-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="5f177-111">在 [规划主题](deployment-strategy.md) 中，提供了多种方法将设备载入服务。</span><span class="sxs-lookup"><span data-stu-id="5f177-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="5f177-112">本主题介绍云本机体系结构。</span><span class="sxs-lookup"><span data-stu-id="5f177-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="5f177-113">![云本机体系结构的图像 ](images/cloud-native-architecture.png)
 *环境体系结构关系图*</span><span class="sxs-lookup"><span data-stu-id="5f177-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="5f177-114">尽管 Defender for Endpoint 支持载入各种终结点和工具，但本文并未涵盖它们。</span><span class="sxs-lookup"><span data-stu-id="5f177-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="5f177-115">有关使用其他受支持的部署工具和方法进行常规载入的信息，请参阅 [载入概述](onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="5f177-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="5f177-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) 是统一多个服务的解决方案平台。</span><span class="sxs-lookup"><span data-stu-id="5f177-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="5f177-117">它包括[用于基于云的设备管理的 Microsoft Intune。](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="5f177-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="5f177-118">本主题指导用户：</span><span class="sxs-lookup"><span data-stu-id="5f177-118">This topic guides users in:</span></span>
- <span data-ttu-id="5f177-119">步骤 1：在 Microsoft Endpoint Manager 和 MEM (创建组，将设备载入) 分配配置</span><span class="sxs-lookup"><span data-stu-id="5f177-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="5f177-120">步骤 2：使用 Microsoft Endpoint Manager 为终结点功能配置 Defender</span><span class="sxs-lookup"><span data-stu-id="5f177-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="5f177-121">此载入指南将指导你完成使用 Microsoft Endpoint Manager 时需要执行以下基本步骤：</span><span class="sxs-lookup"><span data-stu-id="5f177-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="5f177-122">标识目标设备或用户</span><span class="sxs-lookup"><span data-stu-id="5f177-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="5f177-123">创建 Azure Active Directory 组 (用户或设备) </span><span class="sxs-lookup"><span data-stu-id="5f177-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="5f177-124">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="5f177-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="5f177-125">在 Microsoft Endpoint Manager 中，我们将指导你为每种功能创建单独的策略。</span><span class="sxs-lookup"><span data-stu-id="5f177-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="5f177-126">资源</span><span class="sxs-lookup"><span data-stu-id="5f177-126">Resources</span></span>


<span data-ttu-id="5f177-127">以下是此过程的其余部分所需的链接：</span><span class="sxs-lookup"><span data-stu-id="5f177-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="5f177-128">MEM 门户</span><span class="sxs-lookup"><span data-stu-id="5f177-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="5f177-129">安全中心</span><span class="sxs-lookup"><span data-stu-id="5f177-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="5f177-130">Intune 安全基线</span><span class="sxs-lookup"><span data-stu-id="5f177-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="5f177-131">有关 Microsoft Endpoint Manager 详细信息，请查看以下资源：</span><span class="sxs-lookup"><span data-stu-id="5f177-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="5f177-132">Microsoft Endpoint Manager 页面</span><span class="sxs-lookup"><span data-stu-id="5f177-132">Microsoft Endpoint Manager page</span></span>](https://docs.microsoft.com/mem/)
- [<span data-ttu-id="5f177-133">有关 Intune 和 ConfigMgr 聚合的博客文章</span><span class="sxs-lookup"><span data-stu-id="5f177-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="5f177-134">MEM 简介视频</span><span class="sxs-lookup"><span data-stu-id="5f177-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="5f177-135">步骤 1：在 MEM 中创建组以在上分配配置来载入设备</span><span class="sxs-lookup"><span data-stu-id="5f177-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="5f177-136">确定目标设备或用户</span><span class="sxs-lookup"><span data-stu-id="5f177-136">Identify target devices or users</span></span>
<span data-ttu-id="5f177-137">在此部分中，我们将创建一个测试组来分配配置。</span><span class="sxs-lookup"><span data-stu-id="5f177-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="5f177-138">Intune 使用 Azure Active Directory (Azure AD) 组来管理设备和用户。</span><span class="sxs-lookup"><span data-stu-id="5f177-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="5f177-139">作为 Intune 管理员，你可以设置组以满足你的组织需求。</span><span class="sxs-lookup"><span data-stu-id="5f177-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="5f177-140">有关详细信息，请参阅添加 [组以组织用户和设备](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="5f177-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="5f177-141">创建群组</span><span class="sxs-lookup"><span data-stu-id="5f177-141">Create a group</span></span>

1.  <span data-ttu-id="5f177-142">打开 MEM 门户。</span><span class="sxs-lookup"><span data-stu-id="5f177-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5f177-143">打开 **"组>新建组"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-144">![Microsoft Endpoint Manager 门户的图像1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="5f177-145">输入详细信息并创建新组。</span><span class="sxs-lookup"><span data-stu-id="5f177-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-146">![Microsoft Endpoint Manager 门户 2 的图像](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="5f177-147">添加测试用户或设备。</span><span class="sxs-lookup"><span data-stu-id="5f177-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="5f177-148">从" **组>所有组"窗格中** ，打开新组。</span><span class="sxs-lookup"><span data-stu-id="5f177-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="5f177-149">选择 **"成员>添加成员"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="5f177-150">查找测试用户或设备并选择它。</span><span class="sxs-lookup"><span data-stu-id="5f177-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-151">![Microsoft Endpoint Manager 门户的图像3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="5f177-152">你的测试组现在具有要测试的成员。</span><span class="sxs-lookup"><span data-stu-id="5f177-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="5f177-153">步骤 2：创建配置策略以配置 Microsoft Defender 的终结点功能</span><span class="sxs-lookup"><span data-stu-id="5f177-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="5f177-154">下一节将创建多个配置策略。</span><span class="sxs-lookup"><span data-stu-id="5f177-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="5f177-155">首先，配置策略用于选择哪些用户组或设备将载入到适用于终结点的 Defender：</span><span class="sxs-lookup"><span data-stu-id="5f177-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="5f177-156">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="5f177-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="5f177-157">然后，继续创建几种不同类型的终结点安全策略：</span><span class="sxs-lookup"><span data-stu-id="5f177-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="5f177-158">下一代保护</span><span class="sxs-lookup"><span data-stu-id="5f177-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="5f177-159">攻击面减少</span><span class="sxs-lookup"><span data-stu-id="5f177-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="5f177-160">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="5f177-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="5f177-161">打开 MEM 门户。</span><span class="sxs-lookup"><span data-stu-id="5f177-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5f177-162">导航到 **终结点安全>终结点检测和响应**。</span><span class="sxs-lookup"><span data-stu-id="5f177-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="5f177-163">单击"**创建配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-164">![Microsoft Endpoint Manager 门户的图像4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="5f177-165">在 **平台下，选择 Windows 10 和更高版本，配置文件 - 终结点检测和响应>创建**。</span><span class="sxs-lookup"><span data-stu-id="5f177-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="5f177-166">输入名称和说明，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-167">![Microsoft Endpoint Manager 门户的图像5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="5f177-168">按要求选择设置，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-169">![Microsoft Endpoint Manager 门户的图像6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f177-170">在此实例中，已自动填充，因为 Defender for Endpoint 已与 Intune 集成。</span><span class="sxs-lookup"><span data-stu-id="5f177-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="5f177-171">有关集成详细信息，请参阅在 Intune 中启用[Microsoft Defender for Endpoint。](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="5f177-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="5f177-172">下图是当 Microsoft Defender for Endpoint 未与 Intune 集成时你将看到的示例：</span><span class="sxs-lookup"><span data-stu-id="5f177-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Microsoft Endpoint Manager 门户的图像7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="5f177-174">如有必要，添加范围标记，然后选择下一  **步**。</span><span class="sxs-lookup"><span data-stu-id="5f177-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-175">![Microsoft Endpoint Manager 门户的图像8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="5f177-176">通过单击"选择要包含的 **组**"并选择你的组来添加测试组，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-177">![Microsoft Endpoint Manager 门户的图像9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="5f177-178">查看并接受，  **然后选择创建**。</span><span class="sxs-lookup"><span data-stu-id="5f177-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-179">![Microsoft Endpoint Manager 门户的图像10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="5f177-180">可以查看已完成的策略。</span><span class="sxs-lookup"><span data-stu-id="5f177-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-181">![Microsoft Endpoint Manager 门户的图像11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="5f177-182">下一代保护</span><span class="sxs-lookup"><span data-stu-id="5f177-182">Next-generation protection</span></span>

1.  <span data-ttu-id="5f177-183">打开 MEM 门户。</span><span class="sxs-lookup"><span data-stu-id="5f177-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5f177-184">导航到 **终结点安全>防病毒>创建策略。**</span><span class="sxs-lookup"><span data-stu-id="5f177-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-185">![Microsoft Endpoint Manager 门户的图像12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="5f177-186">选择 **平台 - Windows 10 和更高版本 - Windows 和配置文件 – Microsoft Defender 防病毒>创建**。</span><span class="sxs-lookup"><span data-stu-id="5f177-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="5f177-187">输入名称和说明，然后选择下一  **步**。</span><span class="sxs-lookup"><span data-stu-id="5f177-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-188">![Microsoft Endpoint Manager 门户的图像13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="5f177-189">在" **配置设置"页**：设置 Microsoft Defender 防病毒 (云保护、排除、Real-Time保护和修正) 。</span><span class="sxs-lookup"><span data-stu-id="5f177-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-190">![Microsoft Endpoint Manager 门户的图像14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="5f177-191">如有必要，添加范围标记，然后选择下一  **步**。</span><span class="sxs-lookup"><span data-stu-id="5f177-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-192">![Microsoft Endpoint Manager 门户的图像15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="5f177-193">选择要包含的组，分配给你的测试组，然后选择下一  **步**。</span><span class="sxs-lookup"><span data-stu-id="5f177-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-194">![Microsoft Endpoint Manager 门户的图像16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="5f177-195">查看并创建，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-196">![Microsoft Endpoint Manager 门户的图像17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="5f177-197">你将看到你创建的配置策略。</span><span class="sxs-lookup"><span data-stu-id="5f177-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-198">![Microsoft Endpoint Manager 门户的图像18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="5f177-199">攻击面减少 – 攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="5f177-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="5f177-200">打开 MEM 门户。</span><span class="sxs-lookup"><span data-stu-id="5f177-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5f177-201">导航到 **终结点安全>攻击面减少**。</span><span class="sxs-lookup"><span data-stu-id="5f177-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="5f177-202">选择 **"创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="5f177-203">选择 **平台 - Windows 10 和更高版本 – 配置文件 - 攻击面减少规则>创建**。</span><span class="sxs-lookup"><span data-stu-id="5f177-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-204">![Microsoft Endpoint Manager 门户的图像19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="5f177-205">输入名称和说明，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-206">![Microsoft Endpoint Manager 门户的图像20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="5f177-207">在"**配置设置"页**：设置攻击面减少规则需要的配置，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f177-208">我们将配置所有攻击面减少规则以审核。</span><span class="sxs-lookup"><span data-stu-id="5f177-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="5f177-209">有关详细信息，请参阅攻击 [面减少规则](attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="5f177-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-210">![Microsoft Endpoint Manager 门户的图像21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="5f177-211">根据需要添加范围标记，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-212">![Microsoft Endpoint Manager 门户的图像22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="5f177-213">选择要包含并分配给测试组的组，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-214">![Microsoft Endpoint Manager 门户的图像23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="5f177-215">查看详细信息，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-216">![Microsoft Endpoint Manager 门户的图像24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="5f177-217">查看策略。</span><span class="sxs-lookup"><span data-stu-id="5f177-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-218">![Microsoft Endpoint Manager 门户的图像25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="5f177-219">攻击面减少 – Web 保护</span><span class="sxs-lookup"><span data-stu-id="5f177-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="5f177-220">打开 MEM 门户。</span><span class="sxs-lookup"><span data-stu-id="5f177-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="5f177-221">导航到 **终结点安全>攻击面减少**。</span><span class="sxs-lookup"><span data-stu-id="5f177-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="5f177-222">选择 **"创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="5f177-223">选择 **"Windows 10 和更高版本 – Web >创建"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-224">![Microsoft Endpoint Manager 门户的图像26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="5f177-225">输入名称和说明，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-226">![Microsoft Endpoint Manager 门户的图像27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="5f177-227">在"**配置设置"页**：设置 Web 保护需要的配置，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f177-228">我们正在将 Web 保护配置为阻止。</span><span class="sxs-lookup"><span data-stu-id="5f177-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="5f177-229">有关详细信息，请参阅[Web Protection。](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5f177-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-230">![Microsoft Endpoint Manager 门户的图像28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="5f177-231">根据需要 **在 Next 中添加>标记**。</span><span class="sxs-lookup"><span data-stu-id="5f177-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-232">![Microsoft Endpoint Manager 门户的图像29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="5f177-233">选择 **"分配到测试组>下一步"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-234">![Microsoft Endpoint Manager 门户的图像30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="5f177-235">选择 **"审阅并创建>创建"。**</span><span class="sxs-lookup"><span data-stu-id="5f177-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-236">![Microsoft Endpoint Manager 门户的图像31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="5f177-237">查看策略。</span><span class="sxs-lookup"><span data-stu-id="5f177-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-238">![Microsoft Endpoint Manager 门户的图像32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="5f177-239">验证配置设置</span><span class="sxs-lookup"><span data-stu-id="5f177-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="5f177-240">确认已应用策略</span><span class="sxs-lookup"><span data-stu-id="5f177-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="5f177-241">分配配置策略后，需要一些时间应用。</span><span class="sxs-lookup"><span data-stu-id="5f177-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="5f177-242">有关计时的信息，请参阅 [Intune 配置信息](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)。</span><span class="sxs-lookup"><span data-stu-id="5f177-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="5f177-243">若要确认配置策略已应用于测试设备，请针对每个配置策略执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="5f177-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="5f177-244">打开 MEM 门户并导航到相关策略，如上述步骤所示。</span><span class="sxs-lookup"><span data-stu-id="5f177-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="5f177-245">以下示例显示了下一代保护设置。</span><span class="sxs-lookup"><span data-stu-id="5f177-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-246">[![Microsoft Endpoint Manager 门户的图像33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="5f177-247">选择 **配置策略** 以查看策略状态。</span><span class="sxs-lookup"><span data-stu-id="5f177-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-248">[![Microsoft Endpoint Manager 门户的图像34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="5f177-249">选择  **"设备状态** "以查看状态。</span><span class="sxs-lookup"><span data-stu-id="5f177-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-250">[![Microsoft Endpoint Manager 门户的图像35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="5f177-251">选择  **"用户状态** "以查看状态。</span><span class="sxs-lookup"><span data-stu-id="5f177-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-252">[![Microsoft Endpoint Manager 门户的图像36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="5f177-253">选择  **"每设置状态** "以查看状态。</span><span class="sxs-lookup"><span data-stu-id="5f177-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="5f177-254">此视图对于标识与另一个策略冲突的任何设置非常有用。</span><span class="sxs-lookup"><span data-stu-id="5f177-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-255">[![Microsoft Endpoint Manager 门户的图像37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="5f177-256">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="5f177-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="5f177-257">在应用配置之前，不应启动 Defender for Endpoint Protection 服务。</span><span class="sxs-lookup"><span data-stu-id="5f177-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-258">[![服务面板的图像 1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="5f177-259">应用配置后，应启动 Defender for Endpoint Protection Service。</span><span class="sxs-lookup"><span data-stu-id="5f177-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-260">[![服务面板 2 的图像 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="5f177-261">在设备上运行服务后，设备将显示在 Microsoft Defender 安全中心中。</span><span class="sxs-lookup"><span data-stu-id="5f177-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-262">[![Microsoft Defender 安全中心的图像 ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5f177-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="5f177-263">下一代保护</span><span class="sxs-lookup"><span data-stu-id="5f177-263">Next-generation protection</span></span>

1.  <span data-ttu-id="5f177-264">在测试设备上应用策略之前，你应该能够手动管理设置，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5f177-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-265">![设置页面 1 的图像](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="5f177-266">应用策略后，你将无法手动管理设置。</span><span class="sxs-lookup"><span data-stu-id="5f177-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f177-267">在下图中 **，"启用云提供的** 保护"和 **"** 启用实时保护"将显示为托管保护。</span><span class="sxs-lookup"><span data-stu-id="5f177-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5f177-268">![设置页面 2 的图像](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="5f177-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="5f177-269">攻击面减少 – 攻击面减少规则</span><span class="sxs-lookup"><span data-stu-id="5f177-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="5f177-270">在测试设备上应用该策略之前，笔使用 PowerShell 窗口并键入 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="5f177-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="5f177-271">此响应应包含以下行，无内容：</span><span class="sxs-lookup"><span data-stu-id="5f177-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="5f177-272">AttackSurfaceReductionOnlyExclusions：</span><span class="sxs-lookup"><span data-stu-id="5f177-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="5f177-273">AttackSurfaceReductionRules_Actions：</span><span class="sxs-lookup"><span data-stu-id="5f177-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="5f177-274">AttackSurfaceReductionRules_Ids：</span><span class="sxs-lookup"><span data-stu-id="5f177-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![命令行 1 的图像](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="5f177-276">在测试设备上应用该策略后，打开 PowerShell Windows 并键入 `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="5f177-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="5f177-277">这应该会以以下行作为响应，内容如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f177-277">This should respond with the following lines with content as shown below:</span></span>

    ![命令行 2 的图像](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="5f177-279">攻击面减少 – Web 保护</span><span class="sxs-lookup"><span data-stu-id="5f177-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="5f177-280">在测试设备上，打开 PowerShell Windows 并键入 `(Get-MpPreference).EnableNetworkProtection` 。</span><span class="sxs-lookup"><span data-stu-id="5f177-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="5f177-281">这应该会以 0 作为响应，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5f177-281">This should respond with a 0 as shown below.</span></span>

    ![命令行 3 的图像](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="5f177-283">应用策略后，打开 PowerShell Windows 并键入 `(Get-MpPreference).EnableNetworkProtection` 。</span><span class="sxs-lookup"><span data-stu-id="5f177-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="5f177-284">这应该会以 1 作为响应，如下所示。</span><span class="sxs-lookup"><span data-stu-id="5f177-284">This should respond with a 1 as shown below.</span></span>

    ![命令行 4 的图像](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
