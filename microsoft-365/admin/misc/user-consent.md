---
title: 管理用户对应用程序中应用Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 了解用户对应用的同意，以及如何启用它们以允许第三方应用访问用户Microsoft 365信息。
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391227"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="6145d-103">管理用户对应用程序中应用Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6145d-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="6145d-104">此设置控制用户是否可以同意使用 OpenID 连接和 OAuth 2.0 进行登录和请求访问数据的应用。</span><span class="sxs-lookup"><span data-stu-id="6145d-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="6145d-105">可以从你自己的组织创建应用，也可以来自另一Office 365组织或第三方。</span><span class="sxs-lookup"><span data-stu-id="6145d-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="6145d-106">如果启用此设置，这些应用将要求用户授予访问组织数据的权限，用户可以选择是否允许。</span><span class="sxs-lookup"><span data-stu-id="6145d-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="6145d-107">如果关闭此设置，则管理员必须先同意这些应用，用户才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="6145d-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="6145d-108">在这种情况下，请考虑在 Azure 门户中设置管理员同意工作流，以便用户可以发送管理员批准请求以使用任何阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="6145d-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="6145d-109">用户可以仅向其拥有的、访问其 Office 365 信息的应用授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="6145d-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="6145d-110">他们无法向应用授予对任何其他用户的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6145d-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="6145d-111">打开或关闭用户同意</span><span class="sxs-lookup"><span data-stu-id="6145d-111">Turning user consent on or off</span></span>

<span data-ttu-id="6145d-112">下面将了解如何打开或关闭用户对应用的同意。</span><span class="sxs-lookup"><span data-stu-id="6145d-112">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="6145d-113">In the admin center， go to the **设置** \> **Org settings**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page， and then select **User consent to apps**.</span><span class="sxs-lookup"><span data-stu-id="6145d-113">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="6145d-114">在" **用户同意应用"页上** ，选择打开或关闭用户同意的选项。</span><span class="sxs-lookup"><span data-stu-id="6145d-114">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="related-content"></a><span data-ttu-id="6145d-115">相关内容</span><span class="sxs-lookup"><span data-stu-id="6145d-115">Related content</span></span> 

<span data-ttu-id="6145d-116">[配置管理员同意工作流](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (文章) </span><span class="sxs-lookup"><span data-stu-id="6145d-116">[Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (article)</span></span>\
<span data-ttu-id="6145d-117">[管理对应用程序的同意并评估](/azure/active-directory/manage-apps/manage-consent-requests) 同意请求 (文章) </span><span class="sxs-lookup"><span data-stu-id="6145d-117">[Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests) (article)</span></span>