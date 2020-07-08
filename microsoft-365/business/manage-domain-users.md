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
description: 将受域控制的用户与 Microsoft 365 for business 同步。
ms.openlocfilehash: af9cb7c9b2b639edc2375679a73ab41c4cf6de71
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080055"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="87933-103">将域用户同步到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87933-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="87933-104">1. 准备目录同步</span><span class="sxs-lookup"><span data-stu-id="87933-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="87933-105">在将用户和计算机从本地 Active Directory 域同步之前，请查看 "[准备将目录同步到 Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)"。</span><span class="sxs-lookup"><span data-stu-id="87933-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="87933-106">具体而言：</span><span class="sxs-lookup"><span data-stu-id="87933-106">In particular:</span></span>

   - <span data-ttu-id="87933-107">请确保目录中不存在以下属性的重复项： **mail**、 **proxyAddresses**和**userPrincipalName**。</span><span class="sxs-lookup"><span data-stu-id="87933-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="87933-108">这些值必须是唯一的，并且必须删除任何重复的值。</span><span class="sxs-lookup"><span data-stu-id="87933-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="87933-109">我们建议您为每个本地用户帐户配置**userPrincipalName** （UPN）属性，以匹配与许可的 Microsoft 365 用户对应的主电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="87933-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="87933-110">例如： *mary.shelley@contoso.com*而不是*mary@contoso。本地*</span><span class="sxs-lookup"><span data-stu-id="87933-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="87933-111">如果 Active Directory 域以不可路由的后缀（如*local*或*lan*）结尾，而不是 internet 路由后缀（如 *.com*或 *. org*），请先按照为[目录同步准备不可路由的域](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)中所述的步骤调整本地用户帐户的 UPN 后缀。</span><span class="sxs-lookup"><span data-stu-id="87933-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="87933-112">下面的步骤4（4）中的**Run IdFix**还将确保您的内部部署 Active Directory 已准备好进行目录同步。</span><span class="sxs-lookup"><span data-stu-id="87933-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="87933-113">2. 安装和配置 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="87933-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="87933-114">若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory 中，请安装 Azure Active Directory Connect 并设置目录同步。</span><span class="sxs-lookup"><span data-stu-id="87933-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="87933-115">在左侧导航的 " <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 选择**设置**" 中的 "管理中心"。</span><span class="sxs-lookup"><span data-stu-id="87933-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="87933-116">在 "**登录和安全**" 下，选择 "在**组织的目录中同步用户**" 下的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="87933-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="87933-117">在 "**从您的组织的目录中同步用户**" 页上，选择 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="87933-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="87933-118">在第一步中运行 IdFix 工具以准备目录同步。</span><span class="sxs-lookup"><span data-stu-id="87933-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="87933-119">按照向导步骤下载 Azure AD Connect，并使用它将域控制的用户同步到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="87933-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="87933-120">若要了解详细信息，请参阅[设置 Microsoft 365 的目录同步](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。</span><span class="sxs-lookup"><span data-stu-id="87933-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="87933-121">在为 Azure AD Connect 配置选项时，我们建议您启用**密码同步**、**无缝单一登录**和**密码写回**功能，这在 Microsoft 365 for business 中也受支持。</span><span class="sxs-lookup"><span data-stu-id="87933-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="87933-122">除了 Azure AD Connect 中的复选框之外，还需要执行一些额外的密码写回步骤。</span><span class="sxs-lookup"><span data-stu-id="87933-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="87933-123">有关详细信息，请参阅[操作方法：配置密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。</span><span class="sxs-lookup"><span data-stu-id="87933-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="87933-124">如果你还想要管理加入域的 Windows 10 设备，请参阅[Enable 由 Microsoft 365 商业高级版管理的加入域的 windows 10 设备](manage-windows-devices.md)，以设置混合 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="87933-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 