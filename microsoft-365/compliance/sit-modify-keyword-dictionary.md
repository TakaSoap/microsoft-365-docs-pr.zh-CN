---
title: 修改关键字词典
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何在合规性中心内修改Microsoft 365词典。
ms.openlocfilehash: 3cf6a2df702a109a5e63c641f7ac64a9f9ab7b4f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60187997"
---
# <a name="modify-a-keyword-dictionary"></a>修改关键字词典

可能需要修改一个关键字词典中的关键字，或修改一个内置词典。 可以通过 PowerShell 或合规中心完成此操作。

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>在合规中心修改关键字词典

关键字字典可以用作或用作 SIT 模式 (`Primary elements` `Supporting elements` 敏感信息) 类型。 可以在创建 SIT 时或现有 SIT 中编辑关键字词典。 例如，编辑现有关键字词典：

1. 打开包含要更新的关键字词典的模式。
2. 找到要更新的关键字词典并选择"编辑"。 
3.  每行使用一个关键字进行编辑。

![屏幕截图编辑关键字。](../media/edit-keyword-dictionary.png)

4. 选择 `Done` 。

## <a name="modify-a-keyword-dictionary-using-powershell"></a>使用 PowerShell 修改关键字词典 

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
  
你在最后一步中将关键字保存到了数组中。虽然[从数组中删除项](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))的方法有多种，但简单方法是创建要从词典中删除的关键字数组，再只将要删除的关键字列表中没有的词典关键字复制到其中。
  
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

现在打开文件，添加其他关键字，并使用 Unicode 编码 (UTF-16) 保存文件即可。现在将上传更新后的关键字，并就地更新词典。
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

现在字典已经更新到位了。 `Identity` 字段采用字典名称。 如果还要使用 `set-` cmdlet 更改词典名称，只需将包含新词典名称的 `-Name` 参数添加到上面的命令中即可。 

另请参阅
- [创建关键字字典](create-a-keyword-dictionary.md)
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
