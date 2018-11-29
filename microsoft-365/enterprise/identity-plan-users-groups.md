---
title: 步骤 1：计划用户和组
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 计划为组织工作的一组用户和组。
ms.openlocfilehash: 8062cc2b681f0ae45a8114a6d827f5d1ece2fe3e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865391"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="9eb36-103">步骤 1：计划用户和组</span><span class="sxs-lookup"><span data-stu-id="9eb36-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="9eb36-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="9eb36-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="9eb36-p101">在此步骤中，将创建身份基础结构，以将用户、组和组成员身份与正确配置中的安全功能结合。这将允许你：</span><span class="sxs-lookup"><span data-stu-id="9eb36-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="9eb36-107">维持对有权访问环境中资源的用户的控制。</span><span class="sxs-lookup"><span data-stu-id="9eb36-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="9eb36-108">使用控件保护访问权限可确保身份的高可靠性（用户是其声明的身份）和从安全设备进行访问。</span><span class="sxs-lookup"><span data-stu-id="9eb36-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="9eb36-109">使用合适的权限预配环境中的资源，以减少潜在的危害和数据泄露。</span><span class="sxs-lookup"><span data-stu-id="9eb36-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="9eb36-110">监控环境中的异常用户行为并自动采取措施。</span><span class="sxs-lookup"><span data-stu-id="9eb36-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="9eb36-111">计划主标识提供者</span><span class="sxs-lookup"><span data-stu-id="9eb36-111">Plan your primary identity provider</span></span>

<span data-ttu-id="9eb36-p102">若要创建身份基础结构，需指定主标识提供者。此服务存储用户帐户及其属性、组及其成员身份，并支持其正在进行的管理。</span><span class="sxs-lookup"><span data-stu-id="9eb36-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="9eb36-114">当组织采用 Microsoft 365 企业版时，主标识提供者将为以下之一：</span><span class="sxs-lookup"><span data-stu-id="9eb36-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="9eb36-p103">**Windows Server Active Directory (AD)**，托管在运行 Windows Server 计算机上的 Intranet 标识提供者。它通常由具有现有本地标识提供者的组织使用。</span><span class="sxs-lookup"><span data-stu-id="9eb36-p103">**Windows Server Active Directory (AD)**, an intranet identity provider hosted on computers running Windows Server. This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="9eb36-p104">**Azure Active Directory (Azure AD**)，基于云的标识即服务 (IDaaS)，提供管理和保护环境的广泛功能。它通常由不具备现有本地基础结构的组织使用。</span><span class="sxs-lookup"><span data-stu-id="9eb36-p104">**Azure Active Directory (Azure AD**), a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment. This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="9eb36-p105">如果组织具有现有本地标识提供者，则需要将用户帐户和组从 Windows Server AD 同步到 Azure AD，以提供对 Microsoft 365 企业版基于云的服务无缝访问体验。此外，还可以使用 Azure AD 来创建和管理仅存在于 Microsoft 云中的组。</span><span class="sxs-lookup"><span data-stu-id="9eb36-p105">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from Windows Server AD to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise. You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="9eb36-121">在 Azure AD 中计划好用户和组后，可以：</span><span class="sxs-lookup"><span data-stu-id="9eb36-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="9eb36-122">管理所有云应用程序的所有 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="9eb36-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="9eb36-123">使用同一组控件来保护跨环境对应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="9eb36-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="9eb36-124">与外部合作伙伴进行协作。</span><span class="sxs-lookup"><span data-stu-id="9eb36-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="9eb36-125">监控异常帐户行为（如可疑的登录尝试）并自动采取措施。</span><span class="sxs-lookup"><span data-stu-id="9eb36-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="9eb36-126">按照以下两个部分中的说明来计划和实施用户帐户和组。</span><span class="sxs-lookup"><span data-stu-id="9eb36-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="9eb36-127">对用户分类</span><span class="sxs-lookup"><span data-stu-id="9eb36-127">Categorize your users</span></span>
<span data-ttu-id="9eb36-p106">可使用多种方式对组织中的用户进行分类。例如，某些用户是员工，他们拥有永久身份。某些用户是供应商、承包商或合作伙伴，他们拥有临时身份。某些用户是外部用户，他们没有用户帐户但仍必须被授予访问特定服务和资源的权限，以支持交互和协作。例如：</span><span class="sxs-lookup"><span data-stu-id="9eb36-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="9eb36-133">租户帐户表示组织中许可访问云服务的用户。</span><span class="sxs-lookup"><span data-stu-id="9eb36-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="9eb36-134">企业到企业 (B2B) 帐户表示组织外部邀请加入协作的用户。</span><span class="sxs-lookup"><span data-stu-id="9eb36-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="9eb36-p107">评估组织的用户类型。什么是分组？例如，可以按组织的高级职能或用途对用户进行分组。</span><span class="sxs-lookup"><span data-stu-id="9eb36-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="9eb36-p108">此外，可以将某些云服务与组织外部没有任何用户帐户的用户共享，而且你还需要标识这些用户组。</span><span class="sxs-lookup"><span data-stu-id="9eb36-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-windows-server-ad-and-azure-ad-groups"></a><span data-ttu-id="9eb36-140">计划 Windows Server AD 和 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="9eb36-140">Plan for Windows Server AD and Azure AD groups</span></span>

<span data-ttu-id="9eb36-p109">可将 Azure AD 中的组用于多个目的，以简化云环境的管理。例如，对于 Azure AD 组，可以：</span><span class="sxs-lookup"><span data-stu-id="9eb36-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="9eb36-143">只要在 Azure AD 中添加组或从 Windows Server AD 中同步组，就可以使用基于组的许可将 Office 365 和企业移动性 + 安全性 (EMS) 的许可证自动分配到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9eb36-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from Windows Server AD.</span></span> 
- <span data-ttu-id="9eb36-144">根据用户帐户属性（如部门）将用户帐户动态添加到特定组。</span><span class="sxs-lookup"><span data-stu-id="9eb36-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="9eb36-145">自动预配软件即服务 (SaaS) 应用程序的用户，并通过多重身份验证和其他条件访问规则来保护对这些应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="9eb36-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="9eb36-p110">预配 SharePoint Online 团队网站的权限和访问权限级别。此外，Azure AD 组还可与范围内的 Azure 信息保护策略一起使用，以保护具有加密和权限的文件。</span><span class="sxs-lookup"><span data-stu-id="9eb36-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="9eb36-148">结果</span><span class="sxs-lookup"><span data-stu-id="9eb36-148">Results</span></span>

<span data-ttu-id="9eb36-149">完成这一步后，将具有：</span><span class="sxs-lookup"><span data-stu-id="9eb36-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="9eb36-150">Azure AD 中的用户帐户列表，对应于组织中的员工，以及为组织工作或与组织协作的供应商、承包商和外部合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="9eb36-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="9eb36-151">Azure AD 中的组集合及其成员身份，反映用户帐户和其他组的逻辑集合，用于自动许可预配 Microsoft 云服务的安全设置。</span><span class="sxs-lookup"><span data-stu-id="9eb36-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="9eb36-152">作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-user-groups)。</span><span class="sxs-lookup"><span data-stu-id="9eb36-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="9eb36-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9eb36-153">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="9eb36-154">保护全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="9eb36-154">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |

