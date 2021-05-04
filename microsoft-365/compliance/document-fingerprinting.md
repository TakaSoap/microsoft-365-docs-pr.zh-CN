---
title: 文档指纹
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: 组织中的信息工作人员每天会处理大量的敏感信息。 "文档指纹"可识别贵组织中使用的标准表单，以便于您保护此信息。 本主题介绍文档指纹背后的概念，以及如何使用 PowerShell 创建文档指纹。
ms.openlocfilehash: 392b42e779de249dddc0acb4c7c757a009f9f743
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086735"
---
# <a name="document-fingerprinting"></a><span data-ttu-id="62242-105">文档指纹</span><span class="sxs-lookup"><span data-stu-id="62242-105">Document Fingerprinting</span></span>

<span data-ttu-id="62242-106">组织中的信息工作人员每天会处理大量的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="62242-106">Information workers in your organization handle many kinds of sensitive information during a typical day.</span></span> <span data-ttu-id="62242-107">在安全与合规中心，文档指纹通过标识整个组织使用的标准表单，使保护 &amp; 此信息变得更简单。</span><span class="sxs-lookup"><span data-stu-id="62242-107">In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization.</span></span> <span data-ttu-id="62242-108">本主题介绍文档指纹背后的概念，以及如何使用 PowerShell 创建文档指纹。</span><span class="sxs-lookup"><span data-stu-id="62242-108">This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="62242-109">文档指纹的基本方案</span><span class="sxs-lookup"><span data-stu-id="62242-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="62242-110">文档指纹是一项数据丢失防护 (DLP) 功能，可将标准表单转换为敏感信息类型，可在 DLP 策略的规则中使用该类型。</span><span class="sxs-lookup"><span data-stu-id="62242-110">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies.</span></span> <span data-ttu-id="62242-111">例如，您可以基于空白父模板来创建文档指纹，然后创建 DLP 策略，用于检测和阻止所有包含敏感内容的传出父模板。</span><span class="sxs-lookup"><span data-stu-id="62242-111">For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in.</span></span> <span data-ttu-id="62242-112">（可选）您可以设置策略提示[](use-notifications-and-policy-tips.md)以通知发件人他们可能正在发送敏感信息，并且发件人应验证收件人是否有资格接收专利。</span><span class="sxs-lookup"><span data-stu-id="62242-112">Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents.</span></span> <span data-ttu-id="62242-113">此过程与组织中使用的任何基于文本的表单一起使用。</span><span class="sxs-lookup"><span data-stu-id="62242-113">This process works with any text-based forms used in your organization.</span></span> <span data-ttu-id="62242-114">您可以上载的其他表单示例包括：</span><span class="sxs-lookup"><span data-stu-id="62242-114">Additional examples of forms that you can upload include:</span></span>
  
- <span data-ttu-id="62242-115">政府表单</span><span class="sxs-lookup"><span data-stu-id="62242-115">Government forms</span></span>
- <span data-ttu-id="62242-116">符合《健康保险可携性与责任法案》 (HIPAA) 的表单</span><span class="sxs-lookup"><span data-stu-id="62242-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>  
- <span data-ttu-id="62242-117">人力资源部的员工信息表单</span><span class="sxs-lookup"><span data-stu-id="62242-117">Employee information forms for Human Resources departments</span></span>
- <span data-ttu-id="62242-118">组织专门创建的自定义表单</span><span class="sxs-lookup"><span data-stu-id="62242-118">Custom forms created specifically for your organization</span></span>

<span data-ttu-id="62242-119">理想情况下，贵组织已经创建使用特定表单传输敏感信息的业务实践。</span><span class="sxs-lookup"><span data-stu-id="62242-119">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information.</span></span> <span data-ttu-id="62242-120">上载要转换为文档指纹的空表单并设置相应的策略后，DLP 会检测出站邮件中与此指纹匹配的任何文档。</span><span class="sxs-lookup"><span data-stu-id="62242-120">After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>

## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="62242-121">文档指纹的工作原理</span><span class="sxs-lookup"><span data-stu-id="62242-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="62242-122">您可能已经猜到，文档并非真的有指纹，只是"指纹"这个词可以表明其功能。</span><span class="sxs-lookup"><span data-stu-id="62242-122">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature.</span></span> <span data-ttu-id="62242-123">人的指纹各不相同，同理，文档的单词模式也各不相同。</span><span class="sxs-lookup"><span data-stu-id="62242-123">In the same way that a person's fingerprints have unique patterns, documents have unique word patterns.</span></span> <span data-ttu-id="62242-124">上载文件时，DLP 标识文档中的唯一单词模式，基于该模式创建文档指纹，并使用该文档指纹检测包含相同模式的出站文档。</span><span class="sxs-lookup"><span data-stu-id="62242-124">When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern.</span></span> <span data-ttu-id="62242-125">这也是为什么上载表单或模板可以创建最有效的文档指纹的原因。</span><span class="sxs-lookup"><span data-stu-id="62242-125">That's why uploading a form or template creates the most effective type of document fingerprint.</span></span> <span data-ttu-id="62242-126">填写表单的每个人使用相同的单词集，然后在文档中添加自己的词句。</span><span class="sxs-lookup"><span data-stu-id="62242-126">Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document.</span></span> <span data-ttu-id="62242-127">只要出站文档不受密码保护且包含原始表单的所有文本，DLP 就可以确定文档是否与文档指纹匹配。</span><span class="sxs-lookup"><span data-stu-id="62242-127">As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62242-128">目前，DLP 可以将文档指纹用作仅联机Exchange检测方法。</span><span class="sxs-lookup"><span data-stu-id="62242-128">For now, DLP can use document fingerprinting as a detection method in Exchange online only.</span></span>

<span data-ttu-id="62242-129">下列示例说明了当您基于父模板创建文档指纹时发生了什么，但您可以使用任何表单作为基础来创建文档指纹。</span><span class="sxs-lookup"><span data-stu-id="62242-129">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a><span data-ttu-id="62242-130">与父模板的文档指纹匹配的父文档示例</span><span class="sxs-lookup"><span data-stu-id="62242-130">Example of a patent document matching a document fingerprint of a patent template</span></span>

![文档指纹关系图。](../media/Document-Fingerprinting-diagram.png)
  
<span data-ttu-id="62242-132">专利模板包含空白字段"专利标题"、"专利"和"说明"以及其中每个字段的说明，即单词模式。</span><span class="sxs-lookup"><span data-stu-id="62242-132">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern.</span></span> <span data-ttu-id="62242-133">上载原始专利模板时，该模板是支持的文件类型之一，以纯文本格式显示。</span><span class="sxs-lookup"><span data-stu-id="62242-133">When you upload the original patent template, it's in one of the supported file types and in plain text.</span></span> <span data-ttu-id="62242-134">DLP 将此单词模式转换为文档指纹，文档指纹是一个小的 Unicode XML 文件，其中包含表示原始文本的唯一哈希值，指纹在 Active Directory 中另存为数据分类。</span><span class="sxs-lookup"><span data-stu-id="62242-134">DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory.</span></span> <span data-ttu-id="62242-135"> (作为一种安全措施，原始文档本身不会存储在服务中;仅存储哈希值，并且无法从哈希值重新构造原始文档。) 然后，专利指纹将成为您可以与 DLP 策略关联的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="62242-135">(As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy.</span></span> <span data-ttu-id="62242-136">将指纹与 DLP 策略关联后，DLP 会检测包含与专利指纹匹配的文档的任何出站电子邮件，并根据组织策略处理这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="62242-136">After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="62242-137">例如，您可能希望设置一个 DLP 策略，阻止普通员工发送包含专利的传出邮件。</span><span class="sxs-lookup"><span data-stu-id="62242-137">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents.</span></span> <span data-ttu-id="62242-138">DLP 将使用专利指纹来检测专利并阻止这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="62242-138">DLP will use the patent fingerprint to detect patents and block those emails.</span></span> <span data-ttu-id="62242-139">或者，您可能希望让法律部门能够向其他组织发送专利，因为它具有执行此操作的业务需求。</span><span class="sxs-lookup"><span data-stu-id="62242-139">Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so.</span></span> <span data-ttu-id="62242-140">您可以通过在 DLP 策略中为特定部门创建例外来允许特定部门发送敏感信息，也可以允许它们使用业务理由覆盖策略提示。</span><span class="sxs-lookup"><span data-stu-id="62242-140">You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="62242-141">支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="62242-141">Supported file types</span></span>

