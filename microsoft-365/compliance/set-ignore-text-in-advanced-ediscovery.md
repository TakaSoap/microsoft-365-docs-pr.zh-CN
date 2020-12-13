---
title: 设置"忽略文本"选项以在高级电子数据展示中分析
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: 了解如何定义在高级电子数据展示中使用分析和处理模块时忽略特定文本的规则。
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663467"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a>设置"忽略文本"选项以在高级电子数据展示和经典 (分析) 

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
忽略文本功能可应用于以下所有或任一高级电子数据展示模块：分析 (近重复项、电子邮件线程、主题) 和相关性。 忽略的文本将不会显示在相关性中显示的文件中，并且分析/计算将丢弃忽略的文本。
  
如果以前为已经运行的模块定义了"忽略文本"功能，则"忽略文本"设置现在将受到保护，不会进行修改。 但是，相关性模块的"忽略文本"功能仍可随时更改。
  
## <a name="how-ignore-text-filters-are-applied"></a>如何应用忽略文本筛选器

将按输入的顺序应用多个忽略文本筛选器。 若要更改应用的顺序，必须删除它们，然后按所需顺序重新输入它们。
  
例如，如果文本内容为"DAVE BOB ALICE ALICE ALICE 一文"，则下面是"忽略文本"条目的示例以及这些条目产生的结果：

|**忽略文本条目** <br/> |**结果** <br/> |
|:-----|:-----|
|"ALICE"、"BOB  <br/> |"DAVE 一文"  <br/> |
|"ALICE"、"BOB ALICE ALICE"  <br/> |"DAVE BOB 一级 2013  <br/> |
   
第二个"忽略文本"条目未实现，因为在应用了第一个"忽略文本"后找不到该字符串。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>定义忽略文本时使用正则表达式

正则表达式支持在定义忽略文本时使用。 以下是正则表达式语法和用法的示例：
  
- 若要删除 (忽略) 从 Begin 到行末尾的文本：
    
     `Begin(.*)$`
    
    其中"Begin"是行中此字符串的初始匹配项。
    
    例如，对于以下文本：
    
    **"这是第一句和第一行**
    
    **这是第二句和第二行"**
    
    正则表达式第一 (。 \*) $ 将导致：
    
    **"This is**
    
    **这是第二句和第二行"**
    
- 若要删除自动插入到电子邮件线索末尾的免责声明和法律声明，请执行下列操作：
    
     `Begin(.|\s)*End`
    
    其中，"Begin"和"End"是环绕文本段落的开头和结尾的唯一字符串。 
    
    例如，以下正则表达式将删除在电子邮件线程中"开始"和"结束"字符串之间的免责声明和法律声明：
    
    **此邮件包含机密信息 (。|\s) \* 如果需要验证，请请求硬拷贝版本**
    
- 若要删除包含 (字符的免责声明) ： 
    
    例如，对于以下文本 (x's) ： 
    
    **/\*\ 此消息包含机密信息。xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx 如果需要验证，请请求硬复制版本。/\*\**
    
    用于删除上述免责声明的正则表达式应为： 
    
    **\/\\*\\此邮件包含机密信息 \. (。|\s) \* 如果需要验证，请请求硬拷贝版本 \.\/\\*\\**
    
- 正则表达式规则：
    
  - 除空格之外，不是字母表中的任何字符都必须 () 、"_"和"-"前面必须有" \" 。
    
  - 常规 eExpression 字段的长度可以不受限制。
    
> [!TIP]
> 有关正则表达式的说明和详细语法，请参阅： [正则表达式语言 - 快速参考](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)。 
  
## <a name="define-ignore-text-rule"></a>定义忽略文本规则

1. 在 **"管理 \> 分析 \> 分析选项** "选项卡的"忽略 **文本** "部分，单击 **+** 图标以添加规则。 
    
2. 在 **"添加忽略文本** "对话框中的 **"** 名称"字段中，键入"忽略文本"规则的名称。 
    
    ![添加忽略的文本](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. 在 **文本框** 中，键入要忽略的文本。 文本字段允许无限数量的字符。 
    
    > [!TIP]
    > 如上面的窗口所示，单击 **灯以** 查看忽略文本规则的常见语法准则。 
  
4. 如果需要 **，请** 选中"区分大小写"复选框。 
    
5. 在 **"应用于"** 列表中，选择要应用定义的高级电子数据展示模块。 
    
6. 如果希望对示例文本运行测试，请在"输入"文本框中键入示例文本，然后单击"**测试"。** 结果显示在"输出 **"** 文本框中。 
    
7. 单击 **"确定** "保存"忽略文本"规则。 将显示定义的"忽略文本"规则。 
    
    ![设置被忽略的文本名称](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>另请参阅

[高级电子数据展示（经典）](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置 分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

