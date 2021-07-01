---
title: 设置使用 Microsoft 365 实现混合工作的基础结构
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: 在家办公，在家办公，混合，远程工作者，混合办公，远程员工，混合连接，远程访问，远程办公，远程办公，远程办公，移动办公，远程工作，随时随地开展工作，灵活的工作场所
description: 逐步设置基础结构层，以便远程工作者能够安全访问本地和 Microsoft 365 资源。
ms.openlocfilehash: fed23a4607cfb47049a6540dfb592d9a8baf9d21
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229367"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a><span data-ttu-id="a68e3-104">设置使用 Microsoft 365 实现混合工作的基础结构</span><span class="sxs-lookup"><span data-stu-id="a68e3-104">Set up your infrastructure for hybrid work with Microsoft 365</span></span>

<span data-ttu-id="a68e3-105">要保护并优化远程工作者的生产力和协作，你需要允许现场和远程工作者轻松、安全地访问组织内本地和基于云的信息、工具以及资源。</span><span class="sxs-lookup"><span data-stu-id="a68e3-105">To secure and optimize your worker’s productivity and collaboration, you need to allow on-site and remote workers to easily and securely access your organization's on-premises and cloud-based information, tools, and resources.</span></span> <span data-ttu-id="a68e3-106">此解决方案会逐步完成基础设施关键层的部署，让工作者无论在哪里都能够高效工作。</span><span class="sxs-lookup"><span data-stu-id="a68e3-106">This solution steps through the deployment of key layers of infrastructure that empower your workers to do their best work, wherever they are.</span></span>

<span data-ttu-id="a68e3-107">混合工作者可在以多个位置中进行现场或远程工作。</span><span class="sxs-lookup"><span data-stu-id="a68e3-107">Hybrid workers can work on-site or remotely in a combination of locations.</span></span> <span data-ttu-id="a68e3-108">对于许多组织而言，允许工作者在传统办公室外工作非常重要，这有助于:</span><span class="sxs-lookup"><span data-stu-id="a68e3-108">Allowing workers to work away from a traditional office is important for many organizations to:</span></span>

- <span data-ttu-id="a68e3-109">聘用和保留不愿意移动位置或需要灵活工作环境的工作者。</span><span class="sxs-lookup"><span data-stu-id="a68e3-109">Hire and retain workers who are unwilling to relocate or require a flexible work environment.</span></span>
- <span data-ttu-id="a68e3-110">减少工作者通勤，让他们有更多时间实现高效工作并在工作外参与减压活动。</span><span class="sxs-lookup"><span data-stu-id="a68e3-110">Reduce worker commuting, leaving workers with more time to be productive and for stress-reducing activities outside of work.</span></span>
- <span data-ttu-id="a68e3-111">节省办公空间。</span><span class="sxs-lookup"><span data-stu-id="a68e3-111">Save on office space.</span></span>

<span data-ttu-id="a68e3-112">Microsoft 365 具有助力混合工作者现场或远程工作的功能。</span><span class="sxs-lookup"><span data-stu-id="a68e3-112">Microsoft 365 has the capabilities to empower your hybrid workers to work either on-site or remotely.</span></span>

