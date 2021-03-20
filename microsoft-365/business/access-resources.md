---
title: 在 Microsoft 365 商业版中从加入 Azure AD 的设备访问本地资源
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
description: 了解如何从加入 Azure Active Directory 的 Windows 10 设备获取对本地资源（如业务线应用、文件共享和打印机）的访问权限。
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913514"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="d2b28-103">在 Microsoft 365 商业高级版中从加入 Azure AD 的设备访问本地资源</span><span class="sxs-lookup"><span data-stu-id="d2b28-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="d2b28-104">本文适用于 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="d2b28-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="d2b28-105">加入 Azure Active Directory 的任何 Windows 10 设备都有权访问所有基于云的资源（如 Microsoft 365 应用）并受 Microsoft 365 商业高级版保护。</span><span class="sxs-lookup"><span data-stu-id="d2b28-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="d2b28-106">还可以允许访问本地资源，如业务线 (LOB) 应用、文件共享和打印机。</span><span class="sxs-lookup"><span data-stu-id="d2b28-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="d2b28-107">若要允许访问，请使用 [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) 将本地 Active Directory 与 Azure Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="d2b28-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="d2b28-108">若要了解更多信息，请参阅 [Azure Active Directory 中的设备管理简介](/azure/active-directory/device-management-introduction)。</span><span class="sxs-lookup"><span data-stu-id="d2b28-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="d2b28-109">以下各节还汇总了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d2b28-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="d2b28-110">运行 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="d2b28-110">Run Azure AD Connect</span></span>

<span data-ttu-id="d2b28-111">完成以下步骤，使已加入 Azure AD 的组织设备能够访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="d2b28-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="d2b28-112">若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory，请运行目录同步向导和 Azure AD Connect，如设置 [Office 365](../enterprise/set-up-directory-synchronization.md)的目录同步中所述。</span><span class="sxs-lookup"><span data-stu-id="d2b28-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>
    
2. <span data-ttu-id="d2b28-113">目录同步完成后，请确保组织的 Windows 10 设备已加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="d2b28-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="d2b28-114">此步骤在每个 Windows 10 设备上单独完成。</span><span class="sxs-lookup"><span data-stu-id="d2b28-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="d2b28-115">有关详细信息 [，请参阅为 Microsoft 365 商业高级版用户](set-up-windows-devices.md) 设置 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="d2b28-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="d2b28-116">Windows 10 设备加入 Azure AD 后，每个用户必须重新启动其设备，然后使用其 Microsoft 365 商业高级版凭据登录。</span><span class="sxs-lookup"><span data-stu-id="d2b28-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="d2b28-117">所有设备现在也有权访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="d2b28-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="d2b28-118">无需执行其他步骤，就无需访问加入 Azure AD 的设备本地资源。</span><span class="sxs-lookup"><span data-stu-id="d2b28-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="d2b28-119">此功能内置于 Windows 10 中。</span><span class="sxs-lookup"><span data-stu-id="d2b28-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="d2b28-120">如果你计划通过 WHFB 凭据登录登录到 AADJ 设备（如 PIN/Bio-metric）而不是密码方法，然后访问本地资源 (共享、打印机。等) ，请关注 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="d2b28-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="d2b28-121">如果你的组织尚未准备好在上文所述的加入 Azure AD 的设备配置中部署，请考虑设置已加入 [Azure AD 的混合设备配置](manage-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="d2b28-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="d2b28-122">将 Windows 设备加入到 Azure AD 的注意事项</span><span class="sxs-lookup"><span data-stu-id="d2b28-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="d2b28-123">如果加入 Azure-AD 的 Windows 设备之前已加入域或工作组，请考虑以下限制：</span><span class="sxs-lookup"><span data-stu-id="d2b28-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="d2b28-124">当设备 Azure AD 加入时，它将创建一个新用户，而无需引用现有配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2b28-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="d2b28-125">必须手动迁移配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2b28-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="d2b28-126">用户配置文件包含收藏夹、本地文件、浏览器设置和"开始"菜单设置等信息。</span><span class="sxs-lookup"><span data-stu-id="d2b28-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="d2b28-127">最佳方法是查找第三方工具，将现有文件和设置映射到新配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2b28-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="d2b28-128">如果设备使用组策略对象 (GPO) ，则某些 GPO 在 Intune 中可能[](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (配置服务提供程序) 相当。</span><span class="sxs-lookup"><span data-stu-id="d2b28-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="d2b28-129">运行 [MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520) 以查找现有 GPO 的可比较的 CSP。</span><span class="sxs-lookup"><span data-stu-id="d2b28-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="d2b28-130">用户可能无法对依赖于 Active Directory 身份验证的应用程序进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d2b28-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="d2b28-131">评估旧应用，并考虑更新到使用新式身份验证的应用（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="d2b28-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="d2b28-132">Active Directory 打印机发现将不起作用。</span><span class="sxs-lookup"><span data-stu-id="d2b28-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="d2b28-133">可以为所有用户提供直接打印机路径或使用 [通用打印](/universal-print/)。</span><span class="sxs-lookup"><span data-stu-id="d2b28-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>