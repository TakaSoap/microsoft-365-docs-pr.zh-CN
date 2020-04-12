---
title: 垃圾邮件和批量邮件之间有什么差异？
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: 本主题说明了垃圾邮件（垃圾邮件）和批量电子邮件之间的区别以及 Office 365 中的相关控件。
ms.openlocfilehash: 41dedd02febc40b73dc585961487f89bbc6db54a
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230952"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="e6b78-103">垃圾邮件和群发电子邮件有何区别？</span><span class="sxs-lookup"><span data-stu-id="e6b78-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="e6b78-104">Office 365 客户，其中邮箱位于 Exchange Online 或独立 Exchange Online Protection （EOP）中没有 Exchange Online 邮箱的客户有时会问： "垃圾邮件和批量电子邮件的区别是什么？"</span><span class="sxs-lookup"><span data-stu-id="e6b78-104">Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="e6b78-105">本主题介绍 EOP 中可用的控件的区别和说明。</span><span class="sxs-lookup"><span data-stu-id="e6b78-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="e6b78-106">**垃圾邮件**是垃圾邮件，它是未经请求和普遍不需要的邮件（如果正确标识了）。</span><span class="sxs-lookup"><span data-stu-id="e6b78-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="e6b78-107">默认情况下，EOP 会根据源电子邮件服务器的信誉拒绝垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e6b78-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="e6b78-108">如果邮件通过源 IP 检查，则会将其发送到垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="e6b78-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="e6b78-109">如果通过垃圾邮件筛选功能将邮件分类为垃圾邮件，则邮件将被传递到预期收件人并移动到其 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e6b78-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="e6b78-110">您可以配置要对垃圾邮件筛选 verdicts 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e6b78-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="e6b78-111">有关说明，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b78-111">For instructions, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="e6b78-112">如果您不同意垃圾邮件筛选结论，可以通过多种方式报告您认为是垃圾邮件或非垃圾邮件的邮件，如[向 Microsoft 报告邮件和文件](report-junk-email-messages-to-microsoft.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="e6b78-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="e6b78-113">**批量电子邮件**（也称为 "_灰色邮件_"）是更难分类的。</span><span class="sxs-lookup"><span data-stu-id="e6b78-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="e6b78-114">垃圾邮件是一种恒定的威胁，而批量电子邮件通常是一次性广告或市场营销邮件。</span><span class="sxs-lookup"><span data-stu-id="e6b78-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="e6b78-115">某些用户需要批量电子邮件（事实上，他们已特意注册接收它们），而其他用户认为批量电子邮件是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e6b78-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="e6b78-116">例如，某些用户希望接收来自 Contoso Corporation 的广告邮件或对即将到来的会议的网络安全的邀请，而其他用户认为这些邮件是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e6b78-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="e6b78-117">有关标识批量电子邮件的详细信息，请参阅[Office 365 中的大宗投诉级别（BCL）](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b78-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="e6b78-118">如何管理批量邮件</span><span class="sxs-lookup"><span data-stu-id="e6b78-118">How to manage bulk email</span></span>

<span data-ttu-id="e6b78-119">由于批量电子邮件的混合反应，没有适用于每个组织的通用指南。</span><span class="sxs-lookup"><span data-stu-id="e6b78-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="e6b78-120">反垃圾邮件策略具有用于将批量电子邮件标识为垃圾邮件的默认 BCL 阈值。</span><span class="sxs-lookup"><span data-stu-id="e6b78-120">Anti-spam policies have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="e6b78-121">管理员可以增加或减少阈值。</span><span class="sxs-lookup"><span data-stu-id="e6b78-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="e6b78-122">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e6b78-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="e6b78-123">[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e6b78-123">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="e6b78-124">EOP 反垃圾邮件策略设置</span><span class="sxs-lookup"><span data-stu-id="e6b78-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="e6b78-125">易于忽略的另一个选项：如果用户 complains 接收批量电子邮件，但邮件来自传递 EOP 中的垃圾邮件筛选的著名发件人，请让用户在批量电子邮件中检查是否有 "取消订阅" 选项。</span><span class="sxs-lookup"><span data-stu-id="e6b78-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