![使用 Microsoft 365 助力混合工作者](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

> [!NOTE]
> <span data-ttu-id="a68e3-114">如果你第一次使用 Microsoft 365，请参阅 [的](https://www.microsoft.com/microsoft-365)。</span><span class="sxs-lookup"><span data-stu-id="a68e3-114">If you are new to Microsoft 365, see [these resources](https://www.microsoft.com/microsoft-365).</span></span>

<span data-ttu-id="a68e3-115">观看此视频以简要了解部署流程。</span><span class="sxs-lookup"><span data-stu-id="a68e3-115">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

<span data-ttu-id="a68e3-116">对于管理现场和基于云的基础结构以提高混合工作者的生产力的 IT 专业人员，此解决方案提供了以下关键功能:</span><span class="sxs-lookup"><span data-stu-id="a68e3-116">For IT professionals managing onsite and cloud-based infrastructure to enable hybrid worker productivity, this solution provides these key capabilities:</span></span>

- <span data-ttu-id="a68e3-117">已连接</span><span class="sxs-lookup"><span data-stu-id="a68e3-117">Connected</span></span>

  <span data-ttu-id="a68e3-118">工作者能够随时随地访问:</span><span class="sxs-lookup"><span data-stu-id="a68e3-118">From anywhere in the world and at any time, your workers are able to access:</span></span>

  - <span data-ttu-id="a68e3-119">Microsoft 365 订阅中基于云的服务和数据。</span><span class="sxs-lookup"><span data-stu-id="a68e3-119">Cloud-based services and data in your Microsoft 365 subscription.</span></span>

  - <span data-ttu-id="a68e3-120">组织资源，例如由本地应用程序数据中心提供的资源。</span><span class="sxs-lookup"><span data-stu-id="a68e3-120">Organization resources, such those offered by on-premises application datacenters.</span></span>

- <span data-ttu-id="a68e3-121">安全</span><span class="sxs-lookup"><span data-stu-id="a68e3-121">Secure</span></span>

  <span data-ttu-id="a68e3-122">使用 Microsoft 365 和 Windows 10 的多重身份验证 (MFA) 和内置安全功能来保护登录，防止恶意软件、恶意攻击和数据丢失。</span><span class="sxs-lookup"><span data-stu-id="a68e3-122">Sign-ins are secured with multi-factor authentication (MFA) and built-in security features of Microsoft 365 and Windows 10 protect against malware, malicious attacks, and data loss.</span></span>

- <span data-ttu-id="a68e3-123">托管</span><span class="sxs-lookup"><span data-stu-id="a68e3-123">Managed</span></span>

  <span data-ttu-id="a68e3-124">可以使用安全设置和允许的应用从云中管理混合工作者的设备，并要求其符合系统运行状况。</span><span class="sxs-lookup"><span data-stu-id="a68e3-124">Your hybrid worker's devices can be managed from the cloud with security settings, allowed apps, and to require compliance with system health.</span></span>

- <span data-ttu-id="a68e3-125">协作高效</span><span class="sxs-lookup"><span data-stu-id="a68e3-125">Collaborative and productive</span></span>

  <span data-ttu-id="a68e3-126">混合工作者可以以高度协作的方式和本地一样高效工作，方式如下:</span><span class="sxs-lookup"><span data-stu-id="a68e3-126">Your hybrid workers can be as productive as on-premises in a highly collaborative way with:</span></span>

  - <span data-ttu-id="a68e3-127">通过 Teams 进行的联机会议和聊天会话。</span><span class="sxs-lookup"><span data-stu-id="a68e3-127">Online meetings and chat sessions with Teams.</span></span>

  - <span data-ttu-id="a68e3-128">基于云的文件存储的共享工作区，可通过 SharePoint 和 OneDrive 实现全球可访问性和实时协作。</span><span class="sxs-lookup"><span data-stu-id="a68e3-128">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration with SharePoint and OneDrive.</span></span>

  - <span data-ttu-id="a68e3-129">用于划分工作并完成任务的共享任务和工作流。</span><span class="sxs-lookup"><span data-stu-id="a68e3-129">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="a68e3-130">为获得无缝登录体验，应将本地 Active Directory 域服务 (AD DS) 用户帐户与 Azure Active Directory (Azure AD) 同步。</span><span class="sxs-lookup"><span data-stu-id="a68e3-130">For a seamless sign-in experience, your on-premises Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a68e3-131">若要保护 Windows 10 设备，应在 Intune 中对其进行注册。</span><span class="sxs-lookup"><span data-stu-id="a68e3-131">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="a68e3-132">下面是基础结构的高级视图。</span><span class="sxs-lookup"><span data-stu-id="a68e3-132">Here is a high-level view of the infrastructure.</span></span>

![面向使用 Microsoft 365 的混合工作者的基本基础结构](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

<span data-ttu-id="a68e3-134">要为混合工作者启用 Microsoft 365 的功能，请使用以下 Microsoft 365 功能。</span><span class="sxs-lookup"><span data-stu-id="a68e3-134">To enable the capabilities of Microsoft 365 for your hybrid workers, use these Microsoft 365 features.</span></span>

| <span data-ttu-id="a68e3-135">功能或特性</span><span class="sxs-lookup"><span data-stu-id="a68e3-135">Capability or feature</span></span> | <span data-ttu-id="a68e3-136">说明</span><span class="sxs-lookup"><span data-stu-id="a68e3-136">Description</span></span> | <span data-ttu-id="a68e3-137">许可</span><span class="sxs-lookup"><span data-stu-id="a68e3-137">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="a68e3-138">通过安全性默认设置强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="a68e3-138">MFA enforced with security defaults</span></span>   | <span data-ttu-id="a68e3-139">通过请求第二种形式的登录身份验证，抵御遭到入侵的身份和设备的威胁。安全性默认设置要求对所有用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="a68e3-139">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="a68e3-140">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a68e3-140">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="a68e3-141">通过条件访问强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="a68e3-141">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="a68e3-142">要求基于使用条件访问策略的登录的属性进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="a68e3-142">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="a68e3-143">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a68e3-143">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="a68e3-144">通过基于风险的条件访问强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="a68e3-144">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="a68e3-145">需要基于使用 Microsoft Defender for Identity 的用户登录的风险进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="a68e3-145">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="a68e3-146">Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可）</span><span class="sxs-lookup"><span data-stu-id="a68e3-146">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> |
| <span data-ttu-id="a68e3-147">自助服务密码重置 (SSPR)</span><span class="sxs-lookup"><span data-stu-id="a68e3-147">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="a68e3-148">允许用户重置或解锁其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="a68e3-148">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="a68e3-149">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a68e3-149">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="a68e3-150">Azure AD 应用程序代理</span><span class="sxs-lookup"><span data-stu-id="a68e3-150">Azure AD Application Proxy</span></span>    | <span data-ttu-id="a68e3-151">为 Intranet 服务器上托管的基于 Web 的应用程序提供安全的远程访问权限。</span><span class="sxs-lookup"><span data-stu-id="a68e3-151">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="a68e3-152">需要单独的付费 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="a68e3-152">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="a68e3-153">配置点到站点 VPN</span><span class="sxs-lookup"><span data-stu-id="a68e3-153">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="a68e3-154">通过 Azure 虚拟网络创建从远程工作者的设备到 intranet 的安全连接。</span><span class="sxs-lookup"><span data-stu-id="a68e3-154">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="a68e3-155">需要单独的付费 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="a68e3-155">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="a68e3-156">Windows 虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="a68e3-156">Windows Virtual Desktop</span></span>   | <span data-ttu-id="a68e3-157">支持只能将其个人和非托管设备与在 Azure 中运行的虚拟桌面配合使用的远程工作者。</span><span class="sxs-lookup"><span data-stu-id="a68e3-157">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="a68e3-158">需要单独的付费 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="a68e3-158">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="a68e3-159">远程桌面服务 (RDS)</span><span class="sxs-lookup"><span data-stu-id="a68e3-159">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="a68e3-160">允许员工通过 Intranet 连接到基于 Windows 的计算机。</span><span class="sxs-lookup"><span data-stu-id="a68e3-160">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="a68e3-161">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a68e3-161">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="a68e3-162">远程桌面服务网关</span><span class="sxs-lookup"><span data-stu-id="a68e3-162">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="a68e3-163">加密通信，防止 RDS 主机直接向 Internet 公开。</span><span class="sxs-lookup"><span data-stu-id="a68e3-163">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="a68e3-164">需要单独的 Windows Server 许可证</span><span class="sxs-lookup"><span data-stu-id="a68e3-164">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="a68e3-165">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a68e3-165">Microsoft Intune</span></span> | <span data-ttu-id="a68e3-166">管理设备和应用程序。</span><span class="sxs-lookup"><span data-stu-id="a68e3-166">Manage devices and applications.</span></span>   | <span data-ttu-id="a68e3-167">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a68e3-167">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="a68e3-168">内容和功能，</span><span class="sxs-lookup"><span data-stu-id="a68e3-168">Configuration Manager</span></span> | <span data-ttu-id="a68e3-169">管理设备上的软件安装、更新和设置</span><span class="sxs-lookup"><span data-stu-id="a68e3-169">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="a68e3-170">需要单独的 Configuration Manager 许可证</span><span class="sxs-lookup"><span data-stu-id="a68e3-170">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="a68e3-171">桌面分析</span><span class="sxs-lookup"><span data-stu-id="a68e3-171">Desktop Analytics</span></span> | <span data-ttu-id="a68e3-172">确定你的 Windows 客户端的更新准备情况。</span><span class="sxs-lookup"><span data-stu-id="a68e3-172">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="a68e3-173">需要单独的 Configuration Manager 许可证</span><span class="sxs-lookup"><span data-stu-id="a68e3-173">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="a68e3-174">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="a68e3-174">Windows Autopilot</span></span> | <span data-ttu-id="a68e3-175">设置和预配置新的 Windows 10 设备，以便高效使用。</span><span class="sxs-lookup"><span data-stu-id="a68e3-175">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="a68e3-176">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a68e3-176">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="a68e3-177">Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 应用版、Microsoft Power Platform、Yammer</span><span class="sxs-lookup"><span data-stu-id="a68e3-177">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, and Yammer</span></span> | <span data-ttu-id="a68e3-178">创建、沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="a68e3-178">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="a68e3-179">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="a68e3-179">Microsoft 365 E3 or E5</span></span> |
||||

<span data-ttu-id="a68e3-180">有关安全和合规性条件，请参阅[针对远程工作者的部署安全性与合规性](empower-people-to-work-remotely-security-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="a68e3-180">For security and compliance criteria, see [Deploy security and compliance for remote workers](empower-people-to-work-remotely-security-compliance.md).</span></span>

<a name="poster"></a> <span data-ttu-id="a68e3-181">有关此解决方案的两页摘要，请参阅 [“助力混合工作者”海报](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)。</span><span class="sxs-lookup"><span data-stu-id="a68e3-181">For a 2-page summary of this solution, see the [Empower hybrid workers poster](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf).</span></span>

<span data-ttu-id="a68e3-182">[![“助力混合工作者”海报](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)</span><span class="sxs-lookup"><span data-stu-id="a68e3-182">[![Empower hybrid workers poster](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)</span></span>

<span data-ttu-id="a68e3-183">你还可以以 [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx) 格式下载海报，并将其打印在信件、法律文件或小报(11 x 17)大小的纸张上。</span><span class="sxs-lookup"><span data-stu-id="a68e3-183">You can also download this poster in [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="provide-hybrid-working-for-all-of-your-workers"></a><span data-ttu-id="a68e3-184">为所有工作者提供混合工作</span><span class="sxs-lookup"><span data-stu-id="a68e3-184">Provide hybrid working for all of your workers</span></span>

<span data-ttu-id="a68e3-185">使用以下设备，你可以使所有工作者随时随地保持生产力：</span><span class="sxs-lookup"><span data-stu-id="a68e3-185">You can enable all of your workers to stay productive from anywhere with these devices:</span></span>

- <span data-ttu-id="a68e3-186">一个新式设备，例如 Surface laptop 和 Windows 10，具备通过网页直接访问 Microsoft 365 云应用和服务的功能、安全性和性能。</span><span class="sxs-lookup"><span data-stu-id="a68e3-186">A modern device, such as a Surface laptop and Windows 10, which has the features, security, and performance to access Microsoft 365 cloud apps and services directly over the web.</span></span>

- <span data-ttu-id="a68e3-187">包括旧式家用笔记本电脑或台式机在内的任何设备，可通过快速部署的[基于 Windows 10 的虚拟桌面](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices)间接访问 Microsoft 365 云应用和服务。</span><span class="sxs-lookup"><span data-stu-id="a68e3-187">Any device including older laptops or desktops used from home, which can access Microsoft 365 cloud apps and services indirectly through a quickly deployed [Windows 10-based virtual desktop](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices).</span></span> <span data-ttu-id="a68e3-188">该选项能提高性能、增强安全性并简化 IT 管理。</span><span class="sxs-lookup"><span data-stu-id="a68e3-188">This option provides high performance, strong security, and simplified IT management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a68e3-189">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a68e3-189">Next steps</span></span>

<span data-ttu-id="a68e3-190">按照以下步骤保护并优化对组织的服务器和云服务的访问权限，并最大化混合工作者的生产力。</span><span class="sxs-lookup"><span data-stu-id="a68e3-190">Use these steps to secure and optimize access to your organization's servers and cloud services and maximize your hybrid worker's productivity.</span></span>

1. [<span data-ttu-id="a68e3-191">借助 MFA 提升登录安全性</span><span class="sxs-lookup"><span data-stu-id="a68e3-191">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="a68e3-192">提供对本地应用和服务的远程访问权限</span><span class="sxs-lookup"><span data-stu-id="a68e3-192">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="a68e3-193">部署安全与合规服务</span><span class="sxs-lookup"><span data-stu-id="a68e3-193">Deploy security and compliance services</span></span>](empower-people-to-work-remotely-security-compliance.md)
4. [<span data-ttu-id="a68e3-194">部署设备、电脑和其他终结点的终结点管理</span><span class="sxs-lookup"><span data-stu-id="a68e3-194">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
5. [<span data-ttu-id="a68e3-195">部署混合工作者生产力应用和服务</span><span class="sxs-lookup"><span data-stu-id="a68e3-195">Deploy hybrid worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [<span data-ttu-id="a68e3-196">培训员工并处理使用情况反馈</span><span class="sxs-lookup"><span data-stu-id="a68e3-196">Train your workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

<span data-ttu-id="a68e3-197">[![设置使用 Microsoft 365 实现混合工作的基础结构的步骤](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="a68e3-197">[![The steps to set up your infrastructure for hybrid work with Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)</span></span>

<span data-ttu-id="a68e3-198">要了解虚构但具代表性的跨国组织如何为混合工作设置其基础设施，请参阅[Contoso 的 COVID-19 响应措施及混合工作的基础设施](contoso-remote-onsite-work.md)。</span><span class="sxs-lookup"><span data-stu-id="a68e3-198">To see how a fictional but representative multi-national organization set up its infrastructure for hybrid work, see [Contoso's COVID-19 response and infrastructure for hybrid work](contoso-remote-onsite-work.md).</span></span>
