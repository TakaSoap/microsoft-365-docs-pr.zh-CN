---
title: 通过Windows 10将设备载入 Microsoft Defender for Endpoint
description: 使用组策略在 Windows 10部署配置包，以便它们可以载入服务。
keywords: 使用组策略配置设备， 设备管理， 为终结点设备配置 Microsoft Defender， 载入适用于终结点设备的 Microsoft Defender， 组策略
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b8f56c8f2ba92073ea7ae9464f199d9c900b932f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933957"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="55bff-104">使用Windows 10载入设备</span><span class="sxs-lookup"><span data-stu-id="55bff-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55bff-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="55bff-105">**Applies to:**</span></span>

- <span data-ttu-id="55bff-106">组策略</span><span class="sxs-lookup"><span data-stu-id="55bff-106">Group Policy</span></span>
- [<span data-ttu-id="55bff-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="55bff-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55bff-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55bff-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="55bff-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="55bff-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="55bff-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="55bff-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="55bff-111">若要使用组策略 (GP) 更新来部署程序包，必须在 Windows Server 2008 R2 或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="55bff-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="55bff-112">对于 Windows Server 2019，您可能需要将 NT AUTHORITY\Well-Known-System-Account 替换为组策略首选项创建的 XML 文件的 NT AUTHORITY\SYSTEM。</span><span class="sxs-lookup"><span data-stu-id="55bff-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="55bff-113">使用组策略载入设备</span><span class="sxs-lookup"><span data-stu-id="55bff-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="55bff-114">[![显示各种部署路径的 PDF 图像](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="55bff-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="55bff-115">请查看[PDF 或](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)查看部署 Defender for Endpoint 中的各种路径。</span><span class="sxs-lookup"><span data-stu-id="55bff-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="55bff-116">打开 GP 配置包.zip文件 *(WindowsDefenderATPOnboardingPackage.zip)* 从服务载入向导下载的内容。</span><span class="sxs-lookup"><span data-stu-id="55bff-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="55bff-117">还可以从以下版本获取[Microsoft Defender 安全中心：](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="55bff-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="55bff-118">在导航窗格中，选择 **"设置**  >  **载入"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="55bff-119">选择Windows 10操作系统。</span><span class="sxs-lookup"><span data-stu-id="55bff-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="55bff-120">在"**部署方法"** 字段中，选择"**组策略"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="55bff-121">单击 **下载程序包** 并保存.zip文件。</span><span class="sxs-lookup"><span data-stu-id="55bff-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="55bff-122">将文件内容.zip到设备可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="55bff-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="55bff-123">你应该有一个称为 *OptionalParamsPolicy* 的文件夹和文件 *WindowsDefenderATPOnboardingScript.cmd*。</span><span class="sxs-lookup"><span data-stu-id="55bff-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="55bff-124">打开组 [策略](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**</span><span class="sxs-lookup"><span data-stu-id="55bff-124">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="55bff-125">在组 **策略管理编辑器中**，转到"**计算机配置**"，然后转到"**首选项**"，然后转到"**控制面板设置"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="55bff-126">右键单击 **计划任务**，指向 **新建**，然后单击即时任务 (**至少Windows 7)**。</span><span class="sxs-lookup"><span data-stu-id="55bff-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="55bff-127">在打开 **的任务** 窗口中，转到常规 **选项卡**。在 **"安全选项"** 下，单击 **"更改用户或组**"，然后键入"系统"，然后单击"**检查名称**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="55bff-128">NT AUTHORITY\SYSTEM 显示为任务将运行的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="55bff-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="55bff-129">Select **Run whether user is logged on or not and** check the Run with highest **privileges** check box.</span><span class="sxs-lookup"><span data-stu-id="55bff-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="55bff-130">转到"操作 **"选项卡** ，然后单击" **新建..."。** 确保在 **"操作"** 字段中选择了"启动 **程序** "。</span><span class="sxs-lookup"><span data-stu-id="55bff-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="55bff-131">输入共享 *WindowsDefenderATPOnboardingScript.cmd* 文件的文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="55bff-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="55bff-132">单击 **"确定** "并关闭任何打开的 GPMC 窗口。</span><span class="sxs-lookup"><span data-stu-id="55bff-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="55bff-133">载入设备后，你可以选择运行检测测试，以验证设备是否正确载入到服务。</span><span class="sxs-lookup"><span data-stu-id="55bff-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="55bff-134">有关详细信息，请参阅对新载入的适用于终结点 [设备的 Defender](run-detection-test.md)运行检测测试。</span><span class="sxs-lookup"><span data-stu-id="55bff-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="55bff-135">其他 Defender for Endpoint 配置设置</span><span class="sxs-lookup"><span data-stu-id="55bff-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="55bff-136">对于每个设备，你可以说明当通过请求提交文件进行深入分析Microsoft Defender 安全中心是否可以从设备收集示例。</span><span class="sxs-lookup"><span data-stu-id="55bff-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="55bff-137">可以使用组策略 (GP) 配置设置，如深入分析功能中使用的示例共享的设置。</span><span class="sxs-lookup"><span data-stu-id="55bff-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="55bff-138">配置示例集合设置</span><span class="sxs-lookup"><span data-stu-id="55bff-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="55bff-139">在 GP 管理设备上，从配置包复制以下文件：</span><span class="sxs-lookup"><span data-stu-id="55bff-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="55bff-140">将 _AtpConfiguration.admx_ 复制到 _\\ C：Windows \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="55bff-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="55bff-141">将 _AtpConfiguration.adml_ 复制到 _\\ C：Windows \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="55bff-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="55bff-142">如果对组策略管理模板使用中央存储 [，](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)请从配置包中复制以下文件：</span><span class="sxs-lookup"><span data-stu-id="55bff-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="55bff-143">将 _AtpConfiguration.admx_ 复制到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 策略 \\ 策略Definitions_</span><span class="sxs-lookup"><span data-stu-id="55bff-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="55bff-144">将 _AtpConfiguration.adml_ 复制到 _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ 策略 \\ 策略Definitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="55bff-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="55bff-145">打开组 [策略管理控制台，](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)右键单击要配置的 GPO， **然后单击编辑**。</span><span class="sxs-lookup"><span data-stu-id="55bff-145">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="55bff-146">在组 **策略管理编辑器中**，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="55bff-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="55bff-147">单击 **"策略**"，然后单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="55bff-148">单击 **Windows组件**"，然后单击Windows Defender **ATP"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6.  <span data-ttu-id="55bff-149">选择从设备启用或禁用示例共享。</span><span class="sxs-lookup"><span data-stu-id="55bff-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="55bff-150">如果未设置值，则默认值为启用示例集合。</span><span class="sxs-lookup"><span data-stu-id="55bff-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="55bff-151">其他建议的配置设置</span><span class="sxs-lookup"><span data-stu-id="55bff-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="55bff-152">更新终结点保护配置</span><span class="sxs-lookup"><span data-stu-id="55bff-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="55bff-153">配置载入脚本后，继续编辑相同的组策略以添加终结点保护配置。</span><span class="sxs-lookup"><span data-stu-id="55bff-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="55bff-154">从运行 Windows 10 Server 2019 的系统执行组策略编辑，以确保具有所有必需的Microsoft Defender 防病毒功能。</span><span class="sxs-lookup"><span data-stu-id="55bff-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="55bff-155">你可能需要关闭并重新打开组策略对象以注册 Defender ATP 配置设置。</span><span class="sxs-lookup"><span data-stu-id="55bff-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="55bff-156">所有策略都位于 下 `Computer Configuration\Policies\Administrative Templates` 。</span><span class="sxs-lookup"><span data-stu-id="55bff-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="55bff-157">**策略位置：\Windows** Components\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="55bff-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="55bff-158">策略</span><span class="sxs-lookup"><span data-stu-id="55bff-158">Policy</span></span> | <span data-ttu-id="55bff-159">设置</span><span class="sxs-lookup"><span data-stu-id="55bff-159">Setting</span></span> 
:---|:---
<span data-ttu-id="55bff-160">Enable\Disable Sample 集合</span><span class="sxs-lookup"><span data-stu-id="55bff-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="55bff-161">已启用 - 选中"启用计算机上的示例集合"</span><span class="sxs-lookup"><span data-stu-id="55bff-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="55bff-162">**策略位置：\Windows** Components\Windows Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="55bff-162">**Policy location:**  \Windows Components\Windows Defender Antivirus</span></span>

<span data-ttu-id="55bff-163">策略</span><span class="sxs-lookup"><span data-stu-id="55bff-163">Policy</span></span> | <span data-ttu-id="55bff-164">设置</span><span class="sxs-lookup"><span data-stu-id="55bff-164">Setting</span></span> 
:---|:---
<span data-ttu-id="55bff-165">配置对可能不需要的应用程序的检测</span><span class="sxs-lookup"><span data-stu-id="55bff-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="55bff-166">已启用、阻止</span><span class="sxs-lookup"><span data-stu-id="55bff-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="55bff-167">**策略位置：\Windows** Components\Windows Defender 防病毒\MAPS</span><span class="sxs-lookup"><span data-stu-id="55bff-167">**Policy location:** \Windows Components\Windows Defender Antivirus\MAPS</span></span>

<span data-ttu-id="55bff-168">策略</span><span class="sxs-lookup"><span data-stu-id="55bff-168">Policy</span></span> | <span data-ttu-id="55bff-169">设置</span><span class="sxs-lookup"><span data-stu-id="55bff-169">Setting</span></span> 
:---|:---
<span data-ttu-id="55bff-170">加入 Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="55bff-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="55bff-171">已启用、高级 MAPS</span><span class="sxs-lookup"><span data-stu-id="55bff-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="55bff-172">需要进一步分析时发送文件示例</span><span class="sxs-lookup"><span data-stu-id="55bff-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="55bff-173">已启用，发送安全示例</span><span class="sxs-lookup"><span data-stu-id="55bff-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="55bff-174">**策略位置：\Windows** Components\Windows Defender 防病毒\Real-time Protection</span><span class="sxs-lookup"><span data-stu-id="55bff-174">**Policy location:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="55bff-175">策略</span><span class="sxs-lookup"><span data-stu-id="55bff-175">Policy</span></span> | <span data-ttu-id="55bff-176">设置</span><span class="sxs-lookup"><span data-stu-id="55bff-176">Setting</span></span> 
:---|:---
<span data-ttu-id="55bff-177">关闭实时保护</span><span class="sxs-lookup"><span data-stu-id="55bff-177">Turn off real-time protection</span></span>|<span data-ttu-id="55bff-178">已禁用</span><span class="sxs-lookup"><span data-stu-id="55bff-178">Disabled</span></span>
<span data-ttu-id="55bff-179">打开行为监视</span><span class="sxs-lookup"><span data-stu-id="55bff-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="55bff-180">已启用</span><span class="sxs-lookup"><span data-stu-id="55bff-180">Enabled</span></span>
<span data-ttu-id="55bff-181">扫描所有下载的文件和附件</span><span class="sxs-lookup"><span data-stu-id="55bff-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="55bff-182">已启用</span><span class="sxs-lookup"><span data-stu-id="55bff-182">Enabled</span></span>
<span data-ttu-id="55bff-183">监视您的计算机上的文件和程序活动</span><span class="sxs-lookup"><span data-stu-id="55bff-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="55bff-184">已启用</span><span class="sxs-lookup"><span data-stu-id="55bff-184">Enabled</span></span>

<br/>

<span data-ttu-id="55bff-185">**策略位置：\Windows** Components\Windows Defender 防病毒\Scan</span><span class="sxs-lookup"><span data-stu-id="55bff-185">**Policy location:**  \Windows Components\Windows Defender Antivirus\Scan</span></span>

<span data-ttu-id="55bff-186">这些设置配置终结点的定期扫描。</span><span class="sxs-lookup"><span data-stu-id="55bff-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="55bff-187">建议在性能允许的情况下执行每周快速扫描。</span><span class="sxs-lookup"><span data-stu-id="55bff-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="55bff-188">策略</span><span class="sxs-lookup"><span data-stu-id="55bff-188">Policy</span></span> | <span data-ttu-id="55bff-189">设置</span><span class="sxs-lookup"><span data-stu-id="55bff-189">Setting</span></span> 
:---|:---
<span data-ttu-id="55bff-190">在运行计划扫描之前检查最新的病毒和间谍软件安全智能</span><span class="sxs-lookup"><span data-stu-id="55bff-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="55bff-191">已启用</span><span class="sxs-lookup"><span data-stu-id="55bff-191">Enabled</span></span>


<br/>

<span data-ttu-id="55bff-192">**策略位置：\Windows** 组件\Windows Defender 防病毒\Windows Defender攻击防护\攻击面减少</span><span class="sxs-lookup"><span data-stu-id="55bff-192">**Policy location:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="55bff-193">从自定义攻击面减少规则获取攻击面减少 GUID [的当前列表](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="55bff-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="55bff-194">打开配置 **攻击面减少** 策略。</span><span class="sxs-lookup"><span data-stu-id="55bff-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="55bff-195">选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="55bff-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="55bff-196">选择" **显示"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="55bff-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="55bff-197">在"值名称"字段中 **添加** 值为 2 的每个 GUID。</span><span class="sxs-lookup"><span data-stu-id="55bff-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="55bff-198">这将仅为审核设置每个设置。</span><span class="sxs-lookup"><span data-stu-id="55bff-198">This will set each up for audit only.</span></span>

   ![攻击面减少配置的图像](images/asr-guid.png)



<span data-ttu-id="55bff-200">策略</span><span class="sxs-lookup"><span data-stu-id="55bff-200">Policy</span></span> | <span data-ttu-id="55bff-201">设置</span><span class="sxs-lookup"><span data-stu-id="55bff-201">Setting</span></span> 
:---|:---
<span data-ttu-id="55bff-202">配置受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="55bff-202">Configure Controlled folder access</span></span>| <span data-ttu-id="55bff-203">已启用，审核模式</span><span class="sxs-lookup"><span data-stu-id="55bff-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="55bff-204">使用组策略的载出设备</span><span class="sxs-lookup"><span data-stu-id="55bff-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="55bff-205">出于安全考虑，用于"载出"设备的程序包将在下载日期 30 天后过期。</span><span class="sxs-lookup"><span data-stu-id="55bff-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="55bff-206">发送到设备的过期载出包将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="55bff-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="55bff-207">下载载出包时，你将收到程序包到期日期的通知，该日期也将包含在程序包名称中。</span><span class="sxs-lookup"><span data-stu-id="55bff-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="55bff-208">载入和载出策略不得同时部署在同一设备上，否则将导致不可预知的冲突。</span><span class="sxs-lookup"><span data-stu-id="55bff-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="55bff-209">从以下版本[获取Microsoft Defender 安全中心：](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="55bff-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="55bff-210">在导航窗格中，选择 **"设置**  >  **载"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="55bff-211">选择Windows 10操作系统。</span><span class="sxs-lookup"><span data-stu-id="55bff-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="55bff-212">在"**部署方法"** 字段中，选择"**组策略"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="55bff-213">单击 **下载程序包** 并保存.zip文件。</span><span class="sxs-lookup"><span data-stu-id="55bff-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="55bff-214">将文件内容.zip到设备可以访问的共享只读位置。</span><span class="sxs-lookup"><span data-stu-id="55bff-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="55bff-215">你应该有一个名为 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 的文件*。</span><span class="sxs-lookup"><span data-stu-id="55bff-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="55bff-216">打开组 [策略](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)管理控制台 (GPMC) ，右键单击要配置的组策略对象 (GPO) 然后单击 **编辑。**</span><span class="sxs-lookup"><span data-stu-id="55bff-216">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="55bff-217">在组 **策略管理编辑器中**，转到"**计算机配置"，然后** 转到"**首选项**"，然后转到"**控制面板设置"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="55bff-218">右键单击 **"计划任务"，** 指向 **"新建**"，然后单击"**立即任务"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="55bff-219">在打开 **的任务** 窗口中，转到常规 **选项卡** 。在"安全选项"下 (BUILTIN\SYSTEM) **本地系统用户帐户**。</span><span class="sxs-lookup"><span data-stu-id="55bff-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="55bff-220">Select **Run whether user is logged on or not and** check the Run with highest **privileges** check-box.</span><span class="sxs-lookup"><span data-stu-id="55bff-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="55bff-221">转到"操作 **"选项卡** ，然后单击"新建 **..."。** 确保在 **"操作"** 字段中选择了"启动 **程序** "。</span><span class="sxs-lookup"><span data-stu-id="55bff-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="55bff-222">输入共享文件的文件名和  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* 文件。</span><span class="sxs-lookup"><span data-stu-id="55bff-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="55bff-223">单击 **"确定** "并关闭任何打开的 GPMC 窗口。</span><span class="sxs-lookup"><span data-stu-id="55bff-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55bff-224">"载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。</span><span class="sxs-lookup"><span data-stu-id="55bff-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="55bff-225">监视设备配置</span><span class="sxs-lookup"><span data-stu-id="55bff-225">Monitor device configuration</span></span>
<span data-ttu-id="55bff-226">借助组策略，无法监视设备上策略的部署。</span><span class="sxs-lookup"><span data-stu-id="55bff-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="55bff-227">可以直接在门户上或使用不同的部署工具进行监视。</span><span class="sxs-lookup"><span data-stu-id="55bff-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="55bff-228">使用门户监视设备</span><span class="sxs-lookup"><span data-stu-id="55bff-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="55bff-229">转到["Microsoft Defender 安全中心"。](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="55bff-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="55bff-230">单击 **"设备列表"。**</span><span class="sxs-lookup"><span data-stu-id="55bff-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="55bff-231">验证设备是否显示。</span><span class="sxs-lookup"><span data-stu-id="55bff-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="55bff-232">设备可能需要几天时间才能开始在 **"设备"列表上显示**。</span><span class="sxs-lookup"><span data-stu-id="55bff-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="55bff-233">这包括将策略分发到设备所花的时间、用户登录之前所花的时间以及终结点开始报告所花的时间。</span><span class="sxs-lookup"><span data-stu-id="55bff-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="55bff-234">相关主题</span><span class="sxs-lookup"><span data-stu-id="55bff-234">Related topics</span></span>
- [<span data-ttu-id="55bff-235">使用Windows 10载入Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="55bff-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="55bff-236">使用移动设备管理工具载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="55bff-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="55bff-237">使用本地脚本载入 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="55bff-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="55bff-238">载入非永久虚拟桌面基础结构 （VDI） 设备</span><span class="sxs-lookup"><span data-stu-id="55bff-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="55bff-239">对新载入的适用于终结点的 Microsoft Defender 设备运行检测测试</span><span class="sxs-lookup"><span data-stu-id="55bff-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="55bff-240">Microsoft Defender 终结点载入问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="55bff-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
