---
title: 使用 Microsoft 365 为远程工作者提供强大帮助
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 配置安全和服务基础结构，使你的员工能够随时随地进行远程工作。
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560456"
---
# <a name="empower-remote-workers-with-microsoft-365"></a><span data-ttu-id="c3aa2-103">使用 Microsoft 365 为远程工作者提供强大帮助</span><span class="sxs-lookup"><span data-stu-id="c3aa2-103">Empower remote workers with Microsoft 365</span></span>

<span data-ttu-id="c3aa2-104">企业可能需要让员工能够从家中安全地访问组织的本地和基于云的信息、工具和资源。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-104">Your business may need to enable your workers to have secure access to your organization's on-premises and cloud-based information, tools, and resources from their homes.</span></span> <span data-ttu-id="c3aa2-105">对于许多组织而言，允许员工在离开办公室时无缝、安全地工作非常重要，这有助于：</span><span class="sxs-lookup"><span data-stu-id="c3aa2-105">Allowing workers to work away from the office seamlessly and securely is important for many organizations to:</span></span>

- <span data-ttu-id="c3aa2-106">节省办公空间。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-106">Save on office space.</span></span>
- <span data-ttu-id="c3aa2-107">聘用并留住不愿意调动的员工。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-107">Hire and retain workers who are unwilling to relocate.</span></span>
- <span data-ttu-id="c3aa2-108">减少员工通勤，让他们有更多的时间来提高工作效率并在工作之外进行减压活动。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-108">Reduce worker commuting, leaving them with more time to be productive and for stress-reducing activities outside of work.</span></span>

<span data-ttu-id="c3aa2-109">远程工作（也称为远程办公）可以涵盖以下对象：</span><span class="sxs-lookup"><span data-stu-id="c3aa2-109">Remote working, also known as teleworking, can span a spectrum that includes:</span></span>

- <span data-ttu-id="c3aa2-110">偶尔离开办公室参加会议或客户会议的员工。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-110">workers that are occasionally away from the office for conferences or client meetings.</span></span>
- <span data-ttu-id="c3aa2-111">一些远程工作的全职员工。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-111">Some workers that work remotely full-time.</span></span>
- <span data-ttu-id="c3aa2-112">没有办公室且所有员工均为远程员工的完全远程运作的组织。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-112">A fully remote organization in which there is no office and all workers are remote.</span></span>

<span data-ttu-id="c3aa2-113">远程员工必须能够随时随地访问：</span><span class="sxs-lookup"><span data-stu-id="c3aa2-113">From anywhere in the world and at any time, remote workers must be able to access:</span></span>

- <span data-ttu-id="c3aa2-114">组织资源，例如由本地应用程序数据中心提供的资源。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-114">Organization resources, such those offered by on-premises application datacenters.</span></span>
- <span data-ttu-id="c3aa2-115">Microsoft 365 订阅中基于云的服务和数据，如 Teams、Exchange Online、SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-115">Cloud-based services and data in your Microsoft 365 subscription, such as Teams, Exchange Online, SharePoint, and OneDrive.</span></span>

<span data-ttu-id="c3aa2-116">为获得无缝登录体验，应将 Active Directory 域服务 (AD DS) 用户帐户与 Azure Active Directory (Azure AD) 同步。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-116">For a seamless sign-in experience, your Active Directory Domain Services (AD DS) user accounts should be synchronized with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c3aa2-117">若要保护 Windows 10 设备，应在 Intune 中对其进行注册。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-117">To protect your Windows 10 devices, they should be enrolled in Intune.</span></span> <span data-ttu-id="c3aa2-118">下面是基础结构的高级视图。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-118">Here is a high-level view of the infrastructure.</span></span>

![面向使用 Microsoft 365 的远程工作者的基本基础结构](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


<span data-ttu-id="c3aa2-120">为了支持远程工作者（例如，为了应对 COVID-19 危机），Microsoft 365 中的功能组合可使远程工作者采用高度协作的方式开展工作，例如：</span><span class="sxs-lookup"><span data-stu-id="c3aa2-120">To support remote workers, for example in response to the COVID-19 crisis, a combination of features in Microsoft 365 enables your remote workers in a highly collaborative way, such as:</span></span>

- <span data-ttu-id="c3aa2-121">在线会议和聊天会话。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-121">Online meetings and chat sessions.</span></span>
- <span data-ttu-id="c3aa2-122">基于云的文件存储的共享工作区，可实现全球可访问性和实时协作。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-122">Shared workspaces for cloud-based file storage with global accessibility and real-time collaboration.</span></span>
- <span data-ttu-id="c3aa2-123">用于划分工作并完成任务的共享任务和工作流。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-123">Shared tasks and workflows to divide up the work and get things done.</span></span>

<span data-ttu-id="c3aa2-124">为实现强大的安全性，Microsoft 365 包括：</span><span class="sxs-lookup"><span data-stu-id="c3aa2-124">For strong security, Microsoft 365 includes:</span></span>

- <span data-ttu-id="c3aa2-125">强制实施的身份验证要求，用于检测和响应高风险的登录，以及阻止所选应用和不合规的设备。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-125">Enforced authentication requirements, detecting and responding to high-risk sign-ins, and blocking selected apps and non-compliant devices.</span></span>
- <span data-ttu-id="c3aa2-126">在云中加密的连接和数字资产。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-126">Encrypted connections and digital assets in the cloud.</span></span>
- <span data-ttu-id="c3aa2-127">用于定义谁可以对文件执行哪些操作的权限。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-127">Permissions to define who can do what with files.</span></span>
- <span data-ttu-id="c3aa2-128">保护 Windows 10 设备的全面安全功能。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-128">Comprehensive security features to protect Windows 10 devices.</span></span>

<span data-ttu-id="c3aa2-129">若要满足针对远程工作者的这些条件，请使用以下 Microsoft 365 功能和特性。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-129">To meet these criteria for remote workers, use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="c3aa2-130">功能或特性</span><span class="sxs-lookup"><span data-stu-id="c3aa2-130">Capability or feature</span></span> | <span data-ttu-id="c3aa2-131">说明</span><span class="sxs-lookup"><span data-stu-id="c3aa2-131">Description</span></span> | <span data-ttu-id="c3aa2-132">许可</span><span class="sxs-lookup"><span data-stu-id="c3aa2-132">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="c3aa2-133">通过安全性默认设置强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="c3aa2-133">MFA enforced with security defaults</span></span>   | <span data-ttu-id="c3aa2-134">通过请求第二种形式的登录身份验证，抵御遭到入侵的身份和设备的威胁。安全性默认设置要求对所有用户帐户进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-134">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="c3aa2-135">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="c3aa2-135">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="c3aa2-136">通过条件访问强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="c3aa2-136">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="c3aa2-137">要求基于使用条件访问策略的登录的属性进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-137">Require MFA based on the properties of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="c3aa2-138">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="c3aa2-138">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="c3aa2-139">通过基于风险的条件访问强制执行 MFA</span><span class="sxs-lookup"><span data-stu-id="c3aa2-139">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="c3aa2-140">需要基于使用 Azure 高级威胁防护的用户登录的风险进行 MFA。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-140">Require MFA based on the risk of the user sign-in with Azure Advanced Threat Protection.</span></span> | <span data-ttu-id="c3aa2-141">Microsoft 365 E5 或 E3（含 Azure AD Premium P2 许可）</span><span class="sxs-lookup"><span data-stu-id="c3aa2-141">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="c3aa2-142">自助服务密码重置 (SSPR)</span><span class="sxs-lookup"><span data-stu-id="c3aa2-142">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="c3aa2-143">允许用户重置或解锁其密码或帐户。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-143">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="c3aa2-144">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="c3aa2-144">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="c3aa2-145">Azure AD 应用程序代理</span><span class="sxs-lookup"><span data-stu-id="c3aa2-145">Azure AD Application Proxy</span></span>    | <span data-ttu-id="c3aa2-146">为 Intranet 服务器上托管的基于 Web 的应用程序提供安全的远程访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-146">Provide secure remote access for web-based applications hosted on intranet servers.</span></span>   | <span data-ttu-id="c3aa2-147">需要单独的付费 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="c3aa2-147">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="c3aa2-148">配置点到站点 VPN</span><span class="sxs-lookup"><span data-stu-id="c3aa2-148">Azure Point-to-Site VPN</span></span>   | <span data-ttu-id="c3aa2-149">通过 Azure 虚拟网络创建从远程工作者的设备到 intranet 的安全连接。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-149">Create a secure connection from a remote worker’s device to your intranet through an Azure virtual network.</span></span>   | <span data-ttu-id="c3aa2-150">需要单独的付费 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="c3aa2-150">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="c3aa2-151">Windows 虚拟桌面</span><span class="sxs-lookup"><span data-stu-id="c3aa2-151">Windows Virtual Desktop</span></span>   | <span data-ttu-id="c3aa2-152">支持只能将其个人和非托管设备与在 Azure 中运行的虚拟桌面配合使用的远程工作者。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-152">Support remote workers who can only use their personal and unmanaged devices with virtual desktops running in Azure.</span></span> | <span data-ttu-id="c3aa2-153">需要单独的付费 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="c3aa2-153">Requires separate paid Azure subscription</span></span> |
| <span data-ttu-id="c3aa2-154">远程桌面服务 (RDS)</span><span class="sxs-lookup"><span data-stu-id="c3aa2-154">Remote Desktop Services (RDS)</span></span> | <span data-ttu-id="c3aa2-155">允许员工通过 Intranet 连接到基于 Windows 的计算机。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-155">Allow employees to connect into Windows-based computers on your intranet.</span></span> | <span data-ttu-id="c3aa2-156">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="c3aa2-156">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="c3aa2-157">远程桌面服务网关</span><span class="sxs-lookup"><span data-stu-id="c3aa2-157">Remote Desktop Services Gateway</span></span>   | <span data-ttu-id="c3aa2-158">加密通信，防止 RDS 主机直接向 Internet 公开。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-158">Encrypt communications and prevent the RDS hosts from being directly exposed to the Internet.</span></span> | <span data-ttu-id="c3aa2-159">需要单独的 Windows Server 许可证</span><span class="sxs-lookup"><span data-stu-id="c3aa2-159">Requires separate Windows Server licenses</span></span> |
| <span data-ttu-id="c3aa2-160">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c3aa2-160">Microsoft Intune</span></span> | <span data-ttu-id="c3aa2-161">管理设备和应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-161">Manage devices and applications.</span></span>   | <span data-ttu-id="c3aa2-162">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="c3aa2-162">Microsoft 365 E3 and E5</span></span> | 
| <span data-ttu-id="c3aa2-163">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c3aa2-163">Configuration Manager</span></span> | <span data-ttu-id="c3aa2-164">管理设备上的软件安装、更新和设置</span><span class="sxs-lookup"><span data-stu-id="c3aa2-164">Manage software installations, updates, and settings on your devices</span></span> | <span data-ttu-id="c3aa2-165">需要单独的 Configuration Manager 许可证</span><span class="sxs-lookup"><span data-stu-id="c3aa2-165">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="c3aa2-166">桌面分析</span><span class="sxs-lookup"><span data-stu-id="c3aa2-166">Desktop Analytics</span></span> | <span data-ttu-id="c3aa2-167">确定你的 Windows 客户端的更新准备情况。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-167">Determine the update readiness of your Windows clients.</span></span>   | <span data-ttu-id="c3aa2-168">需要单独的 Configuration Manager 许可证</span><span class="sxs-lookup"><span data-stu-id="c3aa2-168">Requires separate Configuration Manager licenses</span></span> |
| <span data-ttu-id="c3aa2-169">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="c3aa2-169">Windows Autopilot</span></span> | <span data-ttu-id="c3aa2-170">设置和预配置新的 Windows 10 设备，以便高效使用。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-170">Set up and pre-configure new Windows 10 devices for productive use.</span></span>   | <span data-ttu-id="c3aa2-171">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="c3aa2-171">Microsoft 365 E3 and E5</span></span> |
| <span data-ttu-id="c3aa2-172">Microsoft Teams、Exchange Online、SharePoint Online 和 OneDrive、Microsoft 365 应用版、Microsoft Power Platform、Yammer、Power Apps</span><span class="sxs-lookup"><span data-stu-id="c3aa2-172">Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Microsoft 365 Apps, Microsoft Power Platform, Yammer, Power Apps</span></span> | <span data-ttu-id="c3aa2-173">创建、沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-173">Create, communicate, and collaborate.</span></span> | <span data-ttu-id="c3aa2-174">Microsoft 365 E3 和 E5</span><span class="sxs-lookup"><span data-stu-id="c3aa2-174">Microsoft 365 E3 and E5</span></span> |
||||

<span data-ttu-id="c3aa2-175">使用以下步骤来保护和优化对组织的服务器、数据和云服务的访问，并实现最大的工作效率。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-175">Use these steps to secure and optimize access to your organization's servers, data, and cloud services and enable maximum worker productivity.</span></span>

1. [<span data-ttu-id="c3aa2-176">借助 MFA 提升登录安全性</span><span class="sxs-lookup"><span data-stu-id="c3aa2-176">Increase sign-in security with MFA</span></span>](empower-people-to-work-remotely-secure-sign-in.md)
2. [<span data-ttu-id="c3aa2-177">提供对本地应用和服务的远程访问权限</span><span class="sxs-lookup"><span data-stu-id="c3aa2-177">Provide remote access to on-premises apps and services</span></span>](empower-people-to-work-remotely-remote-access.md)
3. [<span data-ttu-id="c3aa2-178">部署设备、电脑和其他终结点的终结点管理</span><span class="sxs-lookup"><span data-stu-id="c3aa2-178">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>](empower-people-to-work-remotely-manage-endpoints.md)
4. [<span data-ttu-id="c3aa2-179">部署远程工作者生产力应用和服务</span><span class="sxs-lookup"><span data-stu-id="c3aa2-179">Deploy remote worker productivity apps and services</span></span>](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [<span data-ttu-id="c3aa2-180">创建交流平台</span><span class="sxs-lookup"><span data-stu-id="c3aa2-180">Create communication venues</span></span>](empower-people-to-work-remotely-communication-venues.md)
6. [<span data-ttu-id="c3aa2-181">培训远程工作者和处理使用情况反馈</span><span class="sxs-lookup"><span data-stu-id="c3aa2-181">Train remote workers and address usage feedback</span></span>](empower-people-to-work-remotely-train-monitor-usage.md)

![使用 Microsoft 365 为远程工作者提供帮助的步骤](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

<span data-ttu-id="c3aa2-183">有关 Microsoft 提供的关于支持远程工作者的最新信息，请参阅[启用远程工作技术社区网站](https://resources.techcommunity.microsoft.com/enabling-remote-work/)。</span><span class="sxs-lookup"><span data-stu-id="c3aa2-183">For the latest information from Microsoft about supporting remote workers, see the [Enabling remote work Tech Community site](https://resources.techcommunity.microsoft.com/enabling-remote-work/).</span></span>
