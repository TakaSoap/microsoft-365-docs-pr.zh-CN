---
title: 启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何启用 Microsoft 365 以仅在几个步骤中保护本地的 Active Directory 加入 Windows 10 设备。
ms.openlocfilehash: 8d7caefa1ddcadf684fdb5b712601b1bdd4fb5bd
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550239"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="42c5a-103">启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="42c5a-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="42c5a-104">如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="42c5a-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="42c5a-105">若要设置此保护，可以实现**混合 AZURE AD 加入的设备**。</span><span class="sxs-lookup"><span data-stu-id="42c5a-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="42c5a-106">这些设备将加入本地 Active Directory 和 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="42c5a-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="42c5a-107">本视频介绍了有关如何针对最常见方案对此进行设置的步骤，在下面的步骤中也将对此进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="42c5a-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="42c5a-108">1. 准备目录同步</span><span class="sxs-lookup"><span data-stu-id="42c5a-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="42c5a-109">在将用户和计算机从本地 Active Directory 域同步之前，请查看 "[准备将目录同步到 Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)"。</span><span class="sxs-lookup"><span data-stu-id="42c5a-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="42c5a-110">具体而言：</span><span class="sxs-lookup"><span data-stu-id="42c5a-110">In particular:</span></span>

   - <span data-ttu-id="42c5a-111">请确保目录中不存在以下属性的重复项： **mail**、 **proxyAddresses**和**userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="42c5a-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="42c5a-112">这些值必须是唯一的，并且必须删除任何重复的值。</span><span class="sxs-lookup"><span data-stu-id="42c5a-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="42c5a-113">我们建议您为每个本地用户帐户配置**userPrincipalName** （UPN）属性，以匹配与许可的 Microsoft 365 用户对应的主电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="42c5a-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="42c5a-114">例如： *mary.shelley@contoso.com*而不是*mary@contoso。本地*</span><span class="sxs-lookup"><span data-stu-id="42c5a-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="42c5a-115">如果 Active Directory 域以不可路由的后缀（如*local*或*lan*）结尾，而不是 internet 路由后缀（如 *.com*或 *. org*），请先按照为[目录同步准备不可路由的域](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)中所述的步骤调整本地用户帐户的 UPN 后缀。</span><span class="sxs-lookup"><span data-stu-id="42c5a-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="42c5a-116">2. 安装和配置 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="42c5a-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="42c5a-117">若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory 中，请安装 Azure Active Directory Connect 并设置目录同步。</span><span class="sxs-lookup"><span data-stu-id="42c5a-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="42c5a-118">若要了解详细信息，请参阅[设置 Office 365 的目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)。</span><span class="sxs-lookup"><span data-stu-id="42c5a-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="42c5a-119">对于 Microsoft 365 商业版的步骤完全相同。</span><span class="sxs-lookup"><span data-stu-id="42c5a-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="42c5a-120">在为 Azure AD Connect 配置选项时，我们建议您启用**密码同步**、**无缝单一登录**和**密码写回**功能，这在 Microsoft 365 商业版中也受支持。</span><span class="sxs-lookup"><span data-stu-id="42c5a-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="42c5a-121">除了 Azure AD Connect 中的复选框之外，还需要执行一些额外的密码写回步骤。</span><span class="sxs-lookup"><span data-stu-id="42c5a-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="42c5a-122">有关详细信息，请参阅[操作方法：配置密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。</span><span class="sxs-lookup"><span data-stu-id="42c5a-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="42c5a-123">3. 配置混合 Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="42c5a-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="42c5a-124">在将 Windows 10 设备启用成混合的 Azure AD 之前，请确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="42c5a-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="42c5a-125">您运行的是最新版本的 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="42c5a-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="42c5a-126">Azure AD connect 已同步要连接混合 Azure AD 的设备的所有计算机对象。</span><span class="sxs-lookup"><span data-stu-id="42c5a-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="42c5a-127">如果计算机对象属于特定的组织单位（OU），请确保将这些 Ou 设置为在 Azure AD connect 中进行同步。</span><span class="sxs-lookup"><span data-stu-id="42c5a-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="42c5a-128">若要将现有的加入域的 Windows 10 设备注册为已加入混合的 Azure AD，请按照教程中的步骤[操作： Configure Managed Azure Active Directory join for managed](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)domain。</span><span class="sxs-lookup"><span data-stu-id="42c5a-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="42c5a-129">这种混合-使现有的本地 Active Directory 加入了 Windows 10 计算机并将其设置为云就绪。</span><span class="sxs-lookup"><span data-stu-id="42c5a-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="42c5a-130">4. 为 Windows 10 启用自动注册</span><span class="sxs-lookup"><span data-stu-id="42c5a-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="42c5a-131">若要在 Intune 中自动注册移动设备管理的 Windows 10 设备，请参阅[使用组策略自动注册 windows 10 设备](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)。</span><span class="sxs-lookup"><span data-stu-id="42c5a-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="42c5a-132">您可以在本地计算机级别或批量操作中设置组策略，您可以使用组策略管理控制台和 ADMX 模板在域控制器上创建此组策略设置。</span><span class="sxs-lookup"><span data-stu-id="42c5a-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="42c5a-133">5. 配置无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="42c5a-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="42c5a-134">在使用企业计算机时，无缝 SSO 会自动将用户登录到其 Microsoft 365 云资源。</span><span class="sxs-lookup"><span data-stu-id="42c5a-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="42c5a-135">只需部署[Azure Active Directory 无缝单一登录：快速入门](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)中介绍的两个组策略选项之一即可。</span><span class="sxs-lookup"><span data-stu-id="42c5a-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="42c5a-136">**组策略**选项不允许用户更改其设置，而**组策略首**选项设置值，但也将其保留为用户可配置的。</span><span class="sxs-lookup"><span data-stu-id="42c5a-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="42c5a-137">6. 设置 Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="42c5a-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="42c5a-138">Windows Hello 企业版将使用强双重身份验证（2FA）替换密码，以登录到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="42c5a-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="42c5a-139">一个因素是非对称密钥对，另一个是 PIN 或其他本地手势（如指纹或面部识别）（如果设备支持）。</span><span class="sxs-lookup"><span data-stu-id="42c5a-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="42c5a-140">我们建议您在可能的情况下将密码替换为2FA 和 Windows Hello 企业版。</span><span class="sxs-lookup"><span data-stu-id="42c5a-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="42c5a-141">若要配置混合 Windows Hello 企业版，请查看[混合密钥信任 Windows Hello 企业版先决条件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)。</span><span class="sxs-lookup"><span data-stu-id="42c5a-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="42c5a-142">然后按照[配置混合 Windows Hello For Business 密钥信任设置](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="42c5a-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
