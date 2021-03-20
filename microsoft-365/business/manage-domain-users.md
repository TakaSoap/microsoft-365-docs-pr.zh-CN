---
title: 将域用户同步到 Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 将域控制的用户与 Microsoft 365 商业版同步。
ms.openlocfilehash: 1c939dec7229f02991b15f08c48f184efecaddb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913246"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="8a069-103">将域用户同步到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a069-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="8a069-104">1. 准备目录同步</span><span class="sxs-lookup"><span data-stu-id="8a069-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="8a069-105">在从本地 Active Directory 域同步用户和计算机之前，请查看准备与 [Microsoft 365](../enterprise/prepare-for-directory-synchronization.md)的目录同步。</span><span class="sxs-lookup"><span data-stu-id="8a069-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="8a069-106">特别是：</span><span class="sxs-lookup"><span data-stu-id="8a069-106">In particular:</span></span>

   - <span data-ttu-id="8a069-107">请确保目录中不存在以下属性的重复项 **：mail、proxyAddresses** 和 **userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="8a069-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="8a069-108">这些值必须是唯一的，并且必须删除任何重复项。</span><span class="sxs-lookup"><span data-stu-id="8a069-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="8a069-109">我们建议您为每个本地用户帐户配置 **userPrincipalName** (UPN) 属性，以匹配与许可的 Microsoft 365 用户对应的主电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="8a069-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="8a069-110">例如 *：mary.shelley@contoso.com* 而不是 *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="8a069-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="8a069-111">如果 Active Directory 域以不可路由的后缀（如 *.local* 或 *.lan）* 结束，而不是 Internet 可路由后缀（如 *.com* 或 *.org），* 请首先调整本地用户帐户的 UPN 后缀，如准备目录同步的不可路由域中所述。 [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="8a069-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="8a069-112">下面的步骤 4 (4) 中运行 **IdFix** 还将确保本地 Active Directory 已做好目录同步准备。</span><span class="sxs-lookup"><span data-stu-id="8a069-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="8a069-113">2. 安装和配置 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="8a069-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="8a069-114">若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory，请安装 Azure Active Directory Connect 并设置目录同步。</span><span class="sxs-lookup"><span data-stu-id="8a069-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="8a069-115">在管理 [中心中](https://go.microsoft.com/fwlink/p/?linkid=2024339)**，选择** 左侧导航中的"设置"。</span><span class="sxs-lookup"><span data-stu-id="8a069-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="8a069-116">在 **"登录和安全"下，** 选择 **"** 从组织目录同步用户 **"下的"查看"。**</span><span class="sxs-lookup"><span data-stu-id="8a069-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="8a069-117">在"**从组织目录同步** 用户"页上，选择"**开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="8a069-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="8a069-118">在首次步骤中，运行 IdFix 工具以准备目录同步。</span><span class="sxs-lookup"><span data-stu-id="8a069-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="8a069-119">按照向导步骤下载 Azure AD Connect，并使用它将域控制的用户同步到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8a069-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="8a069-120">有关详细信息 [，请参阅设置 Microsoft 365](../enterprise/set-up-directory-synchronization.md) 的目录同步。</span><span class="sxs-lookup"><span data-stu-id="8a069-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="8a069-121">配置 Azure AD Connect 选项时，我们建议你启用密码同步、无缝单一登录和密码写 **回** 功能，Microsoft 365 商业版也支持此功能。</span><span class="sxs-lookup"><span data-stu-id="8a069-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="8a069-122">除了 Azure AD Connect 中的复选框之外，还有一些额外的密码写回步骤。</span><span class="sxs-lookup"><span data-stu-id="8a069-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="8a069-123">有关详细信息，请参阅 [操作说明：配置密码写回](/azure/active-directory/authentication/howto-sspr-writeback)。</span><span class="sxs-lookup"><span data-stu-id="8a069-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="8a069-124">如果你还想要管理加入域的 Windows 10 设备，请参阅启用加入域的 Windows 10 设备以由 [Microsoft 365](manage-windows-devices.md) 商业高级版管理以设置混合 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="8a069-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>