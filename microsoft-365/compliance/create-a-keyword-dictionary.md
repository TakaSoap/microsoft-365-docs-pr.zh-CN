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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解在 Office 365 安全 & 合规中心中创建关键字词典的基本步骤。
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818051"
---
# <a name="create-a-keyword-dictionary"></a>创建关键字词典

数据丢失防护（DLP）可以识别、监视和保护您的敏感信息。 识别敏感信息有时需要查找关键字，尤其是在标识通用内容（如与医疗保健相关的通信）时，或者不恰当或明确的语言。 虽然您可以在敏感信息类型中创建关键字列表，但关键字列表的大小受到限制，并需要修改 XML 以创建或编辑它们。 关键字字典提供了更简单的关键字管理和更大的规模，支持每个字典最多为100000个术语。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>创建关键字词典的基本步骤

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. 使用**安全 & 合规性中心**（ [https://protection.office.com](https://protection.office.com) ）或连接到**安全 &amp; 合规中心 PowerShell**。
    
2. **定义或加载所需源中的关键字**。 向导和 cmdlet 都接受以逗号分隔的关键字列表来创建自定义关键字词典，因此此步骤将略有不同，具体取决于您的关键字来自何处。 加载后的关键字会在导入前编码并转换为字节数组。
    
3. **创建词典**。 选择名称和说明并创建词典。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>使用安全 & 合规中心创建关键字词典

使用以下步骤创建和导入自定义词典关键字：

1. 连接到安全 & 合规中心（ [https://protection.office.com](https://protection.office.com) ）。

2. 导航到 **“分类”>“敏感信息类型”**。

3. 选择“**创建**”并输入敏感信息类型的“**名称**”和“**说明**”，然后选择“**下一步**”

4. 选择“**添加元素**”，然后选择“**检测内容包含**”下拉列表中的“**词典（大关键字）**”中。

5. 选择“**添加词典**”

6. 在“搜索”控件下，选择“**你可以在此处新建关键字词典**”。

7. 输入自定义词典的“**名称**”。

8. 选择“**导入**”，并根据关键字文件类型选择“**从文本**”或“**从 csv**”。

9. 在文件对话框中，从本地电脑或网络文件共享中选择关键字文件，然后选择“**打开**”。

10. 选择“**保存**”，然后从“**关键字词典**”列表中选择自定义词典。

11. 选择“**添加**”，然后选择“**下一步**”。

12. 检查并完成敏感信息类型选择，然后选择“**完成**”。
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>使用 PowerShell 通过文件创建关键字词典

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. 将关键字复制到文本文件中，并确保每个关键字都单独占一行。
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
3. 运行下面的 cmdlet，以将文件读入变量中：
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. 运行下面的 cmdlet，以创建词典：
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>修改现有关键字词典

可能需要修改一个关键字词典中的关键字，或修改一个内置词典。 目前，只能使用 PowerShell 更新自定义关键字词典。 

例如，我们将在 PowerShell 中修改一些术语，在本地保存这些术语，以便在编辑器中修改它们，然后就地更新以前的术语。 

首先，检索词典对象：
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

打印 `$dict` 将显示各种变量。 关键字本身存储在后端的对象中，但 `$dict.KeywordDictionary` 包含它们的字符串表示形式，您将使用这些关键字来修改字典。 

在修改字典之前，需要使用方法将术语字符串重新转换为数组 `.split(',')` 。 然后，使用方法清除关键字之间不需要的空格 `.trim()` ，只保留要使用的关键字。 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
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

运行下面的命令，以指定要删除的关键字：
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

运行下面的命令，以实际删除列表中的关键字：
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
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

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>在自定义敏感信息类型和 DLP 策略中使用关键字词典

关键字字典可用作自定义敏感信息类型的匹配要求的一部分，也可用作敏感信息类型本身。 两者都要求您创建[自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。 按照链接的文章中的说明操作，以创建敏感的信息类型。 拥有 XML 之后，你将需要使用字典的 GUID 标识符来使用它。
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

若要获得词典标识，请运行下面的命令，并复制 **Identity** 属性值： 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

此命令的输出如下所示：
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
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
