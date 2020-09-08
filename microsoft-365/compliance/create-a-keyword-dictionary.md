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
ms.openlocfilehash: bad95e9a5605631de3e8652e7243909f28b2abde
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282732"
---
# <a name="create-a-keyword-dictionary"></a>创建关键字字典

数据丢失防护 (DLP) 可识别、监视和保护敏感项目。 标识敏感项目有时需要查找关键字，尤其是在标识常规内容（如与医疗保健相关的通信）或不当或露骨语言时。 虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小是有限的，且需要修改 XML 才能创建或编辑它们。 关键字字典可更简单地管理关键字，并且规模更大，可支持多达 100KB 的术语（压缩后），并支持所有语言。 租户限制同样为压缩后 100KB。
  
> [!NOTE]
> Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持（预览）：
> - 简体中文
> - 繁体中文
> - 韩语
> - 日语
> 
>此功能预览仅在商业云中提供，并且仅在以下地区推出：
> - 日本
> - 韩国
> - 中国大陆
> - 香港特别行政区
> - 澳门特别行政区
> - 中国台湾
>
>此支持适用于敏感信息类型。 有关详细信息，请参阅[双字节字符集的信息保护支持发行说明（预览版）](mip-dbcs-relnotes.md)。

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>创建关键字词典的基本步骤

词典可能有多个关键字来源，最常见的来源是服务或 PowerShell cmdlet 中导入的文件（如 .csv 或 .txt 列表）、你直接在 PowerShell cmdlet 中输入的列表或现有词典。创建关键字词典时，请遵循下面的相同核心步骤：
  
1. 使用**安全与合规中心** ([https://protection.office.com](https://protection.office.com)) 或连接到**安全与合规中心 PowerShell**。&amp;
    
2. **定义或加载目标来源中的关键字**。 该向导和 cmdlet 均接受逗号分隔的关键字列表，以创建自定义关键字字典，所以这一步将会因关键字来源不同而略有差异。 加载后的关键字会在导入前编码并转换为字节数组。
    
3. **创建字典**。 选择名称和说明，并创建字典。

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>使用安全与合规中心创建关键字字典

使用以下步骤创建和导入自定义字典关键字：

1. 连接到安全与合规中心 ([https://protection.office.com](https://protection.office.com))。

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

通常情况下，在需要创建大型字典时，可使用从某些其他来源导出的文件或列表中的关键字。 在这种情况下，将会创建一个关键字字典，其中包含将在外部电子邮件中筛选的不当语言的列表。 首先，必须[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。&amp;
  
1. 将关键字复制到文本文件中，并确保每个关键字都单独占一行。
    
2. 使用 Unicode 编码保存文本文件。在记事本中，依次单击“另存为”****\>“编码”****\>“Unicode”****。
    
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

例如，我们将在 PowerShell 中修改一些词条，在可使用编辑器编辑词条的本地位置保存词条，然后就地更新旧词条。 

首先，检索字典对象：
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

打印 `$dict` 将显示各种不同的变量。 关键字本身存储在后端的对象中，但 `$dict.KeywordDictionary` 包含它们的字符串表示形式，将用于修改字典。 

修改字典前，需要使用 `.split(',')` 方法将词条字符串转换回数组。 然后，使用 `.trim()` 方法清理掉关键字之间的多余空格，仅留下要使用的关键字。 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

现在从词典中删除一些关键字。由于示例词典中只有几个关键字，因此你可以很轻松地就跳到导出词典并在记事本中编辑关键字，但词典通常包含大量文本，所以必须先了解如何在 PowerShell 中轻松编辑关键字。
  
你在最后一步中将关键字保存到了数组中。虽然[从数组中删除项](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))的方法有多种，但简单方法是创建要从词典中删除的关键字数组，再只将要删除的关键字列表中没有的词典关键字复制到其中。
  
运行命令 `$terms`，以显示当前关键字列表。此命令的输出如下所示： 
  
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

运行命令 `$updatedTerms`，以显示更新后的关键字列表。此命令的输出如下所示（指定关键字已遭删除）： 
  
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

现在只需打开文件，添加其他关键字，并使用 Unicode 编码 (UTF-16) 保存文件即可。现在将上传更新后的关键字，并就地更新词典。
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

至此，词典已就地更新。请注意，`Identity` 字段需要使用词典名称。如果还要使用 `set-` cmdlet 更改词典名称，只需将包含新词典名称的 `-Name` 参数添加到上面的命令中即可。 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>在自定义敏感信息类型和 DLP 策略中使用关键字词典

关键字字典可用作自定义敏感信息类型的匹配要求的一部分，也可用作敏感信息类型本身。 这两者都要求创建[自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。 请按照链接的文章中的说明创建敏感信息类型。 拥有 XML 后，你将需要 GUID 标识符，以供字典使用。
  
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
