---
title: 来宾帐户的先决条件
description: 来宾帐户的配置指南以及如何调整它们
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694241"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="a9164-104">来宾帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="a9164-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="a9164-105">Microsoft 托管桌面 Azure AD 组织中需要以下设置来访问来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="a9164-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="a9164-106">可以在 Azure 门户的"[](https://portal.azure.com)外部标识 **/外部协作设置"下调整这些设置**：</span><span class="sxs-lookup"><span data-stu-id="a9164-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:</span></span>

-   <span data-ttu-id="a9164-107">对于 **设置为"成员** 用户"的来宾邀请限制，分配给特定管理员角色的用户可以邀请来宾用户（包括具有 **成员权限的来宾）**</span><span class="sxs-lookup"><span data-stu-id="a9164-107">For **Guest invite restrictions** set to **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions**</span></span>
-   <span data-ttu-id="a9164-108">对于 **"协作限制"，** 选择以下任一选项：</span><span class="sxs-lookup"><span data-stu-id="a9164-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="a9164-109">如果选择" **允许邀请发送到任何非独占 (域) ，** 则无需其他配置。</span><span class="sxs-lookup"><span data-stu-id="a9164-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="a9164-110">如果选择" **拒绝对指定** 域的邀请"，请确保 Microsoft.com 未列在目标域中。</span><span class="sxs-lookup"><span data-stu-id="a9164-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="a9164-111">如果选择"**仅允许** 对限制最严格的 (域) "，请确保 Microsoft.com 列出该域。 </span><span class="sxs-lookup"><span data-stu-id="a9164-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="a9164-112">如果设置与这些设置交互的限制，请确保排除"Azure Active Directory **工作区服务帐户"。**</span><span class="sxs-lookup"><span data-stu-id="a9164-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="a9164-113">例如，如果你有一个阻止来宾帐户访问 Intune 门户的条件访问策略，则从此策略中排除 **Modern Workplace Service Accounts** 组。</span><span class="sxs-lookup"><span data-stu-id="a9164-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="a9164-114">准备步骤</span><span class="sxs-lookup"><span data-stu-id="a9164-114">Steps to get ready</span></span>

1. <span data-ttu-id="a9164-115">查看 [托管桌面应用](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="a9164-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="a9164-116">使用 [准备情况评估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="a9164-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="a9164-117">[来宾帐户帐户 (](guest-accounts.md) 本文) </span><span class="sxs-lookup"><span data-stu-id="a9164-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="a9164-118">Microsoft 托管桌面的网络配置</span><span class="sxs-lookup"><span data-stu-id="a9164-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="a9164-119">为 Microsoft 托管桌面准备证书和网络配置文件</span><span class="sxs-lookup"><span data-stu-id="a9164-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="a9164-120">为 Microsoft 托管桌面准备本地资源访问权限</span><span class="sxs-lookup"><span data-stu-id="a9164-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="a9164-121">Microsoft 托管桌面中的应用</span><span class="sxs-lookup"><span data-stu-id="a9164-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="a9164-122">为 Microsoft 托管桌面准备映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="a9164-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="a9164-123">为 Microsoft 托管桌面准备打印资源</span><span class="sxs-lookup"><span data-stu-id="a9164-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
