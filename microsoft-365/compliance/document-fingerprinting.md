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
description: 组织中的信息工作人员每天会处理大量的敏感信息。 "文档指纹"可识别贵组织中使用的标准表单，以便于您保护此信息。 本主题介绍文档指纹背后的概念，以及如何使用 PowerShell 创建一个概念。
ms.openlocfilehash: 37b5649e357f24993e41ae93db6737d980ce0c72
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352019"
---
# <a name="document-fingerprinting"></a><span data-ttu-id="81609-105">文档指纹</span><span class="sxs-lookup"><span data-stu-id="81609-105">Document Fingerprinting</span></span>

<span data-ttu-id="81609-106">组织中的信息工作人员每天会处理大量的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="81609-106">Information workers in your organization handle many kinds of sensitive information during a typical day.</span></span> <span data-ttu-id="81609-107">在安全 &amp; 合规性中心中，文档指纹可使您更轻松地通过标识在整个组织中使用的标准表单来保护此信息。</span><span class="sxs-lookup"><span data-stu-id="81609-107">In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization.</span></span> <span data-ttu-id="81609-108">本主题介绍文档指纹背后的概念，以及如何使用 PowerShell 创建一个概念。</span><span class="sxs-lookup"><span data-stu-id="81609-108">This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="81609-109">文档指纹的基本方案</span><span class="sxs-lookup"><span data-stu-id="81609-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="81609-110">文档指纹是一项数据丢失防护（DLP）功能，可将标准窗体转换为敏感信息类型，您可以在 DLP 策略的规则中使用。</span><span class="sxs-lookup"><span data-stu-id="81609-110">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies.</span></span> <span data-ttu-id="81609-111">例如，您可以基于空白父模板来创建文档指纹，然后创建 DLP 策略，用于检测和阻止所有包含敏感内容的传出父模板。</span><span class="sxs-lookup"><span data-stu-id="81609-111">For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in.</span></span> <span data-ttu-id="81609-112">（可选）您可以设置[策略提示](use-notifications-and-policy-tips.md)以通知发件人他们可能发送敏感信息，并且发件人应验证收件人是否有资格接收专利。</span><span class="sxs-lookup"><span data-stu-id="81609-112">Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents.</span></span> <span data-ttu-id="81609-113">此过程与组织中使用的任何基于文本的表单一起使用。</span><span class="sxs-lookup"><span data-stu-id="81609-113">This process works with any text-based forms used in your organization.</span></span> <span data-ttu-id="81609-114">您可以上载的其他表单示例包括：</span><span class="sxs-lookup"><span data-stu-id="81609-114">Additional examples of forms that you can upload include:</span></span>
  
- <span data-ttu-id="81609-115">政府表单</span><span class="sxs-lookup"><span data-stu-id="81609-115">Government forms</span></span>
- <span data-ttu-id="81609-116">符合《健康保险可携性与责任法案》 (HIPAA) 的表单</span><span class="sxs-lookup"><span data-stu-id="81609-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>  
- <span data-ttu-id="81609-117">人力资源部的员工信息表单</span><span class="sxs-lookup"><span data-stu-id="81609-117">Employee information forms for Human Resources departments</span></span>
- <span data-ttu-id="81609-118">组织专门创建的自定义表单</span><span class="sxs-lookup"><span data-stu-id="81609-118">Custom forms created specifically for your organization</span></span>

<span data-ttu-id="81609-119">理想情况下，贵组织已经创建使用特定表单传输敏感信息的业务实践。</span><span class="sxs-lookup"><span data-stu-id="81609-119">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information.</span></span> <span data-ttu-id="81609-120">在上载要转换为文档指纹的空表单并设置相应的策略后，DLP 将检测出出出出出站邮件中与该指纹匹配的任何文档。</span><span class="sxs-lookup"><span data-stu-id="81609-120">After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>

## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="81609-121">文档指纹的工作原理</span><span class="sxs-lookup"><span data-stu-id="81609-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="81609-122">您可能已经猜到，文档并非真的有指纹，只是"指纹"这个词可以表明其功能。</span><span class="sxs-lookup"><span data-stu-id="81609-122">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature.</span></span> <span data-ttu-id="81609-123">人的指纹各不相同，同理，文档的单词模式也各不相同。</span><span class="sxs-lookup"><span data-stu-id="81609-123">In the same way that a person's fingerprints have unique patterns, documents have unique word patterns.</span></span> <span data-ttu-id="81609-124">上载文件时，DLP 将标识文档中的唯一单词模式，根据该模式创建文档指纹，并使用该文档指纹检测包含相同模式的出站文档。</span><span class="sxs-lookup"><span data-stu-id="81609-124">When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern.</span></span> <span data-ttu-id="81609-125">这也是为什么上载表单或模板可以创建最有效的文档指纹的原因。</span><span class="sxs-lookup"><span data-stu-id="81609-125">That's why uploading a form or template creates the most effective type of document fingerprint.</span></span> <span data-ttu-id="81609-126">填写表单的每个人使用相同的单词集，然后在文档中添加自己的词句。</span><span class="sxs-lookup"><span data-stu-id="81609-126">Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document.</span></span> <span data-ttu-id="81609-127">只要出站文档不受密码保护，并且包含原始表单中的所有文本，DLP 就可以确定文档是否与文档指纹相匹配。</span><span class="sxs-lookup"><span data-stu-id="81609-127">As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81609-128">现在，DLP 可以仅将文档指纹用作 Exchange online 中的检测方法。</span><span class="sxs-lookup"><span data-stu-id="81609-128">For now, DLP can use document fingerprinting as a detection method in Exchange online only.</span></span>

<span data-ttu-id="81609-129">下列示例说明了当您基于父模板创建文档指纹时发生了什么，但您可以使用任何表单作为基础来创建文档指纹。</span><span class="sxs-lookup"><span data-stu-id="81609-129">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a><span data-ttu-id="81609-130">与父模板的文档指纹匹配的父文档示例</span><span class="sxs-lookup"><span data-stu-id="81609-130">Example of a patent document matching a document fingerprint of a patent template</span></span>

![Document-Fingerprinting-diagram](../media/Document-Fingerprinting-diagram.png)
  
<span data-ttu-id="81609-132">专利模板包含空字段 "专利权 title"、"Inventors" 和 "Description" 以及每个字段的说明，即 word 模式。</span><span class="sxs-lookup"><span data-stu-id="81609-132">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern.</span></span> <span data-ttu-id="81609-133">上载原始专利模板时，它采用受支持的文件类型之一和纯文本格式。</span><span class="sxs-lookup"><span data-stu-id="81609-133">When you upload the original patent template, it's in one of the supported file types and in plain text.</span></span> <span data-ttu-id="81609-134">DLP 将此 word 模式转换为文档指纹，这是一个包含代表原始文本的唯一哈希值的小型 Unicode XML 文件，并且指纹在 Active Directory 中保存为数据分类。</span><span class="sxs-lookup"><span data-stu-id="81609-134">DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory.</span></span> <span data-ttu-id="81609-135">（作为一种安全措施，原始文档本身不存储在服务上; 仅存储哈希值，并且无法从哈希值重新构造原始文档。）专利指纹将成为可与 DLP 策略关联的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="81609-135">(As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy.</span></span> <span data-ttu-id="81609-136">将指纹与 DLP 策略相关联后，DLP 将检测任何包含符合专利指纹的文档的出站电子邮件，并根据您的组织的策略对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="81609-136">After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="81609-137">例如，您可能希望设置一个 DLP 策略，以防止普通员工发送包含专利的传出邮件。</span><span class="sxs-lookup"><span data-stu-id="81609-137">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents.</span></span> <span data-ttu-id="81609-138">DLP 将使用专利指纹来检测专利并阻止这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="81609-138">DLP will use the patent fingerprint to detect patents and block those emails.</span></span> <span data-ttu-id="81609-139">或者，您可能希望让法律部门能够将专利发送给其他组织，因为这样做有业务需求。</span><span class="sxs-lookup"><span data-stu-id="81609-139">Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so.</span></span> <span data-ttu-id="81609-140">您可以通过在 DLP 策略中为这些部门创建例外来允许特定部门发送敏感信息，也可以允许他们使用业务理由覆盖策略提示。</span><span class="sxs-lookup"><span data-stu-id="81609-140">You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="81609-141">支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="81609-141">Supported file types</span></span>

<span data-ttu-id="81609-142">文档指纹支持在邮件流规则（也称为传输规则）中受支持的相同文件类型。</span><span class="sxs-lookup"><span data-stu-id="81609-142">Document Fingerprinting supports the same file types that are supported in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="81609-143">有关受支持的文件类型的列表，请参阅[邮件流规则内容检查支持的文件类型](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。</span><span class="sxs-lookup"><span data-stu-id="81609-143">For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).</span></span> <span data-ttu-id="81609-144">有关文件类型的快速说明：邮件流规则和文档指纹都不支持 .dotx 文件类型，因为这是 Word 中的模板文件，这样做可能会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="81609-144">One quick note about file types: neither mail flow rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word.</span></span> <span data-ttu-id="81609-145">当您在本主题或其他文档指纹主题中看到"template"一词时，它是指您构建为标准模板的文档，而非模板文件类型。</span><span class="sxs-lookup"><span data-stu-id="81609-145">When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="81609-146">文档指纹的限制</span><span class="sxs-lookup"><span data-stu-id="81609-146">Limitations of document fingerprinting</span></span>

