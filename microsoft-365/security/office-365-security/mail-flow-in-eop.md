---
title: EOP 中的邮件流
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 Exchange Online Protection (EOP) 中配置邮件流和路由的选项。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c988f58a04abf2322e993ae1b75106a338674acb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289647"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="b1ef1-103">EOP 中的邮件流</span><span class="sxs-lookup"><span data-stu-id="b1ef1-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1ef1-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="b1ef1-104">**Applies to**</span></span>
- [<span data-ttu-id="b1ef1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b1ef1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b1ef1-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b1ef1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b1ef1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1ef1-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b1ef1-108">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，发送到组织的所有邮件都先通过 EOP，然后工作人员才能看到它们。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="b1ef1-109">在将邮件路由到工作收件箱之前，您可以选择如何路由通过 EOP 进行处理的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="b1ef1-110">使用邮件和邮件访问选项</span><span class="sxs-lookup"><span data-stu-id="b1ef1-110">Working with messages and message access options</span></span>

<span data-ttu-id="b1ef1-111">EOP 提供了邮件路由方式的灵活性。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="b1ef1-112">以下主题说明了邮件流过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="b1ef1-113">[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 介绍基于目录的边缘阻止功能，该功能允许您在服务网络外围拒绝无效收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="b1ef1-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="b1ef1-115">如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="b1ef1-116">了解有关在 Exchange Online 中为子域启用邮件流的[子域。](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="b1ef1-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="b1ef1-117">[使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 将引入连接器，并演示如何使用它们自定义邮件路由。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="b1ef1-118">方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="b1ef1-119">[连接器的增强](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 筛选功能描述在邮件路由到 EOP 之前的服务或设备时如何配置连接器。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="b1ef1-120">在独立的 EOP 组织中，需要执行几个配置步骤，以确保垃圾邮件正确路由到每个用户的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="b1ef1-121">这些详细信息在[配置独立 EOP 以将垃圾邮件发送到混合环境的垃圾邮件文件夹。](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="b1ef1-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="b1ef1-122">如果您不想将邮件移动到每个用户的垃圾邮件文件夹，则通过编辑反垃圾邮件策略（也称为内容筛选器策略） (选择另一个) 。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="b1ef1-123">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="b1ef1-124">验证邮件流</span><span class="sxs-lookup"><span data-stu-id="b1ef1-124">Verify mail flow</span></span>

<span data-ttu-id="b1ef1-p106">要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="b1ef1-127">[通过验证 Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) 连接器测试邮件流提供了说明，用于测试邮件流是否正确设置。</span><span class="sxs-lookup"><span data-stu-id="b1ef1-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
