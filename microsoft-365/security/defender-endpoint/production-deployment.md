---
title: 设置 Microsoft Defender for Endpoint 部署
description: 了解如何设置 Microsoft Defender for Endpoint 的部署
keywords: 部署， 设置， 许可验证， 租户配置， 网络配置
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
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7abf1c9e4115c928ae581da3789270fd8ed036d3
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476297"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="a26f0-104">设置 Microsoft Defender for Endpoint 部署</span><span class="sxs-lookup"><span data-stu-id="a26f0-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a26f0-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a26f0-105">**Applies to:**</span></span>
- [<span data-ttu-id="a26f0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a26f0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a26f0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a26f0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a26f0-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a26f0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a26f0-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a26f0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a26f0-110">部署适用于终结点的 Defender 的过程分三个阶段：</span><span class="sxs-lookup"><span data-stu-id="a26f0-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="a26f0-111">[![部署阶段 - 准备](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="a26f0-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="a26f0-112">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="a26f0-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![部署阶段 - 设置](images/phase-diagrams/setup.png)<br><span data-ttu-id="a26f0-114">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="a26f0-114">Phase 2: Setup</span></span> | <span data-ttu-id="a26f0-115">[![部署阶段 - 载入](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="a26f0-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="a26f0-116">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="a26f0-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="a26f0-117">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="a26f0-117">*You are here!*</span></span>||

<span data-ttu-id="a26f0-118">您当前处于设置阶段。</span><span class="sxs-lookup"><span data-stu-id="a26f0-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="a26f0-119">在此部署方案中，将指导你完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a26f0-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="a26f0-120">许可验证</span><span class="sxs-lookup"><span data-stu-id="a26f0-120">Licensing validation</span></span>
- <span data-ttu-id="a26f0-121">租户配置</span><span class="sxs-lookup"><span data-stu-id="a26f0-121">Tenant configuration</span></span>
- <span data-ttu-id="a26f0-122">网络配置</span><span class="sxs-lookup"><span data-stu-id="a26f0-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="a26f0-123">为了指导你完成典型部署，此方案仅涉及 Microsoft Endpoint Configuration Manager 的使用。</span><span class="sxs-lookup"><span data-stu-id="a26f0-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a26f0-124">Defender for Endpoint 支持使用其他载入工具，但不在部署指南中介绍这些方案。</span><span class="sxs-lookup"><span data-stu-id="a26f0-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="a26f0-125">有关详细信息，请参阅 [将设备载入到 Microsoft Defender for Endpoint](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="a26f0-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="a26f0-126">检查许可证状态</span><span class="sxs-lookup"><span data-stu-id="a26f0-126">Check license state</span></span>

<span data-ttu-id="a26f0-127">通过管理中心或 **Microsoft Azure** 门户，可以检查许可证状态及其是否已正确预配。</span><span class="sxs-lookup"><span data-stu-id="a26f0-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="a26f0-128">若要查看许可证，请转到 **Microsoft Azure 门户** 并导航到 Microsoft Azure [门户许可证部分](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="a26f0-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 许可页面的图像](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="a26f0-130">或者，在管理中心中，导航到"**帐单**  >  **""订阅"。**</span><span class="sxs-lookup"><span data-stu-id="a26f0-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="a26f0-131">在屏幕上，你将看到所有预配的许可证及其当前 **状态**。</span><span class="sxs-lookup"><span data-stu-id="a26f0-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![帐单许可证的图像](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="a26f0-133">云服务提供商验证</span><span class="sxs-lookup"><span data-stu-id="a26f0-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="a26f0-134">若要获取向公司预配哪些许可证的访问权限，并检查许可证的状态，请转到管理中心。</span><span class="sxs-lookup"><span data-stu-id="a26f0-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="a26f0-135">从合作伙伴 **门户中，** 选择 **"管理服务> Office 365"。**</span><span class="sxs-lookup"><span data-stu-id="a26f0-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="a26f0-136">单击"**合作伙伴门户**"链接将打开"代表管理员"选项，并授予你客户管理中心的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a26f0-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![O365 管理门户的图像](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="a26f0-138">租户配置</span><span class="sxs-lookup"><span data-stu-id="a26f0-138">Tenant Configuration</span></span>

<span data-ttu-id="a26f0-139">首次访问 Microsoft Defender 安全中心时，向导将指导你完成一些初始步骤。</span><span class="sxs-lookup"><span data-stu-id="a26f0-139">When accessing Microsoft Defender Security Center for the first time, a wizard that will guide you through some initial steps.</span></span> <span data-ttu-id="a26f0-140">在设置向导结束时，将创建一个 Defender for Endpoint 的专用云实例。</span><span class="sxs-lookup"><span data-stu-id="a26f0-140">At the end of the setup wizard, there will be a dedicated cloud instance of Defender for Endpoint created.</span></span> <span data-ttu-id="a26f0-141">最简单的方法是从 Windows 10 客户端设备执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="a26f0-141">The easiest method is to perform these steps from a Windows 10 client device.</span></span>

1. <span data-ttu-id="a26f0-142">在 Web 浏览器中，导航到 <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="a26f0-142">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

    ![为 Microsoft Defender for Endpoint 设置权限的图像](images/atp-setup-permissions-wdatp-portal.png)

2. <span data-ttu-id="a26f0-144">如果通过试用版许可证，请转到"试用 <https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x> () </span><span class="sxs-lookup"><span data-stu-id="a26f0-144">If going through a TRIAL license, go to the link (<https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x>)</span></span>

    <span data-ttu-id="a26f0-145">授权步骤完成后，将显示 **欢迎** 屏幕。</span><span class="sxs-lookup"><span data-stu-id="a26f0-145">Once the authorization step is completed, the **Welcome** screen will be displayed.</span></span>
3. <span data-ttu-id="a26f0-146">完成授权步骤。</span><span class="sxs-lookup"><span data-stu-id="a26f0-146">Go through the authorization steps.</span></span>

    ![门户设置的欢迎屏幕图像](images/welcome1.png)

4. <span data-ttu-id="a26f0-148">设置首选项。</span><span class="sxs-lookup"><span data-stu-id="a26f0-148">Set up preferences.</span></span>

   <span data-ttu-id="a26f0-149">**数据存储位置** - 正确设置这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="a26f0-149">**Data storage location** - It's important to set this up correctly.</span></span> <span data-ttu-id="a26f0-150">确定客户希望主要托管在何处：美国、欧盟或英国。</span><span class="sxs-lookup"><span data-stu-id="a26f0-150">Determine where the customer wants to be primarily hosted: US, EU, or UK.</span></span> <span data-ttu-id="a26f0-151">设置后，你无法更改位置，并且 Microsoft 不会从指定的地理位置传输数据。</span><span class="sxs-lookup"><span data-stu-id="a26f0-151">You can't change the location after this set up and Microsoft won't transfer the data from the specified geolocation.</span></span> 

    <span data-ttu-id="a26f0-152">**数据保留** - 默认值为六个月。</span><span class="sxs-lookup"><span data-stu-id="a26f0-152">**Data retention** - The default is six months.</span></span>

    <span data-ttu-id="a26f0-153">**启用预览功能** - 默认为打开，可在以后更改。</span><span class="sxs-lookup"><span data-stu-id="a26f0-153">**Enable preview features** - The default is on, can be changed later.</span></span>

    ![设置中的地理位置图像](images/setup-preferences.png)

5. <span data-ttu-id="a26f0-155">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="a26f0-155">Select **Next**.</span></span>

     ![最终首选项设置的图像](images/setup-preferences2.png)

6. <span data-ttu-id="a26f0-157">选择"**继续"。**</span><span class="sxs-lookup"><span data-stu-id="a26f0-157">Select **Continue**.</span></span>


## <a name="network-configuration"></a><span data-ttu-id="a26f0-158">网络配置</span><span class="sxs-lookup"><span data-stu-id="a26f0-158">Network configuration</span></span>
<span data-ttu-id="a26f0-159">如果组织不要求终结点使用代理访问 Internet，请跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="a26f0-159">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="a26f0-160">Microsoft Defender for Endpoint 感官方案需要 Microsoft Windows HTTP （WinHTTP） 报告感官数据，并与 Microsoft Defender for Endpoint 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="a26f0-160">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="a26f0-161">嵌入的 Microsoft Defender for Endpoint 传感器使用 LocalSystem 帐户在系统上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="a26f0-161">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="a26f0-162">该感官服务使用 Microsoft Windows HTTP Services （WinHTTP） 与 Microsoft Defender for Endpoint 云服务启用通信。</span><span class="sxs-lookup"><span data-stu-id="a26f0-162">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="a26f0-163">WinHTTP 配置设置独立于 Windows Internet (WinINet) Internet 浏览代理设置，并且只能使用下列发现方法发现代理服务器：</span><span class="sxs-lookup"><span data-stu-id="a26f0-163">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="a26f0-164">**自动发现方法：**</span><span class="sxs-lookup"><span data-stu-id="a26f0-164">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="a26f0-165">透明代理</span><span class="sxs-lookup"><span data-stu-id="a26f0-165">Transparent proxy</span></span>

-   <span data-ttu-id="a26f0-166">Web 代理自动发现协议 (WPAD) </span><span class="sxs-lookup"><span data-stu-id="a26f0-166">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="a26f0-167">如果在网络拓扑中实施了透明代理或 WPAD，则不需要特殊的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a26f0-167">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="a26f0-168">有关代理中终结点 URL 排除的 Microsoft Defender 详细信息，请参阅[](production-deployment.md#proxy-service-urls)本文档中的代理服务 URL 部分，了解 URL 允许列表或配置设备代理和[Internet 连接设置](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="a26f0-168">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="a26f0-169">**手动静态代理配置：**</span><span class="sxs-lookup"><span data-stu-id="a26f0-169">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="a26f0-170">基于注册表的配置</span><span class="sxs-lookup"><span data-stu-id="a26f0-170">Registry-based configuration</span></span>

-   <span data-ttu-id="a26f0-171">使用 netsh 命令配置的 WinHTTP</span><span class="sxs-lookup"><span data-stu-id="a26f0-171">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="a26f0-172">仅适用于稳定拓扑结构中的桌面 (例如：企业网络中同一代理服务器后面的桌面) </span><span class="sxs-lookup"><span data-stu-id="a26f0-172">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="a26f0-173">使用基于注册表的静态代理手动配置代理服务器</span><span class="sxs-lookup"><span data-stu-id="a26f0-173">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="a26f0-174">配置基于注册表的静态代理，以允许仅 Microsoft Defender for Endpoint 传感器报告诊断数据，并与 Microsoft Defender for Endpoint 服务进行通信（如果不允许计算机连接到 Internet）。</span><span class="sxs-lookup"><span data-stu-id="a26f0-174">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="a26f0-175">静态代理可以通过组策略 (GP) 配置。</span><span class="sxs-lookup"><span data-stu-id="a26f0-175">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="a26f0-176">可以在以下位置找到组策略：</span><span class="sxs-lookup"><span data-stu-id="a26f0-176">The group policy can be found under:</span></span>

 - <span data-ttu-id="a26f0-177">管理模板 \> Windows 组件 \> 数据收集和预览版 配置连接的用户体验和遥测服务的已验证 \> 代理使用情况</span><span class="sxs-lookup"><span data-stu-id="a26f0-177">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="a26f0-178">将其设置为" **已启用"，** 然后选择 **"禁用经过身份验证的代理用法"**</span><span class="sxs-lookup"><span data-stu-id="a26f0-178">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="a26f0-179">打开组策略管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a26f0-179">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="a26f0-180">根据组织实践创建策略或编辑现有策略。</span><span class="sxs-lookup"><span data-stu-id="a26f0-180">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="a26f0-181">编辑组策略并导航到"管理模板""Windows 组件""数据收集和预览版""配置连接的用户体验和遥测服务的已验证 **\> \> \> 代理使用情况"。**</span><span class="sxs-lookup"><span data-stu-id="a26f0-181">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="a26f0-182">![组策略配置的图像](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="a26f0-182">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="a26f0-183">选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="a26f0-183">Select **Enabled**.</span></span>
5. <span data-ttu-id="a26f0-184">选择 **"禁用经过身份验证的代理用法"。**</span><span class="sxs-lookup"><span data-stu-id="a26f0-184">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="a26f0-185">导航到 **管理模板 \> Windows 组件 \> 数据收集和预览版 \> 配置连接的用户体验和遥测**。</span><span class="sxs-lookup"><span data-stu-id="a26f0-185">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="a26f0-186">![组策略配置设置的图像](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="a26f0-186">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="a26f0-187">选择“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="a26f0-187">Select **Enabled**.</span></span>
8. <span data-ttu-id="a26f0-188">输入 **代理服务器名称**。</span><span class="sxs-lookup"><span data-stu-id="a26f0-188">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="a26f0-189">策略将注册表项 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的两个注册表值 `TelemetryProxyServer` 设置为 REG\u SZ，`DisableEnterpriseAuthProxy` 设置为 REG\u DWORD。</span><span class="sxs-lookup"><span data-stu-id="a26f0-189">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="a26f0-190">注册表值 `TelemetryProxyServer` 采用以下字符串格式：</span><span class="sxs-lookup"><span data-stu-id="a26f0-190">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="a26f0-191">例如：10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="a26f0-191">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="a26f0-192">此注册表值 `DisableEnterpriseAuthProxy` 应当设置为 1。</span><span class="sxs-lookup"><span data-stu-id="a26f0-192">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="a26f0-193">使用 netsh 命令手动配置代理服务器</span><span class="sxs-lookup"><span data-stu-id="a26f0-193">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="a26f0-194">使用 netsh 配置系统范围的静态代理。</span><span class="sxs-lookup"><span data-stu-id="a26f0-194">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="a26f0-195">这将影响所有应用程序，包括使用带默认代理的 WinHTTP 的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="a26f0-195">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="a26f0-196">更改拓扑结构（例如 (：从办公室到家庭) netsh 将发生故障。</span><span class="sxs-lookup"><span data-stu-id="a26f0-196">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="a26f0-197">使用基于注册表的静态代理配置。</span><span class="sxs-lookup"><span data-stu-id="a26f0-197">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="a26f0-198">打开提升的命令行:</span><span class="sxs-lookup"><span data-stu-id="a26f0-198">Open an elevated command line:</span></span>

    1. <span data-ttu-id="a26f0-199">转到“**开始**”并键入“**cmd**”。</span><span class="sxs-lookup"><span data-stu-id="a26f0-199">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="a26f0-200">右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="a26f0-200">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="a26f0-201">输入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="a26f0-201">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="a26f0-202">例如：netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="a26f0-202">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="a26f0-203">低级别设备的代理配置</span><span class="sxs-lookup"><span data-stu-id="a26f0-203">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="a26f0-204">Down-Level包括 Windows 7 SP1 和 Windows 8.1 工作站以及 Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2 和 Windows Server CB 1803 之前的 Windows Server 2016 版本。</span><span class="sxs-lookup"><span data-stu-id="a26f0-204">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="a26f0-205">这些操作系统将代理配置为 Microsoft 管理代理的一部分，以处理从终结点到 Azure 的通信。</span><span class="sxs-lookup"><span data-stu-id="a26f0-205">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="a26f0-206">请参阅 Microsoft 管理代理快速部署指南，了解如何在这些设备上配置代理。</span><span class="sxs-lookup"><span data-stu-id="a26f0-206">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="a26f0-207">代理服务 URL</span><span class="sxs-lookup"><span data-stu-id="a26f0-207">Proxy Service URLs</span></span>
<span data-ttu-id="a26f0-208">仅在有 Windows 10 版本 1803 或更高版本的设备时，才需要包含 v20 的 URL。</span><span class="sxs-lookup"><span data-stu-id="a26f0-208">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="a26f0-209">例如， ```us-v20.events.data.microsoft.com``` 仅在设备在 Windows 10 版本 1803 或更高版本上时需要 。</span><span class="sxs-lookup"><span data-stu-id="a26f0-209">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="a26f0-210">如果代理或防火墙阻止匿名流量，因为 Microsoft Defender for Endpoint 传感器从系统上下文连接，请确保允许列出的 URL 中的匿名流量。</span><span class="sxs-lookup"><span data-stu-id="a26f0-210">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="a26f0-211">以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。</span><span class="sxs-lookup"><span data-stu-id="a26f0-211">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="a26f0-212">确保没有拒绝访问这些 URL 的防火墙或网络筛选规则，或者您可能需要专门为它们创建允许规则。 </span><span class="sxs-lookup"><span data-stu-id="a26f0-212">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="a26f0-213">**域列表电子表格**</span><span class="sxs-lookup"><span data-stu-id="a26f0-213">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="a26f0-214">**描述**</span><span class="sxs-lookup"><span data-stu-id="a26f0-214">**Description**</span></span>|
|:-----|:-----|
|![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/>  | <span data-ttu-id="a26f0-216">服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。</span><span class="sxs-lookup"><span data-stu-id="a26f0-216">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="a26f0-217">在此处下载电子表格。</span><span class="sxs-lookup"><span data-stu-id="a26f0-217">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="a26f0-218">Microsoft Defender for Endpoint 服务后端 IP 范围</span><span class="sxs-lookup"><span data-stu-id="a26f0-218">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="a26f0-219">如果网络设备不支持基于 DNS 的规则，请改为使用 IP 范围。</span><span class="sxs-lookup"><span data-stu-id="a26f0-219">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="a26f0-220">Defender for Endpoint 内置于 Azure 云中，部署在以下区域：</span><span class="sxs-lookup"><span data-stu-id="a26f0-220">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="a26f0-221">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="a26f0-221">AzureCloud.eastus</span></span>
- <span data-ttu-id="a26f0-222">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="a26f0-222">AzureCloud.eastus2</span></span>
- <span data-ttu-id="a26f0-223">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="a26f0-223">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="a26f0-224">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="a26f0-224">AzureCloud.northeurope</span></span>
- <span data-ttu-id="a26f0-225">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="a26f0-225">AzureCloud.westeurope</span></span>
- <span data-ttu-id="a26f0-226">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="a26f0-226">AzureCloud.uksouth</span></span>
- <span data-ttu-id="a26f0-227">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="a26f0-227">AzureCloud.ukwest</span></span>

<span data-ttu-id="a26f0-228">可以在 Azure IP 范围和服务标记 - 公共云 [中查找 Azure](https://www.microsoft.com/download/details.aspx?id=56519)IP 范围。</span><span class="sxs-lookup"><span data-stu-id="a26f0-228">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="a26f0-229">作为基于云的解决方案，IP 地址范围可能会更改。</span><span class="sxs-lookup"><span data-stu-id="a26f0-229">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="a26f0-230">建议移动到基于 DNS 的规则。</span><span class="sxs-lookup"><span data-stu-id="a26f0-230">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="a26f0-231">如果你是美国政府客户，请参阅美国政府终结点 [Defender 页面中的相应](gov.md#service-backend-ip-ranges) 部分。</span><span class="sxs-lookup"><span data-stu-id="a26f0-231">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="a26f0-232">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a26f0-232">Next step</span></span>

<span data-ttu-id="a26f0-233">![**阶段 3：载入**](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="a26f0-233">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="a26f0-234">[阶段 3：载入](onboarding.md)：将设备载入服务，以便 Microsoft Defender for Endpoint 服务可以从它们获取传感器数据。</span><span class="sxs-lookup"><span data-stu-id="a26f0-234">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
