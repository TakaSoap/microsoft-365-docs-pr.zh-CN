---
title: 步骤 7：同步身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/09/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解身份选项并配置 Azure AD Connect，以将本地 Windows Server AD 与 Azure AD 同步。
ms.openlocfilehash: 2391ee11a1706bbbfdeb248c5967822d3ea68f72
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865473"
---
# <a name="step-7-synchronize-identities"></a><span data-ttu-id="4157f-103">步骤 7：同步身份</span><span class="sxs-lookup"><span data-stu-id="4157f-103">Step 7: Synchronize identities</span></span>

<span data-ttu-id="4157f-104">\*\* 此步骤对于混合环境来说是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="4157f-104">*This step is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4157f-105">在此步骤中，将本地 Windows Server Active Directory (AD) 与 Office 365 和企业移动性 + 安全性 (EMS) 订阅所使用的 Azure Active Directory (AD) 租户同步。</span><span class="sxs-lookup"><span data-stu-id="4157f-105">In this step, you'll synchronize your on-premises Windows Server Active Directory (AD) with the Azure Active Directory (AD) tenant used by your Office 365 and Enterprise Mobility + Security (EMS) subscriptions.</span></span>

<span data-ttu-id="4157f-106">Azure AD Connect 是受支持的 Microsoft 工具，可引导你只将真正需要的身份从单林或多林 Windows Server AD 环境同步到 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="4157f-106">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest Windows Server AD environments to your Azure AD tenant.</span></span>

![Azure AD Connect 如何将本地目录同步到 Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

<span data-ttu-id="4157f-108">*Azure AD Connect 如何将本地目录同步到 Azure AD*</span><span class="sxs-lookup"><span data-stu-id="4157f-108">*How Azure AD Connect synchronizes your on-premises directory with Azure AD*</span></span>

<span data-ttu-id="4157f-p101">在混合身份解决方案中首先要决定的是身份验证要求。以下是可供选择的选项：</span><span class="sxs-lookup"><span data-stu-id="4157f-p101">The first decision in your hybrid identity solution is your authentication requirement. The following options are options:</span></span>

- <span data-ttu-id="4157f-p102">使用“托管身份验证”\*\*\*\*，Azure AD 将处理用户登录的身份验证过程。有两种托管身份验证的方法：</span><span class="sxs-lookup"><span data-stu-id="4157f-p102">With **managed authentication**, Azure AD handles the authentication process for user sign-in. There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="4157f-p103">**密码哈希同步 (PHS)** [推荐使用，且对于某些高级功能是必选方法]。这是针对 Azure AD 中的本地目录对象启用身份验证的最简单方法。Azure AD Connect 从 Windows Server AD 中提取哈希密码，对密码执行额外的安全处理，然后将其保存在 Azure AD 中。有关详细信息，请参阅[通过 Azure AD Connect 同步实现密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="4157f-p103">**Password Hash Sync (PHS)** [Recommended and required for some premium features]. This is the simplest way to enable authentication for on-premises directory objects in Azure AD. Azure AD Connect extracts the hashed password from Windows Server AD, does extra security processing on the password, and saves it in Azure AD. For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).</span></span>
    - <span data-ttu-id="4157f-p104">**传递身份验证 (PTA)** 为基于 Azure AD 的服务提供简单的密码验证解决方案。PTA 使用在一个或多个本地服务器上运行的代理直接在本地 Windows Server AD 中验证用户身份验证。有关详细信息，请参阅[使用 Azure Active Directory 传递身份验证的用户登录](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)。</span><span class="sxs-lookup"><span data-stu-id="4157f-p104">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services. PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises Windows Server AD. For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="4157f-p105">通过**联合身份验证**，身份验证过程会通过身份联合服务器被重定向到其他标识提供者（例如，Active Directory 联合身份验证服务 (AD FS)），以用于用户登录。该标识提供者可提供其他身份验证方法（例如，基于智能卡的身份验证）。有关详细信息，请参阅[为你的 Azure Active Directory 混合身份解决方案提供正确的身份验证方法](https://docs.microsoft.com/azure/security/azure-ad-choose-authn)。</span><span class="sxs-lookup"><span data-stu-id="4157f-p105">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in. The identity provider can provide additional authentication methods, such as smartcard-based authentication. For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).</span></span>

<span data-ttu-id="4157f-123">确定混合身份解决方案后，下载并运行 [IdFix 目录同步错误修正工具](https://www.microsoft.com/download/details.aspx?id=36832)，以分析 Windows Server AD 中存在的问题。</span><span class="sxs-lookup"><span data-stu-id="4157f-123">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your Windows Server AD for issues.</span></span>

<span data-ttu-id="4157f-p106">解决了由 IdFix 工具标识的所有问题后，请参阅[实施密码哈希同步](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization)，了解如何为 Office 365 和 EMS 订阅安装 Azure AD Connect 工具，以及在本地 Windows Server AD 和 Azure AD 租户之间配置目录同步。同步启动后，你将使用本地标识提供者（如 Windows Server AD）维护用户帐户和组。</span><span class="sxs-lookup"><span data-stu-id="4157f-p106">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises Windows Server AD and the Azure AD tenant for your Office 365 and EMS subscriptions. After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as Windows Server AD.</span></span>

<span data-ttu-id="4157f-126">Microsoft 提供了一组有关[身份和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。</span><span class="sxs-lookup"><span data-stu-id="4157f-126">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 
- <span data-ttu-id="4157f-127">有关混合环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**支持密码哈希同步的 Active Directory**列。</span><span class="sxs-lookup"><span data-stu-id="4157f-127">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="4157f-128">有关仅限云环境的推荐要求，请参阅[先决条件](identity-access-prerequisites.md#prerequisites)中的**仅限云**列。</span><span class="sxs-lookup"><span data-stu-id="4157f-128">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4157f-130">测试实验室指南：密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="4157f-130">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="4157f-131">测试实验室指南：传递身份验证</span><span class="sxs-lookup"><span data-stu-id="4157f-131">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="4157f-132">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-sync)。</span><span class="sxs-lookup"><span data-stu-id="4157f-132">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="4157f-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4157f-133">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="4157f-134">监控同步运行状况</span><span class="sxs-lookup"><span data-stu-id="4157f-134">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |

