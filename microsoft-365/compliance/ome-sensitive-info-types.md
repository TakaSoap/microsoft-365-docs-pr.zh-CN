---
title: 使用 Office 365 邮件加密创建敏感信息类型策略
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: 了解如何使用 Office 365 邮件加密为组织创建敏感信息类型策略。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22aec87b149c58b2537f6921fb7c37552ef72f98
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741375"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="96372-103">使用邮件加密为组织创建敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="96372-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="96372-104">您可以使用 Exchange 邮件流规则或数据丢失防护 (DLP) Office 365 邮件加密创建敏感信息类型策略。</span><span class="sxs-lookup"><span data-stu-id="96372-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="96372-105">若要创建 Exchange 邮件流规则，可以使用 Exchange 管理中心或 (EAC) PowerShell。</span><span class="sxs-lookup"><span data-stu-id="96372-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="96372-106">使用 EAC 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="96372-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="96372-107">登录到 Exchange 管理中心 (EAC) ，**然后转到"** 邮件流""规则  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="96372-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="96372-108">在"规则"页上，创建应用 Office 365 邮件加密的规则。</span><span class="sxs-lookup"><span data-stu-id="96372-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="96372-109">您可以基于某些条件（如邮件或附件中是否存在某些关键字或敏感信息类型）创建规则。</span><span class="sxs-lookup"><span data-stu-id="96372-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="96372-110">使用 PowerShell 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="96372-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="96372-111">使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="96372-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="96372-112">有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="96372-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="96372-113">使用 Set-IRMConfiguration 和 New-TransportRule cmdlet 创建策略。</span><span class="sxs-lookup"><span data-stu-id="96372-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="96372-114">使用 PowerShell 创建的邮件流规则示例</span><span class="sxs-lookup"><span data-stu-id="96372-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="96372-115">在 PowerShell 中运行以下命令，创建 Exchange 邮件流规则，如果电子邮件或附件包含以下敏感信息类型，则使用仅加密选项自动加密发送到组织外部的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="96372-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="96372-116">ABA 路由号码</span><span class="sxs-lookup"><span data-stu-id="96372-116">ABA routing number</span></span>
- <span data-ttu-id="96372-117">信用卡号</span><span class="sxs-lookup"><span data-stu-id="96372-117">Credit card Number</span></span>
- <span data-ttu-id="96372-118">管制局 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="96372-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="96372-119">美国/英国</span><span class="sxs-lookup"><span data-stu-id="96372-119">U.S. / U.K.</span></span> <span data-ttu-id="96372-120">passport number</span><span class="sxs-lookup"><span data-stu-id="96372-120">passport number</span></span>
- <span data-ttu-id="96372-121">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="96372-121">U.S. bank account number</span></span>
- <span data-ttu-id="96372-122">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="96372-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="96372-123">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="96372-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="96372-124">有关详细信息，请参阅[Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration)和[New-TransportRule。](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)</span><span class="sxs-lookup"><span data-stu-id="96372-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="96372-125">收件人如何访问附件</span><span class="sxs-lookup"><span data-stu-id="96372-125">How recipients access attachments</span></span>

<span data-ttu-id="96372-126">Microsoft 加密邮件后，收件人在访问和打开其加密电子邮件时可以不受限制地访问附件。</span><span class="sxs-lookup"><span data-stu-id="96372-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="96372-127">准备进行此更改</span><span class="sxs-lookup"><span data-stu-id="96372-127">To prepare for this change</span></span>

<span data-ttu-id="96372-128">您可能需要更新任何适用的最终用户文档和培训材料，以让组织人员为此更改做好准备。</span><span class="sxs-lookup"><span data-stu-id="96372-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="96372-129">根据情况与用户共享这些 Office 365 邮件加密资源：</span><span class="sxs-lookup"><span data-stu-id="96372-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="96372-130">在 Outlook for PC 中发送、查看和回复加密邮件</span><span class="sxs-lookup"><span data-stu-id="96372-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="96372-131">Microsoft 365 Essentials 视频：Office 邮件加密</span><span class="sxs-lookup"><span data-stu-id="96372-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="96372-132">在"管理"中查看审核日志</span><span class="sxs-lookup"><span data-stu-id="96372-132">View these changes in the audit log</span></span>

<span data-ttu-id="96372-133">Microsoft 365 审核此活动，并提供给管理员使用。</span><span class="sxs-lookup"><span data-stu-id="96372-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="96372-134">操作为"New-TransportRule"，下面是安全与合规中心审核日志搜索&代码段：</span><span class="sxs-lookup"><span data-stu-id="96372-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="96372-135">禁用或自定义敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="96372-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="96372-136">创建 Exchange 邮件流规则后，可以通过在 Exchange [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)管理中心 (EAC ) 中访问"邮件流规则"来禁用或编辑该规则) 并禁用规则"加密出站敏感电子邮件 (开箱即用规则  >  *) "。*</span><span class="sxs-lookup"><span data-stu-id="96372-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
