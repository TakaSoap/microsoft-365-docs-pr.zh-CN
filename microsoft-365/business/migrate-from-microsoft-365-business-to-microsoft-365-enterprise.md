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
description: 了解如何将你的企业从 Microsoft 365 商业高级版移动到 Microsoft 365 E3。
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126193"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="2b467-103">从 Microsoft 365 商业高级版迁移到 Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="2b467-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="2b467-104">Microsoft 365 商业高级版提供小型企业所需的一切，将一流的基于云的生产力应用与简单的设备管理和安全性相结合，使员工能够尽最大努力。</span><span class="sxs-lookup"><span data-stu-id="2b467-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="2b467-105">但在某些情况下，可能需要将 Microsoft 365 商业高级版订阅迁移到 Microsoft 365 E3。</span><span class="sxs-lookup"><span data-stu-id="2b467-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="2b467-106">例如，你的业务已增长，并且需要超过 300 个许可证 (祝贺你，方式) 。</span><span class="sxs-lookup"><span data-stu-id="2b467-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="2b467-107">或者，你的企业需要企业功能，如 Microsoft 365 企业应用版、Windows 10 企业版 E3 或企业客户端访问许可证 (CAL) 。</span><span class="sxs-lookup"><span data-stu-id="2b467-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="2b467-108">升级非常简单：可以从管理中心 [开始升级](../commerce/subscriptions/upgrade-to-different-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="2b467-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="2b467-109">将保留当前订阅中所有数据和配置。</span><span class="sxs-lookup"><span data-stu-id="2b467-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="2b467-110">除了利用新功能之外，您没有任何准备来准备迁移，之后不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="2b467-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="2b467-111">您还可以使用最多 300 个席位的 Microsoft 365 商业高级版订阅，并获取超过 300 个席位的 Microsoft 365 E3 订阅。</span><span class="sxs-lookup"><span data-stu-id="2b467-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="2b467-112">但是，Microsoft 365 E3 不包含 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b467-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="2b467-113">若要持续进行威胁防护，应添加其他适用于 Office 365 的 Defender 许可证，以便许可你的 Defender for Office 365 政策范围内的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2b467-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="2b467-114">Microsoft 365 商业高级版和 Microsoft 365 企业版之间的差异</span><span class="sxs-lookup"><span data-stu-id="2b467-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="2b467-115">此表显示了 Microsoft 365 商业高级版和 Microsoft 365 E3 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2b467-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="2b467-116">功能</span><span class="sxs-lookup"><span data-stu-id="2b467-116">Feature</span></span>    | <span data-ttu-id="2b467-117">Microsoft 365 商业高级版支持</span><span class="sxs-lookup"><span data-stu-id="2b467-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="2b467-118">Microsoft 365 E3 中的支持</span><span class="sxs-lookup"><span data-stu-id="2b467-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="2b467-119">**本地**</span><span class="sxs-lookup"><span data-stu-id="2b467-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="2b467-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2b467-120">Windows 10</span></span>    | <span data-ttu-id="2b467-121">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="2b467-121">Windows 10 Business</span></span>  |     <span data-ttu-id="2b467-122">Windows 10 企业版 E3</span><span class="sxs-lookup"><span data-stu-id="2b467-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="2b467-123">Office 应用\*</span><span class="sxs-lookup"><span data-stu-id="2b467-123">Office apps\*</span></span>    | [<span data-ttu-id="2b467-124">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="2b467-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="2b467-125">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="2b467-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="2b467-126">**云生产力应用**</span><span class="sxs-lookup"><span data-stu-id="2b467-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="2b467-127">Exchange Online 和 Outlook</span><span class="sxs-lookup"><span data-stu-id="2b467-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="2b467-128">每个邮箱 50 GB 存储限制和无限制 Exchange Online 存档</span><span class="sxs-lookup"><span data-stu-id="2b467-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="2b467-129">每个邮箱 100 GB 存储限制和无限制 Exchange Online 存档</span><span class="sxs-lookup"><span data-stu-id="2b467-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="2b467-130">Teams</span><span class="sxs-lookup"><span data-stu-id="2b467-130">Teams</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2b467-133">OneDrive for Business</span></span>    | <span data-ttu-id="2b467-134">每个用户 1 TB 存储限制</span><span class="sxs-lookup"><span data-stu-id="2b467-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="2b467-135">无限制</span><span class="sxs-lookup"><span data-stu-id="2b467-135">Unlimited</span></span> | 
| <span data-ttu-id="2b467-136">Yammer、SharePoint Online、Planner、Stream</span><span class="sxs-lookup"><span data-stu-id="2b467-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-139">MileIQ</span><span class="sxs-lookup"><span data-stu-id="2b467-139">MileIQ</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | | 
| <span data-ttu-id="2b467-141">**威胁防护**</span><span class="sxs-lookup"><span data-stu-id="2b467-141">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="2b467-142">攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="2b467-142">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="2b467-143">请参阅此列表</span><span class="sxs-lookup"><span data-stu-id="2b467-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="2b467-144">Microsoft Edge 基于硬件的隔离的企业管理</span><span class="sxs-lookup"><span data-stu-id="2b467-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="2b467-145">Defender for Office 365 计划 1</span><span class="sxs-lookup"><span data-stu-id="2b467-145">Defender for Office 365 Plan 1</span></span> | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | <span data-ttu-id="2b467-147">不包括，但可添加</span><span class="sxs-lookup"><span data-stu-id="2b467-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="2b467-148">**身份管理**</span><span class="sxs-lookup"><span data-stu-id="2b467-148">**Identity management**</span></span>        | | | 
| <span data-ttu-id="2b467-149">混合 Azure Active Directory (Azure AD) 帐户、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回的自助服务密码重置</span><span class="sxs-lookup"><span data-stu-id="2b467-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-152">Cloud App Discovery， Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="2b467-152">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-154">Azure AD Office 365 应用单一 Sign-On (SSO) ：每个用户 10 个应用 (库 SaaS 应用（如 Salesforce) \*</span><span class="sxs-lookup"><span data-stu-id="2b467-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-157">Azure AD Premium 1 SSO： (Azure AD 应用程序代理和非库应用使用 Self-Service 应用集成模板访问本地应用) </span><span class="sxs-lookup"><span data-stu-id="2b467-157">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-159">**设备和应用管理**</span><span class="sxs-lookup"><span data-stu-id="2b467-159">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="2b467-160">Microsoft Intune、Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="2b467-160">Microsoft Intune, Windows Autopilot</span></span>|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
|<span data-ttu-id="2b467-163">VDA (虚拟桌面) </span><span class="sxs-lookup"><span data-stu-id="2b467-163">Virtual Desktop Access (VDA)</span></span>    |  |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
|<span data-ttu-id="2b467-165">Windows 虚拟桌面 (WVD) </span><span class="sxs-lookup"><span data-stu-id="2b467-165">Windows Virtual Desktop (WVD)</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png) |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
|<span data-ttu-id="2b467-168">共享计算机激活 (标) </span><span class="sxs-lookup"><span data-stu-id="2b467-168">Shared Computer Activation (SCA)</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png) |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-171">Microsoft 桌面优化程序包</span><span class="sxs-lookup"><span data-stu-id="2b467-171">Microsoft Desktop Optimization Package</span></span>    | |     ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-173">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="2b467-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="2b467-174">Office 365 数据丢失防护、Azure 信息保护计划 1</span><span class="sxs-lookup"><span data-stu-id="2b467-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-177">终结点 DLP 的窗口信息保护</span><span class="sxs-lookup"><span data-stu-id="2b467-177">Window Information Protection for endpoint DLP</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-180">**客户端访问许可证 (CAL 权限)**</span><span class="sxs-lookup"><span data-stu-id="2b467-180">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="2b467-181">Enterprise CAL Suite (Exchange、SharePoint、Skype、Windows、Microsoft Endpoint Configuration Manager、Windows Rights Management) </span><span class="sxs-lookup"><span data-stu-id="2b467-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-183">**合规性**</span><span class="sxs-lookup"><span data-stu-id="2b467-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="2b467-184">无限制电子邮件存档</span><span class="sxs-lookup"><span data-stu-id="2b467-184">Unlimited email archiving</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-187">合规性管理器</span><span class="sxs-lookup"><span data-stu-id="2b467-187">Compliance Manager</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-190">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="2b467-190">eDiscovery</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-193">就地保留和诉讼保留</span><span class="sxs-lookup"><span data-stu-id="2b467-193">In-place hold and litigation hold</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
| <span data-ttu-id="2b467-196">邮件记录管理 (MRM) 保留标记和保留策略</span><span class="sxs-lookup"><span data-stu-id="2b467-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![包含在 Microsoft 365 E3 中](../media/check-mark.png) | 
||||

