---
title: 创建关键字词典
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解在 Office 365 安全与合规中心中创建关键字字典的基本步骤。
ms.openlocfilehash: 8d313650f298f2ab26989bec9df1260918f7dd5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300098"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="026b6-103">创建关键字字典</span><span class="sxs-lookup"><span data-stu-id="026b6-103">Create a keyword dictionary</span></span>

<span data-ttu-id="026b6-104">数据丢失防护 (DLP) 可识别、监视和保护敏感项目。</span><span class="sxs-lookup"><span data-stu-id="026b6-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="026b6-105">标识敏感项目有时需要查找关键字，尤其是在标识常规内容（如与医疗保健相关的通信）或不当或露骨语言时。</span><span class="sxs-lookup"><span data-stu-id="026b6-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="026b6-106">虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小是有限的，且需要修改 XML 才能创建或编辑它们。</span><span class="sxs-lookup"><span data-stu-id="026b6-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="026b6-107">关键字字典可更简单地管理关键字，并且规模更大，可支持多达 1 MB 的术语（压缩后），并支持所有语言。</span><span class="sxs-lookup"><span data-stu-id="026b6-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1 MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="026b6-108">租户限制同样为压缩后 1 MB。</span><span class="sxs-lookup"><span data-stu-id="026b6-108">The tenant limit is also 1 MB after compression.</span></span> <span data-ttu-id="026b6-109">压缩后限值 1 MB 意味着租户中合并的所有词典可能接近 100 万字符。</span><span class="sxs-lookup"><span data-stu-id="026b6-109">1 MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million characters.</span></span>

## <a name="keyword-dictionary-limits"></a><span data-ttu-id="026b6-110">关键字字典限制</span><span class="sxs-lookup"><span data-stu-id="026b6-110">Keyword dictionary limits</span></span>

