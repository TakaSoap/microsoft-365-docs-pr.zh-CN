---
title: 网络设备发现和漏洞管理
description: 安全建议和漏洞检测现在适用于交换机、路由器、WLAN 控制器和防火墙的操作系统。
keywords: 网络设备、网络设备漏洞检测、交换机、路由器、WLAN 控制器和防火墙的操作系统
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06b52e937dd0260a50883c45c36389a6a955ad0e
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604496"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="17a65-104">网络设备发现和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="17a65-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17a65-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="17a65-105">**Applies to:**</span></span>

- [<span data-ttu-id="17a65-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="17a65-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="17a65-107">威胁和漏洞管理</span><span class="sxs-lookup"><span data-stu-id="17a65-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="17a65-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17a65-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="17a65-109">**扫描和管理网络设备目前处于公共预览阶段**</span><span class="sxs-lookup"><span data-stu-id="17a65-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="17a65-110">此预览版本在没有服务级别协议的情况下提供，不建议用于生产工作负载。</span><span class="sxs-lookup"><span data-stu-id="17a65-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="17a65-111">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="17a65-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="17a65-112">有关详细信息，请参阅适用于终结点预览[功能的 Microsoft Defender。](preview.md)</span><span class="sxs-lookup"><span data-stu-id="17a65-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="17a65-113">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="17a65-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="17a65-114">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="17a65-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="17a65-115">Microsoft 365 安全中心和 Microsoft Defender 安全中心控制台的设备清单部分提供了网络发现功能。</span><span class="sxs-lookup"><span data-stu-id="17a65-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="17a65-116">指定的 Microsoft Defender for Endpoint 设备将用于每个网段，以定期对预配置的网络设备执行经过身份验证的扫描。</span><span class="sxs-lookup"><span data-stu-id="17a65-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="17a65-117">发现后，终结点的 Defender 威胁和漏洞管理功能将提供集成的工作流，用于保护发现的交换机、路由器、WLAN 控制器、防火墙和 VPN 网关。</span><span class="sxs-lookup"><span data-stu-id="17a65-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="17a65-118">发现网络设备并进行分类后，安全管理员将能够接收最新的安全建议，并查看最近发现的跨组织部署的网络设备的漏洞。</span><span class="sxs-lookup"><span data-stu-id="17a65-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities foron network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="17a65-119">方法</span><span class="sxs-lookup"><span data-stu-id="17a65-119">Approach</span></span>

<span data-ttu-id="17a65-120">由于 Defender for Endpoint 本身没有内置于网络设备中的传感器，因此不会将网络设备作为标准终结点进行管理。</span><span class="sxs-lookup"><span data-stu-id="17a65-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="17a65-121">这些类型的设备需要无代理方法，远程扫描将获取设备的必要信息。</span><span class="sxs-lookup"><span data-stu-id="17a65-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="17a65-122">根据网络拓扑和特征，已载入 Microsoft Defender for Endpoint 的一台或几台设备使用 SNMP (只读) 对网络设备执行经过身份验证的扫描。</span><span class="sxs-lookup"><span data-stu-id="17a65-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="17a65-123">需要记住两种类型的设备：</span><span class="sxs-lookup"><span data-stu-id="17a65-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="17a65-124">**评估** 设备：已载入用于扫描网络设备的设备。</span><span class="sxs-lookup"><span data-stu-id="17a65-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="17a65-125">**网络设备**：计划扫描和载入的网络设备。</span><span class="sxs-lookup"><span data-stu-id="17a65-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="17a65-126">网络设备的漏洞管理</span><span class="sxs-lookup"><span data-stu-id="17a65-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="17a65-127">发现网络设备并进行分类后，安全管理员将能够接收最新的安全建议，并查看最近在组织中部署的网络设备上发现的漏洞。</span><span class="sxs-lookup"><span data-stu-id="17a65-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="17a65-128">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="17a65-128">Operating systems that are supported</span></span>

<span data-ttu-id="17a65-129">目前支持以下操作系统：</span><span class="sxs-lookup"><span data-stu-id="17a65-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="17a65-130">Cisco IOS、IOS-XE、NX-OS</span><span class="sxs-lookup"><span data-stu-id="17a65-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="17a65-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="17a65-131">Juniper JUNOS</span></span>
- <span data-ttu-id="17a65-132">HPE 更新、安装交换机软件</span><span class="sxs-lookup"><span data-stu-id="17a65-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="17a65-133">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="17a65-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="17a65-134">随着时间的推移，将基于从客户使用情况收集的数据，添加更多网络供应商和操作系统。</span><span class="sxs-lookup"><span data-stu-id="17a65-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="17a65-135">因此，建议配置所有网络设备，即使在此列表中未指定这些设备。</span><span class="sxs-lookup"><span data-stu-id="17a65-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="17a65-136">如何开始使用</span><span class="sxs-lookup"><span data-stu-id="17a65-136">How to get started</span></span>

<span data-ttu-id="17a65-137">第一步是选择将执行经过身份验证的网络扫描的设备。</span><span class="sxs-lookup"><span data-stu-id="17a65-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="17a65-138">确定适用于终结点的 Defender (客户端或) ，该客户端或服务器具有与计划扫描的网络设备的管理端口的网络连接。</span><span class="sxs-lookup"><span data-stu-id="17a65-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="17a65-139">必须允许 Defender for Endpoint 评估设备和目标网络设备之间的 SNMP 流量 (例如，防火墙) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="17a65-140">确定将针对漏洞评估哪些网络设备 (例如：Cisco 交换机或 Palo Alto Networks 防火墙) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="17a65-141">确保在所有已配置的网络设备上启用 SNMP 只读，以允许 Defender for Endpoint 评估设备查询配置的网络设备。</span><span class="sxs-lookup"><span data-stu-id="17a65-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="17a65-142">此功能的正确功能不需要"SNMP 写入"。</span><span class="sxs-lookup"><span data-stu-id="17a65-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="17a65-143">获取要扫描的网络设备的 IP 地址 (或将这些设备部署到的子网) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="17a65-144">获取网络设备的 SNMP 凭据 (例如：Community String、noAuthNoPriv、authNoPriv、authPriv) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="17a65-145">配置新的评估作业时，需要提供凭据。</span><span class="sxs-lookup"><span data-stu-id="17a65-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="17a65-146">代理客户端配置：除 Defender for Endpoint 设备代理要求外，无需其他配置。</span><span class="sxs-lookup"><span data-stu-id="17a65-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="17a65-147">若要允许网络扫描程序进行身份验证并正常运行，必须添加以下域/URL：</span><span class="sxs-lookup"><span data-stu-id="17a65-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="17a65-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="17a65-148">login.windows.net</span></span>  
    - <span data-ttu-id="17a65-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="17a65-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="17a65-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="17a65-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="17a65-151">*.blob.core.windows.net/networkscannerstable/*</span><span class="sxs-lookup"><span data-stu-id="17a65-151">*.blob.core.windows.net/networkscannerstable/*</span></span>

    <span data-ttu-id="17a65-152">注意：这些 URL 未在允许数据收集的 Defender for Endpoint 记录列表中指定。</span><span class="sxs-lookup"><span data-stu-id="17a65-152">Note: These URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="17a65-153">权限</span><span class="sxs-lookup"><span data-stu-id="17a65-153">Permissions</span></span>

<span data-ttu-id="17a65-154">若要配置评估作业，需要以下用户权限选项： **在安全中心中管理安全设置**。</span><span class="sxs-lookup"><span data-stu-id="17a65-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="17a65-155">可以通过访问"设置""角色 **"来查找**  >  **权限**。</span><span class="sxs-lookup"><span data-stu-id="17a65-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="17a65-156">有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="17a65-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="17a65-157">安装网络扫描程序</span><span class="sxs-lookup"><span data-stu-id="17a65-157">Install the network scanner</span></span>

1. <span data-ttu-id="17a65-158">转到"网络评估"下 (Microsoft **365** 安全设置终结点评估  >    >    >  作业) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="17a65-159">在 Microsoft Defender 安全中心中，转到"设置>评估作业"页面。</span><span class="sxs-lookup"><span data-stu-id="17a65-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="17a65-160">下载网络扫描程序，将其安装在指定的 Defender for Endpoint 评估设备上。</span><span class="sxs-lookup"><span data-stu-id="17a65-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![下载扫描程序按钮](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="17a65-162">网络扫描程序安装&注册</span><span class="sxs-lookup"><span data-stu-id="17a65-162">Network scanner installation & registration</span></span>

<span data-ttu-id="17a65-163">登录过程可以在指定的评估设备本身或其他任何设备（例如，你的个人客户端设备 (）上) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="17a65-164">要完成网络扫描程序注册过程，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="17a65-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="17a65-165">复制并遵循命令行上出现的 URL，并使用提供的安装代码完成注册过程。</span><span class="sxs-lookup"><span data-stu-id="17a65-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="17a65-166">注意：可能需要更改命令提示符设置才能复制 URL。</span><span class="sxs-lookup"><span data-stu-id="17a65-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="17a65-167">输入代码，然后使用具有名为"在安全中心管理安全设置"的 Defender for Endpoint 权限的 Microsoft 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="17a65-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="17a65-168">完成后，应该会看到一条消息，确认你已登录。</span><span class="sxs-lookup"><span data-stu-id="17a65-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="17a65-169">配置新的评估作业</span><span class="sxs-lookup"><span data-stu-id="17a65-169">Configure a new assessment job</span></span>  

<span data-ttu-id="17a65-170">在"设置"中的"评估作业 **"页中**，选择 **"添加网络评估作业"。**</span><span class="sxs-lookup"><span data-stu-id="17a65-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="17a65-171">按照设置过程选择要定期扫描并添加到设备清单的网络设备。</span><span class="sxs-lookup"><span data-stu-id="17a65-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="17a65-172">若要防止网络设备清单中的设备重复，请确保跨多个评估设备仅配置每个 IP 地址一次。</span><span class="sxs-lookup"><span data-stu-id="17a65-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![添加网络评估作业按钮](images/assessment-jobs-add.png)

<span data-ttu-id="17a65-174">添加网络评估作业步骤：</span><span class="sxs-lookup"><span data-stu-id="17a65-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="17a65-175">选择"评估作业"名称和"评估设备"，其中安装了网络扫描程序。</span><span class="sxs-lookup"><span data-stu-id="17a65-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="17a65-176">此设备将定期执行经过身份验证的扫描。</span><span class="sxs-lookup"><span data-stu-id="17a65-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="17a65-177">添加要扫描的目标网络设备的 IP 地址 (或部署这些设备的子网) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="17a65-178">添加目标网络设备所需的 SNMP 凭据。</span><span class="sxs-lookup"><span data-stu-id="17a65-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="17a65-179">保存新配置的网络评估作业以启动定期网络扫描。</span><span class="sxs-lookup"><span data-stu-id="17a65-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="17a65-180">扫描和添加网络设备</span><span class="sxs-lookup"><span data-stu-id="17a65-180">Scan and add network devices</span></span>

<span data-ttu-id="17a65-181">在设置过程中，可以执行一次测试扫描来验证：</span><span class="sxs-lookup"><span data-stu-id="17a65-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="17a65-182">Defender for Endpoint 评估设备和已配置的目标网络设备之间具有连接。</span><span class="sxs-lookup"><span data-stu-id="17a65-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="17a65-183">配置的 SNMP 凭据正确。</span><span class="sxs-lookup"><span data-stu-id="17a65-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="17a65-184">每个评估设备可支持最多 1，500 个成功的 IP 地址扫描。</span><span class="sxs-lookup"><span data-stu-id="17a65-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="17a65-185">例如，如果扫描仅 100 个 IP 地址返回成功结果的 10 个不同子网，您将能够扫描来自同一评估设备上其他子网的 1，400 个 IP 其他地址。</span><span class="sxs-lookup"><span data-stu-id="17a65-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="17a65-186">如果有多个 IP 地址范围/子网要扫描，则测试扫描结果需要几分钟时间才能显示。</span><span class="sxs-lookup"><span data-stu-id="17a65-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="17a65-187">测试扫描最多可用于 1，024 个地址。</span><span class="sxs-lookup"><span data-stu-id="17a65-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="17a65-188">显示结果后，你可以选择哪些设备将包含在定期扫描中。</span><span class="sxs-lookup"><span data-stu-id="17a65-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="17a65-189">如果跳过查看扫描结果，则所有配置的 IP 地址都将添加到网络评估作业 (无论设备的响应状态如何) 。</span><span class="sxs-lookup"><span data-stu-id="17a65-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="17a65-190">也可以导出扫描结果。</span><span class="sxs-lookup"><span data-stu-id="17a65-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="17a65-191">设备清单</span><span class="sxs-lookup"><span data-stu-id="17a65-191">Device inventory</span></span>

<span data-ttu-id="17a65-192">新发现的设备将显示在"设备清单"页中的"新网络设备"**选项卡** 下。</span><span class="sxs-lookup"><span data-stu-id="17a65-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="17a65-193">添加评估作业后最多可能需要两个小时，直到设备更新。</span><span class="sxs-lookup"><span data-stu-id="17a65-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

!["设备清单"中的"网络设备"部分](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="17a65-195">疑难解答</span><span class="sxs-lookup"><span data-stu-id="17a65-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="17a65-196">网络扫描程序安装失败</span><span class="sxs-lookup"><span data-stu-id="17a65-196">Network scanner installation has failed</span></span>

<span data-ttu-id="17a65-197">验证所需的 URL 是否添加到防火墙设置中的允许域。</span><span class="sxs-lookup"><span data-stu-id="17a65-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="17a65-198">此外，请确保代理设置已配置，如配置 [设备代理和 Internet 连接设置中所述](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="17a65-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="17a65-199">未 Microsoft.com/devicelogin 网页</span><span class="sxs-lookup"><span data-stu-id="17a65-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="17a65-200">验证所需的 URL 是否添加到防火墙中的允许域。</span><span class="sxs-lookup"><span data-stu-id="17a65-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="17a65-201">此外，请确保代理设置已配置，如配置 [设备代理和 Internet 连接设置 中所述](configure-proxy-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="17a65-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="17a65-202">几个小时后，网络设备不会显示在设备清单中</span><span class="sxs-lookup"><span data-stu-id="17a65-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="17a65-203">完成评估作业配置后，应在进行初始扫描后几小时更新扫描结果。</span><span class="sxs-lookup"><span data-stu-id="17a65-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="17a65-204">如果仍未显示设备，请验证服务"MdatpNetworkScanService"是否正在你安装了网络扫描程序的评估设备上运行，并执行相关评估作业配置中的"运行扫描"。</span><span class="sxs-lookup"><span data-stu-id="17a65-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="17a65-205">如果在 5 分钟后仍未获得结果，请重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="17a65-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="17a65-206">设备上次看到时间超过 24 小时</span><span class="sxs-lookup"><span data-stu-id="17a65-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="17a65-207">验证扫描程序是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="17a65-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="17a65-208">然后转到扫描定义，然后选择"运行测试"。</span><span class="sxs-lookup"><span data-stu-id="17a65-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="17a65-209">检查从相关 IP 地址返回的错误消息。</span><span class="sxs-lookup"><span data-stu-id="17a65-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="17a65-210">必需的威胁和漏洞管理用户权限</span><span class="sxs-lookup"><span data-stu-id="17a65-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="17a65-211">注册后出现错误："看起来你没有足够的权限添加新代理。</span><span class="sxs-lookup"><span data-stu-id="17a65-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="17a65-212">所需权限为"在安全中心管理安全设置"。</span><span class="sxs-lookup"><span data-stu-id="17a65-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="17a65-213">按任意键退出。</span><span class="sxs-lookup"><span data-stu-id="17a65-213">Press any key to exit.</span></span>

<span data-ttu-id="17a65-214">要求系统管理员分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="17a65-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="17a65-215">或者，请求其他相关成员通过为他们提供登录代码和链接来帮助你执行登录过程。</span><span class="sxs-lookup"><span data-stu-id="17a65-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="17a65-216">注册过程在注册过程中使用命令行中提供的链接失败</span><span class="sxs-lookup"><span data-stu-id="17a65-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="17a65-217">请尝试不同的浏览器，或将登录链接和代码复制到其他设备。</span><span class="sxs-lookup"><span data-stu-id="17a65-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="17a65-218">文本过小或无法从命令行复制文本</span><span class="sxs-lookup"><span data-stu-id="17a65-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="17a65-219">更改设备的命令行设置，以允许复制和更改文本大小。</span><span class="sxs-lookup"><span data-stu-id="17a65-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="17a65-220">相关文章</span><span class="sxs-lookup"><span data-stu-id="17a65-220">Related articles</span></span>

- [<span data-ttu-id="17a65-221">设备清单</span><span class="sxs-lookup"><span data-stu-id="17a65-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="17a65-222">配置高级功能</span><span class="sxs-lookup"><span data-stu-id="17a65-222">Configure advanced features</span></span>](advanced-features.md)
