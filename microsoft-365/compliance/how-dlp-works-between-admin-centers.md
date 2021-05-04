---
title: DLP 如何与安全与&中心& Exchange中心一起工作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解安全与合规&中的 DLP 如何与 DLP 和邮件流规则 (管理中心) 传输Exchange规则。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c5249279e1dd04447235aae813128cf458adde03
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114070"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="722df-103">DLP 在安全与合规中心和 Exchange 管理中心中之间的工作原理</span><span class="sxs-lookup"><span data-stu-id="722df-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="722df-104">在Office 365中，可以在两个不同的管理中心 (DLP) 策略创建数据丢失防护：</span><span class="sxs-lookup"><span data-stu-id="722df-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="722df-105">在 **安全&** 合规中心，您可以创建单个 DLP 策略来帮助保护 SharePoint、OneDrive、Exchange 和 Microsoft Teams 中Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="722df-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="722df-106">如果可能，我们建议你在此处创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="722df-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="722df-107">有关详细信息，请参阅数据丢失 [防护参考](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="722df-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="722df-108">在 **Exchange** 管理中心中，您可以创建 DLP 策略以帮助保护仅Exchange。</span><span class="sxs-lookup"><span data-stu-id="722df-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="722df-109">此策略可以使用Exchange规则 (传输规则) ，因此它具有更多特定于处理电子邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="722df-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="722df-110">有关详细信息，请参阅管理中心[中的 DLP Exchange DLP。](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="722df-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="722df-111">在这些管理中心中创建的 DLP 策略并行工作 - 本主题将介绍如何。</span><span class="sxs-lookup"><span data-stu-id="722df-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![安全与合规中心和管理中心Exchange DLP 页面](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="722df-113">安全与合规&中的 DLP 如何与管理中心中的 DLP 和Exchange规则一起工作</span><span class="sxs-lookup"><span data-stu-id="722df-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="722df-114">在安全与合规中心& DLP 策略后，该策略将部署到策略中包含的所有位置。</span><span class="sxs-lookup"><span data-stu-id="722df-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="722df-115">如果策略包含Exchange Online，则策略会同步到该策略，并且强制执行方式与在管理中心中创建的 DLP 策略Exchange完全相同。</span><span class="sxs-lookup"><span data-stu-id="722df-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="722df-116">如果在管理中心内创建了 DLP 策略Exchange，这些策略将继续与在安全与合规中心内创建的任何电子邮件策略&一起工作。</span><span class="sxs-lookup"><span data-stu-id="722df-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="722df-117">但请注意，在管理中心Exchange规则优先。</span><span class="sxs-lookup"><span data-stu-id="722df-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="722df-118">首先Exchange所有邮件流规则，然后处理来自安全与合规& DLP 规则。</span><span class="sxs-lookup"><span data-stu-id="722df-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="722df-119">这意味着：</span><span class="sxs-lookup"><span data-stu-id="722df-119">This means that:</span></span>
  
- <span data-ttu-id="722df-120">邮件流规则Exchange阻止的邮件不会由安全与合规中心中创建的 DLP &扫描。</span><span class="sxs-lookup"><span data-stu-id="722df-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="722df-121">如果 Exchange 邮件流规则修改邮件的方式会导致邮件与安全 & 合规中心中的 DLP 策略匹配（如添加外部用户），则 DLP 规则将检测此情况并根据需要强制执行该策略。</span><span class="sxs-lookup"><span data-stu-id="722df-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="722df-122">另请注意Exchange"停止处理"操作的邮件流规则不会影响安全与合规中心内 DLP &的处理，仍将进行处理。</span><span class="sxs-lookup"><span data-stu-id="722df-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="722df-123">安全与合规中心&策略提示Exchange中心</span><span class="sxs-lookup"><span data-stu-id="722df-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="722df-124">策略提示既可以与在 Exchange 管理中心中创建的 DLP 策略和邮件流规则一起使用，也可以与在安全与合规中心创建的 DLP &一起使用，但不能同时使用。</span><span class="sxs-lookup"><span data-stu-id="722df-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="722df-125">这是因为这些策略存储在不同位置，但策略提示只能从单个位置绘制。</span><span class="sxs-lookup"><span data-stu-id="722df-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="722df-126">如果在 Exchange 管理中心中配置了策略提示，那么在 Outlook 网页版和 Outlook 2013 及更高版本中关闭 Exchange 管理中心中的提示之前，在安全 & 合规中心中配置的任何策略提示将不会向用户显示。</span><span class="sxs-lookup"><span data-stu-id="722df-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="722df-127">这可确保当前Exchange邮件流规则继续工作，直到您选择切换到安全与合规&中心。</span><span class="sxs-lookup"><span data-stu-id="722df-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="722df-128">请注意，虽然策略提示只能从单个位置进行绘制，但始终会发送电子邮件通知，即使您同时在安全与合规中心和 Exchange 管理中心内使用 & DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="722df-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
