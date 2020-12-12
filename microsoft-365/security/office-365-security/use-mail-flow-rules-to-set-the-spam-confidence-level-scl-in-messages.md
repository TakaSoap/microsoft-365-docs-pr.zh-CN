---
title: 在邮件中将邮件流规则用于 SCL
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
description: 了解如何创建邮件流规则 (传输规则) 标识邮件，以及设置 Exchange Online Protection 中邮件的 (SCL) 垃圾邮件可信度。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659833"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="e4b43-103">使用邮件流规则在 EOP 中的 (SCL) 设置垃圾邮件可信度</span><span class="sxs-lookup"><span data-stu-id="e4b43-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4b43-104">在具有 Exchange Online 邮箱的 Microsoft 365 组织或独立 Exchange Online Protection (EOP) 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 扫描入站邮件中的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="e4b43-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="e4b43-105">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b43-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e4b43-106">如果要在垃圾邮件筛选扫描特定邮件之前将其标记为垃圾邮件，或者将邮件标记为跳过垃圾邮件筛选，可以创建邮件流规则 (也称为传输规则) 以标识邮件，并设置垃圾邮件可信度 (SCL) 。</span><span class="sxs-lookup"><span data-stu-id="e4b43-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="e4b43-107">有关 SCL 详细信息，请参阅 [EOP](spam-confidence-levels.md)中 SCL (垃圾邮件) 级别。</span><span class="sxs-lookup"><span data-stu-id="e4b43-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4b43-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="e4b43-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4b43-109">您需在 Exchange Online 或 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="e4b43-109">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="e4b43-110">具体来说，您需要传输 **规则** 角色，默认情况下，该角色分配给组织管理、合规性 **管理 (全局** 管理员) 和 **记录** 管理角色组。</span><span class="sxs-lookup"><span data-stu-id="e4b43-110">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="e4b43-111">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e4b43-111">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="e4b43-112">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="e4b43-112">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="e4b43-113">独立 EOP 中的权限</span><span class="sxs-lookup"><span data-stu-id="e4b43-113">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="e4b43-114">使用 EAC 修改角色组的成员列表</span><span class="sxs-lookup"><span data-stu-id="e4b43-114">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="e4b43-115">若要在 Exchange Online 中打开 EAC，请参阅 Exchange Online 中的 [Exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="e4b43-115">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="e4b43-116">若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b43-116">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e4b43-117">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e4b43-117">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e4b43-118">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e4b43-118">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e4b43-119">有关 Exchange Online 和 Exchange Online Protection 中的邮件流规则详细信息，请参阅 Exchange Online 中的邮件流规则 ([传输) 规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="e4b43-119">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="e4b43-120">使用 EAC 创建设置邮件 SCL 的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="e4b43-120">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="e4b43-121">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="e4b43-121">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="e4b43-122">单击 **"** ![ 添加" ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择 **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="e4b43-122">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="e4b43-123">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="e4b43-123">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="e4b43-124">**名称**：为规则输入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="e4b43-124">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="e4b43-125">单击“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="e4b43-125">Click **More Options**.</span></span>

   - <span data-ttu-id="e4b43-126">**如果：选择** 一个或多个条件来标识邮件，则应用此规则。</span><span class="sxs-lookup"><span data-stu-id="e4b43-126">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="e4b43-127">有关详细信息，请参阅 Exchange Online 中的邮件流 [规则 (和) 例外](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="e4b43-127">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="e4b43-128">**执行以下操作：** 选择 **"修改邮件属性** \> **"设置 SCL (垃圾邮件可信度) 。**</span><span class="sxs-lookup"><span data-stu-id="e4b43-128">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="e4b43-129">在 **出现的"指定 SCL"** 对话框中，配置下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e4b43-129">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="e4b43-130">**绕过垃圾邮件筛选**：邮件将跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="e4b43-130">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="e4b43-131">在允许邮件跳过垃圾邮件筛选时请非常小心。</span><span class="sxs-lookup"><span data-stu-id="e4b43-131">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="e4b43-132">攻击者可以使用此漏洞向组织发送网络钓鱼和其他恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="e4b43-132">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="e4b43-133">邮件流规则需要的不仅仅是发件人的电子邮件地址或域。</span><span class="sxs-lookup"><span data-stu-id="e4b43-133">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="e4b43-134">有关详细信息，请参阅在 [EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b43-134">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="e4b43-135">**0 到 4：** 邮件通过垃圾邮件筛选进行发送，以进一步处理。</span><span class="sxs-lookup"><span data-stu-id="e4b43-135">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="e4b43-136">**5 或 6：** 邮件被 **标记为垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="e4b43-136">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="e4b43-137">为反垃圾邮件策略中的垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件"文件夹) 。 </span><span class="sxs-lookup"><span data-stu-id="e4b43-137">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="e4b43-138">**7 到 9：** 邮件被标记为 **高可信度垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="e4b43-138">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="e4b43-139">为反垃圾邮件策略中的高可信度垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件"文件夹) 。 </span><span class="sxs-lookup"><span data-stu-id="e4b43-139">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="e4b43-140">指定规则需要的任何附加属性。</span><span class="sxs-lookup"><span data-stu-id="e4b43-140">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="e4b43-141">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="e4b43-141">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e4b43-142">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="e4b43-142">How do you know this worked?</span></span>

<span data-ttu-id="e4b43-143">要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。</span><span class="sxs-lookup"><span data-stu-id="e4b43-143">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="e4b43-144">例如，如果将 SCL 的垃圾邮件可信度 **(SCL**) **绕过** 垃圾邮件筛选，则邮件应发送到指定收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="e4b43-144">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="e4b43-145">但是，如果将垃圾邮件可信度 **(SCL)** 设置为 **9，** 并且适用的反垃圾邮件策略的高可信度垃圾邮件操作是将邮件移动到"垃圾邮件"文件夹，则邮件应发送到指定收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4b43-145">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
