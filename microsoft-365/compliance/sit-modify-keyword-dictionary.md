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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何在合规性中心内修改Microsoft 365词典。
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685198"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="3af92-103">修改关键字词典</span><span class="sxs-lookup"><span data-stu-id="3af92-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="3af92-104">可能需要修改一个关键字词典中的关键字，或修改一个内置词典。</span><span class="sxs-lookup"><span data-stu-id="3af92-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="3af92-105">可以通过 PowerShell 或合规中心完成此操作。</span><span class="sxs-lookup"><span data-stu-id="3af92-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="3af92-106">在合规中心修改关键字词典</span><span class="sxs-lookup"><span data-stu-id="3af92-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="3af92-107">关键字词典可以用作或用作 SIT 模式 (`Primary elements` `Supporting elements` 敏感信息) 类型。</span><span class="sxs-lookup"><span data-stu-id="3af92-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="3af92-108">可以在创建 SIT 时或现有 SIT 中编辑关键字词典。</span><span class="sxs-lookup"><span data-stu-id="3af92-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="3af92-109">例如，编辑现有关键字词典：</span><span class="sxs-lookup"><span data-stu-id="3af92-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="3af92-110">打开包含要更新的关键字词典的模式。</span><span class="sxs-lookup"><span data-stu-id="3af92-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="3af92-111">找到要更新的关键字词典并选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="3af92-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="3af92-112">每行使用一个关键字进行编辑。</span><span class="sxs-lookup"><span data-stu-id="3af92-112">Make your edits, using one keyword per line.</span></span>

![屏幕截图编辑关键字](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="3af92-114">选择 `Done` 。</span><span class="sxs-lookup"><span data-stu-id="3af92-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="3af92-115">使用 PowerShell 修改关键字词典</span><span class="sxs-lookup"><span data-stu-id="3af92-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="3af92-116">例如，我们将在 PowerShell 中修改一些词条，在可使用编辑器编辑词条的本地位置保存词条，然后就地更新旧词条。</span><span class="sxs-lookup"><span data-stu-id="3af92-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="3af92-117">首先，检索字典对象：</span><span class="sxs-lookup"><span data-stu-id="3af92-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="3af92-118">打印 `$dict` 将显示各种不同的变量。</span><span class="sxs-lookup"><span data-stu-id="3af92-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="3af92-119">关键字本身存储在后端的对象中，但 `$dict.KeywordDictionary` 包含它们的字符串表示形式，将用于修改字典。</span><span class="sxs-lookup"><span data-stu-id="3af92-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="3af92-120">修改字典前，需要使用 `.split(',')` 方法将词条字符串转换回数组。</span><span class="sxs-lookup"><span data-stu-id="3af92-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="3af92-121">然后，使用 `.trim()` 方法清理掉关键字之间的多余空格，仅留下要使用的关键字。</span><span class="sxs-lookup"><span data-stu-id="3af92-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="3af92-p105">现在从词典中删除一些关键字。由于示例词典中只有几个关键字，因此你可以很轻松地就跳到导出词典并在记事本中编辑关键字，但词典通常包含大量文本，所以必须先了解如何在 PowerShell 中轻松编辑关键字。</span><span class="sxs-lookup"><span data-stu-id="3af92-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="3af92-p106">你在最后一步中将关键字保存到了数组中。虽然[从数组中删除项](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10))的方法有多种，但简单方法是创建要从词典中删除的关键字数组，再只将要删除的关键字列表中没有的词典关键字复制到其中。</span><span class="sxs-lookup"><span data-stu-id="3af92-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="3af92-p107">运行命令 `$terms`，以显示当前关键字列表。此命令的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="3af92-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
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

<span data-ttu-id="3af92-128">运行下面的命令，以指定要删除的关键字：</span><span class="sxs-lookup"><span data-stu-id="3af92-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="3af92-129">运行下面的命令，以实际删除列表中的关键字：</span><span class="sxs-lookup"><span data-stu-id="3af92-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="3af92-p108">运行命令 `$updatedTerms`，以显示更新后的关键字列表。此命令的输出如下所示（指定关键字已遭删除）：</span><span class="sxs-lookup"><span data-stu-id="3af92-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
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

<span data-ttu-id="3af92-p109">现在打开文件，添加其他关键字，并使用 Unicode 编码 (UTF-16) 保存文件即可。现在将上传更新后的关键字，并就地更新词典。</span><span class="sxs-lookup"><span data-stu-id="3af92-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="3af92-134">现在字典已经更新到位了。</span><span class="sxs-lookup"><span data-stu-id="3af92-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="3af92-135">`Identity` 字段采用字典名称。</span><span class="sxs-lookup"><span data-stu-id="3af92-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="3af92-136">如果还要使用 `set-` cmdlet 更改词典名称，只需将包含新词典名称的 `-Name` 参数添加到上面的命令中即可。</span><span class="sxs-lookup"><span data-stu-id="3af92-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="3af92-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3af92-137">See Also</span></span>
- [<span data-ttu-id="3af92-138">创建关键字字典</span><span class="sxs-lookup"><span data-stu-id="3af92-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="3af92-139">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="3af92-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