<span data-ttu-id="2b467-199">\* 已分配 SaaS 应用访问权限的用户可以获取最多 10 个应用的 SSO 访问权限。</span><span class="sxs-lookup"><span data-stu-id="2b467-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="2b467-200">管理员可以配置 SSO 并更改用户对不同 SaaS 应用的访问权限，但一次每个用户只能访问 10 个应用。</span><span class="sxs-lookup"><span data-stu-id="2b467-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="2b467-201">所有 Office 365 应用都计为单个应用。</span><span class="sxs-lookup"><span data-stu-id="2b467-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="2b467-202">迁移</span><span class="sxs-lookup"><span data-stu-id="2b467-202">Migration</span></span>

<span data-ttu-id="2b467-203">若要迁移，请与合作伙伴合作，将 Microsoft 365 商业高级版订阅和许可证移动到具有其许可证的合适 Microsoft 365 E3 订阅。</span><span class="sxs-lookup"><span data-stu-id="2b467-203">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="2b467-204">以下各节介绍您需要进行哪些更改（如果有）以及迁移后可以执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="2b467-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="2b467-205">Microsoft 365 订阅配置和数据</span><span class="sxs-lookup"><span data-stu-id="2b467-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="2b467-206">在迁移之前，无需对当前订阅或数据进行任何更改，其中包括：</span><span class="sxs-lookup"><span data-stu-id="2b467-206">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="2b467-207">订阅配置，如 DNS 域名。</span><span class="sxs-lookup"><span data-stu-id="2b467-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="2b467-208">用户和组帐户以及身份验证设置，如多重身份验证或条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="2b467-208">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="2b467-209">生产力服务配置及其数据，如 Teams、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。</span><span class="sxs-lookup"><span data-stu-id="2b467-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="2b467-210">您的用户现在可以在 Exchange Online 邮箱和 OneDrive for Business 文件夹中享受无限存储空间。</span><span class="sxs-lookup"><span data-stu-id="2b467-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="2b467-211">你可以开始对 10 多个应用使用云应用发现、Azure AD Connect Health 和 SSO。</span><span class="sxs-lookup"><span data-stu-id="2b467-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="2b467-212">迁移到 Microsoft 365 E3 的用户无法再使用一个。</a0></span><span class="sxs-lookup"><span data-stu-id="2b467-212">Users migrated to Microsoft 365 E3 can no longer use MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="2b467-213">威胁防护</span><span class="sxs-lookup"><span data-stu-id="2b467-213">Threat protection</span></span>

