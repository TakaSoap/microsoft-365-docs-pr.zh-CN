---
title: 修复发件人域见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解安全 & 合规性中心的 "邮件流" 仪表板中的 "修复发件人域的洞察力"。
ms.openlocfilehash: c4cf4a87ad770325ca6ad2f0b87ac8ce52c345c2
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818827"
---
# <a name="fix-sender-domain-insight"></a><span data-ttu-id="7e168-103">修复发件人域见解</span><span class="sxs-lookup"><span data-stu-id="7e168-103">Fix sender domain insight</span></span>

<span data-ttu-id="7e168-104">Microsoft 365 需要从内部本地电子邮件环境发送到 Microsoft 365 的邮件，以满足特定的安全条件：</span><span class="sxs-lookup"><span data-stu-id="7e168-104">Microsoft 365 requires messages sending from internal on-premises email environments to Microsoft 365 to meet certain security criteria:</span></span>

- <span data-ttu-id="7e168-105">你已在 Microsoft 365 中创建了一个入站连接器，以通过使用源 IP 地址或证书来验证来自你的本地电子邮件服务器的 SMTP 连接。</span><span class="sxs-lookup"><span data-stu-id="7e168-105">You've created an inbound connector in Microsoft 365 to authenticate SMTP connections from your on-premises email server by using the source IP address or a certificate.</span></span>

- <span data-ttu-id="7e168-106">您已将本地电子邮件服务器配置为通过 Microsoft 365 将电子邮件中继到外部世界。</span><span class="sxs-lookup"><span data-stu-id="7e168-106">You've configured your on-premises email server to relay email via Microsoft 365 to external world.</span></span>

- <span data-ttu-id="7e168-107">在您的配置中，下列陈述中的一条为真：</span><span class="sxs-lookup"><span data-stu-id="7e168-107">In your configuration, one of the following statements is true:</span></span>

  - <span data-ttu-id="7e168-108">发件人的电子邮件域已在您的组织中注册。</span><span class="sxs-lookup"><span data-stu-id="7e168-108">The sender's email domain is registered in your organization.</span></span> <span data-ttu-id="7e168-109">有关更多信息，请参阅 在 Office 365 中添加域。</span><span class="sxs-lookup"><span data-stu-id="7e168-109">For more information, see Add Domains in Office 365.</span></span>

  - <span data-ttu-id="7e168-110">您的内部部署电子邮件服务器配置为使用证书向 Microsoft 365 发送电子邮件，证书包含或与您在 Microsoft 365 中注册的域名完全匹配，并且您已在 Microsoft 365 中使用该域创建了一个基于证书的连接器。</span><span class="sxs-lookup"><span data-stu-id="7e168-110">Your on-premises email server is configured to use a certificate to send email to Microsoft 365, the certificate contains or exactly matches a domain name that you've registered in Microsoft 365, and you've created a certificate based connector in Microsoft 365 with that domain.</span></span> 

<span data-ttu-id="7e168-111">不符合条件的邮件将不会被组织到组织中，并且可能会被拒绝。</span><span class="sxs-lookup"><span data-stu-id="7e168-111">Messages that don't meet the criteria will not be attributed to the organization and could be rejected.</span></span>

<span data-ttu-id="7e168-112">**Fix sender domain**真知灼见显示从本地环境中不符合条件的电子邮件，可帮助您识别本地电子邮件环境中可能受到危害的计算机和用户帐户，并帮助您采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="7e168-112">The **Fix sender domain** insight shows you email from your on-premises environment that doesn't meet the criteria, helps you to identify potentially compromised machines and user accounts in your on-premises email environment, and helps you to take remediation actions.</span></span>

![安全 & 合规性中心的邮件流仪表板中的修补发件人域洞察力](../../media/sender-domain-insight-selected.png)

<span data-ttu-id="7e168-114">当您单击 "**查看详细信息**" 时，会转到另一个小部件，其中包含更多详细信息，如下图中所示：</span><span class="sxs-lookup"><span data-stu-id="7e168-114">When you click **View details**, you are taken to another widget with more details as shown in the following diagram:</span></span>

![修复发件人域洞察力中的详细信息小部件](../../media/sender-domain-view-details.png)

<span data-ttu-id="7e168-116">你将看到用于将邮件传递到 Office 365 的入站连接器。</span><span class="sxs-lookup"><span data-stu-id="7e168-116">You'll see the inbound connector that was used to deliver the messages to Office 365.</span></span> <span data-ttu-id="7e168-117">您还可以单击 "**查看示例邮件 id** " 以查看从您的本地电子邮件环境中发送的邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7e168-117">You can also click **view sample message IDs** to see details for the messages that were sent from your on-premises email environment.</span></span> <span data-ttu-id="7e168-118">由于这些邮件是由 Office 365 拒绝的，因此不能使用邮件跟踪，但可以使用示例邮件 id 来跟踪本地电子邮件环境中的邮件。</span><span class="sxs-lookup"><span data-stu-id="7e168-118">Because these messages were rejected by Office 365, you can't use message trace, but you can use the sample message ids to track the messages in your on-premises email environment.</span></span>

![查看修补发件人域洞察力中的示例邮件 id](../../media/sender-domain-view-sample-message-ids.png)

## <a name="related-topics"></a><span data-ttu-id="7e168-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="7e168-120">Related topics</span></span>

<span data-ttu-id="7e168-121">有关邮件流仪表板中的其他邮件流见解的详细信息，请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="7e168-121">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