<span data-ttu-id="81609-147">在下列情况下，文档指纹不会检测敏感信息：</span><span class="sxs-lookup"><span data-stu-id="81609-147">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="81609-148">密码保护的文件</span><span class="sxs-lookup"><span data-stu-id="81609-148">Password protected files</span></span>
- <span data-ttu-id="81609-149">仅包含图片的文件</span><span class="sxs-lookup"><span data-stu-id="81609-149">Files that contain only images</span></span>
- <span data-ttu-id="81609-150">不包含用于创建文档指纹的原始表单中所有文本的文档</span><span class="sxs-lookup"><span data-stu-id="81609-150">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="81609-151">使用 PowerShell 创建基于文档指纹的分类规则包</span><span class="sxs-lookup"><span data-stu-id="81609-151">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="81609-152">请注意，当前可以在安全合规中心中使用 PowerShell 创建文档指纹 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="81609-152">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="81609-153">若要进行连接，请参阅[connect To Security & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="81609-153">To connect, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="81609-154">DLP 使用分类规则包来检测敏感内容。</span><span class="sxs-lookup"><span data-stu-id="81609-154">DLP uses classification rule packages to detect sensitive content.</span></span> <span data-ttu-id="81609-155">若要创建基于文档指纹的分类规则包，请使用**DlpFingerprint**和**DlpSensitiveInformationType** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="81609-155">To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets.</span></span> <span data-ttu-id="81609-156">由于**DlpFingerprint**的结果不会存储在数据分类规则的外部，因此您始终在同一 PowerShell 会话中运行**DlpFingerprint**和**DlpSensitiveInformationType**或**DlpSensitiveInformationType**等新的结果。</span><span class="sxs-lookup"><span data-stu-id="81609-156">Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session.</span></span> <span data-ttu-id="81609-157">以下示例基于文件 C:\My Documents\Contoso Employee Template.docx 创建新的文档指纹。</span><span class="sxs-lookup"><span data-stu-id="81609-157">The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx.</span></span> <span data-ttu-id="81609-158">将新的指纹存储为变量，以便您可以在同一 PowerShell 会话中将其与**DlpSensitiveInformationType** cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="81609-158">You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span>
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="81609-159">现在，我们可以一起创建名为"Contoso Employee Confidential"的新数据分类规则，该规则使用文件 C:\My Documents\Contoso Customer Information Form.docx 的文档指纹。</span><span class="sxs-lookup"><span data-stu-id="81609-159">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="81609-160">现在，您可以使用**DlpSensitiveInformationType** cmdlet 查找所有 DLP 数据分类规则包，在此示例中，"Contoso Customer 保密" 是 "数据分类规则包" 列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="81609-160">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="81609-161">最后，将 "Contoso Customer 保密" 数据分类规则包添加到安全合规中心中的 DLP 策略 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="81609-161">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="81609-162">本示例将一个规则添加到名为 "ConfidentialPolicy" 的现有 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="81609-162">This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="81609-163">您还可以在 Exchange Online 中使用邮件流规则中的数据分类规则包，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="81609-163">You can also use the data classification rule package in mail flow rules in Exchange Online, as shown in the following example.</span></span> <span data-ttu-id="81609-164">若要运行此命令，首先需要[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="81609-164">To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="81609-165">另请注意，规则包从安全 &amp; 合规中心同步到 Exchange 管理中心需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="81609-165">Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange admin center.</span></span>
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

<span data-ttu-id="81609-166">DLP 现在检测与 Contoso Customer 表单的 .docx 文档指纹相匹配的文档。</span><span class="sxs-lookup"><span data-stu-id="81609-166">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="81609-167">有关语法和参数的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="81609-167">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="81609-168">新 DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="81609-168">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/New-DlpFingerprint)
- [<span data-ttu-id="81609-169">新 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="81609-169">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/New-DlpSensitiveInformationType)
- [<span data-ttu-id="81609-170">DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="81609-170">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="81609-171">DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="81609-171">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="81609-172">DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="81609-172">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/Get-DlpSensitiveInformationType)
