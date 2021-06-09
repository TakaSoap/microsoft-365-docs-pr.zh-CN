---
title: 使用 Microsoft Endpoint Configuration Manager 载入
description: 了解如何使用 Microsoft Defender for Endpoint Microsoft Endpoint Configuration Manager
keywords: 载入， 配置， 部署， 部署， 终结点配置管理器， Microsoft Defender for Endpoint， 集合创建， 终结点检测响应， 下一代保护， 攻击面减少， Microsoft 终结点配置管理器
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
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843502"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="8cad5-104">使用 Microsoft Endpoint Configuration Manager 载入</span><span class="sxs-lookup"><span data-stu-id="8cad5-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8cad5-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8cad5-105">**Applies to:**</span></span>
- [<span data-ttu-id="8cad5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8cad5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8cad5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cad5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8cad5-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8cad5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8cad5-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="8cad5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="8cad5-110">本文是部署指南的一部分，并作为示例载入方法。</span><span class="sxs-lookup"><span data-stu-id="8cad5-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="8cad5-111">在 [规划主题](deployment-strategy.md) 中，提供了多种方法将设备载入服务。</span><span class="sxs-lookup"><span data-stu-id="8cad5-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="8cad5-112">本主题介绍共同管理体系结构。</span><span class="sxs-lookup"><span data-stu-id="8cad5-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="8cad5-113">![云本机体系结构的图像 ](images/co-management-architecture.png)
 *环境体系结构关系图*</span><span class="sxs-lookup"><span data-stu-id="8cad5-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="8cad5-114">尽管 Defender for Endpoint 支持载入各种终结点和工具，但本文并未涵盖它们。</span><span class="sxs-lookup"><span data-stu-id="8cad5-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="8cad5-115">有关使用其他受支持的部署工具和方法进行常规载入的信息，请参阅 [载入概述](onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="8cad5-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="8cad5-116">本主题指导用户：</span><span class="sxs-lookup"><span data-stu-id="8cad5-116">This topic guides users in:</span></span>
- <span data-ttu-id="8cad5-117">步骤 1：Windows设备加入服务</span><span class="sxs-lookup"><span data-stu-id="8cad5-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="8cad5-118">步骤 2：为终结点功能配置 Defender</span><span class="sxs-lookup"><span data-stu-id="8cad5-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="8cad5-119">本载入指南将指导你完成在使用应用时需要执行Microsoft Endpoint Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="8cad5-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="8cad5-120">**在 Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="8cad5-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="8cad5-121">**使用 Microsoft Endpoint Configuration Manager 为终结点配置 Microsoft Defender Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="8cad5-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="8cad5-122">此示例Windows仅涵盖所有设备。</span><span class="sxs-lookup"><span data-stu-id="8cad5-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="8cad5-123">步骤 1：Windows设备载入Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8cad5-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="8cad5-124">集合创建</span><span class="sxs-lookup"><span data-stu-id="8cad5-124">Collection creation</span></span>
<span data-ttu-id="8cad5-125">若要Windows 10设备载入Microsoft Endpoint Configuration Manager，部署可以面向现有集合，也可以创建一个新集合进行测试。</span><span class="sxs-lookup"><span data-stu-id="8cad5-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="8cad5-126">使用组策略或手动方法等工具载入不会在系统上安装任何代理。</span><span class="sxs-lookup"><span data-stu-id="8cad5-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="8cad5-127">在Microsoft Endpoint Configuration Manager控制台中，载入过程将配置为控制台内的合规性设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="8cad5-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="8cad5-128">只要 Configuration Manager 客户端继续从管理点接收此策略，接收此必需配置的任何系统都将保持该配置。</span><span class="sxs-lookup"><span data-stu-id="8cad5-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="8cad5-129">按照以下步骤使用 Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="8cad5-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="8cad5-130">In Microsoft Endpoint Configuration Manager console， navigate to **Assets and Compliance Overview Device \> \> Collections**.</span><span class="sxs-lookup"><span data-stu-id="8cad5-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Microsoft Endpoint Configuration Manager向导的图像1](images/configmgr-device-collections.png)

2. <span data-ttu-id="8cad5-132">右键单击 **设备集合** ，然后选择 **创建设备集合**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Microsoft Endpoint Configuration Manager向导 2 的图像](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="8cad5-134">提供名称和 **限制集合，** 然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager向导的图像3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="8cad5-136">选择 **"添加规则**"，然后选择"**查询规则"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![向导Microsoft Endpoint Configuration Manager 4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="8cad5-138">在 **"直接** 成员身份向导"上单击"下一步 **"，** 然后单击"**编辑查询语句"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![向导Microsoft Endpoint Configuration Manager 5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="8cad5-140">选择 **条件** ，然后选择星形图标。</span><span class="sxs-lookup"><span data-stu-id="8cad5-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Microsoft Endpoint Configuration Manager向导 6 的图像](images/configmgr-criteria.png)

7. <span data-ttu-id="8cad5-142">将条件类型保留为 **简单值**，选择"操作系统 **-** 内部版本号"，运算符为大于或等于值 **14393，** 然后单击"确定 **"。** </span><span class="sxs-lookup"><span data-stu-id="8cad5-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager向导的图像7](images/configmgr-simple-value.png)

8. <span data-ttu-id="8cad5-144">选择 **"下一步**"和"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-144">Select **Next** and **Close**.</span></span>

    ![向导Microsoft Endpoint Configuration Manager的图像8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="8cad5-146">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="8cad5-146">Select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager向导9 的图像](images/configmgr-confirm.png)


<span data-ttu-id="8cad5-148">完成此任务后，你现在拥有一个设备集合，Windows 10环境中的所有终结点。</span><span class="sxs-lookup"><span data-stu-id="8cad5-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="8cad5-149">步骤 2：为终结点功能配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8cad5-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="8cad5-150">本部分指导你在设备上使用 Microsoft Endpoint Configuration Manager 配置Windows功能：</span><span class="sxs-lookup"><span data-stu-id="8cad5-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="8cad5-151">**终结点检测和响应**</span><span class="sxs-lookup"><span data-stu-id="8cad5-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="8cad5-152">**下一代保护**</span><span class="sxs-lookup"><span data-stu-id="8cad5-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="8cad5-153">**减少攻击面**</span><span class="sxs-lookup"><span data-stu-id="8cad5-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="8cad5-154">终结点检测和响应</span><span class="sxs-lookup"><span data-stu-id="8cad5-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="8cad5-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8cad5-155">Windows 10</span></span>
<span data-ttu-id="8cad5-156">从 Microsoft Defender 安全中心可以下载可用于在 System Center Configuration Manager 中创建策略的".onboarding"策略，Windows 10部署该策略。</span><span class="sxs-lookup"><span data-stu-id="8cad5-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="8cad5-157">从"Microsoft Defender 安全中心门户"中，[选择"设置"，然后选择"载入"。](https://securitycenter.windows.com/preferences2/onboarding)</span><span class="sxs-lookup"><span data-stu-id="8cad5-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="8cad5-158">在"部署方法"下，选择支持的版本 **Microsoft Endpoint Configuration Manager。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![适用于终结点载入向导的 Microsoft Defender 的图像10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="8cad5-160">选择 **下载程序包**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-160">Select **Download package**.</span></span>

    ![适用于终结点载入向导的 Microsoft Defender 的图像11](images/mdatp-download-package.png)

4. <span data-ttu-id="8cad5-162">将程序包保存到可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="8cad5-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="8cad5-163">In Microsoft Endpoint Configuration Manager， navigate to： **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span><span class="sxs-lookup"><span data-stu-id="8cad5-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="8cad5-164">右键单击 **"Microsoft Defender ATP策略"，** 然后选择"**创建Microsoft Defender ATP策略"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Microsoft Endpoint Configuration Manager向导12 的图像](images/configmgr-create-policy.png)

7. <span data-ttu-id="8cad5-166">输入名称和说明，确认 **已选择载入** ，然后选择下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager向导13 的图像](images/configmgr-policy-name.png)


8. <span data-ttu-id="8cad5-168">单击"浏览"。</span><span class="sxs-lookup"><span data-stu-id="8cad5-168">Click **Browse**.</span></span>

9. <span data-ttu-id="8cad5-169">从上面的步骤 4 导航到已下载文件的位置。</span><span class="sxs-lookup"><span data-stu-id="8cad5-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="8cad5-170">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="8cad5-170">Click **Next**.</span></span>
11. <span data-ttu-id="8cad5-171">使用"无"或"所有文件类型 (**相应的示例配置代理) 。** </span><span class="sxs-lookup"><span data-stu-id="8cad5-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![配置设置的图像1](images/configmgr-config-settings.png)

12. <span data-ttu-id="8cad5-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8cad5-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![配置设置的图像2](images/configmgr-telemetry.png)

14. <span data-ttu-id="8cad5-175">验证配置，然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-175">Verify the configuration, then click **Next**.</span></span>

     ![配置设置的图像3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="8cad5-177">向导 **完成后** ，单击"关闭"。</span><span class="sxs-lookup"><span data-stu-id="8cad5-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="8cad5-178">在 Microsoft Endpoint Configuration Manager 控制台中，右键单击刚创建的 Defender for Endpoint 策略，**然后选择部署**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![配置设置的图像4](images/configmgr-deploy.png)

17. <span data-ttu-id="8cad5-180">在右侧面板上，选择之前创建的集合，**然后单击确定。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![配置设置的图像5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="8cad5-182">早期版本的 Windows Client (Windows 7 和 Windows 8.1) </span><span class="sxs-lookup"><span data-stu-id="8cad5-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="8cad5-183">按照以下步骤标识 Defender for Endpoint Workspace ID 和工作区密钥，这是载入早期版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="8cad5-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="8cad5-184">从"Microsoft Defender 安全中心门户"中 **，设置 >"载入"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="8cad5-185">在操作系统下 **，Windows 7 SP1 和 8.1。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="8cad5-186">复制 **工作区 ID 和\*\*\*\*工作区密钥并** 保存它们。</span><span class="sxs-lookup"><span data-stu-id="8cad5-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="8cad5-187">稍后将在过程中使用。</span><span class="sxs-lookup"><span data-stu-id="8cad5-187">They will be used later in the process.</span></span>

    ![载入图像](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="8cad5-189">安装Microsoft Monitoring Agent (MMA) 。</span><span class="sxs-lookup"><span data-stu-id="8cad5-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="8cad5-190">MMA 当前 (2019 年 1) 以下操作系统Windows支持：</span><span class="sxs-lookup"><span data-stu-id="8cad5-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="8cad5-191">服务器 SKUS：Windows Server 2008 SP1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8cad5-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="8cad5-192">客户端 SKUS：Windows 7 SP1 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8cad5-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="8cad5-193">MMA 代理将需要安装在Windows设备上。</span><span class="sxs-lookup"><span data-stu-id="8cad5-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="8cad5-194">若要安装代理，某些系统将需要下载客户体验更新和诊断[](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)遥测，以便使用 MMA 收集数据。</span><span class="sxs-lookup"><span data-stu-id="8cad5-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="8cad5-195">这些系统版本包括但不限于：</span><span class="sxs-lookup"><span data-stu-id="8cad5-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="8cad5-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="8cad5-196">Windows 8.1</span></span>

    -   <span data-ttu-id="8cad5-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="8cad5-197">Windows 7</span></span>

    -   <span data-ttu-id="8cad5-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8cad5-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="8cad5-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8cad5-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="8cad5-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8cad5-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="8cad5-201">具体而言，Windows 7 SP1，必须安装以下修补程序：</span><span class="sxs-lookup"><span data-stu-id="8cad5-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="8cad5-202">安装 [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="8cad5-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="8cad5-203">安装 .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (或更高版本)  
         [KB3154518。](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="8cad5-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="8cad5-204">不要在同一个系统中同时安装这两者。</span><span class="sxs-lookup"><span data-stu-id="8cad5-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="8cad5-205">如果使用代理连接到 Internet，请参阅配置代理设置部分。</span><span class="sxs-lookup"><span data-stu-id="8cad5-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="8cad5-206">完成后，你应该在一小时内在门户中看到已载入的终结点。</span><span class="sxs-lookup"><span data-stu-id="8cad5-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="8cad5-207">下一代保护</span><span class="sxs-lookup"><span data-stu-id="8cad5-207">Next generation protection</span></span> 
<span data-ttu-id="8cad5-208">Microsoft Defender 防病毒是内置反恶意软件解决方案，为台式机、便携式计算机和服务器提供安全提供下一代防护。</span><span class="sxs-lookup"><span data-stu-id="8cad5-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="8cad5-209">在Microsoft Endpoint Configuration Manager控制台中，导航到"资产和合规性概述 **\> \> Endpoint Protection \> 反恶意软件策略"，** 然后选择"**创建反恶意软件策略"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![反恶意软件策略的图像](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="8cad5-211">选择 **计划扫描**、**扫描** 设置、**默认** 操作、**实时保护**、**排除** 设置、**高级**、威胁覆盖、**云保护** 服务 **和安全智能更新**，**然后选择确定。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![下一代保护窗格的图像1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="8cad5-213">在某些行业或某些选择的企业中，客户可能对如何配置防病毒有特定需求。</span><span class="sxs-lookup"><span data-stu-id="8cad5-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="8cad5-214">快速扫描与完全扫描和自定义扫描</span><span class="sxs-lookup"><span data-stu-id="8cad5-214">Quick scan versus full scan and custom scan</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="8cad5-215">有关详细信息，请参阅配置[Windows 安全中心框架](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="8cad5-215">For more details, see [Windows Security configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![下一代保护窗格的图像2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![下一代保护窗格的图像3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![下一代保护窗格的图像4](images/a28afc02c1940d5220b233640364970c.png)

    ![下一代保护窗格的图像5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![下一代保护窗格的图像6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![下一代保护窗格的图像7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![下一代保护窗格的图像8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![下一代保护窗格的图像9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="8cad5-224">右键单击新创建的反恶意软件策略， **然后选择部署**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![下一代保护窗格的图像10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="8cad5-226">将新的反恶意软件策略定向到 Windows 10 集合，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![下一代保护窗格的图像11](images/configmgr-select-collection.png)

<span data-ttu-id="8cad5-228">完成此任务后，现在已成功配置Windows Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="8cad5-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="8cad5-229">攻击面减少</span><span class="sxs-lookup"><span data-stu-id="8cad5-229">Attack surface reduction</span></span>
<span data-ttu-id="8cad5-230">适用于终结点的 Defender 的攻击面减少支柱包括攻击防护下提供的功能集。</span><span class="sxs-lookup"><span data-stu-id="8cad5-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="8cad5-231">攻击面减少 (ASR) 规则、受控文件夹访问权限、网络保护和 Exploit Protection。</span><span class="sxs-lookup"><span data-stu-id="8cad5-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="8cad5-232">所有这些功能都提供审核模式和阻止模式。</span><span class="sxs-lookup"><span data-stu-id="8cad5-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="8cad5-233">在审核模式下，对最终用户没有影响。</span><span class="sxs-lookup"><span data-stu-id="8cad5-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="8cad5-234">它所执行的所有工作就是收集其他遥测，并使其在Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8cad5-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="8cad5-235">部署的目标是将安全控件分步移动到阻止模式。</span><span class="sxs-lookup"><span data-stu-id="8cad5-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="8cad5-236">在审核模式下设置 ASR 规则：</span><span class="sxs-lookup"><span data-stu-id="8cad5-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="8cad5-237">In the Microsoft Endpoint Configuration Manager console， navigate to **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** and choose **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="8cad5-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Microsoft Endpoint Configuration Manager控制台 0 的图像](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="8cad5-239">选择 **攻击面减少**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="8cad5-240">将规则设置为 **审核，** 然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-240">Set rules to **Audit** and click **Next**.</span></span>


    ![控制台Microsoft Endpoint Configuration Manager 1 的图像](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="8cad5-242">通过单击下一步确认新的攻击 **防护策略**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![控制台 2 Microsoft Endpoint Configuration Manager的图像](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="8cad5-244">创建策略后，单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-244">Once the policy is created click **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager控制台 3 的图像](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![控制台 1 Microsoft Endpoint Manager的图像](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="8cad5-247">右键单击新创建的策略， **然后选择部署**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![控制台Microsoft Endpoint Configuration Manager 4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="8cad5-249">将策略定向到新创建的 Windows 10 集合，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![控制台 5 Microsoft Endpoint Configuration Manager映像](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="8cad5-251">完成此任务后，现在可以在审核模式下成功配置 ASR 规则。</span><span class="sxs-lookup"><span data-stu-id="8cad5-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="8cad5-252">下面是验证 ASR 规则是否已正确应用到终结点的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="8cad5-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="8cad5-253"> (这可能需要几分钟) </span><span class="sxs-lookup"><span data-stu-id="8cad5-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="8cad5-254">在 Web 浏览器中，导航到 <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="8cad5-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="8cad5-255">从 **左侧菜单中选择** 配置管理。</span><span class="sxs-lookup"><span data-stu-id="8cad5-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="8cad5-256">单击 **攻击面管理面板中的** 转到攻击面管理。</span><span class="sxs-lookup"><span data-stu-id="8cad5-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![攻击面管理的图像](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="8cad5-258">单击 **攻击面** 减少规则报告中的"配置"选项卡。</span><span class="sxs-lookup"><span data-stu-id="8cad5-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="8cad5-259">它显示每台设备的 ASR 规则配置概述和 ASR 规则状态。</span><span class="sxs-lookup"><span data-stu-id="8cad5-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![攻击面减少规则报告屏幕截图1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="8cad5-261">单击每台设备可显示 ASR 规则的配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="8cad5-261">Click each device shows configuration details of ASR rules.</span></span>

    ![攻击面减少规则报告屏幕截图2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="8cad5-263">有关 [更多详细信息，请参阅优化 ASR 规则](/microsoft-365/security/defender-endpoint/configure-machines-asr)   部署和检测。</span><span class="sxs-lookup"><span data-stu-id="8cad5-263">See [Optimize ASR rule deployment and detections](/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="8cad5-264">在审核模式下设置网络保护规则：</span><span class="sxs-lookup"><span data-stu-id="8cad5-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="8cad5-265">In the Microsoft Endpoint Configuration Manager console， navigate to **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** and choose **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="8cad5-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Configuration Manager System Center屏幕截图1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="8cad5-267">选择 **"网络保护"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="8cad5-268">将设置设置为审核 **，** 然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Confirugatiom manager2 System Center屏幕截图](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="8cad5-270">通过单击下一步确认新的攻击防护 **策略**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Screenshot Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="8cad5-272">创建策略后，单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-272">Once the policy is created click on **Close**.</span></span>

    ![Screenshot Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="8cad5-274">右键单击新创建的策略， **然后选择部署**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Microsoft Endpoint Configuration Manager1 屏幕截图](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="8cad5-276">选择新创建的组策略Windows 10选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager2 屏幕截图](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="8cad5-278">完成此任务后，现在可以在审核模式下成功配置网络保护。</span><span class="sxs-lookup"><span data-stu-id="8cad5-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="8cad5-279">在审核模式下设置受控文件夹访问权限规则：</span><span class="sxs-lookup"><span data-stu-id="8cad5-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="8cad5-280">In the Microsoft Endpoint Configuration Manager console， navigate to **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard** and choose **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="8cad5-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Microsoft Endpoint Configuration Manager3 的屏幕截图](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="8cad5-282">选择 **受控文件夹访问权限**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="8cad5-283">将配置设置为审核 **，** 然后单击下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager4 的屏幕截图](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="8cad5-285">通过单击下一步确认新的攻击防护 **策略**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager5 的屏幕截图](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="8cad5-287">创建策略后，单击"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-287">Once the policy is created click on **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager6 的屏幕截图](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="8cad5-289">右键单击新创建的策略， **然后选择部署**。</span><span class="sxs-lookup"><span data-stu-id="8cad5-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Microsoft Endpoint Configuration Manager7 的屏幕截图](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="8cad5-291">将策略定向到新创建的 Windows 10 集合，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="8cad5-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Microsoft Endpoint Configuration Manager8 的屏幕截图](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="8cad5-293">现在，你已成功在审核模式下配置受控文件夹访问权限。</span><span class="sxs-lookup"><span data-stu-id="8cad5-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="8cad5-294">相关主题</span><span class="sxs-lookup"><span data-stu-id="8cad5-294">Related topic</span></span>
- [<span data-ttu-id="8cad5-295">使用 Microsoft Endpoint Manager 载入</span><span class="sxs-lookup"><span data-stu-id="8cad5-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
