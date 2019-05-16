---
title: 从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 了解如何从加入 Windows 10 设备的 Azure Active Directory 中获取本地资源 (如业务线应用、文件共享和打印机) 的访问权限。
ms.openlocfilehash: fa3cf640e799feb81ff08c5b7b81d57f707e0152
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072022"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="8662e-103">从 Microsoft 365 商业版中的 Azure AD 加入设备访问本地资源</span><span class="sxs-lookup"><span data-stu-id="8662e-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="8662e-104">任何已加入 Azure Active Directory 的 Windows 10 设备都将有权访问所有基于云的资源 (如 Office 365 应用程序), 并可通过 Microsoft 365 商业版进行保护。</span><span class="sxs-lookup"><span data-stu-id="8662e-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="8662e-105">若要同时允许访问本地资源 (如业务线 (LOB) 应用程序、文件共享和打印机), 您必须使用[AZURE AD Connect 将](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)本地 Active Directory 与 Azure active directory 同步。</span><span class="sxs-lookup"><span data-stu-id="8662e-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> <span data-ttu-id="8662e-106">若要了解详细信息, 请参阅[Azure Active Directory 中的设备管理简介](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)。</span><span class="sxs-lookup"><span data-stu-id="8662e-106">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="8662e-107">运行 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="8662e-107">Run Azure AD Connect</span></span>

<span data-ttu-id="8662e-108">完成以下步骤, 使组织的 Azure AD 加入设备能够访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="8662e-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="8662e-109">若要将您的用户、组和联系人从本地 Active Directory 同步到 Azure Active Directory, 请运行目录同步向导和 Azure AD Connect, 如[设置 Office 365 的 "设置目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="8662e-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="8662e-110">目录同步完成后, 请确保你的组织的 Windows 10 设备已加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="8662e-110">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="8662e-111">此步骤是在每个 Windows 10 设备上单独执行的。</span><span class="sxs-lookup"><span data-stu-id="8662e-111">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="8662e-112">有关详细信息, 请参阅为[Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="8662e-112">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="8662e-113">一旦 Windows 10 设备加入了 Azure AD, 每个用户都应重新启动其设备并使用其 Microsoft 365 商业版凭据登录。</span><span class="sxs-lookup"><span data-stu-id="8662e-113">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="8662e-114">所有设备现在都可以访问本地资源。</span><span class="sxs-lookup"><span data-stu-id="8662e-114">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="8662e-115">无需执行任何其他步骤即可访问 Azure AD 加入设备的本地资源。</span><span class="sxs-lookup"><span data-stu-id="8662e-115">No additional steps are required to get access to on-premise resources for Azure AD joined devices.</span></span> <span data-ttu-id="8662e-116">这是 Windows 10 中提供的内置功能。</span><span class="sxs-lookup"><span data-stu-id="8662e-116">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="8662e-117">如果你的组织未准备好在上述 Azure AD 联接的设备配置中进行部署, 请考虑设置[混合 AZURE ad 已加入设备配置](manage-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="8662e-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="8662e-118">将 Windows 设备加入 Azure AD 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="8662e-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="8662e-119">如果 Azure AD 加入之前已加入域或在工作组中的 Windows 设备, 则需要考虑以下限制:</span><span class="sxs-lookup"><span data-stu-id="8662e-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="8662e-120">设备 Azure AD 加入时, 它会在不引用现有配置文件的情况下创建新用户。</span><span class="sxs-lookup"><span data-stu-id="8662e-120">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="8662e-121">若要解决此问题, 需要手动迁移配置文件。</span><span class="sxs-lookup"><span data-stu-id="8662e-121">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="8662e-122">用户配置文件包含诸如收藏夹、本地文件、浏览器设置、"开始" 菜单设置等信息。一种最佳方法是查找第三方工具以将现有文件和设置映射到新的配置文件</span><span class="sxs-lookup"><span data-stu-id="8662e-122">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="8662e-123">如果设备使用的是组策略对象 (GPO), 则某些 Gpo 在 Intune 中可能没有可比较的[配置服务提供程序](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)(CSP)。</span><span class="sxs-lookup"><span data-stu-id="8662e-123">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="8662e-124">运行[MMAT 工具](https://www.microsoft.com/download/details.aspx?id=45520)以查找现有 gpo 的可比较 csp。</span><span class="sxs-lookup"><span data-stu-id="8662e-124">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="8662e-125">用户将无法对依赖 Active Directory 身份验证的应用程序进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8662e-125">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="8662e-126">若要处理此评估, 请使用旧版应用程序, 并考虑更新到使用新式身份验证的应用 (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="8662e-126">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="8662e-127">Active Directory 打印机发现将不起作用。</span><span class="sxs-lookup"><span data-stu-id="8662e-127">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="8662e-128">若要解决此问题, 请为所有用户提供直接打印机路径, 或利用[混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="8662e-128">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
