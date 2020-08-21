---
title: 使用邮件流规则至邮件中 SCL
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 了解如何创建邮件流规则 (传输规则) 以标识邮件，并设置 Exchange Online Protection 中邮件的 (可信度) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827369"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="b29e6-103">使用邮件流规则设置 EOP 中邮件中邮件 (可信) 性</span><span class="sxs-lookup"><span data-stu-id="b29e6-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

<span data-ttu-id="b29e6-104">在有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 来扫描入站邮件中的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b29e6-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="b29e6-105">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b29e6-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="b29e6-106">如果想要在垃圾邮件筛选被垃圾邮件筛选之前将特定邮件标记为垃圾邮件，或将邮件标记为跳过垃圾邮件筛选，可以创建邮件流规则 (也称为传输规则) 来标识邮件，并设置垃圾邮件可信度为 (SCL) 。</span><span class="sxs-lookup"><span data-stu-id="b29e6-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="b29e6-107">有关 SCL 的详细信息，请参阅["垃圾邮件可信度" (在 EOP (的") SCL"。](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="b29e6-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b29e6-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="b29e6-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b29e6-109">必须先分配有 Exchange Online 中的权限，才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="b29e6-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="b29e6-110">具体而下，您需分配 **Transport Rules** role， which is assigned to the **Organization Management**， Compliance **Management，** and **Records Management** roles by default.</span><span class="sxs-lookup"><span data-stu-id="b29e6-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="b29e6-111">有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="b29e6-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="b29e6-112">若要在 Exchange Online 中打开 EAC，请参阅[Exchange Online 中的"Exchange 管理中心"。](https://docs.microsoft.com/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="b29e6-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="b29e6-113">若要详细了解 Exchange Online 中的邮件流规则，请参阅 [Exchange Online (传输规则) 邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="b29e6-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="b29e6-114">使用 EAC 创建设置邮件的 SCL 的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="b29e6-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="b29e6-115">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="b29e6-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="b29e6-116">单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择"**创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="b29e6-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="b29e6-117">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="b29e6-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="b29e6-118">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="b29e6-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="b29e6-119">单击“其他选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b29e6-119">Click **More Options**.</span></span>

   - <span data-ttu-id="b29e6-120">**在以下情况应用此**规则：选择一个或多个条件以标识邮件。</span><span class="sxs-lookup"><span data-stu-id="b29e6-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="b29e6-121">有关详细信息，请参阅 [邮件流规则条件和例外， (Exchange Online 中的谓词) 例外](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="b29e6-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="b29e6-122">**执行以下操作：** 选择 **"修改邮件** \> \*\*属性"，然后将垃圾邮件可信度设为 (SCL) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="b29e6-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="b29e6-123">在出现 **的"指定 SCL"** 对话框中，配置以下值之一：</span><span class="sxs-lookup"><span data-stu-id="b29e6-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="b29e6-124">**不使用垃圾邮件筛选**：邮件将跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="b29e6-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="b29e6-125">在允许邮件跳过垃圾邮件筛选时请非常细心。</span><span class="sxs-lookup"><span data-stu-id="b29e6-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="b29e6-126">攻击者可以使用此漏洞将网络钓鱼和其他恶意邮件发送到你的组织。</span><span class="sxs-lookup"><span data-stu-id="b29e6-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="b29e6-127">邮件流规则不仅需要发件人的电子邮件地址或域。</span><span class="sxs-lookup"><span data-stu-id="b29e6-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="b29e6-128">有关详细信息，请参阅"[在 EOP 中创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="b29e6-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="b29e6-129">**0 到 4：** 邮件通过垃圾邮件筛选发送以进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="b29e6-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="b29e6-130">**5 或 6：** 邮件被标记为 **垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="b29e6-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="b29e6-131">您在反垃圾邮件策略中为 **垃圾邮件** 筛选欺词配置的操作将应用于邮件 (默认值为将 **邮件移至垃圾邮件** 文件夹的) 。</span><span class="sxs-lookup"><span data-stu-id="b29e6-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="b29e6-132">**7 到 9：** 邮件被标记**为"高可信度垃圾邮件"。**</span><span class="sxs-lookup"><span data-stu-id="b29e6-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="b29e6-133">您在反垃圾邮件策略中为 **高可信度垃圾邮件** 筛选反应器配置的操作将应用到邮件 (默认值为 **将邮件移至垃圾邮件文件夹**) 。</span><span class="sxs-lookup"><span data-stu-id="b29e6-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="b29e6-134">为规则指定任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="b29e6-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="b29e6-135">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b29e6-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b29e6-136">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="b29e6-136">How do you know this worked?</span></span>

<span data-ttu-id="b29e6-137">要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。</span><span class="sxs-lookup"><span data-stu-id="b29e6-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="b29e6-138">例如，如果您**将垃圾邮件可信度 (SCL) 设置为\*\*\*\*"不使用垃圾邮件筛选**"，则该邮件应被发送至指定收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="b29e6-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="b29e6-139">但是，如果您 \*\*将垃圾邮件可信度 (SCL) \*\* 设置为 **9，** 并且 **适用的** 反垃圾邮件策略的"高可信度垃圾邮件"会将该邮件移至"垃圾邮件"文件夹，那么该邮件应被发送至指定收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b29e6-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
