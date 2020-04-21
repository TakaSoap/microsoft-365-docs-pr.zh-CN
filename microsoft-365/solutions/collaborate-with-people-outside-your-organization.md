---
title: 与组织外部的人员进行协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: 了解如何配置 Microsoft 365 以与组织外部的人员进行协作。
ms.openlocfilehash: 1b2a15312dcaacc398bb521f3ecfb6e7453f66bb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630721"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="3a14e-103">与组织外部的人员进行协作</span><span class="sxs-lookup"><span data-stu-id="3a14e-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="3a14e-104">Microsoft 365 中的外部共享功能为组织中的人员与合作伙伴、供应商、客户和其他在你的目录中没有帐户的人进行协作提供了机会。</span><span class="sxs-lookup"><span data-stu-id="3a14e-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="3a14e-105">您可以与组织外部的人员或仅与单个文件共享整个团队或网站。</span><span class="sxs-lookup"><span data-stu-id="3a14e-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="3a14e-106">与组织外部的人员进行协作包含以下两个主要组件：</span><span class="sxs-lookup"><span data-stu-id="3a14e-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="3a14e-107">**启用共享**-在 Azure Active Directory、团队、Microsoft 365 组和 SharePoint 之间共享共享控件，以允许您的组织所需的共享级别。</span><span class="sxs-lookup"><span data-stu-id="3a14e-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="3a14e-108">**启用其他安全性**-尽管可以将基本共享功能配置为要求组织外部的人员进行身份验证，但 Microsoft 365 提供了许多额外的安全性和合规性功能，可帮助您在外部共享时保护数据并维护您的管理策略。</span><span class="sxs-lookup"><span data-stu-id="3a14e-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="3a14e-109">启用共享</span><span class="sxs-lookup"><span data-stu-id="3a14e-109">Enable sharing</span></span>

<span data-ttu-id="3a14e-110">默认情况下，在 Microsoft 365 中，与组织外部的人员共享启用 SharePoint 和 OneDrive，但对团队禁用。</span><span class="sxs-lookup"><span data-stu-id="3a14e-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="3a14e-111">许多 SharePoint 和 OneDrive 外部共享方案的工作方式不需要进一步配置。</span><span class="sxs-lookup"><span data-stu-id="3a14e-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="3a14e-112">若要确认您正在使用的方案的设置，或启用新的设置，请从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="3a14e-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="3a14e-113">[对文档进行协作](collaborate-on-documents.md)-了解如何配置 Microsoft 365 以允许与您的组织外部的人员（来宾和未经身份验证的用户）共享和协作处理文件和文件夹中的人员。</span><span class="sxs-lookup"><span data-stu-id="3a14e-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="3a14e-114">[在网站中进行协作](collaborate-in-site.md)-了解如何配置 Microsoft 365 以启用与来宾共享 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="3a14e-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="3a14e-115">[作为团队协作](collaborate-as-team.md)-了解如何配置 Microsoft 365 以在团队中启用来宾协作。</span><span class="sxs-lookup"><span data-stu-id="3a14e-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="3a14e-116">有关跨 Microsoft 365 提供的来宾共享设置的全面查看，请参阅[microsoft 365 来宾共享设置参考](microsoft-365-guest-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3a14e-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="3a14e-117">启用其他安全性</span><span class="sxs-lookup"><span data-stu-id="3a14e-117">Enable additional security</span></span>

<span data-ttu-id="3a14e-118">启用了要用于与组织外部的人员共享的方案后，请考虑其他保护措施，以防止无意或有意的不恰当的共享中保护您的内容。</span><span class="sxs-lookup"><span data-stu-id="3a14e-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="3a14e-119">[使用未经身份验证的用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)-了解与未经身份验证的用户共享的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="3a14e-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="3a14e-120">[限制意外曝光](share-limit-accidental-exposure.md)-了解如何减少与组织外部人员意外共享敏感内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="3a14e-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="3a14e-121">[创建安全来宾共享环境](create-secure-guest-sharing-environment.md)）-了解 Microsoft 365 中提供的工具，以帮助确保与组织外部的人员共享以安全且安全的方式完成，并满足您的治理要求。</span><span class="sxs-lookup"><span data-stu-id="3a14e-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md)) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="3a14e-122">与合作伙伴公司协作</span><span class="sxs-lookup"><span data-stu-id="3a14e-122">Collaborate with partner companies</span></span>

<span data-ttu-id="3a14e-123">当您在大型项目中工作时，如果有来自其他组织的多个来宾，或者如果来宾经常在其中进行更改，则可以使用 Azure Active Directory 中的权限管理简化来宾管理，并允许合作伙伴公司在此职责中进行共享。</span><span class="sxs-lookup"><span data-stu-id="3a14e-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="3a14e-124">有关详细信息，请参阅[Create a B2B extranet with 托管来宾](b2b-extranet.md)。</span><span class="sxs-lookup"><span data-stu-id="3a14e-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="3a14e-125">限制共享</span><span class="sxs-lookup"><span data-stu-id="3a14e-125">Limit sharing</span></span>

<span data-ttu-id="3a14e-126">如果 Microsoft 365 中的某些共享功能与您的治理策略冲突，请参阅[在 microsoft 365 中限制共享](microsoft-365-limit-sharing.md)以了解用于限制共享的选项。</span><span class="sxs-lookup"><span data-stu-id="3a14e-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a14e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a14e-127">See Also</span></span>

[<span data-ttu-id="3a14e-128">Microsoft 365 中的文件协作简介</span><span class="sxs-lookup"><span data-stu-id="3a14e-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="3a14e-129">使用 Microsoft 365 在 SharePoint 中规划文件协作</span><span class="sxs-lookup"><span data-stu-id="3a14e-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
