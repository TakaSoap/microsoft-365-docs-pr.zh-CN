---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用邮件流规则 (传输规则) 接收用户向 Microsoft 报告的邮件副本。
ms.openlocfilehash: 0f3046c9d1962366ffd75353347b6cf7b72afd14
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659845"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="f5727-103">使用邮件流规则来查看用户向 Microsoft 报告的内容</span><span class="sxs-lookup"><span data-stu-id="f5727-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f5727-104">在 Exchange Online 中拥有邮箱的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，用户有多种方法将邮件报告给 Microsoft 进行分析，如向 [Microsoft](report-junk-email-messages-to-microsoft.md)报告邮件和文件中所述。</span><span class="sxs-lookup"><span data-stu-id="f5727-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="f5727-105">您可以创建邮件流规则 (也称为传输规则) ，用于查找用户向 Microsoft 报告的邮件，还可以将"Bcc"收件人配置为接收这些报告的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="f5727-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="f5727-106">您可以在 Exchange 管理中心 (EAC) 和 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织创建邮件流规则;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。</span><span class="sxs-lookup"><span data-stu-id="f5727-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f5727-107">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="f5727-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f5727-108">您需在 Exchange Online 或 Exchange Online Protection 中获得权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="f5727-108">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f5727-109">具体来说，您需要传输 **规则** 角色，默认情况下，该角色分配给组织管理、合规性 **管理 (全局** 管理员) 和 **记录** 管理角色组。</span><span class="sxs-lookup"><span data-stu-id="f5727-109">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="f5727-110">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f5727-110">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="f5727-111">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="f5727-111">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="f5727-112">独立 EOP 中的权限</span><span class="sxs-lookup"><span data-stu-id="f5727-112">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="f5727-113">使用 EAC 修改角色组的成员列表</span><span class="sxs-lookup"><span data-stu-id="f5727-113">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="f5727-114">若要在 Exchange Online 中打开 EAC，请参阅 Exchange Online 中的 [Exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f5727-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="f5727-115">若要在独立 EOP 中打开 EAC，请参阅 [独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="f5727-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f5727-116">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f5727-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f5727-117">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f5727-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f5727-118">有关 Exchange Online 和独立 EOP 中的邮件流规则详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f5727-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="f5727-119">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="f5727-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="f5727-120">Exchange Online 中的邮件流规则 (和) 例外</span><span class="sxs-lookup"><span data-stu-id="f5727-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="f5727-121">Exchange Online 中的邮件流规则操作</span><span class="sxs-lookup"><span data-stu-id="f5727-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="f5727-122">使用 EAC 创建邮件流规则以接收报告的邮件副本</span><span class="sxs-lookup"><span data-stu-id="f5727-122">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="f5727-123">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="f5727-123">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="f5727-124">单击 **"** ![ 添加" ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择 **"创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="f5727-124">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="f5727-125">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="f5727-125">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f5727-126">**名称**：为规则输入唯一的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="f5727-126">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="f5727-127">例如，向 Microsoft 报告的"Bcc 邮件"。</span><span class="sxs-lookup"><span data-stu-id="f5727-127">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="f5727-128">单击“其他选项”。</span><span class="sxs-lookup"><span data-stu-id="f5727-128">Click **More Options**.</span></span>

   - <span data-ttu-id="f5727-129">如果 \>  ![ ：选择"收件人地址包含以下任何词语："在出现的"指定单词或短语"对话框中，输入下列值之一，单击"添加图标"，然后重复，直到输入所有值。 ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="f5727-129">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="f5727-130">若要编辑条目，请选择它，然后单击" **编辑编辑"** ![ 图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="f5727-130">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="f5727-131">若要删除条目，请选择它，然后单击 **"删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="f5727-131">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="f5727-132">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="f5727-132">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="f5727-133">**执行以下操作：** 选择 **"将收件人** \> **添加到"Bcc 框**。</span><span class="sxs-lookup"><span data-stu-id="f5727-133">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="f5727-134">在出现的对话框中，查找并选择要添加的收件人。</span><span class="sxs-lookup"><span data-stu-id="f5727-134">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="f5727-135">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="f5727-135">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="f5727-136">您可以进行其他选择，以审核规则、测试规则、激活特定时间段的规则和其他设置。</span><span class="sxs-lookup"><span data-stu-id="f5727-136">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="f5727-137">建议在强制执行规则之前测试它。</span><span class="sxs-lookup"><span data-stu-id="f5727-137">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="f5727-138">完成时，请单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="f5727-138">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="f5727-139">使用 PowerShell 创建邮件流规则以接收报告的邮件副本</span><span class="sxs-lookup"><span data-stu-id="f5727-139">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="f5727-140">本示例创建一个名为"Bcc Messages Reported to Microsoft"的新邮件流规则，该规则使用本文中所述的方法查找报告给 Microsoft 的电子邮件，并将用户 laura@contoso.com 和 julia@contoso.com 添加为"Bcc"收件人。</span><span class="sxs-lookup"><span data-stu-id="f5727-140">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="f5727-141">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="f5727-141">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f5727-142">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="f5727-142">How do you know this worked?</span></span>

<span data-ttu-id="f5727-143">若要验证您是否已配置邮件流规则以接收报告的邮件副本，请执行下列任一步骤：</span><span class="sxs-lookup"><span data-stu-id="f5727-143">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="f5727-144">在 EAC 中，转到"**邮件流** \> **规则**" \> 选择规则 \> ，单击"编辑 ![ 编辑"图标 ](../../media/ITPro-EAC-EditIcon.png) ，然后验证设置。</span><span class="sxs-lookup"><span data-stu-id="f5727-144">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="f5727-145">在 PowerShell 中，运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="f5727-145">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="f5727-146">将测试邮件发送到其中一个报告电子邮件地址并验证结果。</span><span class="sxs-lookup"><span data-stu-id="f5727-146">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
