---
title: 将邮件流规则用于邮件中的 SCL
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
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection 中设置邮件的 SCL。
ms.openlocfilehash: cc75130d1e30b4cd64c32b1729c8145ad3088742
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636424"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="2dd0a-103">使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)</span><span class="sxs-lookup"><span data-stu-id="2dd0a-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="2dd0a-104">如果您是 Exchange Online 邮箱或独立 Exchange Online Protection （EOP）客户（没有 Exchange Online 邮箱）的 Microsoft 365 客户，则 EOP 使用反垃圾邮件策略（也称为垃圾邮件筛选器策略或内容筛选器策略）来扫描入站邮件中的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-104">If you're a Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="2dd0a-105">有关详细信息，请参阅[在 Office 365 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="2dd0a-106">如果要将特定邮件标记为垃圾邮件，然后再通过垃圾邮件筛选进行扫描，或将邮件标记为跳过垃圾邮件筛选，则可以创建邮件流规则（也称为传输规则），以标识邮件并设置垃圾邮件可信度（SCL）。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="2dd0a-107">有关 SCL 的详细信息，请参阅[Office 365 中的垃圾邮件可信度（SCL）](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-107">For more information about the SCL, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2dd0a-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2dd0a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2dd0a-109">您需要先在 Exchange Online 中分配权限，然后才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="2dd0a-110">具体来说，您需要分配 "**传输规则**" 角色，默认情况下会将其分配给 "**组织管理**"、"**合规性管理**" 和 "**记录管理**" 角色。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="2dd0a-111">有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="2dd0a-112">若要在 Exchange Online 中打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="2dd0a-113">有关 Exchange Online 中的邮件流规则的详细信息，请参阅[Exchange online 中的邮件流规则（传输规则）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="2dd0a-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="2dd0a-114">使用 EAC 创建邮件流规则，以设置邮件的 SCL</span><span class="sxs-lookup"><span data-stu-id="2dd0a-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="2dd0a-115">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="2dd0a-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="2dd0a-116">单击 "**添加** !["](../../media/ITPro-EAC-AddIcon.png) "添加" 图标，然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="2dd0a-117">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="2dd0a-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2dd0a-118">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="2dd0a-119">单击“其他选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-119">Click **More Options**.</span></span>

   - <span data-ttu-id="2dd0a-120">**在以下情况应用此规则**：选择一个或多个条件来标识邮件。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="2dd0a-121">有关详细信息，请参阅[Exchange Online 中的邮件流规则条件和例外（谓词）](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="2dd0a-122">**执行以下**操作：选择 "**修改邮件属性** \> **" 设置垃圾邮件可信度（SCL）**。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="2dd0a-123">在出现的 "**指定 SCL** " 对话框中，配置下列值之一：</span><span class="sxs-lookup"><span data-stu-id="2dd0a-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="2dd0a-124">**绕过垃圾邮件筛选**：这会将 SCL 设置为-1，这意味着邮件将跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-124">**Bypass spam filtering**: This sets the SCL to -1, which means the messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="2dd0a-125">务必小心允许邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="2dd0a-126">攻击者可以利用此漏洞将网络钓鱼和其他恶意邮件发送到您的组织中。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="2dd0a-127">邮件流规则需要的不仅仅是发件人的电子邮件地址或域。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="2dd0a-128">有关详细信息，请参阅[在 Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-128">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="2dd0a-129">**0 到 4**：通过垃圾邮件筛选发送邮件以进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="2dd0a-130">**5 或 6**：邮件被标记为**垃圾**邮件。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="2dd0a-131">您为反垃圾邮件策略中的**垃圾**邮件筛选 verdicts 配置的操作将应用于该邮件（默认值为 "**将邮件移动到垃圾邮件" 文件夹**）。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="2dd0a-132">**7 至 9**：将邮件标记为**高可信度垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="2dd0a-133">您为**高可信度垃圾**邮件筛选 verdicts 配置的操作将应用于该邮件（默认值为 "**将邮件移动到垃圾邮件" 文件夹**）。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="2dd0a-134">为规则指定所需的任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="2dd0a-135">完成后，单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2dd0a-136">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="2dd0a-136">How do you know this worked?</span></span>

<span data-ttu-id="2dd0a-137">要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="2dd0a-138">例如，如果**将垃圾邮件可信度（SCL）设置**为 "**绕过垃圾邮件筛选**"，则应将邮件发送到指定收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="2dd0a-139">但是，如果您**将垃圾邮件可信度（SCL）设置**为**9**，并且适用的内容筛选器策略的**高可信度垃圾邮件**操作是将邮件移至 "垃圾邮件" 文件夹，则邮件应发送到指定收件人的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2dd0a-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
