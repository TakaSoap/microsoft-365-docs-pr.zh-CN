---
title: 步骤 3：配置混合标识
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解标识选项并配置 Azure AD Connect，以将本地 Active Directory 域服务 与 Azure AD 同步。
ms.openlocfilehash: 0b494047f984d9fd830e840d2d1f4fafa06fe8ab
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073822"
---
# <a name="step-3-configure-hybrid-identity"></a><span data-ttu-id="2008e-103">步骤 3：配置混合标识</span><span class="sxs-lookup"><span data-stu-id="2008e-103">Step 3: Configure hybrid identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a><span data-ttu-id="2008e-104">同步标识</span><span class="sxs-lookup"><span data-stu-id="2008e-104">Synchronize identities</span></span>

<span data-ttu-id="2008e-105">*此部分对于混合环境来说是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="2008e-105">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2008e-106">在此部分中，将本地 Active Directory 域服务 (AD DS) 与 Office 365 和企业移动性 + 安全性 (EMS) 订阅所使用的 Azure Active Directory (AD) 租户同步。</span><span class="sxs-lookup"><span data-stu-id="2008e-106">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure Active Directory (Azure AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="2008e-107">Azure AD Connect 是受支持的 Microsoft 工具，可引导你只将真正需要的身份从单林或多林 AD DS 环境同步到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="2008e-107">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="2008e-108">下图显示了 Azure AD Connect 同步的基本流程。</span><span class="sxs-lookup"><span data-stu-id="2008e-108">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Azure AD Connect 如何将本地目录同步到 Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. <span data-ttu-id="2008e-110">服务器上运行的 Azure AD Connect 将轮询 AD DS，以了解帐户、组和联系人是否发生了更改。</span><span class="sxs-lookup"><span data-stu-id="2008e-110">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="2008e-111">Azure AD Connect 将更改发送至 Microsoft 365 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="2008e-111">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="2008e-p102">在混合身份解决方案中首先要决定的是身份验证要求。以下是可供选择的选项：</span><span class="sxs-lookup"><span data-stu-id="2008e-p102">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="2008e-p103">使用“托管身份验证”\*\*\*\*，Azure AD 将处理用户登录的身份验证过程。有两种托管身份验证的方法：</span><span class="sxs-lookup"><span data-stu-id="2008e-p103">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="2008e-116">**密码哈希同步 (PHS)** [推荐使用，对某些高级功能来说是必需的]。</span><span class="sxs-lookup"><span data-stu-id="2008e-116">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="2008e-117">这是对 Azure AD 中的本地目录对象进行身份验证的最简单方式。</span><span class="sxs-lookup"><span data-stu-id="2008e-117">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="2008e-118">Azure AD Connect 将从 AD DS 提取哈希密码，对密码进行额外的安全处理并将其保存到 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="2008e-118">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password, and saves it in Azure AD.</span></span> <span data-ttu-id="2008e-119">有关详细信息，请参阅[使用 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="2008e-119">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="2008e-120">**传递身份验证 (PTA)** 为基于 Azure AD 的服务提供简单的密码验证解决方案。</span><span class="sxs-lookup"><span data-stu-id="2008e-120">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="2008e-121">PTA 使用在一个或多个本地服务器上运行的代理直接在本地 AD DS 中验证用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="2008e-121">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="2008e-122">有关详细信息，请参阅[使用 Azure Active Directory 传递身份验证的用户登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)。</span><span class="sxs-lookup"><span data-stu-id="2008e-122">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="2008e-p106">通过**联合身份验证**，身份验证过程会通过身份联合服务器被重定向到其他标识提供者（例如，Active Directory 联合身份验证服务 (AD FS)），以用于用户登录。该标识提供者可提供其他身份验证方法（例如，基于智能卡的身份验证）。有关详细信息，请参阅[为你的 Azure Active Directory 混合身份解决方案提供正确的身份验证方法](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)。</span><span class="sxs-lookup"><span data-stu-id="2008e-p106">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="2008e-126">确定混合身份解决方案后，下载并运行 [IdFix 目录同步错误修正工具](https://www.microsoft.com/download/details.aspx?id=36832)，以分析 AD DS 中存在的问题。</span><span class="sxs-lookup"><span data-stu-id="2008e-126">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="2008e-127">解决了由 IdFix 工具标识的所有问题后，请参阅[实施密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)，了解如何为 Office 365 和 EMS 订阅安装 Azure AD Connect 工具，以及在本地 AD DS 和 Azure AD 租户之间配置目录同步。</span><span class="sxs-lookup"><span data-stu-id="2008e-127">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span> <span data-ttu-id="2008e-128">同步启动后，你将使用本地标识提供程序（如 AD DS）维护用户帐户和组。</span><span class="sxs-lookup"><span data-stu-id="2008e-128">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="2008e-129">Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。</span><span class="sxs-lookup"><span data-stu-id="2008e-129">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="2008e-130">有关混合环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**支持密码哈希同步的 Active Directory**列。</span><span class="sxs-lookup"><span data-stu-id="2008e-130">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="2008e-131">有关仅限云环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**仅限云**列。</span><span class="sxs-lookup"><span data-stu-id="2008e-131">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="2008e-132">在本地用户和组出现在 Azure AD 中后，便可以开始分配许可证和使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="2008e-132">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using Exchange Online.</span></span> <span data-ttu-id="2008e-133">若要向用户推广 Exchange Online 并迁移本地邮箱，请参阅[部署 Microsoft 365 企业版的 Exchange Online](exchangeonline-workload.md)。</span><span class="sxs-lookup"><span data-stu-id="2008e-133">To roll out Exchange Online to your users and migrate on-premises mailboxes, see [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md).</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2008e-135">测试实验室指南：密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="2008e-135">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="2008e-136">测试实验室指南：传递身份验证</span><span class="sxs-lookup"><span data-stu-id="2008e-136">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="2008e-137">作为临时检查点，请查看对应于此部分的[退出条件](identity-exit-criteria.md#crit-identity-sync)。</span><span class="sxs-lookup"><span data-stu-id="2008e-137">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="2008e-138">监控同步运行状况</span><span class="sxs-lookup"><span data-stu-id="2008e-138">Monitor synchronization health</span></span>

<span data-ttu-id="2008e-139">*这是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="2008e-139">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2008e-140">在此部分中，将在每个本地标识服务器上安装 Azure AD Connect Health 代理，以监控由 Azure AD Connect 提供的身份基础架构和同步服务。</span><span class="sxs-lookup"><span data-stu-id="2008e-140">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="2008e-141">Azure AD Connect Health 门户提供了监控信息，可以从中查看警报、性能监控、使用情况分析和其他信息。</span><span class="sxs-lookup"><span data-stu-id="2008e-141">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health 组件](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="2008e-143">如何使用 Azure AD Connect Health 的关键设计决策是基于使用 Azure AD Connect 的方式：</span><span class="sxs-lookup"><span data-stu-id="2008e-143">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="2008e-144">如果你使用的是\*\*\*\*“托管身份验证”选项，请从[使用用于同步的 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="2008e-144">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="2008e-145">如果仅使用\*\*\*\*“联合身份验证”将帐户和组的名称与 Active Directory 联合身份验证服务 (AD FS) 同步，请从[在 AD FS 中使用 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="2008e-145">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="2008e-146">完成这一部分后，将具有：</span><span class="sxs-lookup"><span data-stu-id="2008e-146">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="2008e-147">在本地标识提供者服务器上安装的 Azure AD Connect Health 代理。</span><span class="sxs-lookup"><span data-stu-id="2008e-147">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="2008e-148">显示本地基础结构的当前状态，以及与 Office 365 和 EMS 订阅的 Azure AD 租户同步活动的 Azure AD Connect Health 门户。</span><span class="sxs-lookup"><span data-stu-id="2008e-148">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="2008e-149">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-sync-health)。</span><span class="sxs-lookup"><span data-stu-id="2008e-149">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="2008e-150">下一步骤</span><span class="sxs-lookup"><span data-stu-id="2008e-150">Next step</span></span>

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="2008e-151">配置安全的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="2008e-151">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md)
