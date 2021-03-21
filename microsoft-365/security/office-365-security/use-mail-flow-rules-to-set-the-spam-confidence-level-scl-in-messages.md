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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 了解如何创建邮件流规则 (传输规则) 标识邮件，以及如何在 Exchange Online Protection 中将 (SCL) 设置为垃圾邮件可信度。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d7d1de194d8529fd3cf3e2d1da68c1f928ffcfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921128"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="6293f-103">使用邮件流规则在 EOP 中的 (SCL) 设置垃圾邮件可信度</span><span class="sxs-lookup"><span data-stu-id="6293f-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6293f-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="6293f-104">**Applies to**</span></span>
- [<span data-ttu-id="6293f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6293f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6293f-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="6293f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6293f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6293f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6293f-108">在具有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，EOP 使用反垃圾邮件策略 (也称为垃圾邮件筛选器策略或内容筛选器策略) 扫描入站邮件中的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="6293f-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="6293f-109">有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6293f-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="6293f-110">如果您希望在垃圾邮件筛选扫描特定邮件之前将其标记为垃圾邮件，或将邮件标记为跳过垃圾邮件筛选，您可以创建邮件流规则 (也称为传输规则) 以标识邮件，并设置垃圾邮件可信度 (SCL) 。</span><span class="sxs-lookup"><span data-stu-id="6293f-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="6293f-111">有关 SCL 详细信息，请参阅 [EOP](spam-confidence-levels.md)中的垃圾邮件 (SCL) 级别。</span><span class="sxs-lookup"><span data-stu-id="6293f-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6293f-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="6293f-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6293f-113">您需在 Exchange Online 或 Exchange Online Protection 中分配权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="6293f-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="6293f-114">具体来说，您需要传输规则角色，默认情况下，该角色分配给组织管理、合规性 **管理 (全局** 管理员) 角色组和 **记录** 管理角色组。</span><span class="sxs-lookup"><span data-stu-id="6293f-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="6293f-115">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="6293f-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="6293f-116">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="6293f-116">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="6293f-117">独立 EOP 中的权限</span><span class="sxs-lookup"><span data-stu-id="6293f-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="6293f-118">使用 EAC 修改角色组的成员列表</span><span class="sxs-lookup"><span data-stu-id="6293f-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="6293f-119">若要在 Exchange Online 中打开 EAC，请参阅 [Exchange Online 中的 Exchange 管理中心](/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="6293f-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="6293f-120">若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="6293f-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="6293f-121">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6293f-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6293f-122">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6293f-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6293f-123">有关 Exchange Online 和 Exchange Online Protection 中的邮件流规则详细信息，请参阅 Mail [flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="6293f-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="6293f-124">使用 EAC 创建设置邮件 SCL 的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="6293f-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="6293f-125">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="6293f-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="6293f-126">单击 **添加** ![ 添加图标 ](../../media/ITPro-EAC-AddIcon.png) ，然后选择 **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="6293f-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="6293f-127">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="6293f-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="6293f-128">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="6293f-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="6293f-129">单击“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="6293f-129">Click **More Options**.</span></span>

   - <span data-ttu-id="6293f-130">**在 以下情况下应用此规则**：选择一个或多个条件来标识邮件。</span><span class="sxs-lookup"><span data-stu-id="6293f-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="6293f-131">有关详细信息，请参阅 Mail [flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="6293f-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="6293f-132">**执行以下操作：选择\*\*\*\*"修改邮件属性** \> **"设置 SCL (垃圾邮件可信度) 。**</span><span class="sxs-lookup"><span data-stu-id="6293f-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="6293f-133">在出现的 **"指定 SCL"** 对话框中，配置下列值之一：</span><span class="sxs-lookup"><span data-stu-id="6293f-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="6293f-134">**绕过垃圾邮件筛选**：邮件将跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="6293f-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="6293f-135">请谨慎允许邮件跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="6293f-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="6293f-136">攻击者可以使用此漏洞向组织发送网络钓鱼邮件和其他恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="6293f-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="6293f-137">邮件流规则需要的不仅仅是发件人的电子邮件地址或域。</span><span class="sxs-lookup"><span data-stu-id="6293f-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="6293f-138">有关详细信息，请参阅在 [EOP 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="6293f-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="6293f-139">**0 到 4：** 邮件通过垃圾邮件筛选进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="6293f-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="6293f-140">**5 或 6：** 邮件被标记为"垃圾邮件 **"。**</span><span class="sxs-lookup"><span data-stu-id="6293f-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="6293f-141">为反垃圾邮件策略中的垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="6293f-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="6293f-142">**7 到 9：** 邮件被标记为 **高可信度垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="6293f-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="6293f-143">为反垃圾邮件策略中的高可信度垃圾邮件筛选裁定配置的操作将应用于邮件 (默认值为"将邮件移动到垃圾邮件文件夹") 。 </span><span class="sxs-lookup"><span data-stu-id="6293f-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="6293f-144">指定规则需要的任何附加属性。</span><span class="sxs-lookup"><span data-stu-id="6293f-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="6293f-145">完成后，单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="6293f-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6293f-146">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="6293f-146">How do you know this worked?</span></span>

<span data-ttu-id="6293f-147">要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。</span><span class="sxs-lookup"><span data-stu-id="6293f-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="6293f-148">例如，如果将垃圾邮件可信度设置为 **(SCL** **) "绕过** 垃圾邮件筛选"，则邮件应发送到指定收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="6293f-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="6293f-149">但是，如果将垃圾邮件可信度 **(SCL)** 设置为 **9，** 并且适用反垃圾邮件策略的高可信度垃圾邮件操作是将邮件移动到"垃圾邮件"文件夹，则邮件应发送到指定收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="6293f-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>