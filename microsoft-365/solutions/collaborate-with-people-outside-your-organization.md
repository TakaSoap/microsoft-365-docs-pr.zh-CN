---
title: 与组织外部人员进行协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: 了解如何配置 Microsoft 365 应用（如 Teams、OneDrive 和 SharePoint）与组织外部人员进行协作。
ms.openlocfilehash: 85aa77982fa15adb62bd587856546d2828edb942
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599815"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="6a3dd-103">与组织外部人员进行协作</span><span class="sxs-lookup"><span data-stu-id="6a3dd-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="6a3dd-104">Microsoft 365 中的外部共享功能为组织内部人员提供了与合作伙伴、供应商、客户以及目录中没有帐户的其他人进行协作的机会。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="6a3dd-105">可以与组织外部人员共享整个团队或网站，也可以只共享单个文件。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="6a3dd-106">与组织外部人员协作由两个主要部分组成：</span><span class="sxs-lookup"><span data-stu-id="6a3dd-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="6a3dd-107">**启用共享** - 配置 Azure Active Directory、Teams、Microsoft 365 组和 SharePoint 中的共享控件，以允许组织达到希望的共享级别。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="6a3dd-108">启用 **其他** 安全性 - 虽然基本共享功能可以配置为要求组织外部人员进行身份验证，但 Microsoft 365 提供了许多其他安全性和合规性功能，可帮助你在外部共享时保护数据和维护管理策略。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

<span data-ttu-id="6a3dd-109">阅读 [设置与 Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams) 和 Microsoft Teams 的安全协作，了解外部共享如何与 Microsoft 365 协作指南的总体联系。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-109">Read [Set up secure collaboration with Microsoft 365 and Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams) to learn how external sharing ties in with the overall Microsoft 365 collaboration guidance.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="6a3dd-110">启用共享</span><span class="sxs-lookup"><span data-stu-id="6a3dd-110">Enable sharing</span></span>

<span data-ttu-id="6a3dd-111">默认情况下，在 Microsoft 365 中，与组织外部人员共享已启用。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-111">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="6a3dd-112">许多外部共享方案无需进一步配置即可工作。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-112">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="6a3dd-113">若要确认你使用的方案的设置或启用新方案，请从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="6a3dd-113">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="6a3dd-114">协作处理文档[-](collaborate-on-documents.md)了解如何配置 Microsoft 365 以允许与组织外部人员共享和协作 (来宾和未经身份验证的用户) 文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-114">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="6a3dd-115">[在网站中协作](collaborate-in-site.md) - 了解如何配置 Microsoft 365 以允许与来宾共享 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-115">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="6a3dd-116">[团队协作](collaborate-as-team.md) - 了解如何配置 Microsoft 365 以在 Teams 中启用来宾协作。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-116">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="6a3dd-117">有关 Microsoft 365 中提供的来宾共享设置的全面信息，请参阅 [Microsoft 365 来宾共享设置参考](microsoft-365-guest-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-117">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="6a3dd-118">启用其他安全性</span><span class="sxs-lookup"><span data-stu-id="6a3dd-118">Enable additional security</span></span>

<span data-ttu-id="6a3dd-119">启用要用于与组织外部人员共享的方案后，请考虑其他安全措施来帮助保护内容，防止意外或有意不当共享。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-119">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="6a3dd-120">[与未经身份验证的用户](best-practices-anonymous-sharing.md) 共享文件和文件夹的最佳实践 - 了解与未经身份验证的用户共享的最佳方案。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-120">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="6a3dd-121">[限制意外曝光](share-limit-accidental-exposure.md) - 了解如何减少意外与组织外部人员共享敏感内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-121">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="6a3dd-122">[创建安全的来宾](create-secure-guest-sharing-environment.md) 共享环境 - 了解 Microsoft 365 中提供的工具，以帮助确保以安全的方式与组织外部人员共享，并满足管理要求。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-122">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="6a3dd-123">与合作伙伴公司协作</span><span class="sxs-lookup"><span data-stu-id="6a3dd-123">Collaborate with partner companies</span></span>

<span data-ttu-id="6a3dd-124">当你正在处理涉及来自另一个组织的许多来宾的大型项目时，或者如果你具有经常更改来宾的供应商关系，可以使用 Azure Active Directory 中的权利管理来简化来宾管理并允许合作伙伴公司共同承担该责任。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-124">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="6a3dd-125">有关详细信息[，请参阅使用托管来宾创建 B2B Extranet。](b2b-extranet.md)</span><span class="sxs-lookup"><span data-stu-id="6a3dd-125">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="6a3dd-126">限制共享</span><span class="sxs-lookup"><span data-stu-id="6a3dd-126">Limit sharing</span></span>

<span data-ttu-id="6a3dd-127">如果 Microsoft 365 中的某些共享功能与管理策略冲突，请参阅限制 [Microsoft 365](microsoft-365-limit-sharing.md) 中的共享以了解用于限制共享的选项。</span><span class="sxs-lookup"><span data-stu-id="6a3dd-127">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a3dd-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="6a3dd-128">Related topics</span></span>

[<span data-ttu-id="6a3dd-129">Microsoft 365 中的文件协作简介</span><span class="sxs-lookup"><span data-stu-id="6a3dd-129">Intro to file collaboration in Microsoft 365</span></span>](/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="6a3dd-130">使用 Microsoft 365 在 SharePoint 中规划文件协作</span><span class="sxs-lookup"><span data-stu-id="6a3dd-130">Plan file collaboration in SharePoint with Microsoft 365</span></span>](/sharepoint/deploy-file-collaboration)
