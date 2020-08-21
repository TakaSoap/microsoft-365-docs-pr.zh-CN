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
description: 管理员可以了解如何使用邮件流规则和 (也称为传输规则，) 以接收用户向 Microsoft 报告的邮件副本。
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827381"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="d1661-103">使用邮件流规则来查看用户向 Microsoft 报告的内容</span><span class="sxs-lookup"><span data-stu-id="d1661-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="d1661-104">在有 Exchange Online 邮箱的 Microsoft 365 组织中，或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，如"向 Microsoft 报告邮件和文件"中所述，用户可以通过多种方式向 Microsoft 报告邮件以 [供分析](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="d1661-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="d1661-105">你可以创建邮件流规则 (也称为传输规则) 后者，用于查找用户向 Microsoft 报告的邮件，还可以将"抄送"收件人配置为接收这些报告的邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="d1661-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="d1661-106">你可以在 Exchange 管理中心 (EAC) 和 PowerShell (Exchange Online PowerShell 为具有 Exchange Online 邮箱的 Exchange Online PowerShell 创建邮件流规则;独立 EOP PowerShell 适用于没有 Exchange Online 邮箱和站点) 。</span><span class="sxs-lookup"><span data-stu-id="d1661-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d1661-107">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="d1661-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d1661-108">必须先在 Exchange Online 或 EOP 中分配有权限，才能执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d1661-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="d1661-109">具体而下，您需分配 **Transport Rules** role， which is assigned to the **Organization Management**， Compliance **Management，** and **Records Management** roles by default.</span><span class="sxs-lookup"><span data-stu-id="d1661-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="d1661-110">有关详细信息，请参阅[在 Exchange Online 中管理角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="d1661-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="d1661-111">要打开 EAC，请参阅 [Exchange Online 中的 Exchange](https://docs.microsoft.com/Exchange/exchange-admin-center) 管理中心 [或独立 EOP 中的 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d1661-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="d1661-112">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d1661-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d1661-113">若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d1661-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d1661-114">若要详细了解 Exchange Online 和独立 EOP 中的邮件流规则，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d1661-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="d1661-115">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="d1661-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="d1661-116">在 Exchange Online 中预测 (邮件流规则) 条件和异常</span><span class="sxs-lookup"><span data-stu-id="d1661-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="d1661-117">Exchange Online 中的邮件流规则操作</span><span class="sxs-lookup"><span data-stu-id="d1661-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="d1661-118">使用 EAC 创建邮件流规则以接收报告的邮件的副本</span><span class="sxs-lookup"><span data-stu-id="d1661-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="d1661-119">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="d1661-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d1661-120">单击 **"添加** ![ " ](../../media/ITPro-EAC-AddIcon.png) 图标，然后选择"**创建新规则"。**</span><span class="sxs-lookup"><span data-stu-id="d1661-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="d1661-121">在打开的" **新规则**"窗口中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="d1661-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d1661-122">**名称**：输入规则的唯一描述性名称。</span><span class="sxs-lookup"><span data-stu-id="d1661-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="d1661-123">例如，报告给 Microsoft 的"邮件"。</span><span class="sxs-lookup"><span data-stu-id="d1661-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="d1661-124">单击“其他选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1661-124">Click **More Options**.</span></span>

   - <span data-ttu-id="d1661-125">**在以下条件下应用**此规则：**选择收件人** \> **地址包括以下**任何词语：在出现的"指定词语或**短语**"对话框中，输入以下值之一，单击"**Add** ![ 添加图标"，然后在输入所有所有值 ](../../media/ITPro-EAC-AddIcon.png) 后重复发送操作。</span><span class="sxs-lookup"><span data-stu-id="d1661-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="d1661-126">若要编辑条目，请将其选中，然后单击**Edit**"编辑 ![ "图标 ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d1661-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="d1661-127">若要删除条目，请选中它，并单击" **删除"** ![ 图标 ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="d1661-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="d1661-128">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d1661-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="d1661-129">**执行下列操作：** 选择 **"将收件人** \> **添加到"送件抄送"框**。</span><span class="sxs-lookup"><span data-stu-id="d1661-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="d1661-130">在出现的对话框中，找到并选择要添加的收件人。</span><span class="sxs-lookup"><span data-stu-id="d1661-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="d1661-131">完成后，单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="d1661-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="d1661-132">您可以进行其他选择，在特定时间内审核规则、测试规则及激活规则以及其他设置。</span><span class="sxs-lookup"><span data-stu-id="d1661-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="d1661-133">我们建议您在强制执行规则之前测试规则。</span><span class="sxs-lookup"><span data-stu-id="d1661-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="d1661-134">完成时，请单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1661-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="d1661-135">使用 PowerShell 创建邮件流规则以接收报告的邮件的副本</span><span class="sxs-lookup"><span data-stu-id="d1661-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="d1661-136">此示例创建一个名为"送给 Microsoft"的新的名为"Bcc Messages"的邮件流规则，该规则查找通过使用本主题中介绍的方法报告给 Microsoft 的电子邮件，并添加了作为"Laura@contoso.com"和"julia@contoso.com"收件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d1661-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="d1661-137">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)。</span><span class="sxs-lookup"><span data-stu-id="d1661-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d1661-138">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="d1661-138">How do you know this worked?</span></span>

<span data-ttu-id="d1661-139">若要验证是否已配置邮件流规则以接收报告的邮件的副本，请执行以下任意步骤：</span><span class="sxs-lookup"><span data-stu-id="d1661-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="d1661-140">在 EAC 中，转到"**邮件流规则** \> **"** \> 后，选择规则 \> ，单击"**Edit** ![ 编辑" ](../../media/ITPro-EAC-EditIcon.png) 图标，然后验证设置。</span><span class="sxs-lookup"><span data-stu-id="d1661-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="d1661-141">在 PowerShell 中，运行以下命令来验证设置：</span><span class="sxs-lookup"><span data-stu-id="d1661-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="d1661-142">向报告电子邮件地址之一发送测试邮件并验证结果。</span><span class="sxs-lookup"><span data-stu-id="d1661-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
