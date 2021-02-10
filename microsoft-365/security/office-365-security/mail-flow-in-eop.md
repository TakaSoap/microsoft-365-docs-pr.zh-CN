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
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167235"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="5349e-103">EOP 中的邮件流</span><span class="sxs-lookup"><span data-stu-id="5349e-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5349e-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="5349e-104">**Applies to**</span></span>
- [<span data-ttu-id="5349e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5349e-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="5349e-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="5349e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="5349e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5349e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="5349e-108">在具有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，发送到组织的所有邮件都先通过 EOP，然后工作人员才能看到这些邮件。</span><span class="sxs-lookup"><span data-stu-id="5349e-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="5349e-109">在邮件路由到工作收件箱之前，可以通过 EOP 路由邮件进行处理。</span><span class="sxs-lookup"><span data-stu-id="5349e-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="5349e-110">使用邮件和邮件访问选项</span><span class="sxs-lookup"><span data-stu-id="5349e-110">Working with messages and message access options</span></span>

<span data-ttu-id="5349e-111">EOP 提供了邮件路由方式的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5349e-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="5349e-112">以下主题说明了邮件流过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="5349e-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="5349e-113">[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 介绍基于目录的边缘阻止功能，该功能允许您拒绝服务网络外围无效收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="5349e-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="5349e-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。</span><span class="sxs-lookup"><span data-stu-id="5349e-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="5349e-115">如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。</span><span class="sxs-lookup"><span data-stu-id="5349e-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="5349e-116">了解有关在 Exchange Online 中为子域启用邮件流中的[子域。](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="5349e-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="5349e-117">[使用连接器配置邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 将引入连接器，并演示如何使用它们自定义邮件路由。</span><span class="sxs-lookup"><span data-stu-id="5349e-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="5349e-118">方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。</span><span class="sxs-lookup"><span data-stu-id="5349e-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="5349e-119">[连接器的增强](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 筛选功能描述在 EOP 之前将邮件路由到服务或设备时如何配置连接器。</span><span class="sxs-lookup"><span data-stu-id="5349e-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="5349e-120">在独立 EOP 组织中，需要执行几个配置步骤，以确保垃圾邮件正确路由到每个用户的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="5349e-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="5349e-121">这些详细信息在 [配置独立 EOP 以将垃圾邮件发送到](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)混合环境中垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="5349e-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="5349e-122">如果您不想将邮件移动到每个用户的垃圾邮件文件夹，您可以选择其他操作，通过编辑反垃圾邮件策略 (也称为内容筛选器策略) 。</span><span class="sxs-lookup"><span data-stu-id="5349e-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="5349e-123">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5349e-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="5349e-124">验证邮件流</span><span class="sxs-lookup"><span data-stu-id="5349e-124">Verify mail flow</span></span>

<span data-ttu-id="5349e-p106">要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。</span><span class="sxs-lookup"><span data-stu-id="5349e-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="5349e-127">[通过验证 Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) 连接器测试邮件流提供了测试邮件流是否正确设置的说明。</span><span class="sxs-lookup"><span data-stu-id="5349e-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