<span data-ttu-id="62242-142">文档指纹支持与邮件流规则支持的相同文件类型 (也称为传输规则) 。</span><span class="sxs-lookup"><span data-stu-id="62242-142">Document Fingerprinting supports the same file types that are supported in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="62242-143">有关受支持的文件类型的列表，请参阅支持的邮件 [流规则内容检查的文件类型](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。</span><span class="sxs-lookup"><span data-stu-id="62242-143">For a list of supported file types, see [Supported file types for mail flow rule content inspection](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).</span></span> <span data-ttu-id="62242-144">关于文件类型的一个快速说明：邮件流规则或文档指纹均支持 .dotx 文件类型，这可能会令人困惑，因为这是 Word 中的模板文件。</span><span class="sxs-lookup"><span data-stu-id="62242-144">One quick note about file types: neither mail flow rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word.</span></span> <span data-ttu-id="62242-145">当您在本主题或其他文档指纹主题中看到"template"一词时，它是指您构建为标准模板的文档，而非模板文件类型。</span><span class="sxs-lookup"><span data-stu-id="62242-145">When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="62242-146">文档指纹的限制</span><span class="sxs-lookup"><span data-stu-id="62242-146">Limitations of document fingerprinting</span></span>

<span data-ttu-id="62242-147">在下列情况下，文档指纹不会检测敏感信息：</span><span class="sxs-lookup"><span data-stu-id="62242-147">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="62242-148">密码保护的文件</span><span class="sxs-lookup"><span data-stu-id="62242-148">Password protected files</span></span>
- <span data-ttu-id="62242-149">仅包含图片的文件</span><span class="sxs-lookup"><span data-stu-id="62242-149">Files that contain only images</span></span>
- <span data-ttu-id="62242-150">不包含用于创建文档指纹的原始表单中所有文本的文档</span><span class="sxs-lookup"><span data-stu-id="62242-150">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
- <span data-ttu-id="62242-151">大于 10 MB 的文件</span><span class="sxs-lookup"><span data-stu-id="62242-151">Files greater than 10 MB</span></span>

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="62242-152">使用 PowerShell 创建基于文档指纹的分类规则包</span><span class="sxs-lookup"><span data-stu-id="62242-152">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="62242-153">请注意，当前只能使用安全与合规中心中的 PowerShell 创建文档 &amp; 指纹。</span><span class="sxs-lookup"><span data-stu-id="62242-153">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="62242-154">若要连接，请参阅[连接安全&中心 PowerShell。](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="62242-154">To connect, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="62242-155">DLP 使用分类规则包检测敏感内容。</span><span class="sxs-lookup"><span data-stu-id="62242-155">DLP uses classification rule packages to detect sensitive content.</span></span> <span data-ttu-id="62242-156">若要创建基于文档指纹的分类规则包，请使用 **New-DlpFingerprint** 和 **New-DlpSensitiveInformationType** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62242-156">To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets.</span></span> <span data-ttu-id="62242-157">由于 **New-DlpFingerprint** 的结果不存储在数据分类规则外部，因此始终在同一 PowerShell 会话中运行 **New-DlpFingerprint** 和 **New-DlpSensitiveInformationType** 或 **Set-DlpSensitiveInformationType。**</span><span class="sxs-lookup"><span data-stu-id="62242-157">Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session.</span></span> <span data-ttu-id="62242-158">以下示例基于文件 C:\My Documents\Contoso Employee Template.docx 创建新的文档指纹。</span><span class="sxs-lookup"><span data-stu-id="62242-158">The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx.</span></span> <span data-ttu-id="62242-159">将新指纹存储为变量，以便可以在同一 PowerShell 会话中将新指纹与 **New-DlpSensitiveInformationType** cmdlet 一同使用。</span><span class="sxs-lookup"><span data-stu-id="62242-159">You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span>
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="62242-160">现在，我们可以一起创建名为"Contoso Employee Confidential"的新数据分类规则，该规则使用文件 C:\My Documents\Contoso Customer Information Form.docx 的文档指纹。</span><span class="sxs-lookup"><span data-stu-id="62242-160">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="62242-161">现在，您可以使用 **Get-DlpSensitiveInformationType** cmdlet 查找所有 DLP 数据分类规则包，并且本示例中，"Contoso Customer Confidential"是数据分类规则包列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="62242-161">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="62242-162">最后，将"Contoso Customer Confidential"数据分类规则包添加到安全与合规中心中的 DLP &amp; 策略。</span><span class="sxs-lookup"><span data-stu-id="62242-162">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="62242-163">本示例向名为"ConfidentialPolicy"的现有 DLP 策略添加规则。</span><span class="sxs-lookup"><span data-stu-id="62242-163">This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="62242-164">您还可以使用邮件流规则中的数据分类规则包Exchange Online，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="62242-164">You can also use the data classification rule package in mail flow rules in Exchange Online, as shown in the following example.</span></span> <span data-ttu-id="62242-165">若要运行此命令，首先需要连接[Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="62242-165">To run this command, you first need to [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="62242-166">另请注意，规则包需要一段时间才能从安全与合规中心同步到Exchange &amp; 中心。</span><span class="sxs-lookup"><span data-stu-id="62242-166">Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange admin center.</span></span>
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

<span data-ttu-id="62242-167">DLP 现在检测到与 Contoso Customer 和文档指纹Form.docx匹配的文档。</span><span class="sxs-lookup"><span data-stu-id="62242-167">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="62242-168">有关语法和参数的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="62242-168">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="62242-169">New-DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="62242-169">New-DlpFingerprint</span></span>](/powershell/module/exchange/New-DlpFingerprint)
- [<span data-ttu-id="62242-170">New-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="62242-170">New-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [<span data-ttu-id="62242-171">Remove-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="62242-171">Remove-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="62242-172">Set-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="62242-172">Set-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="62242-173">Get-DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="62242-173">Get-DlpSensitiveInformationType</span></span>](/powershell/module/exchange/Get-DlpSensitiveInformationType)
