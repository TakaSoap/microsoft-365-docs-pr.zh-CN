---
title: 管理用户同意 Microsoft 365 中的应用程序
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 了解用户对应用程序的同意，以及如何将其打开以允许第三方应用访问用户的 Microsoft 365 信息。
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999558"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="d5785-103">管理用户同意 Microsoft 365 中的应用程序</span><span class="sxs-lookup"><span data-stu-id="d5785-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="d5785-104">此设置控制用户是否可以同意使用 OpenID Connect 和 OAuth 2.0 的应用进行登录，并请求访问数据。</span><span class="sxs-lookup"><span data-stu-id="d5785-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="d5785-105">可以从您自己的组织中创建应用程序，也可以通过其他 Office 365 组织或第三方来创建。</span><span class="sxs-lookup"><span data-stu-id="d5785-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="d5785-106">如果启用此设置，则这些应用将向用户询问您的组织的数据的访问权限，并且用户可以选择是否允许。</span><span class="sxs-lookup"><span data-stu-id="d5785-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="d5785-107">如果关闭此设置，则管理员必须先同意这些应用，然后用户才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="d5785-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="d5785-108">在这种情况下，请考虑在 Azure 门户中设置管理员同意工作流，以便用户可以发送管理员批准的请求，以使用任何已阻止的应用。</span><span class="sxs-lookup"><span data-stu-id="d5785-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="d5785-109">用户可以仅向其拥有的、访问其 Office 365 信息的应用授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="d5785-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="d5785-110">他们无法向应用授予对任何其他用户的信息的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d5785-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="d5785-111">打开或关闭用户同意</span><span class="sxs-lookup"><span data-stu-id="d5785-111">Turning user consent on or off</span></span>
<span data-ttu-id="d5785-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="d5785-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="d5785-113">下面介绍了如何打开或关闭应用程序的用户同意。</span><span class="sxs-lookup"><span data-stu-id="d5785-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="d5785-114">在管理中心中，转到 " **设置** \> **组织设置**  >  [服务](https://go.microsoft.com/fwlink/p/?linkid=2053743)" 页面，然后选择 " **用户同意应用** "。</span><span class="sxs-lookup"><span data-stu-id="d5785-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="d5785-115">在 " **用户同意应用程序** " 页上，选择打开或关闭用户同意的选项。</span><span class="sxs-lookup"><span data-stu-id="d5785-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="d5785-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d5785-116">More info</span></span>
<span data-ttu-id="d5785-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="d5785-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="d5785-118">若要了解如何在 Azure active directory 中配置同意设置，请参阅 [配置管理员同意工作流](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)。</span><span class="sxs-lookup"><span data-stu-id="d5785-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="d5785-119">若要了解如何管理用户对应用的同意，请阅读 [对应用程序的同意和评估同意请求的管理](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)。</span><span class="sxs-lookup"><span data-stu-id="d5785-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>