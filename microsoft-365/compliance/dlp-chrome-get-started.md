---
title: Microsoft 合规性扩展入门
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 准备及部署 Microsoft 合规性扩展。
ms.openlocfilehash: c20381b23a70fdf8e6571af65b74688cc57ea760
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226955"
---
# <a name="get-started-with-microsoft-compliance-extension"></a><span data-ttu-id="90fff-103">Microsoft 合规性扩展入门</span><span class="sxs-lookup"><span data-stu-id="90fff-103">Get started with Microsoft Compliance Extension</span></span>

<span data-ttu-id="90fff-104">使用这些过程推出 Microsoft 合规性扩展。</span><span class="sxs-lookup"><span data-stu-id="90fff-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="90fff-105">开始之前</span><span class="sxs-lookup"><span data-stu-id="90fff-105">Before you begin</span></span>

<span data-ttu-id="90fff-106">要使用 Microsoft 合规性扩展，设备必须装载到终结点 DLP中。</span><span class="sxs-lookup"><span data-stu-id="90fff-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="90fff-107">如果您是 DLP 或终结点 DLP 的新手，请阅读这些文章</span><span class="sxs-lookup"><span data-stu-id="90fff-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="90fff-108">了解 Microsoft 合规性扩展</span><span class="sxs-lookup"><span data-stu-id="90fff-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="90fff-109">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="90fff-109">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="90fff-110">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="90fff-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="90fff-111">根据模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="90fff-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="90fff-112">了解终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="90fff-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="90fff-113">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="90fff-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="90fff-114">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="90fff-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="90fff-115">为 Endpoint DLP 配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="90fff-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="90fff-116">使用终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="90fff-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="90fff-117">SKU/订阅许可</span><span class="sxs-lookup"><span data-stu-id="90fff-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="90fff-118">在开始使用终结点 DLP 之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何加载项。</span><span class="sxs-lookup"><span data-stu-id="90fff-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="90fff-119">若要访问和使用终结点 DLP 功能，必须具有这些订阅或加载项中的一个。</span><span class="sxs-lookup"><span data-stu-id="90fff-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="90fff-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="90fff-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="90fff-121">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="90fff-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="90fff-122">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="90fff-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="90fff-123">Microsoft 365 A5 合规</span><span class="sxs-lookup"><span data-stu-id="90fff-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="90fff-124">Microsoft 365 E5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="90fff-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="90fff-125">Microsoft 365 A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="90fff-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="90fff-126">有关详细的许可指南，请参阅 [适用于安全性与合规性的 Microsoft 365 许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="90fff-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="90fff-127">您的组织必须获得终结点 DLP 的许可</span><span class="sxs-lookup"><span data-stu-id="90fff-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="90fff-128">您的设备必须运行 Windows 10 x64 内部版本 1809 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="90fff-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="90fff-129">设备必须具有反恶意软件客户端（版本为 4.18.2101.9 或更高）。</span><span class="sxs-lookup"><span data-stu-id="90fff-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="90fff-130">请通过打开“**Windows 安全中心**”应用，选择“**设置**”图标，然后选择“**关于**”来查看当前版本。</span><span class="sxs-lookup"><span data-stu-id="90fff-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="90fff-131">权限</span><span class="sxs-lookup"><span data-stu-id="90fff-131">Permissions</span></span>

<span data-ttu-id="90fff-132">可在 [活动资源管理器](data-classification-activity-explorer.md) 中查看终结点 DLP 中的数据。</span><span class="sxs-lookup"><span data-stu-id="90fff-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="90fff-133">有七个角色可向活动资源管理器授予权限，用于访问数据的帐户必须是其中任何一个的成员。</span><span class="sxs-lookup"><span data-stu-id="90fff-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="90fff-134">全局管理员</span><span class="sxs-lookup"><span data-stu-id="90fff-134">Global admin</span></span>
- <span data-ttu-id="90fff-135">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="90fff-135">Compliance admin</span></span>
- <span data-ttu-id="90fff-136">安全管理员</span><span class="sxs-lookup"><span data-stu-id="90fff-136">Security admin</span></span>
- <span data-ttu-id="90fff-137">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="90fff-137">Compliance data admin</span></span>
- <span data-ttu-id="90fff-138">全局读取者</span><span class="sxs-lookup"><span data-stu-id="90fff-138">Global reader</span></span>
- <span data-ttu-id="90fff-139">安全读者</span><span class="sxs-lookup"><span data-stu-id="90fff-139">Security reader</span></span>
- <span data-ttu-id="90fff-140">报表阅读人员</span><span class="sxs-lookup"><span data-stu-id="90fff-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="90fff-141">整体安装工作流</span><span class="sxs-lookup"><span data-stu-id="90fff-141">Overall installation workflow</span></span>

<span data-ttu-id="90fff-p105">部署 Microsoft 合规性扩展是一个多阶段过程。可选择一次在一台计算机上安装，或将 Microsoft Endpoint Manager 或组策略用于组织范围的部署。</span><span class="sxs-lookup"><span data-stu-id="90fff-p105">Deploying Microsoft Compliance Extension is a multi-phase process. You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="90fff-144">[准备设备](#prepare-your-devices)。</span><span class="sxs-lookup"><span data-stu-id="90fff-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="90fff-145">基本设置单机自托管</span><span class="sxs-lookup"><span data-stu-id="90fff-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="90fff-146">使用 Microsoft Endpoint Manager 部署</span><span class="sxs-lookup"><span data-stu-id="90fff-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="90fff-147">使用组策略部署</span><span class="sxs-lookup"><span data-stu-id="90fff-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="90fff-148">测试扩展</span><span class="sxs-lookup"><span data-stu-id="90fff-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="90fff-149">使用警报管理仪表板查看 Chrome DLP 警报</span><span class="sxs-lookup"><span data-stu-id="90fff-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [<span data-ttu-id="90fff-150">在活动资源管理器中查看 Chrome DLP 数据</span><span class="sxs-lookup"><span data-stu-id="90fff-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer)

### <a name="prepare-infrastructure"></a><span data-ttu-id="90fff-151">准备基础结构</span><span class="sxs-lookup"><span data-stu-id="90fff-151">Prepare infrastructure</span></span>

<span data-ttu-id="90fff-152">如果要向所有受监视 Windows 10 设备推出 Microsoft 合规性扩展，应从不允许的应用列表中删除 Google Chrome。</span><span class="sxs-lookup"><span data-stu-id="90fff-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="90fff-153">有关详细信息，请参阅 [不允许的浏览器](endpoint-dlp-using.md#unallowed-browsers)。</span><span class="sxs-lookup"><span data-stu-id="90fff-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="90fff-154">如果只向少数设备推出，则可在不允许的浏览器列表中保留 Chrome。</span><span class="sxs-lookup"><span data-stu-id="90fff-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="90fff-155">对于已安装 Microsoft 合规性扩展的计算机，Microsoft 合规性扩展将绕过不允许应用列表的限制。</span><span class="sxs-lookup"><span data-stu-id="90fff-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>

### <a name="prepare-your-devices"></a><span data-ttu-id="90fff-156">准备设备</span><span class="sxs-lookup"><span data-stu-id="90fff-156">Prepare your devices</span></span>

1. <span data-ttu-id="90fff-157">使用这些主题中的过程载入设备：</span><span class="sxs-lookup"><span data-stu-id="90fff-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="90fff-158">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="90fff-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="90fff-159">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="90fff-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="90fff-160">为 Endpoint DLP 配置设备代理和 Internet 连接设置</span><span class="sxs-lookup"><span data-stu-id="90fff-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="90fff-161">基本设置单机自托管</span><span class="sxs-lookup"><span data-stu-id="90fff-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="90fff-162">这是推荐采用的方法。</span><span class="sxs-lookup"><span data-stu-id="90fff-162">This is the recommended method.</span></span>

1. <span data-ttu-id="90fff-163">登录到要安装 Microsoft 合规性扩展的 Windows 10 计算机，并以管理员身份运行此 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="90fff-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span>

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ```

2.  <span data-ttu-id="90fff-164">导航到“[Microsoft 合规性扩展 - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)。</span><span class="sxs-lookup"><span data-stu-id="90fff-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="90fff-165">按照 Chrome Web Store 页面上的说明安装扩展。</span><span class="sxs-lookup"><span data-stu-id="90fff-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="90fff-166">使用 Microsoft Endpoint Manager 进行部署</span><span class="sxs-lookup"><span data-stu-id="90fff-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="90fff-167">使用此设置方法进行组织范围的部署</span><span class="sxs-lookup"><span data-stu-id="90fff-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="90fff-168">通过 Microsoft Endpoint Manager 启用所需的注册表项</span><span class="sxs-lookup"><span data-stu-id="90fff-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="90fff-169">创建具有以下内容的 PowerShell 脚本：</span><span class="sxs-lookup"><span data-stu-id="90fff-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="90fff-170">登录 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="90fff-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="90fff-171">导航到“**设备**” > “**脚本**”，并选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="90fff-172">浏览到系统提示时创建的脚本位置。</span><span class="sxs-lookup"><span data-stu-id="90fff-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="90fff-173">使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="90fff-173">Select the following settings:</span></span>
    1. <span data-ttu-id="90fff-174">使用登录凭据运行此脚本：是</span><span class="sxs-lookup"><span data-stu-id="90fff-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="90fff-175">执行脚本签名检查：否</span><span class="sxs-lookup"><span data-stu-id="90fff-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="90fff-176">在 64 位 PowerShell 主机中运行脚本：是</span><span class="sxs-lookup"><span data-stu-id="90fff-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="90fff-177">选择适当的设备组并应用该策略。</span><span class="sxs-lookup"><span data-stu-id="90fff-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="90fff-178">Microsoft Endpoint Manager 强制安装步骤</span><span class="sxs-lookup"><span data-stu-id="90fff-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="90fff-179">将 Microsoft 合规性扩展添加到强制安装的扩展列表之前，引入 Chrome ADMX 是一个重要过程。</span><span class="sxs-lookup"><span data-stu-id="90fff-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="90fff-180">Google 记录了 Microsoft Endpoint Manager 中此过程的步骤：[使用 Microsoft Intune 管理 Chrome 浏览器 - Google Chrome 企业版帮助](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)。</span><span class="sxs-lookup"><span data-stu-id="90fff-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="90fff-181">引入 ADMX 后，可按照以下步骤为此扩展创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="90fff-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="90fff-182">登录 Microsoft Endpoint Manager 管理中心 (https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="90fff-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="90fff-183">导航到配置文件。</span><span class="sxs-lookup"><span data-stu-id="90fff-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="90fff-184">选择“**创建配置文件**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="90fff-185">选择“**Windows 10**”平台。</span><span class="sxs-lookup"><span data-stu-id="90fff-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="90fff-186">选择“**自定义**”配置文件类型。</span><span class="sxs-lookup"><span data-stu-id="90fff-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="90fff-187">选择“**设置**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="90fff-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="90fff-188">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-188">Select **Add**.</span></span>

8.  <span data-ttu-id="90fff-189">输入以下策略信息。</span><span class="sxs-lookup"><span data-stu-id="90fff-189">Enter the following policy information.</span></span>

    <span data-ttu-id="90fff-190">OMA-URI： `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="90fff-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="90fff-191">数据类型`String`</span><span class="sxs-lookup"><span data-stu-id="90fff-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="90fff-192">值：`<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="90fff-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="90fff-193">单击“创建”。</span><span class="sxs-lookup"><span data-stu-id="90fff-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="90fff-194">使用组策略部署</span><span class="sxs-lookup"><span data-stu-id="90fff-194">Deploy using Group Policy</span></span>

<span data-ttu-id="90fff-195">如果不想使用 Microsoft Endpoint Manager，可使用组策略在组织中部署 Microsoft 合规性扩展</span><span class="sxs-lookup"><span data-stu-id="90fff-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="90fff-196">设备必须可通过组策略进行管理，并且需要将所有 Chrome ADMX 导入组策略中央存储。</span><span class="sxs-lookup"><span data-stu-id="90fff-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="90fff-197">有关详细信息，请参阅 [如何在 Windows 中创建和管理组策略管理模板的中央存储](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)。</span><span class="sxs-lookup"><span data-stu-id="90fff-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="90fff-198">使用下面的方法创建 PowerShell 脚本：</span><span class="sxs-lookup"><span data-stu-id="90fff-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="90fff-199">打开“**组策略管理控制台**”并导航到组织单位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="90fff-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="90fff-200">右键单击并选择“**在此域中创建 GPO，并在此处链接它**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="90fff-201">系统提示时，为此组策略对象 (GPO) 分配一个描述性名称，然后完成创建。</span><span class="sxs-lookup"><span data-stu-id="90fff-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="90fff-202">右键单击“GPO”，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="90fff-203">转到“**计算机配置**” > “**首选项**” > **控制面板设置** > “**已计划任务**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="90fff-204">通过右键单击，然后选择“**新建任务**” > “**立即任务（至少为 Windows 7）**”来创建新的立即任务。</span><span class="sxs-lookup"><span data-stu-id="90fff-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="90fff-205">命名任务并提供说明。</span><span class="sxs-lookup"><span data-stu-id="90fff-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="90fff-206">选择相应的帐户以运行立即任务，例如 NT Authority</span><span class="sxs-lookup"><span data-stu-id="90fff-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="90fff-207">选择“**以最高权限运行**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="90fff-208">配置 Windows 10 的策略。</span><span class="sxs-lookup"><span data-stu-id="90fff-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="90fff-209">在“**操作**”选项卡中，选择“**启动程序**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="90fff-210">输入步骤 1 中创建的程序/脚本的路径。</span><span class="sxs-lookup"><span data-stu-id="90fff-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="90fff-211">选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="90fff-212">将 Chrome 扩展添加到 ForceInstall 列表</span><span class="sxs-lookup"><span data-stu-id="90fff-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="90fff-213">在组策略管理编辑器中，导航到“OU”。</span><span class="sxs-lookup"><span data-stu-id="90fff-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="90fff-214">展开以下路径“**计算机/用户配置**” > “**策略**” > “**管理模板**” > “**经典管理模板**” > “**Google**” > “**Google Chrome**” > “**扩展**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="90fff-215">此路径可能有所不同，具体取决于你的配置。</span><span class="sxs-lookup"><span data-stu-id="90fff-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="90fff-216">选择“**配置强制安装的扩展列表**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="90fff-217">右键单击并选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="90fff-218">选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="90fff-219">选择“**显示**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-219">Select **Show**.</span></span>

7.  <span data-ttu-id="90fff-220">在“**值**”下添加以下条目：`echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="90fff-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="90fff-221">依次选择“**确定**”和“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="90fff-222">测试扩展</span><span class="sxs-lookup"><span data-stu-id="90fff-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="90fff-223">上传到云服务，或通过不允许的浏览器云出口访问</span><span class="sxs-lookup"><span data-stu-id="90fff-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>

1. <span data-ttu-id="90fff-224">创建或获取敏感项目，并尝试将文件上传到组织受限服务域之一。</span><span class="sxs-lookup"><span data-stu-id="90fff-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="90fff-225">敏感数据必须与我们的一个内置 [敏感信息类型](sensitive-information-type-entity-definitions.md) 或组织的敏感信息类型之一相匹配。</span><span class="sxs-lookup"><span data-stu-id="90fff-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="90fff-226">应从正在测试的设备上收到 DLP toast 通知，说明当文件打开时不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="90fff-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="90fff-227">在 Chrome 中测试其他 DLP 方案</span><span class="sxs-lookup"><span data-stu-id="90fff-227">Testing other DLP scenarios in Chrome</span></span>

<span data-ttu-id="90fff-228">因为已从不允许的浏览器/应用列表中删除 Chrome，现可测试以下方案，以确认行为符合组织要求：</span><span class="sxs-lookup"><span data-stu-id="90fff-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="90fff-229">使用剪贴板将敏感项的数据复制到另一个文档</span><span class="sxs-lookup"><span data-stu-id="90fff-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
  - <span data-ttu-id="90fff-230">若要测试，请在 Chrome 浏览器中打开要防止复制到剪贴板操作的文件，然后尝试复制该文件的数据。</span><span class="sxs-lookup"><span data-stu-id="90fff-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
  - <span data-ttu-id="90fff-231">预期结果：DLP toast 通知，显示打开文件时不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="90fff-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="90fff-232">打印文档</span><span class="sxs-lookup"><span data-stu-id="90fff-232">Print a document</span></span>
  - <span data-ttu-id="90fff-233">若要测试，请在 Chrome 浏览器中打开防止打印操作的文件，然后尝试打印该文件。</span><span class="sxs-lookup"><span data-stu-id="90fff-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
  - <span data-ttu-id="90fff-234">预期结果：DLP toast 通知，显示打开文件时不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="90fff-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="90fff-235">复制到 USB 可移动媒体</span><span class="sxs-lookup"><span data-stu-id="90fff-235">Copy to USB Removeable Media</span></span>
  - <span data-ttu-id="90fff-236">若要测试，请尝试将文件保存到可移动媒体存储器。</span><span class="sxs-lookup"><span data-stu-id="90fff-236">To test, try to save the file to a removeable media storage.</span></span>
  - <span data-ttu-id="90fff-237">预期结果：DLP toast 通知，显示打开文件时不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="90fff-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="90fff-238">复制到网络共享</span><span class="sxs-lookup"><span data-stu-id="90fff-238">Copy to Network Share</span></span>
  - <span data-ttu-id="90fff-239">若要测试，请尝试将文件保存到网络共享。</span><span class="sxs-lookup"><span data-stu-id="90fff-239">To test, try to save the file to a network share.</span></span>
  - <span data-ttu-id="90fff-240">预期结果：DLP toast 通知，显示打开文件时不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="90fff-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>

### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="90fff-241">使用警报管理仪表板查看 Chrome DLP 警报</span><span class="sxs-lookup"><span data-stu-id="90fff-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="90fff-242">在 [Microsoft 365 合规中心](https://compliance.microsoft.com) 内打开“**数据丢失防护**”页面，然后选择“**警报**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="90fff-243">请参阅 [如何配置和查看 DLP 策略警报](dlp-configure-view-alerts-policies.md) 中的过程，以查看你的终结点 DLP 策略警报。</span><span class="sxs-lookup"><span data-stu-id="90fff-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="90fff-244">在活动资源管理器中查看 Chrome DLP 数据</span><span class="sxs-lookup"><span data-stu-id="90fff-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="90fff-245">在 Microsoft 365 合规中心中打开域的“[数据分类页面](https://compliance.microsoft.com/dataclassification?viewid=overview)”，然后选择“**活动资源管理器**”。</span><span class="sxs-lookup"><span data-stu-id="90fff-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="90fff-246">请参考[活动资源管理器入门](data-classification-activity-explorer.md)中的程序，以访问和筛选终结点设备的所有数据。</span><span class="sxs-lookup"><span data-stu-id="90fff-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="90fff-247">![终结点设备的活动资源管理器筛选器](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="90fff-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="90fff-248">已知问题和限制</span><span class="sxs-lookup"><span data-stu-id="90fff-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="90fff-249">不支持对云出口执行阻止替代。</span><span class="sxs-lookup"><span data-stu-id="90fff-249">Block Override enforcement for cloud egress is not supported.</span></span>
2. <span data-ttu-id="90fff-250">不支持并必须禁用 Incognito 模式。</span><span class="sxs-lookup"><span data-stu-id="90fff-250">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="90fff-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="90fff-251">Next steps</span></span>

<span data-ttu-id="90fff-252">现在，你已载入设备，并且可以在“活动资源管理器”中查看活动数据，那么就可以继续下一步，在其中创建保护敏感项目的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="90fff-252">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="90fff-253">使用端点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="90fff-253">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="90fff-254">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90fff-254">See also</span></span>

- [<span data-ttu-id="90fff-255">了解终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="90fff-255">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="90fff-256">使用终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="90fff-256">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="90fff-257">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="90fff-257">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="90fff-258">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="90fff-258">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="90fff-259">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="90fff-259">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="90fff-260">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="90fff-260">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="90fff-261">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="90fff-261">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="90fff-262">Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="90fff-262">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="90fff-263">已建立 Azure AD 联接的设备</span><span class="sxs-lookup"><span data-stu-id="90fff-263">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="90fff-264">下载基于 Chromium 的新 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="90fff-264">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
