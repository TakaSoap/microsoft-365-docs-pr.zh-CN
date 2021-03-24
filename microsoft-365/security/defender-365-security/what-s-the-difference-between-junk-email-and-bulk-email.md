---
title: 垃圾邮件 &apos; 和批量电子邮件之间有什么区别？
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的垃圾邮件和 (灰色) 垃圾邮件 (差异) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056401"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="ff79e-103">EOP 中的垃圾邮件和批量电子邮件之间有什么区别？</span><span class="sxs-lookup"><span data-stu-id="ff79e-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff79e-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="ff79e-104">**Applies to**</span></span>
- [<span data-ttu-id="ff79e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ff79e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ff79e-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="ff79e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ff79e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff79e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ff79e-108">在邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱的 Microsoft 365 组织中，客户有时会问："垃圾邮件和批量电子邮件之间有什么区别？"</span><span class="sxs-lookup"><span data-stu-id="ff79e-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="ff79e-109">本主题介绍区别，并介绍 EOP 中可用的控件。</span><span class="sxs-lookup"><span data-stu-id="ff79e-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="ff79e-110">**垃圾邮件是** 垃圾邮件，如果标识正确，垃圾邮件是未经请求 (不必要的) 。</span><span class="sxs-lookup"><span data-stu-id="ff79e-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="ff79e-111">默认情况下，EOP 根据源电子邮件服务器的信誉拒绝垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ff79e-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="ff79e-112">如果邮件通过源 IP 检查，则发送到垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="ff79e-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="ff79e-113">如果邮件被垃圾邮件筛选分类为垃圾邮件，则默认情况下 (邮件) 目标收件人并移动到其"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ff79e-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="ff79e-114">您可以配置对垃圾邮件筛选裁定采取的操作。</span><span class="sxs-lookup"><span data-stu-id="ff79e-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="ff79e-115">有关说明，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ff79e-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="ff79e-116">如果您对垃圾邮件筛选裁定不一致，您可以通过多种方式向 Microsoft 报告视为垃圾邮件或非垃圾邮件的邮件，如向 Microsoft 报告邮件和文件 [中所述](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="ff79e-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="ff79e-117">**群发** (也称为 _灰色_ 邮件) ，更难分类。</span><span class="sxs-lookup"><span data-stu-id="ff79e-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="ff79e-118">垃圾邮件是一种持续的威胁，而批量电子邮件通常是一次广告或营销邮件。</span><span class="sxs-lookup"><span data-stu-id="ff79e-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="ff79e-119">一些用户希望批量电子邮件 (实际上，他们特意注册以接收这些) ，而其他用户则认为批量电子邮件是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ff79e-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="ff79e-120">例如，一些用户希望接收来自 Contoso Corporation 的广告邮件或邀请参加即将召开的网络安全会议，而其他用户则认为这些相同的邮件是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ff79e-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="ff79e-121">有关如何识别批量电子邮件详细信息，请参阅批量投诉级别 [ (BCL) EOP](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="ff79e-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="ff79e-122">如何管理批量邮件</span><span class="sxs-lookup"><span data-stu-id="ff79e-122">How to manage bulk email</span></span>

<span data-ttu-id="ff79e-123">由于对批量电子邮件的混合反应，没有适用于每个组织的通用指南。</span><span class="sxs-lookup"><span data-stu-id="ff79e-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="ff79e-124">反垃圾邮件策略具有一个默认 BCL 阈值，用于将批量电子邮件标识为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ff79e-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="ff79e-125">管理员可以增加或减小阈值。</span><span class="sxs-lookup"><span data-stu-id="ff79e-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="ff79e-126">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="ff79e-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="ff79e-127">[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ff79e-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="ff79e-128">EOP 反垃圾邮件策略设置</span><span class="sxs-lookup"><span data-stu-id="ff79e-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

<span data-ttu-id="ff79e-129">另一个易于忽略的选项：如果用户抱怨接收批量电子邮件，但邮件来自在 EOP 中通过垃圾邮件筛选的声誉良好的发件人，请让用户检查批量电子邮件中的取消订阅选项。</span><span class="sxs-lookup"><span data-stu-id="ff79e-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