<span data-ttu-id="2b467-214">Windows 10 商业应用包括以下保护：</span><span class="sxs-lookup"><span data-stu-id="2b467-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="2b467-215">操作系统启动过程的完整性实施</span><span class="sxs-lookup"><span data-stu-id="2b467-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="2b467-216">敏感操作组件的完整性实施</span><span class="sxs-lookup"><span data-stu-id="2b467-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="2b467-217">高级漏洞和零日攻击缓解</span><span class="sxs-lookup"><span data-stu-id="2b467-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="2b467-218">Microsoft Edge、microsoft Edge、microsoft Internet Explorer 和 Chrome 的基于信誉的网络保护</span><span class="sxs-lookup"><span data-stu-id="2b467-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="2b467-219">基于主机的防火墙</span><span class="sxs-lookup"><span data-stu-id="2b467-219">Host-based firewall</span></span>
- <span data-ttu-id="2b467-220">勒索软件缓解</span><span class="sxs-lookup"><span data-stu-id="2b467-220">Ransomware mitigations</span></span>
- <span data-ttu-id="2b467-221">Microsoft Edge 基于硬件的隔离</span><span class="sxs-lookup"><span data-stu-id="2b467-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="2b467-222">由 Intelligent Security Graph 提供的应用程序控制</span><span class="sxs-lookup"><span data-stu-id="2b467-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="2b467-223">USB (设备) </span><span class="sxs-lookup"><span data-stu-id="2b467-223">Device control (USB)</span></span>
- <span data-ttu-id="2b467-224">针对基于 Web 的威胁的网络保护</span><span class="sxs-lookup"><span data-stu-id="2b467-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="2b467-225">主机入侵防护规则</span><span class="sxs-lookup"><span data-stu-id="2b467-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="2b467-226">Windows 10 企业版 E3 还包括针对 Microsoft Edge 的基于硬件的隔离的企业管理。</span><span class="sxs-lookup"><span data-stu-id="2b467-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="2b467-227">迁移到 Microsoft 365 E3 的用户都需要 Microsoft Defender for Office 365 许可证，才能持续进行威胁防护。</span><span class="sxs-lookup"><span data-stu-id="2b467-227">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="2b467-228">请务必购买适用于 Office 365 的其他 Defender 许可证，以便你的 Defender for Office 365 范围内的所有用户都获得许可。</span><span class="sxs-lookup"><span data-stu-id="2b467-228">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="2b467-229">Intune 的设备管理</span><span class="sxs-lookup"><span data-stu-id="2b467-229">Device management with Intune</span></span>

