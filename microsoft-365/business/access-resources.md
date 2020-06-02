---
title: 从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何从加入 Windows 10 设备的 Azure Active Directory 中获取本地资源（如业务线应用、文件共享和打印机）的访问权限。
ms.openlocfilehash: 9615ecc9469992d3e5a7479f4799c610db11fb41
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471243"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="e66e0-103">从 Microsoft 365 商业高级版中的 Azure AD 加入设备访问本地资源</span><span class="sxs-lookup"><span data-stu-id="e66e0-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="e66e0-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="e66e0-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="e66e0-105">任何已加入 Azure Active Directory 的 Windows 10 设备都有权访问所有基于云的资源（如 Microsoft 365 应用），并且可以通过 Microsoft 365 商业高级版进行保护。</span><span class="sxs-lookup"><span data-stu-id="e66e0-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="e66e0-106">您还可以允许访问本地资源，如业务线（LOB）应用程序、文件共享和打印机。</span><span class="sxs-lookup"><span data-stu-id="e66e0-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="e66e0-107">若要允许访问，请使用[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)将本地 Active Directory 与 Azure active directory 同步。</span><span class="sxs-lookup"><span data-stu-id="e66e0-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="e66e0-108">若要了解详细信息，请参阅[Azure Active Directory 中的设备管理简介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。</span><span class="sxs-lookup"><span data-stu-id="e66e0-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="e66e0-109">以下各节也汇总了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e66e0-109">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e66e0-110">此过程仅适用于 OAuth 和 NTLM。</span><span class="sxs-lookup"><span data-stu-id="e66e0-110">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="e66e0-111">Kerberos 不受支持。</span><span class="sxs-lookup"><span data-stu-id="e66e0-111">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="e66e0-112">运行 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="e66e0-112">Run Azure AD Connect</span></span>

<span data-ttu-id="e66e0-113">完成以下步骤，使组织的 Azure AD 加入设备能够访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="e66e0-113">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="e66e0-114">若要将您的用户、组和联系人从本地 Active Directory 同步到 Azure Active Directory，请运行目录同步向导和 Azure AD Connect，如[设置 Office 365 的目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)中所述。</span><span class="sxs-lookup"><span data-stu-id="e66e0-114">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="e66e0-115">目录同步完成后，请确保你的组织的 Windows 10 设备已加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="e66e0-115">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="e66e0-116">此步骤是在每个 Windows 10 设备上单独执行的。</span><span class="sxs-lookup"><span data-stu-id="e66e0-116">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="e66e0-117">有关详细信息，请参阅为[Microsoft 365 商业高级版用户设置 Windows 设备](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="e66e0-117">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="e66e0-118">一旦 Windows 10 设备加入了 Azure AD，每个用户都必须重新启动其设备，并使用其 Microsoft 365 商业高级凭据登录。</span><span class="sxs-lookup"><span data-stu-id="e66e0-118">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="e66e0-119">现在，所有设备都有权访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="e66e0-119">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="e66e0-120">无需执行任何其他步骤即可访问 Azure AD 加入的设备的本地资源。</span><span class="sxs-lookup"><span data-stu-id="e66e0-120">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="e66e0-121">此功能内置在 Windows 10 中。</span><span class="sxs-lookup"><span data-stu-id="e66e0-121">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="e66e0-122">如果您计划登录到 AADJ 设备而不是 password 方法（如通过 WHFB 凭据登录的 PIN/Bio 指标），然后访问本地资源（共享、打印机）。等），请按照https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="e66e0-122">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="e66e0-123">如果你的组织未准备好在上面所述的 Azure AD 联接的设备配置中进行部署，请考虑设置[混合 AZURE ad 已加入设备配置](manage-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="e66e0-123">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="e66e0-124">将 Windows 设备加入 Azure AD 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="e66e0-124">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="e66e0-125">如果你的 Azure 加入的 Windows 设备之前已加入域或在工作组中，请考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="e66e0-125">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="e66e0-126">设备 Azure AD 加入时，它会在不引用现有配置文件的情况下创建新用户。</span><span class="sxs-lookup"><span data-stu-id="e66e0-126">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="e66e0-127">必须手动迁移配置文件。</span><span class="sxs-lookup"><span data-stu-id="e66e0-127">Profiles must be manually migrated.</span></span> <span data-ttu-id="e66e0-128">用户配置文件包含收藏夹、本地文件、浏览器设置和「开始」菜单设置等信息。</span><span class="sxs-lookup"><span data-stu-id="e66e0-128">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="e66e0-129">最佳方法是查找第三方工具以将现有文件和设置映射到新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="e66e0-129">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="e66e0-130">如果设备使用的是组策略对象（GPO），则某些 Gpo 在 Intune 中可能没有可比较的[配置服务提供程序](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)（CSP）。</span><span class="sxs-lookup"><span data-stu-id="e66e0-130">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="e66e0-131">运行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)以查找现有 gpo 的可比较 csp。</span><span class="sxs-lookup"><span data-stu-id="e66e0-131">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="e66e0-132">用户将无法对依赖 Active Directory 身份验证的应用程序进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e66e0-132">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="e66e0-133">评估旧版应用程序，并考虑更新到使用新式身份验证的应用（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="e66e0-133">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="e66e0-134">Active Directory 打印机发现将不起作用。</span><span class="sxs-lookup"><span data-stu-id="e66e0-134">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="e66e0-135">您可以为所有用户提供直接打印机路径，也可以使用[混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="e66e0-135">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
