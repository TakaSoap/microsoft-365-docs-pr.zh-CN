---
title: 从 Microsoft 365 商业版迁移到 Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 了解如何将业务从Microsoft 365 商业高级版移动到Microsoft 365 E3。
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227611"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="7c899-103">从 Microsoft 365 商业高级版迁移到 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="7c899-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="7c899-104">Microsoft 365 商业高级版你的小型企业所需的一切，将一流的基于云的生产力应用与简单的设备管理和安全性相结合，使员工能够最好地完成自己的工作。</span><span class="sxs-lookup"><span data-stu-id="7c899-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="7c899-105">但是，在某些情况下，可能需要将你的 Microsoft 365 商业高级版 订阅迁移到Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="7c899-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span>

<span data-ttu-id="7c899-106">例如，你的业务已增长，并且需要 300 (许可证，这一点) 。</span><span class="sxs-lookup"><span data-stu-id="7c899-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="7c899-107">或者，您的业务需要企业功能，如 Microsoft 365 企业应用版、Windows 10 企业版 E3 或 Enterprise 客户端访问许可证 (CAL) 。</span><span class="sxs-lookup"><span data-stu-id="7c899-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="7c899-108">升级非常简单：可以从管理中心 [开始升级](../commerce/subscriptions/upgrade-to-different-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="7c899-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="7c899-109">将保留当前订阅中所有数据和配置。</span><span class="sxs-lookup"><span data-stu-id="7c899-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="7c899-110">除了利用新功能之外，您不执行任何操作来准备迁移，之后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="7c899-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

> [!NOTE]
> <span data-ttu-id="7c899-111">您还可以使用最多 300 个席位的 Microsoft 365 商业高级版 订阅，并获取超过 300 Microsoft 365 E3的订阅。</span><span class="sxs-lookup"><span data-stu-id="7c899-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="7c899-112">但是，Microsoft Defender for Office 365不包含在 Microsoft 365 E3 中。</span><span class="sxs-lookup"><span data-stu-id="7c899-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="7c899-113">为了持续进行威胁防护，你应该添加其他 Defender for Office 365 许可证，以便你的 Defender for Office 365 范围内的所有用户都获得许可。</span><span class="sxs-lookup"><span data-stu-id="7c899-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="7c899-114">Microsoft 365 商业高级版和Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="7c899-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7c899-115">此表显示了 Microsoft 365 商业高级版 和 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="7c899-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="7c899-116">功能</span><span class="sxs-lookup"><span data-stu-id="7c899-116">Feature</span></span>    | <span data-ttu-id="7c899-117">支持Microsoft 365 商业高级版</span><span class="sxs-lookup"><span data-stu-id="7c899-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="7c899-118">支持Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="7c899-118">Support in Microsoft 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="7c899-119">**本地**</span><span class="sxs-lookup"><span data-stu-id="7c899-119">**On-premises**</span></span>        | | |
| <span data-ttu-id="7c899-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c899-120">Windows 10</span></span>    | <span data-ttu-id="7c899-121">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="7c899-121">Windows 10 Business</span></span>  |     <span data-ttu-id="7c899-122">Windows 10 企业版E3</span><span class="sxs-lookup"><span data-stu-id="7c899-122">Windows 10 Enterprise E3</span></span>|
| <span data-ttu-id="7c899-123">Office应用\*</span><span class="sxs-lookup"><span data-stu-id="7c899-123">Office apps\*</span></span>    | [<span data-ttu-id="7c899-124">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="7c899-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="7c899-125">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="7c899-125">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="7c899-126">**云生产力应用**</span><span class="sxs-lookup"><span data-stu-id="7c899-126">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="7c899-127">Exchange Online 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="7c899-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="7c899-128">每个邮箱 50 GB 存储限制和无限制Exchange Online存档</span><span class="sxs-lookup"><span data-stu-id="7c899-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="7c899-129">每个邮箱 100 GB 存储限制和无限制Exchange Online存档</span><span class="sxs-lookup"><span data-stu-id="7c899-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> |
| <span data-ttu-id="7c899-130">Teams</span><span class="sxs-lookup"><span data-stu-id="7c899-130">Teams</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7c899-133">OneDrive for Business</span></span>    | <span data-ttu-id="7c899-134">每个用户 1 TB 存储限制</span><span class="sxs-lookup"><span data-stu-id="7c899-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="7c899-135">无限制</span><span class="sxs-lookup"><span data-stu-id="7c899-135">Unlimited</span></span> |
| <span data-ttu-id="7c899-136">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="7c899-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-139">**威胁防护**</span><span class="sxs-lookup"><span data-stu-id="7c899-139">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="7c899-140">攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="7c899-140">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="7c899-141">查看此列表</span><span class="sxs-lookup"><span data-stu-id="7c899-141">See this list</span></span>](#threat-protection) | <span data-ttu-id="7c899-142">Enterprise基于硬件的隔离的管理Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7c899-142">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> |
| <span data-ttu-id="7c899-143">Defender for Office 365 计划 1</span><span class="sxs-lookup"><span data-stu-id="7c899-143">Defender for Office 365 Plan 1</span></span> | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | <span data-ttu-id="7c899-145">不包含，但可添加到</span><span class="sxs-lookup"><span data-stu-id="7c899-145">Not included, but can be added on</span></span> |
| <span data-ttu-id="7c899-146">**身份管理**</span><span class="sxs-lookup"><span data-stu-id="7c899-146">**Identity management**</span></span>        | | |
| <span data-ttu-id="7c899-147">Azure AD) 帐户的混合 Azure Active Directory (自助服务密码重置、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回</span><span class="sxs-lookup"><span data-stu-id="7c899-147">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-150">Cloud App Discovery， Azure AD 连接 Health</span><span class="sxs-lookup"><span data-stu-id="7c899-150">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-152">Azure AD Office 365 应用 单一Sign-On (SSO) ：每个用户 10 个应用 (库 SaaS 应用，如 Salesforce) \*</span><span class="sxs-lookup"><span data-stu-id="7c899-152">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-155">Azure AD Premium 1 个 SSO： (Azure AD 应用程序代理和非库应用使用 Azure AD 应用程序集成模板Self-Service本地应用) </span><span class="sxs-lookup"><span data-stu-id="7c899-155">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-157">**设备和应用管理**</span><span class="sxs-lookup"><span data-stu-id="7c899-157">**Device and app management**</span></span>        | | |
| <span data-ttu-id="7c899-158">Microsoft Intune、Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7c899-158">Microsoft Intune, Windows Autopilot</span></span>|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="7c899-161">虚拟桌面访问 (VDA) </span><span class="sxs-lookup"><span data-stu-id="7c899-161">Virtual Desktop Access (VDA)</span></span>    |  |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="7c899-163">Windows虚拟桌面 (WVD) </span><span class="sxs-lookup"><span data-stu-id="7c899-163">Windows Virtual Desktop (WVD)</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png) |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="7c899-166">共享计算机激活 (SCA) </span><span class="sxs-lookup"><span data-stu-id="7c899-166">Shared Computer Activation (SCA)</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png) |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-169">Microsoft 桌面优化程序包</span><span class="sxs-lookup"><span data-stu-id="7c899-169">Microsoft Desktop Optimization Package</span></span>    | |     ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-171">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="7c899-171">**Information protection**</span></span>        | | |
| <span data-ttu-id="7c899-172">Office 365数据丢失防护、Azure 信息保护计划 1</span><span class="sxs-lookup"><span data-stu-id="7c899-172">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-175">终结点 DLP 的窗口信息保护</span><span class="sxs-lookup"><span data-stu-id="7c899-175">Window Information Protection for endpoint DLP</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-178">**客户端访问许可证 (CAL 权限)**</span><span class="sxs-lookup"><span data-stu-id="7c899-178">**Client Access License (CAL rights)**</span></span>    | | |
| <span data-ttu-id="7c899-179">EnterpriseCAL Suite (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows Rights Management) </span><span class="sxs-lookup"><span data-stu-id="7c899-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-181">**合规性**</span><span class="sxs-lookup"><span data-stu-id="7c899-181">**Compliance**</span></span>        | | |
| <span data-ttu-id="7c899-182">无限制电子邮件存档</span><span class="sxs-lookup"><span data-stu-id="7c899-182">Unlimited email archiving</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-185">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="7c899-185">Compliance Manager</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-188">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="7c899-188">eDiscovery</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-191">就地保留和诉讼保留</span><span class="sxs-lookup"><span data-stu-id="7c899-191">In-place hold and litigation hold</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="7c899-194">邮件传递记录管理 (MRM) 保留标记和保留策略</span><span class="sxs-lookup"><span data-stu-id="7c899-194">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在Microsoft 365 E3](../media/check-mark.png) |
||||

<span data-ttu-id="7c899-197">\* 已分配 SaaS 应用访问权限的用户可以获取最多 10 个应用的 SSO 访问权限。</span><span class="sxs-lookup"><span data-stu-id="7c899-197">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="7c899-198">管理员可以配置 SSO 并更改用户对不同 SaaS 应用的访问权限，但每次每个用户只能访问 10 个应用。</span><span class="sxs-lookup"><span data-stu-id="7c899-198">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="7c899-199">所有Office 365应用都计为单个应用。</span><span class="sxs-lookup"><span data-stu-id="7c899-199">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="7c899-200">迁移</span><span class="sxs-lookup"><span data-stu-id="7c899-200">Migration</span></span>

<span data-ttu-id="7c899-201">若要迁移，请与合作伙伴合作，将你的 Microsoft 365 商业高级版 订阅和许可证移动到Microsoft 365 E3许可证的合适订阅。</span><span class="sxs-lookup"><span data-stu-id="7c899-201">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="7c899-202">以下各节介绍您需要进行哪些更改（如果有）以及您可以在迁移后执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="7c899-202">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="7c899-203">Microsoft 365订阅配置和数据</span><span class="sxs-lookup"><span data-stu-id="7c899-203">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="7c899-204">在迁移之前，无需对当前订阅或数据做出任何更改，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7c899-204">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="7c899-205">订阅配置，例如 DNS 域名。</span><span class="sxs-lookup"><span data-stu-id="7c899-205">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="7c899-206">用户和组帐户以及身份验证设置，如多重身份验证或条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="7c899-206">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="7c899-207">生产力服务配置及其数据，例如Teams、Exchange Online邮箱、SharePoint Online 网站、OneDrive for Business文件夹OneNote笔记本。</span><span class="sxs-lookup"><span data-stu-id="7c899-207">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="7c899-208">现在，用户可以在邮箱和文件夹中Exchange Online无限制OneDrive for Business存储空间。</span><span class="sxs-lookup"><span data-stu-id="7c899-208">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="7c899-209">你可以开始对 10 多个应用使用 Cloud App Discovery、Azure AD 连接 Health 和 SSO。</span><span class="sxs-lookup"><span data-stu-id="7c899-209">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="7c899-210">威胁防护</span><span class="sxs-lookup"><span data-stu-id="7c899-210">Threat protection</span></span>

<span data-ttu-id="7c899-211">Windows 10 商业版包括以下保护：</span><span class="sxs-lookup"><span data-stu-id="7c899-211">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="7c899-212">操作系统启动过程的完整性强制</span><span class="sxs-lookup"><span data-stu-id="7c899-212">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="7c899-213">敏感操作组件的完整性实施</span><span class="sxs-lookup"><span data-stu-id="7c899-213">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="7c899-214">高级漏洞和零日攻击缓解</span><span class="sxs-lookup"><span data-stu-id="7c899-214">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="7c899-215">针对 Microsoft Edge、Internet Explorer 和 Chrome 的基于信誉的网络保护</span><span class="sxs-lookup"><span data-stu-id="7c899-215">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="7c899-216">基于主机的防火墙</span><span class="sxs-lookup"><span data-stu-id="7c899-216">Host-based firewall</span></span>
- <span data-ttu-id="7c899-217">勒索软件缓解</span><span class="sxs-lookup"><span data-stu-id="7c899-217">Ransomware mitigations</span></span>
- <span data-ttu-id="7c899-218">基于硬件的隔离Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7c899-218">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="7c899-219">由智能安全中心控制Graph</span><span class="sxs-lookup"><span data-stu-id="7c899-219">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="7c899-220">USB (设备) </span><span class="sxs-lookup"><span data-stu-id="7c899-220">Device control (USB)</span></span>
- <span data-ttu-id="7c899-221">针对基于 Web 的威胁的网络保护</span><span class="sxs-lookup"><span data-stu-id="7c899-221">Network protection for web-based threats</span></span>
- <span data-ttu-id="7c899-222">主机入侵防护规则</span><span class="sxs-lookup"><span data-stu-id="7c899-222">Host intrusion prevention rules</span></span>

<span data-ttu-id="7c899-223">Windows 10 企业版E3 还包括企业对基于硬件的隔离进行企业Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="7c899-223">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="7c899-224">迁移到 Microsoft 365 E3 用户都需要 Microsoft Defender for Office 365 许可证，才能持续进行威胁防护。</span><span class="sxs-lookup"><span data-stu-id="7c899-224">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="7c899-225">请务必购买其他 Defender for Office 365 许可证，以便你的 Defender for Office 365 范围内的所有用户都获得许可。</span><span class="sxs-lookup"><span data-stu-id="7c899-225">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>

### <a name="device-management-with-intune"></a><span data-ttu-id="7c899-226">使用 Intune 进行设备管理</span><span class="sxs-lookup"><span data-stu-id="7c899-226">Device management with Intune</span></span>

<span data-ttu-id="7c899-227">在迁移之前，无需对当前的 Intune 配置做出任何更改，其中包括已注册的设备以及设备和应用设置。</span><span class="sxs-lookup"><span data-stu-id="7c899-227">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="7c899-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="7c899-228">Windows 10</span></span>

<span data-ttu-id="7c899-229">Microsoft 365 商业高级版包括Windows 10 商业版，你可以将其与 AutoPilot Windows一起安装。</span><span class="sxs-lookup"><span data-stu-id="7c899-229">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="7c899-230">迁移到 Microsoft 365 E3 时，每个用户许可证Windows 10 企业版 E3，也可以随 Autopilot Windows E3。</span><span class="sxs-lookup"><span data-stu-id="7c899-230">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="7c899-231">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="7c899-231">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="7c899-232">设备上Microsoft 365 商业应用版的客户端将自动开始使用 Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="7c899-232">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="7c899-233">迁移后，你现在可以使用：</span><span class="sxs-lookup"><span data-stu-id="7c899-233">After migration, you can now use:</span></span>

- <span data-ttu-id="7c899-234">组策略支持</span><span class="sxs-lookup"><span data-stu-id="7c899-234">Group Policy support</span></span>
- <span data-ttu-id="7c899-235">电子表格比较和查询</span><span class="sxs-lookup"><span data-stu-id="7c899-235">Spreadsheet compare and inquire</span></span>
- <span data-ttu-id="7c899-236">商业智能</span><span class="sxs-lookup"><span data-stu-id="7c899-236">Business intelligence</span></span>
