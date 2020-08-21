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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解在 Exchange Online Protection 和 EOP 应用程序中配置邮件流 () 。
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827721"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="3efad-103">EOP 中的邮件流</span><span class="sxs-lookup"><span data-stu-id="3efad-103">Mail flow in EOP</span></span>

<span data-ttu-id="3efad-104">在有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。</span><span class="sxs-lookup"><span data-stu-id="3efad-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="3efad-105">你可以选择如何路由邮件，这些邮件通过 EOP 处理，然后才能路由到工作人员收件箱。</span><span class="sxs-lookup"><span data-stu-id="3efad-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="3efad-106">使用邮件和邮件访问选项</span><span class="sxs-lookup"><span data-stu-id="3efad-106">Working with messages and message access options</span></span>

<span data-ttu-id="3efad-107">EOP 在您的邮件路由方法上提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="3efad-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="3efad-108">以下主题说明了邮件流过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="3efad-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="3efad-109">[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 介绍基于目录的边缘阻止功能，允许您拒绝在服务网络外围向无效收件人发送邮件。</span><span class="sxs-lookup"><span data-stu-id="3efad-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="3efad-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。</span><span class="sxs-lookup"><span data-stu-id="3efad-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="3efad-111">如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。</span><span class="sxs-lookup"><span data-stu-id="3efad-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="3efad-112">在 Exchange Online 中为 [子域启用邮件流，了解有关子域的详细信息](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="3efad-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="3efad-113">[配置使用连接器的邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介绍了连接器，并演示如何使用连接器自定义邮件路由。</span><span class="sxs-lookup"><span data-stu-id="3efad-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="3efad-114">方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。</span><span class="sxs-lookup"><span data-stu-id="3efad-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="3efad-115">[适用于连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 介绍了在 EOP 之前，如果邮件已路由到服务或设备，如何配置连接器。</span><span class="sxs-lookup"><span data-stu-id="3efad-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="3efad-116">在独立 EOP 组织中，您需要执行几个配置步骤，以确保垃圾邮件正确路由到每个用户的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="3efad-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="3efad-117">这些信息在" [配置独立 EOP"中详细说明了如何向混合环境中的"垃圾邮件"文件夹递送垃圾邮件](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="3efad-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="3efad-118">如果您不想将邮件移至每个用户的垃圾电子邮件文件夹，可以选择其他操作，方法为编辑反垃圾邮件策略 (也称为内容筛选策略) 。</span><span class="sxs-lookup"><span data-stu-id="3efad-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="3efad-119">有关详细信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3efad-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="3efad-120">验证邮件流</span><span class="sxs-lookup"><span data-stu-id="3efad-120">Verify mail flow</span></span>

<span data-ttu-id="3efad-p106">要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。</span><span class="sxs-lookup"><span data-stu-id="3efad-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="3efad-123">[通过验证 Microsoft 365 连接器来测试邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) ，该说明提供了测试您的邮件流设置正确的说明。</span><span class="sxs-lookup"><span data-stu-id="3efad-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
