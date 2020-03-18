---
title: 使用 Office 365 中的免费 Azure Active Directory 订阅
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: 了解如何访问组织已购买 Office 365 付费订阅中包含的 Azure Active Directory。
ms.openlocfilehash: fb1e2586c0b21c72084d7120b8735fccccd1a004
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710491"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="fee71-103">使用 Office 365 中的免费 Azure Active Directory 订阅</span><span class="sxs-lookup"><span data-stu-id="fee71-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="fee71-p101">如果组织已购买 Office 365、Microsoft Dynamics CRM Online、企业移动性套件或其他 Microsoft 服务的付费订阅，表明你已免费订阅 Microsoft Azure Active Directory。你和其他管理员可使用 Azure AD 创建并管理用户和组帐户。若要使用 Azure AD，只需转到 Azure 门户，并使用 Office 365 帐户登录即可。</span><span class="sxs-lookup"><span data-stu-id="fee71-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fee71-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="fee71-107">Before you begin</span></span>

<span data-ttu-id="fee71-p102">使用专用浏览会话（而不是常规会话）来访问 Azure 门户（下面的第 1 步），这样可以防止将当前登录时使用的凭据传递到 Azure。若要打开专用浏览会话：</span><span class="sxs-lookup"><span data-stu-id="fee71-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this prevents the credentials that you're currently logged on with from being passed to Azure. To open an private browsing session:</span></span>

- <span data-ttu-id="fee71-110">在 Microsoft Edge（旧版）、Internet Explorer 或 Mozilla FireFox 中，按下 `CTRL+SHIFT+P`。</span><span class="sxs-lookup"><span data-stu-id="fee71-110">In Microsoft Edge (legacy version), Internet Explorer, or Mozilla FireFox, press `CTRL+SHIFT+P`.</span></span>

- <span data-ttu-id="fee71-111">在 Microsoft Edge （最新版本）或 Google Chrome 中，按下 `CTRL+SHIFT+N`。</span><span class="sxs-lookup"><span data-stu-id="fee71-111">In Microsoft Edge (newest version) or Google Chrome, press `CTRL+SHIFT+N`.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="fee71-112">访问 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fee71-112">Access Azure Active Directory</span></span>

1. <span data-ttu-id="fee71-113">转到 [portal.azure.com](https://portal.azure.com)，再使用 Office 365 工作或学生帐户登录。</span><span class="sxs-lookup"><span data-stu-id="fee71-113">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="fee71-114">在 Azure 门户内的左侧导航窗格中，单击“Azure Active Directory”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fee71-114">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![在 Azure 门户内的左侧导航窗格中，单击“Azure Active Directory”。](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="fee71-116">此时，**Azure Active Directory** 管理中心显示。</span><span class="sxs-lookup"><span data-stu-id="fee71-116">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="fee71-117">更多信息</span><span class="sxs-lookup"><span data-stu-id="fee71-117">More information</span></span>

- <span data-ttu-id="fee71-118">免费 Azure Active Directory 订阅不包括登录活动报告。</span><span class="sxs-lookup"><span data-stu-id="fee71-118">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="fee71-119">若要记录登录活动（这在数据泄露时可能非常有用），需要 Azure Active Directory Premium 订阅。</span><span class="sxs-lookup"><span data-stu-id="fee71-119">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="fee71-120">有关详细信息，请参阅“[Azure AD 存储数据多长时间？](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)”</span><span class="sxs-lookup"><span data-stu-id="fee71-120">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="fee71-121">也可以从 Microsoft 365 管理中心访问“**Azure Active Directory**”管理中心。</span><span class="sxs-lookup"><span data-stu-id="fee71-121">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="fee71-122">在 Microsoft 365 管理中心的左侧导航窗格中，单击“**管理中心**”\>“**Azure Active Directory**”。</span><span class="sxs-lookup"><span data-stu-id="fee71-122">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="fee71-123">若要了解如何管理用户和组，并执行其他目录管理任务，请参阅[管理 Azure AD 目录](https://docs.microsoft.com/azure/active-directory/active-directory-administer)。</span><span class="sxs-lookup"><span data-stu-id="fee71-123">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
