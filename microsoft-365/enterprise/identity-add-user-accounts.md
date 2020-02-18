---
title: 步骤 4：添加用户帐户
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 直接在云中或通过与本地目录同步来添加用户帐户和组。
ms.openlocfilehash: 324d4662f868a4a92693b43c6bc0f75c11f20519
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067362"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="ea0ae-103">步骤 4：添加用户帐户</span><span class="sxs-lookup"><span data-stu-id="ea0ae-103">Step 4: Add your user accounts</span></span>

![第 2 阶段 - 标识](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="ea0ae-105">为仅限云的标识创建用户帐户</span><span class="sxs-lookup"><span data-stu-id="ea0ae-105">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="ea0ae-106">对于仅限云的标识，在 Azure Active Directory (Azure AD) 中创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-106">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="ea0ae-107">您可以使用：</span><span class="sxs-lookup"><span data-stu-id="ea0ae-107">You can use:</span></span>

- <span data-ttu-id="ea0ae-108">Microsoft 365 管理员中心</span><span class="sxs-lookup"><span data-stu-id="ea0ae-108">The Microsoft 365 admin center</span></span>
- <span data-ttu-id="ea0ae-109">Azure 门户</span><span class="sxs-lookup"><span data-stu-id="ea0ae-109">The Azure portal</span></span>
- <span data-ttu-id="ea0ae-110">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea0ae-110">Azure PowerShell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="ea0ae-111">为混合标识同步标识</span><span class="sxs-lookup"><span data-stu-id="ea0ae-111">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="ea0ae-112">*此部分对于混合环境来说是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="ea0ae-112">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="ea0ae-113">在此部分中，将本地 Active Directory 域服务 (AD DS) 与 Microsoft 365 企业版包含的 Office 365、Microsoft Intune 和其他基于云的服务所使用的 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-113">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="ea0ae-114">Azure AD Connect 是受支持的 Microsoft 工具，可引导你只将真正需要的身份从单林或多林 AD DS 环境同步到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-114">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="ea0ae-115">下图显示了 Azure AD Connect 同步的基本流程。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-115">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Azure AD Connect 如何将本地目录同步到 Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="ea0ae-117">服务器上运行的 Azure AD Connect 将轮询 AD DS，以了解帐户、组和联系人是否发生了更改。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-117">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="ea0ae-118">Azure AD Connect 将更改发送至 Microsoft 365 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-118">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="ea0ae-p103">在混合身份解决方案中首先要决定的是身份验证要求。以下是可供选择的选项：</span><span class="sxs-lookup"><span data-stu-id="ea0ae-p103">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="ea0ae-p104">使用“托管身份验证”\*\*\*\*，Azure AD 将处理用户登录的身份验证过程。有两种托管身份验证的方法：</span><span class="sxs-lookup"><span data-stu-id="ea0ae-p104">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="ea0ae-123">**密码哈希同步 (PHS)** [推荐使用，对某些高级功能来说是必需的]。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-123">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="ea0ae-124">这是对 Azure AD 中的本地目录对象进行身份验证的最简单方式。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-124">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="ea0ae-125">Azure AD Connect 将从 AD DS 提取哈希密码，对密码进行额外的安全处理并将其同步到 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-125">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password hash, and synchronizes it to Azure AD.</span></span> <span data-ttu-id="ea0ae-126">有关详细信息，请参阅[使用 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-126">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="ea0ae-127">**传递身份验证 (PTA)** 为基于 Azure AD 的服务提供简单的密码验证解决方案。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-127">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="ea0ae-128">PTA 使用在一个或多个本地服务器上运行的代理直接在本地 AD DS 中验证用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-128">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="ea0ae-129">有关详细信息，请参阅[使用 Azure Active Directory 传递身份验证的用户登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-129">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="ea0ae-p107">通过**联合身份验证**，身份验证过程会通过身份联合服务器被重定向到其他标识提供者（例如，Active Directory 联合身份验证服务 (AD FS)），以用于用户登录。该标识提供者可提供其他身份验证方法（例如，基于智能卡的身份验证）。有关详细信息，请参阅[为你的 Azure Active Directory 混合身份解决方案提供正确的身份验证方法](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-p107">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="ea0ae-133">观看此视频，以获取 Microsoft 365 企业版身份模型和身份验证的概述。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-133">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="ea0ae-134"><p> </p></span><span class="sxs-lookup"><span data-stu-id="ea0ae-134"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="ea0ae-135">确定混合身份解决方案后，下载并运行 [IdFix 目录同步错误修正工具](https://www.microsoft.com/download/details.aspx?id=36832)，以分析 AD DS 中存在的问题。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-135">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="ea0ae-136">解决了由 IdFix 工具标识的所有问题后，请参阅[实施密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)，了解如何为 Microsoft 365 订阅安装 Azure AD Connect 工具，以及在本地 AD DS 和 Azure AD 租户之间配置目录同步。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-136">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="ea0ae-137">同步启动后，你将使用本地标识提供程序（如 AD DS）维护用户帐户和组。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-137">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="ea0ae-138">Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-138">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="ea0ae-139">有关混合环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**支持密码哈希同步的 Active Directory**列。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-139">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="ea0ae-140">有关仅限云环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**仅限云**列。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-140">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="ea0ae-141">在本地用户和组出现在 Azure AD 中后，便可以开始分配许可证和使用 OneDrive for Business 和 Exchange Online 等生产力工作负载。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-141">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using productivity workloads such as OneDrive for Business and Exchange Online.</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="ea0ae-143">测试实验室指南：密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="ea0ae-143">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="ea0ae-144">测试实验室指南：传递身份验证</span><span class="sxs-lookup"><span data-stu-id="ea0ae-144">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="ea0ae-145">作为临时检查点，请查看对应于此部分的[退出条件](identity-exit-criteria.md#crit-identity-sync)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="ea0ae-146">监控同步运行状况</span><span class="sxs-lookup"><span data-stu-id="ea0ae-146">Monitor synchronization health</span></span>

<span data-ttu-id="ea0ae-147">*这是可选的，适用于 Microsoft 365 的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="ea0ae-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="ea0ae-148">在此部分中，将在每个本地 AD DS 域控制器上安装 Azure AD Connect Health 代理，以监控由 Azure AD Connect 提供的标识基础架构和同步服务。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-148">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="ea0ae-149">Azure AD Connect Health 门户提供了监控信息，可以从中查看警报、性能监控、使用情况分析和其他信息。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-149">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health 组件](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="ea0ae-151">如何使用 Azure AD Connect Health 的关键设计决策是基于使用 Azure AD Connect 的方式：</span><span class="sxs-lookup"><span data-stu-id="ea0ae-151">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="ea0ae-152">如果你使用的是\*\*\*\*“托管身份验证”选项，请从[使用用于同步的 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-152">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="ea0ae-153">如果仅使用\*\*\*\*“联合身份验证”将帐户和组的名称与 Active Directory 联合身份验证服务 (AD FS) 同步，请从[在 AD FS 中使用 Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 开始，以理解并配置 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-153">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="ea0ae-154">完成这一部分后，将具有：</span><span class="sxs-lookup"><span data-stu-id="ea0ae-154">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="ea0ae-155">在本地标识提供者服务器上安装的 Azure AD Connect Health 代理。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-155">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="ea0ae-156">显示本地基础结构的当前状态，以及与 Microsoft 365 订阅的 Azure AD 租户同步活动的 Azure AD Connect Health 门户。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-156">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

<span data-ttu-id="ea0ae-157">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-sync-health)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-157">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="ea0ae-158">简化密码更新</span><span class="sxs-lookup"><span data-stu-id="ea0ae-158">Simplify password updates</span></span>

<span data-ttu-id="ea0ae-159">*这对于混合环境来说是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="ea0ae-159">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="ea0ae-160">在此部分中，将允许用户通过 Azure Active Directory (AD) 重置其密码，然后复制到本地 Active Directory 域服务 (AD DS)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-160">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="ea0ae-161">此过程称为密码写回。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-161">This process is known as password writeback.</span></span> <span data-ttu-id="ea0ae-162">通过密码写回，用户不需要通过本地 AD DS（用户帐户及其属性的存储位置）更新其密码。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-162">With password writeback, users don’t need to update their passwords through the on-premises AD DS where user accounts and their attributes are stored.</span></span> <span data-ttu-id="ea0ae-163">这非常适用于对本地网络没有远程访问连接的漫游或远程用户。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-163">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="ea0ae-164">需要密码写回才可充分利用 Azure AD 标识保护功能，例如，当检测到高风险的帐户泄露时要求用户更改其本地密码。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-164">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="ea0ae-165">有关其他信息和配置说明，请参阅 [Azure AD SSPR 密码写回](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-165">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="ea0ae-p111">升级到最新版本的 Azure AD Connect，以确保即时获取最佳体验和新功能。有关详细信息，请参阅 [Azure AD Connect 自定义安装](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-p111">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="ea0ae-169">测试实验室指南：密码写回</span><span class="sxs-lookup"><span data-stu-id="ea0ae-169">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="ea0ae-170">作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-pw-writeback)。</span><span class="sxs-lookup"><span data-stu-id="ea0ae-170">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![第 5 步](../media/stepnumbers/Step5.png)| [<span data-ttu-id="ea0ae-172">使用组进行管理</span><span class="sxs-lookup"><span data-stu-id="ea0ae-172">Use groups for management</span></span>](identity-use-group-management.md) |