<span data-ttu-id="2b467-230">迁移之前，无需对当前的 Intune 配置进行任何更改，其中包括已注册的设备以及设备和应用设置。</span><span class="sxs-lookup"><span data-stu-id="2b467-230">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="2b467-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="2b467-231">Windows 10</span></span>

<span data-ttu-id="2b467-232">Microsoft 365 商业高级版包括 Windows 10 商业版，你可以将其与 Windows AutoPilot 一起安装。</span><span class="sxs-lookup"><span data-stu-id="2b467-232">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="2b467-233">迁移到 Microsoft 365 E3 时，每个用户许可证包括 Windows 10 企业版 E3，也可以随 Windows Autopilot 一起安装。</span><span class="sxs-lookup"><span data-stu-id="2b467-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="2b467-234">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="2b467-234">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="2b467-235">设备上安装的 Microsoft 365 企业应用版客户端将自动开始使用 Microsoft 365 企业应用版的功能。</span><span class="sxs-lookup"><span data-stu-id="2b467-235">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="2b467-236">迁移后，你现在可以使用：</span><span class="sxs-lookup"><span data-stu-id="2b467-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="2b467-237">组策略支持</span><span class="sxs-lookup"><span data-stu-id="2b467-237">Group Policy support</span></span>
 - <span data-ttu-id="2b467-238">电子表格比较和查询</span><span class="sxs-lookup"><span data-stu-id="2b467-238">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="2b467-239">商业智能</span><span class="sxs-lookup"><span data-stu-id="2b467-239">Business intelligence</span></span>

