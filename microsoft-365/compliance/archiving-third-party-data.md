---
title: 存档第三方数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 了解如何将第三方数据从社交媒体平台、即时消息平台和文档协作平台导入到 Microsoft 365 邮箱。
ms.openlocfilehash: 0db7019b607388b7c62fe19210b85b8410083f32
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035480"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="ea861-103">存档第三方数据</span><span class="sxs-lookup"><span data-stu-id="ea861-103">Archive third-party data</span></span>

<span data-ttu-id="ea861-104">Microsoft 365 使管理员能够从社交媒体平台、即时消息平台和文档协作平台将第三方数据导入和存档到 Microsoft 365 组织中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea861-104">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ea861-105">可以导入到 Microsoft 365 的第三方数据源示例包括以下服务：</span><span class="sxs-lookup"><span data-stu-id="ea861-105">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="ea861-106">**社交：** Facebook、LinkedIn、Twitter 和 Yammer</span><span class="sxs-lookup"><span data-stu-id="ea861-106">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="ea861-107">**即时消息：** Yahoo Messenger 和 GoogleTalk</span><span class="sxs-lookup"><span data-stu-id="ea861-107">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="ea861-108">**文档协作：** Box 和 DropBox</span><span class="sxs-lookup"><span data-stu-id="ea861-108">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="ea861-109">**纵向行业：** 客户关系管理（如 Salesforce Chatter）和金融服务（如 Bloomberg 和 Thomson Reuters）</span><span class="sxs-lookup"><span data-stu-id="ea861-109">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="ea861-110">**短信/短信服务：** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="ea861-110">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="ea861-111">导入第三方数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、就地存档、审核、通信合规性和保留策略）应用于此类数据。</span><span class="sxs-lookup"><span data-stu-id="ea861-111">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="ea861-112">例如，当将邮箱置于诉讼保留状态时，将保留第三方数据。</span><span class="sxs-lookup"><span data-stu-id="ea861-112">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="ea861-113">您可以使用 Microsoft 电子数据展示工具搜索第三方数据。</span><span class="sxs-lookup"><span data-stu-id="ea861-113">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="ea861-114">或者，您可以将存档和保留策略应用于第三方数据，就像 Microsoft 数据一样。</span><span class="sxs-lookup"><span data-stu-id="ea861-114">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="ea861-115">简言之，在 Microsoft 365 中存档第三方数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="ea861-115">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="ea861-116">有两种方法可在 Microsoft 365 中导入和存档第三方数据：</span><span class="sxs-lookup"><span data-stu-id="ea861-116">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="ea861-117">**在安全 & 合规性中心中使用第三方数据连接器：** 使用 Microsoft 365 合规性中心提供的自定义数据连接器。</span><span class="sxs-lookup"><span data-stu-id="ea861-117">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ea861-118">在设置并配置连接器后，它会连接到第三方数据源，将项目的内容转换为电子邮件格式，然后将该项目导入到 Microsoft 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ea861-118">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="ea861-119">目前，您可以实现连接器以导入和存档来自 Facebook 商业页面、公司 Twitter 帐户、LinkedIn、即时 Bloomberg 和组织的人力资源（HR）数据的数据。</span><span class="sxs-lookup"><span data-stu-id="ea861-119">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="ea861-120">有关设置这些连接器之一的分步说明，请参阅：</span><span class="sxs-lookup"><span data-stu-id="ea861-120">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="ea861-121">**Facebook：** [使用连接器存档 Facebook 数据](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="ea861-121">**Facebook:** [Use a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="ea861-122">**Twitter：** [使用连接器存档 Twitter 数据](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="ea861-122">**Twitter:** [Use a connector to archive Twitter data](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="ea861-123">**LinkedIn：** [设置用于存档 LinkedIn 数据的连接器](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="ea861-123">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="ea861-124">**即时 Bloomberg：** [设置连接器以存档即时 Bloomberg 数据](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="ea861-124">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="ea861-125">**HR 数据：** [设置连接器以导入 HR 数据](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="ea861-125">**HR data:** [Set up a connector to import HR data](import-hr-data.md)</span></span>

- <span data-ttu-id="ea861-126">**与 Microsoft 合作伙伴合作：** 您的组织与 Microsoft 合作伙伴合作，该合作伙伴将提供一个自定义连接器，该连接器将配置为定期从第三方数据源提取项目，然后通过第三方 API 连接到 Microsoft 云，并将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ea861-126">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="ea861-127">合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件，然后将其导入到 Microsoft 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ea861-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="ea861-128">有关您可以使用的合作伙伴列表和此方法的分步过程，请参阅[在 Microsoft 365 中使用合作伙伴存档第三方数据](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="ea861-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
