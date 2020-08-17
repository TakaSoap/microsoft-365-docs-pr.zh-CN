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
ms.openlocfilehash: d3308de0138b13391a5bd8a4493cda87c4023bd8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686634"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="cad88-103">创建关键字字典</span><span class="sxs-lookup"><span data-stu-id="cad88-103">Create a keyword dictionary</span></span>

<span data-ttu-id="cad88-104">数据丢失防护 (DLP) 可识别、监视和保护敏感项目。</span><span class="sxs-lookup"><span data-stu-id="cad88-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="cad88-105">标识敏感项目有时需要查找关键字，尤其是在标识常规内容（如与医疗保健相关的通信）或不当或露骨语言时。</span><span class="sxs-lookup"><span data-stu-id="cad88-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="cad88-106">虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小是有限的，且需要修改 XML 才能创建或编辑它们。</span><span class="sxs-lookup"><span data-stu-id="cad88-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="cad88-107">关键字字典提供了更简单的关键字管理方式，并且规模更大，每个字典最多可支持 100000 个词条。</span><span class="sxs-lookup"><span data-stu-id="cad88-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 100,000 terms per dictionary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cad88-108">Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：</span><span class="sxs-lookup"><span data-stu-id="cad88-108">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="cad88-109">简体中文</span><span class="sxs-lookup"><span data-stu-id="cad88-109">Chinese (simplified)</span></span>
> - <span data-ttu-id="cad88-110">繁体中文</span><span class="sxs-lookup"><span data-stu-id="cad88-110">Chinese (traditional)</span></span>
> - <span data-ttu-id="cad88-111">韩语</span><span class="sxs-lookup"><span data-stu-id="cad88-111">Korean</span></span>
> - <span data-ttu-id="cad88-112">日语</span><span class="sxs-lookup"><span data-stu-id="cad88-112">Japanese</span></span>
> 
><span data-ttu-id="cad88-113">此功能预览仅在商业云中提供，并且仅在以下地区推出：</span><span class="sxs-lookup"><span data-stu-id="cad88-113">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="cad88-114">日本</span><span class="sxs-lookup"><span data-stu-id="cad88-114">Japan</span></span>
> - <span data-ttu-id="cad88-115">韩国</span><span class="sxs-lookup"><span data-stu-id="cad88-115">Korea</span></span>
> - <span data-ttu-id="cad88-116">中国大陆</span><span class="sxs-lookup"><span data-stu-id="cad88-116">China</span></span>
> - <span data-ttu-id="cad88-117">香港特别行政区</span><span class="sxs-lookup"><span data-stu-id="cad88-117">Hong Kong</span></span>
> - <span data-ttu-id="cad88-118">澳门特别行政区</span><span class="sxs-lookup"><span data-stu-id="cad88-118">Macau</span></span>
> - <span data-ttu-id="cad88-119">中国台湾</span><span class="sxs-lookup"><span data-stu-id="cad88-119">Taiwan</span></span>
>
><span data-ttu-id="cad88-120">此支持适用于敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="cad88-120">This support is available for sensitive information types.</span></span> <span data-ttu-id="cad88-121">有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。</span><span class="sxs-lookup"><span data-stu-id="cad88-121">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="cad88-122">创建关键字词典的基本步骤</span><span class="sxs-lookup"><span data-stu-id="cad88-122">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="cad88-p103">词典可能有多个关键字来源，最常见的来源是服务或 PowerShell cmdlet 中导入的文件（如 .csv 或 .txt 列表）、你直接在 PowerShell cmdlet 中输入的列表或现有词典。创建关键字词典时，请遵循下面的相同核心步骤：</span><span class="sxs-lookup"><span data-stu-id="cad88-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="cad88-125">使用**安全与合规中心** ([https://protection.office.com](https://protection.office.com)) 或连接到**安全与合规中心 PowerShell**。&amp;</span><span class="sxs-lookup"><span data-stu-id="cad88-125">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="cad88-126">**定义或加载目标来源中的关键字**。</span><span class="sxs-lookup"><span data-stu-id="cad88-126">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="cad88-127">该向导和 cmdlet 均接受逗号分隔的关键字列表，以创建自定义关键字字典，所以这一步将会因关键字来源不同而略有差异。</span><span class="sxs-lookup"><span data-stu-id="cad88-127">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="cad88-128">加载后的关键字会在导入前编码并转换为字节数组。</span><span class="sxs-lookup"><span data-stu-id="cad88-128">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="cad88-129">**创建字典**。</span><span class="sxs-lookup"><span data-stu-id="cad88-129">**Create your dictionary**.</span></span> <span data-ttu-id="cad88-130">选择名称和说明，并创建字典。</span><span class="sxs-lookup"><span data-stu-id="cad88-130">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="cad88-131">使用安全与合规中心创建关键字字典</span><span class="sxs-lookup"><span data-stu-id="cad88-131">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="cad88-132">使用以下步骤创建和导入自定义字典关键字：</span><span class="sxs-lookup"><span data-stu-id="cad88-132">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="cad88-133">连接到安全与合规中心 ([https://protection.office.com](https://protection.office.com))。</span><span class="sxs-lookup"><span data-stu-id="cad88-133">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="cad88-134">导航到 **“分类”>“敏感信息类型”**。</span><span class="sxs-lookup"><span data-stu-id="cad88-134">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="cad88-135">选择“**创建**”并输入敏感信息类型的“**名称**”和“**说明**”，然后选择“**下一步**”</span><span class="sxs-lookup"><span data-stu-id="cad88-135">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="cad88-136">选择“**添加元素**”，然后选择“**检测内容包含**”下拉列表中的“**词典（大关键字）**”中。</span><span class="sxs-lookup"><span data-stu-id="cad88-136">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="cad88-137">选择“**添加词典**”</span><span class="sxs-lookup"><span data-stu-id="cad88-137">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="cad88-138">在“搜索”控件下，选择“**你可以在此处新建关键字词典**”。</span><span class="sxs-lookup"><span data-stu-id="cad88-138">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="cad88-139">输入自定义词典的“**名称**”。</span><span class="sxs-lookup"><span data-stu-id="cad88-139">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="cad88-140">选择“**导入**”，并根据关键字文件类型选择“**从文本**”或“**从 csv**”。</span><span class="sxs-lookup"><span data-stu-id="cad88-140">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="cad88-141">在文件对话框中，从本地电脑或网络文件共享中选择关键字文件，然后选择“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="cad88-141">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="cad88-142">选择“**保存**”，然后从“**关键字词典**”列表中选择自定义词典。</span><span class="sxs-lookup"><span data-stu-id="cad88-142">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="cad88-143">选择“**添加**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="cad88-143">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="cad88-144">检查并完成敏感信息类型选择，然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="cad88-144">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="cad88-145">使用 PowerShell 通过文件创建关键字词典</span><span class="sxs-lookup"><span data-stu-id="cad88-145">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="cad88-146">通常情况下，在需要创建大型字典时，可使用从某些其他来源导出的文件或列表中的关键字。</span><span class="sxs-lookup"><span data-stu-id="cad88-146">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="cad88-147">在这种情况下，将会创建一个关键字字典，其中包含将在外部电子邮件中筛选的不当语言的列表。</span><span class="sxs-lookup"><span data-stu-id="cad88-147">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="cad88-148">首先，必须[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。&amp;</span><span class="sxs-lookup"><span data-stu-id="cad88-148">You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="cad88-149">将关键字复制到文本文件中，并确保每个关键字都单独占一行。</span><span class="sxs-lookup"><span data-stu-id="cad88-149">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="cad88-p107">使用 Unicode 编码保存文本文件。在记事本中，依次单击“另存为”\*\*\*\*\>“编码”\*\*\*\*\>“Unicode”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cad88-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="cad88-152">运行下面的 cmdlet，以将文件读入变量中：</span><span class="sxs-lookup"><span data-stu-id="cad88-152">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="cad88-153">运行下面的 cmdlet，以创建词典：</span><span class="sxs-lookup"><span data-stu-id="cad88-153">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="cad88-154">修改现有关键字词典</span><span class="sxs-lookup"><span data-stu-id="cad88-154">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="cad88-155">可能需要修改一个关键字词典中的关键字，或修改一个内置词典。</span><span class="sxs-lookup"><span data-stu-id="cad88-155">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="cad88-156">目前，只能使用 PowerShell 更新自定义关键字词典。</span><span class="sxs-lookup"><span data-stu-id="cad88-156">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="cad88-157">例如，我们将在 PowerShell 中修改一些词条，在可使用编辑器编辑词条的本地位置保存词条，然后就地更新旧词条。</span><span class="sxs-lookup"><span data-stu-id="cad88-157">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="cad88-158">首先，检索字典对象：</span><span class="sxs-lookup"><span data-stu-id="cad88-158">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="cad88-159">打印 `$dict` 将显示各种不同的变量。</span><span class="sxs-lookup"><span data-stu-id="cad88-159">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="cad88-160">关键字本身存储在后端的对象中，但 `$dict.KeywordDictionary` 包含它们的字符串表示形式，将用于修改字典。</span><span class="sxs-lookup"><span data-stu-id="cad88-160">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="cad88-161">修改字典前，需要使用 `.split(',')` 方法将词条字符串转换回数组。</span><span class="sxs-lookup"><span data-stu-id="cad88-161">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="cad88-162">然后，使用 `.trim()` 方法清理掉关键字之间的多余空格，仅留下要使用的关键字。</span><span class="sxs-lookup"><span data-stu-id="cad88-162">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="cad88-p111">现在从词典中删除一些关键字。由于示例词典中只有几个关键字，因此你可以很轻松地就跳到导出词典并在记事本中编辑关键字，但词典通常包含大量文本，所以必须先了解如何在 PowerShell 中轻松编辑关键字。</span><span class="sxs-lookup"><span data-stu-id="cad88-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="cad88-p112">你在最后一步中将关键字保存到了数组中。虽然[从数组中删除项](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))的方法有多种，但简单方法是创建要从词典中删除的关键字数组，再只将要删除的关键字列表中没有的词典关键字复制到其中。</span><span class="sxs-lookup"><span data-stu-id="cad88-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="cad88-p113">运行命令 `$terms`，以显示当前关键字列表。此命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="cad88-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="cad88-169">运行下面的命令，以指定要删除的关键字：</span><span class="sxs-lookup"><span data-stu-id="cad88-169">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="cad88-170">运行下面的命令，以实际删除列表中的关键字：</span><span class="sxs-lookup"><span data-stu-id="cad88-170">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="cad88-p114">运行命令 `$updatedTerms`，以显示更新后的关键字列表。此命令的输出如下所示（指定关键字已遭删除）：</span><span class="sxs-lookup"><span data-stu-id="cad88-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="cad88-p115">现在只需打开文件，添加其他关键字，并使用 Unicode 编码 (UTF-16) 保存文件即可。现在将上传更新后的关键字，并就地更新词典。</span><span class="sxs-lookup"><span data-stu-id="cad88-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="cad88-p116">至此，词典已就地更新。请注意，`Identity` 字段需要使用词典名称。如果还要使用 `set-` cmdlet 更改词典名称，只需将包含新词典名称的 `-Name` 参数添加到上面的命令中即可。</span><span class="sxs-lookup"><span data-stu-id="cad88-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="cad88-178">在自定义敏感信息类型和 DLP 策略中使用关键字词典</span><span class="sxs-lookup"><span data-stu-id="cad88-178">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="cad88-179">关键字字典可用作自定义敏感信息类型的匹配要求的一部分，也可用作敏感信息类型本身。</span><span class="sxs-lookup"><span data-stu-id="cad88-179">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="cad88-180">这两者都要求创建[自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="cad88-180">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="cad88-181">请按照链接的文章中的说明创建敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="cad88-181">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="cad88-182">拥有 XML 后，你将需要 GUID 标识符，以供字典使用。</span><span class="sxs-lookup"><span data-stu-id="cad88-182">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="cad88-183">若要获得词典标识，请运行下面的命令，并复制 **Identity** 属性值：</span><span class="sxs-lookup"><span data-stu-id="cad88-183">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="cad88-184">此命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="cad88-184">The output of the command looks like this:</span></span>
  
<span data-ttu-id="cad88-185">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="cad88-185">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="cad88-p118">将标识粘贴到自定义敏感信息类型的 XML 中，并上传它。此时，词典会出现在敏感信息类型列表中，你可以直接在策略中使用它，同时指定必须匹配多少个关键字。</span><span class="sxs-lookup"><span data-stu-id="cad88-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
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
