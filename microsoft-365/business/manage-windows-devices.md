---
title: 启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备
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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何启用 Microsoft 365 以保护本地 AD 加入 Windows 10 设备。
ms.openlocfilehash: 392c57a7350a901c1481be632e880cc9fcaa6140
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575970"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="28cab-103">启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="28cab-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="28cab-104">如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="28cab-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="28cab-105">若要进行此设置，您可以实现**混合的 AZURE AD 加入的设备**。</span><span class="sxs-lookup"><span data-stu-id="28cab-105">To set this up, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="28cab-106">这些是同时连接到本地 Active Directory 和 Azure Active Directory 的设备。</span><span class="sxs-lookup"><span data-stu-id="28cab-106">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="28cab-107">下面的视频详细介绍了如何对此进行设置，以了解在以下步骤中也详细介绍的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="28cab-107">The following video details the steps for how to set this up for the most common scenario that is also detailed in the following steps.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="28cab-108">1. 准备目录同步</span><span class="sxs-lookup"><span data-stu-id="28cab-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="28cab-109">在将用户和计算机从本地 Active Directory 域同步之前，请查看 "[准备将目录同步到 Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)"。</span><span class="sxs-lookup"><span data-stu-id="28cab-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="28cab-110">具体而言：</span><span class="sxs-lookup"><span data-stu-id="28cab-110">In particular:</span></span>

   - <span data-ttu-id="28cab-111">确保目录中不存在以下属性的重复项： **mail**、 **proxyAddresses**和**userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="28cab-111">Ensure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="28cab-112">这些值应是唯一的，并且应删除任何重复项。</span><span class="sxs-lookup"><span data-stu-id="28cab-112">These values should be unique and any duplicates should be removed.</span></span>
   
   - <span data-ttu-id="28cab-113">建议将每个本地用户帐户的**userPrincipalName** （UPN）属性配置为与与许可的 Microsoft 365 用户相对应的主电子邮件地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="28cab-113">We recommend that the **userPrincipalName** (UPN) attribute for each local user account is configured to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="28cab-114">例如*mary.shelley@contoso.com* ，而不是*mary @ contoso. 本地*</span><span class="sxs-lookup"><span data-stu-id="28cab-114">For example *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="28cab-115">如果 Active Directory 域以不可路由的后缀（如*local*或*lan*）结尾，而不是 internet 路由后缀（如 .com 或 *. org*），则需要先按照中所述调整本地用户帐户的 UPN 后缀，如中所述 *。*[为目录同步准备不可路由的域](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="28cab-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, you will need to adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="28cab-116">2. 安装和配置 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="28cab-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="28cab-117">若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory 中，请安装 Azure Active Directory Connect 并设置目录同步。</span><span class="sxs-lookup"><span data-stu-id="28cab-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="28cab-118">若要了解详细信息，请参阅[设置 Office 365 的目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)。</span><span class="sxs-lookup"><span data-stu-id="28cab-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="28cab-119">对于 Microsoft 365 商业版的步骤完全相同。</span><span class="sxs-lookup"><span data-stu-id="28cab-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="28cab-120">在为 Azure AD Connect 配置选项时，我们建议启用**密码同步**和**无缝单一登录**，以及 Microsoft 365 商业版中也支持的**密码写回**功能。</span><span class="sxs-lookup"><span data-stu-id="28cab-120">As you configure your options for Azure AD Connect, we recommend enabling **Password Synchronization** and **Seamless Single Sign-On**, as well as the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="28cab-121">除了 Azure AD Connect 中的复选框之外，还需要执行一些额外的密码写回步骤。</span><span class="sxs-lookup"><span data-stu-id="28cab-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="28cab-122">有关详细信息，请参阅[操作方法：配置密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。</span><span class="sxs-lookup"><span data-stu-id="28cab-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="28cab-123">3. 配置混合 Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="28cab-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="28cab-124">在将 Windows 10 设备设置为混合使用 Azure AD 之前，应确保满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="28cab-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, you should make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="28cab-125">您运行的是最新版本的 Azure AD connect。</span><span class="sxs-lookup"><span data-stu-id="28cab-125">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="28cab-126">Azure AD connect 已同步要连接混合 Azure AD 的设备的所有计算机对象。</span><span class="sxs-lookup"><span data-stu-id="28cab-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="28cab-127">如果计算机对象属于特定的组织单位（OU），请确保将这些 Ou 设置为在 Azure AD connect 中进行同步。</span><span class="sxs-lookup"><span data-stu-id="28cab-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="28cab-128">若要将现有的加入域的 Windows 10 设备注册为已加入混合的 Azure AD，请按照教程中的步骤[操作： Configure Managed Azure Active Directory join for managed](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)domain。</span><span class="sxs-lookup"><span data-stu-id="28cab-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="28cab-129">这将混合启用现有的本地 Active Directory 加入 Windows 10 计算机，并将其设置为云就绪。</span><span class="sxs-lookup"><span data-stu-id="28cab-129">This will hybrid-enable your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="28cab-130">4. 为 Windows 10 启用自动注册</span><span class="sxs-lookup"><span data-stu-id="28cab-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="28cab-131">若要在 Intune 中自动注册移动设备管理的 Windows 10 设备，请参阅[使用组策略自动注册 windows 10 设备](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)。</span><span class="sxs-lookup"><span data-stu-id="28cab-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="28cab-132">你可以在本地计算机级别或批量操作中设置组策略，可以使用组策略管理控制台和 ADMX 模板在域控制器上创建此组策略设置。</span><span class="sxs-lookup"><span data-stu-id="28cab-132">You can set the Group Policy at a local computer level, or for bulk operations, you can create this group policy setting on your Domain Controller using the Group Policy Management Console and ADMX templates.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="28cab-133">5. 配置无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="28cab-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="28cab-134">在使用企业计算机时，无缝 SSO 将自动将用户登录到其 Microsoft 365 云资源。</span><span class="sxs-lookup"><span data-stu-id="28cab-134">Seamless SSO will automatically sign users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="28cab-135">只需部署[Azure Active Directory 无缝单一登录：快速入门](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature)中介绍的两个组策略选项之一即可。</span><span class="sxs-lookup"><span data-stu-id="28cab-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="28cab-136">**组策略**选项不允许用户更改其设置，而**组策略首**选项设置值，但也将其保留为用户可配置的。</span><span class="sxs-lookup"><span data-stu-id="28cab-136">The **Group Policy** option does not allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="28cab-137">6. 设置 Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="28cab-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="28cab-138">Windows Hello 企业版将使用强双重身份验证（2FA）替换密码，以登录到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="28cab-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="28cab-139">一个因素是非对称密钥对，另一个是 PIN 或其他本地手势（如指纹或面部识别）（如果设备支持）。</span><span class="sxs-lookup"><span data-stu-id="28cab-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="28cab-140">我们建议您在可能的情况下将密码替换为2FA 和 Windows Hello 企业版。</span><span class="sxs-lookup"><span data-stu-id="28cab-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="28cab-141">若要配置混合 Windows Hello 企业版，请查看[混合密钥信任 Windows Hello 企业版先决条件](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)。</span><span class="sxs-lookup"><span data-stu-id="28cab-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="28cab-142">然后按照[配置混合 Windows Hello For Business 密钥信任设置](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="28cab-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
