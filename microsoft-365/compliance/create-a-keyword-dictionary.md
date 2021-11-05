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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: 了解在 Office 365 安全与合规中心中创建关键字字典的基本步骤。
ms.openlocfilehash: b1749b51367bda90945e0d8e61e9674acc5077b6
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747718"
---
# <a name="create-a-keyword-dictionary"></a>创建关键字字典

数据丢失防护 (DLP) 可识别、监视和保护敏感项目。 标识敏感项目有时需要查找关键字，尤其是在标识常规内容（如与医疗保健相关的通信）或不当或露骨语言时。 虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小是有限的，且需要修改 XML 才能创建或编辑它们。 关键字字典可更简单地管理关键字，并且规模更大，可支持多达 1 MB 的术语（压缩后），并支持所有语言。 租户限制同样为压缩后 1 MB。 压缩后限值 1 MB 意味着租户中合并的所有词典可能接近 100 万字符。

## <a name="keyword-dictionary-limits"></a>关键字字典限制

每个租户最多可以创建 50 种基于关键字字典的敏感信息类型。 要了解租户中有多少关键字词典，请使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)中的过程进行连接，以连接到租户并运行此 PowerShell 脚本。

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

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>创建关键字词典的基本步骤

词典可能有多个关键字来源，最常见的来源是服务或 PowerShell cmdlet 中导入的文件（如 .csv 或 .txt 列表）、你直接在 PowerShell cmdlet 中输入的列表或现有词典。创建关键字词典时，请遵循下面的相同核心步骤：
  
1. 使用 *<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 安全与合规中心</a> 或连接到 **安全 &amp; 合规中心 PowerShell**。
    
2. **定义或从预期源加载关键字**。向导和 cmdlet 都接受以逗号分隔的关键字列表来创建自定义关键字字典，因此这一步骤将略有不同，具体取决于关键字的来源。加载后，在导入之前将对其进行编码并转换为字节数组。
    
3. **创建字典**。选择名称和说明并创建字典。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>使用安全与合规中心创建关键字字典

使用以下步骤创建和导入自定义字典关键字：

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>。

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

如果经常需要创建大型字典，则使用从其他某来源导出的文件或列表中的关键字。在此案例中，你将创建包含要在外部电子邮件中筛查的不当语言列表的关键字字典。首先，必须 [连接到安全 &amp; 与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。
  
1. 将关键字复制到文本文件中，并确保每个关键字都单独占一行。
    
2. 使用 Unicode 编码保存文本文件。在记事本中，依次单击“另存为”\>“编码”\>“Unicode”。
    
3. 运行下面的 cmdlet，以将文件读入变量中：
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. 运行下面的 cmdlet，以创建词典：
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>在自定义敏感信息类型和 DLP 策略中使用关键字词典

关键字词典可用作自定义敏感信息类型的部分匹配要求，也可用作敏感信息类型本身。上述两种情况都要求 [创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。请按照链接文章中的说明操作，以创建敏感信息类型。创建 XML 后，必须具有 GUID 标识符才能使用字典。
  
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


将标识粘贴到自定义敏感信息类型的 XML 中，并上传它。此时，词典会出现在敏感信息类型列表中，你可以直接在策略中使用它，同时指定必须匹配多少个关键字。
  
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
> Microsoft 365 信息保护支持双字节字符集语言，用于:
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语
>
>此支持适用于敏感信息类型。 有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。

> [!TIP]
> 若要检测含有中文/日文字符和单字节字符的模式，或检测含有中文/日文和英文的模式，则需要定义两个变体的关键词或词组。 
> - 例如，若要检测像“机密的文件”这样的关键词，则要使用该关键词的两个变体; 一个是在日语和英语文本之间有空格，另一个是在日语和英语文本之间没有空格。 因此，在 SIT 中要添加的关键词应该是“机密的 文档”和“机密的文档”。 同样，若要检测短语 "東京オリンピック2020"，则应该使用两个变体;“東京オリンピック 2020”和“東京オリンピック2020”。

> 除了中文/日语/双字节字符外，如果关键字/短语列表中还包含非中文/日语字词（如仅含英语的字词），建议创建两个字典/关键字列表。 一个针对包含中文/日语/双字节字符的关键字，另一个针对仅含英语的关键字。 
> - 例如，如果要创建包含“Highly confidential”、“機密性が高い”和“机密的document”这三个短语的关键字字典/列表，则应创建两个关键字列表。 
>     1. Highly confidential
>     2. “機密性が高い”、“机密的document”和“机密的 document”
>     
> 当使用双字节连字符或双字节句号创建 regex 时，请确保像在 regex 中转义连字符或句号一样转义这两个字符。以下是供参考的示例 regex：
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> 建议在关键词列表中使用字符串匹配而不是单词匹配。
