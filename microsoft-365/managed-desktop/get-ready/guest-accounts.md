---
title: 来宾帐户的先决条件
description: 来宾帐户的配置准则以及如何对其进行调整
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073192"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="da16e-104">来宾帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="da16e-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="da16e-105">Microsoft 托管桌面需要 Azure AD 组织中的以下设置，以供来宾帐户访问。</span><span class="sxs-lookup"><span data-stu-id="da16e-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="da16e-106">可以在 " **外部标识/外部协作** " 下的 [Azure 门户](https://portal.azure.com)中调整这些设置：</span><span class="sxs-lookup"><span data-stu-id="da16e-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="da16e-107">**来宾邀请者角色中的管理员和用户可以邀请** 设置为 **"是"**</span><span class="sxs-lookup"><span data-stu-id="da16e-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="da16e-108">对于 " **协作限制** "，选择以下任一选项：</span><span class="sxs-lookup"><span data-stu-id="da16e-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="da16e-109">如果选择 " **允许将邀请发送到任何域 (最包含的)** ，则不需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="da16e-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="da16e-110">如果选择 " **拒绝向指定域发出邀请** "，请确保未在目标域中列出 Microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="da16e-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="da16e-111">如果选择 **"仅允许对指定域的邀请" (最严格)** ，请 *确保 Microsoft.com 列* 在目标域中。</span><span class="sxs-lookup"><span data-stu-id="da16e-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="da16e-112">如果设置了与这些设置进行交互的限制，请确保排除 Azure Active Directory **新式 Workplace Service 帐户** 。</span><span class="sxs-lookup"><span data-stu-id="da16e-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="da16e-113">例如，如果您有一个条件访问策略来阻止来宾帐户访问 Intune 门户，则从该策略中排除 **新式的 Workplace Service 帐户** 组。</span><span class="sxs-lookup"><span data-stu-id="da16e-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