<span data-ttu-id="026b6-111">每个租户最多可以创建 50 种基于关键字字典的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="026b6-111">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span> <span data-ttu-id="026b6-112">要了解租户中有多少关键字词典，请使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)中的过程进行连接，以连接到租户并运行此 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="026b6-112">To find out how many keyword dictionaries you have in your tenant, connect using the procedures in [Connect to the Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to connect to your tenant and run this PowerShell script.</span></span>

```powershell
$rawFile = $env:TEMP + "\rule.xml"

$kd = Get-DlpKeywordDictionary
$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
Set-Content -path $rawFile -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
$UnicodeEncoding = New-Object System.Text.UnicodeEncoding
$FileContent = [System.IO.File]::ReadAllText((Resolve-Path $rawFile), $unicodeEncoding)

if($kd.Count -gt 0)
{
$count = 0
$entities = $FileContent -split "Entity id"
for($j=1;$j -lt $entities.Count;$j++)
{
for($i=0;$i -lt $kd.Count;$i++)
{
$Matches = Select-String -InputObject $entities[$j] -Pattern $kd[$i].Identity -AllMatches
$count = $Matches.Matches.Count + $count
if($Matches.Matches.Count -gt 0) {break}
}
}

Write-Output "Total Keyword Dictionary SIT:"
$count
}
else
{
$Matches = Select-String -InputObject $FileContent -Pattern $kd.Identity -AllMatches
Write-Output "Total Keyword Dictionary SIT:"
$Matches.Matches.Count
}

Remove-Item $rawFile
```

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="026b6-113">创建关键字词典的基本步骤</span><span class="sxs-lookup"><span data-stu-id="026b6-113">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="026b6-p103">词典可能有多个关键字来源，最常见的来源是服务或 PowerShell cmdlet 中导入的文件（如 .csv 或 .txt 列表）、你直接在 PowerShell cmdlet 中输入的列表或现有词典。创建关键字词典时，请遵循下面的相同核心步骤：</span><span class="sxs-lookup"><span data-stu-id="026b6-p103">The keywords for your dictionary could come from various sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="026b6-116">使用 **安全与合规中心** ([https://protection.office.com](https://protection.office.com)) 或连接到 **安全与合规中心 PowerShell**。&amp;</span><span class="sxs-lookup"><span data-stu-id="026b6-116">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="026b6-117">**定义或加载目标来源中的关键字**。</span><span class="sxs-lookup"><span data-stu-id="026b6-117">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="026b6-118">该向导和 cmdlet 均接受逗号分隔的关键字列表，以创建自定义关键字字典，所以这一步将会因关键字来源不同而略有差异。</span><span class="sxs-lookup"><span data-stu-id="026b6-118">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="026b6-119">加载后的关键字会在导入前编码并转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="026b6-119">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="026b6-120">**创建字典**。</span><span class="sxs-lookup"><span data-stu-id="026b6-120">**Create your dictionary**.</span></span> <span data-ttu-id="026b6-121">选择名称和说明，并创建字典。</span><span class="sxs-lookup"><span data-stu-id="026b6-121">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="026b6-122">使用安全与合规中心创建关键字字典</span><span class="sxs-lookup"><span data-stu-id="026b6-122">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="026b6-123">使用以下步骤创建和导入自定义字典关键字：</span><span class="sxs-lookup"><span data-stu-id="026b6-123">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="026b6-124">连接到安全与合规中心 ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="026b6-124">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="026b6-125">导航到 **“分类”>“敏感信息类型”**。</span><span class="sxs-lookup"><span data-stu-id="026b6-125">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="026b6-126">选择“**创建**”并输入敏感信息类型的“**名称**”和“**说明**”，然后选择“**下一步**”</span><span class="sxs-lookup"><span data-stu-id="026b6-126">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="026b6-127">选择“**添加元素**”，然后选择“**检测内容包含**”下拉列表中的“**词典（大关键字）**”中。</span><span class="sxs-lookup"><span data-stu-id="026b6-127">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="026b6-128">选择“**添加词典**”</span><span class="sxs-lookup"><span data-stu-id="026b6-128">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="026b6-129">在“搜索”控件下，选择“**你可以在此处新建关键字词典**”。</span><span class="sxs-lookup"><span data-stu-id="026b6-129">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="026b6-130">输入自定义词典的“**名称**”。</span><span class="sxs-lookup"><span data-stu-id="026b6-130">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="026b6-131">选择“**导入**”，并根据关键字文件类型选择“**从文本**”或“**从 csv**”。</span><span class="sxs-lookup"><span data-stu-id="026b6-131">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="026b6-132">在文件对话框中，从本地电脑或网络文件共享中选择关键字文件，然后选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="026b6-132">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="026b6-133">选择“**保存**”，然后从“**关键字词典**”列表中选择自定义词典。</span><span class="sxs-lookup"><span data-stu-id="026b6-133">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="026b6-134">选择“**添加**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="026b6-134">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="026b6-135">检查并完成敏感信息类型选择，然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="026b6-135">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="026b6-136">使用 PowerShell 通过文件创建关键字词典</span><span class="sxs-lookup"><span data-stu-id="026b6-136">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="026b6-137">通常情况下，在需要创建大型字典时，可使用从某些其他来源导出的文件或列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="026b6-137">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="026b6-138">在这种情况下，将会创建一个关键字字典，其中包含将在外部电子邮件中筛选的不当语言的列表。</span><span class="sxs-lookup"><span data-stu-id="026b6-138">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="026b6-139">首先，必须[连接到安全与&amp;合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="026b6-139">You must first [Connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="026b6-140">将关键字复制到文本文件中，并确保每个关键字都单独占一行。</span><span class="sxs-lookup"><span data-stu-id="026b6-140">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="026b6-p107">使用 Unicode 编码保存文本文件。在记事本中，依次单击“另存为”\>“编码”\>“Unicode”。</span><span class="sxs-lookup"><span data-stu-id="026b6-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="026b6-143">运行下面的 cmdlet，以将文件读入变量中：</span><span class="sxs-lookup"><span data-stu-id="026b6-143">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="026b6-144">运行下面的 cmdlet，以创建词典：</span><span class="sxs-lookup"><span data-stu-id="026b6-144">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="026b6-145">在自定义敏感信息类型和 DLP 策略中使用关键字词典</span><span class="sxs-lookup"><span data-stu-id="026b6-145">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="026b6-146">关键字字典可用作自定义敏感信息类型的匹配要求的一部分，也可用作敏感信息类型本身。</span><span class="sxs-lookup"><span data-stu-id="026b6-146">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="026b6-147">这两者都要求创建[自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="026b6-147">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="026b6-148">请按照链接的文章中的说明创建敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="026b6-148">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="026b6-149">拥有 XML 后，你将需要 GUID 标识符，以供字典使用。</span><span class="sxs-lookup"><span data-stu-id="026b6-149">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="026b6-150">若要获得词典标识，请运行下面的命令，并复制 **Identity** 属性值：</span><span class="sxs-lookup"><span data-stu-id="026b6-150">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="026b6-151">此命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="026b6-151">The output of the command looks like this:</span></span>
  
<span data-ttu-id="026b6-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="026b6-152">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="026b6-p109">将标识粘贴到自定义敏感信息类型的 XML 中，并上传它。此时，词典会出现在敏感信息类型列表中，你可以直接在策略中使用它，同时指定必须匹配多少个关键字。</span><span class="sxs-lookup"><span data-stu-id="026b6-p109">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```

> [!NOTE]
> <span data-ttu-id="026b6-155">Microsoft 365 信息保护支持双字节字符集语言，用于:</span><span class="sxs-lookup"><span data-stu-id="026b6-155">Microsoft 365 Information Protection supports double byte character set languages for:</span></span>
> - <span data-ttu-id="026b6-156">简体中文</span><span class="sxs-lookup"><span data-stu-id="026b6-156">Chinese (simplified)</span></span>
> - <span data-ttu-id="026b6-157">繁体中文</span><span class="sxs-lookup"><span data-stu-id="026b6-157">Chinese (traditional)</span></span>
> - <span data-ttu-id="026b6-158">韩语</span><span class="sxs-lookup"><span data-stu-id="026b6-158">Korean</span></span>
> - <span data-ttu-id="026b6-159">日语</span><span class="sxs-lookup"><span data-stu-id="026b6-159">Japanese</span></span>
>
><span data-ttu-id="026b6-160">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="026b6-160">This support is available for sensitive information types.</span></span> <span data-ttu-id="026b6-161">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="026b6-161">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="026b6-162">若要检测含有中文/日文字符和单字节字符的模式，或检测含有中文/日文和英文的模式，则需要定义两个变体的关键词或词组。</span><span class="sxs-lookup"><span data-stu-id="026b6-162">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span> 
>
> <span data-ttu-id="026b6-163">例如，若要检测像“机密的文件”这样的关键词，则要使用该关键词的两个变体; 一个是在日语和英语文本之间有空格，另一个是在日语和英语文本之间没有空格。</span><span class="sxs-lookup"><span data-stu-id="026b6-163">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="026b6-164">因此，在 SIT 中要添加的关键词应该是“机密的 文档”和“机密的文档”。</span><span class="sxs-lookup"><span data-stu-id="026b6-164">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="026b6-165">同样，若要检测短语 "東京オリンピック2020"，则应该使用两个变体;“東京オリンピック 2020”和“東京オリンピック2020”。</span><span class="sxs-lookup"><span data-stu-id="026b6-165">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
>
> <span data-ttu-id="026b6-p112">当使用双字节连字符或双字节句号创建 regex 时，请确保像在 regex 中转义连字符或句号一样转义这两个字符。以下是供参考的示例 regex：</span><span class="sxs-lookup"><span data-stu-id="026b6-p112">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>
>    - <span data-ttu-id="026b6-168">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="026b6-168">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="026b6-169">建议在关键词列表中使用字符串匹配而不是单词匹配。</span><span class="sxs-lookup"><span data-stu-id="026b6-169">We recommend using a string match instead of a word match in a keyword list.</span></span>
