---
title: 'SharePoint 整合辅助功能模式 '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: 了解如何在 SharePoint Syntex 中培训模型时使用辅助功能模式。
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515144"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="06c12-103">SharePoint 整合辅助功能模式</span><span class="sxs-lookup"><span data-stu-id="06c12-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="06c12-104">在 [SharePoint Syntex](index.md)中，用户可以在使用示例文档时在模型 (、培训、测试) 启用辅助功能模式。</span><span class="sxs-lookup"><span data-stu-id="06c12-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="06c12-105">使用辅助功能模式可帮助低视力用户在文档查看器中导航和标记项目时更轻松地使用键盘辅助功能。</span><span class="sxs-lookup"><span data-stu-id="06c12-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="06c12-106">这可帮助用户使用键盘在文档查看器中浏览文本，并不仅听到所选值的旁白，还有助于听到操作 (（如标记或删除所选文本) 中的标签）或用其他示例文档训练模型时预测的标签值。</span><span class="sxs-lookup"><span data-stu-id="06c12-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![辅助功能模式](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="06c12-108">要求</span><span class="sxs-lookup"><span data-stu-id="06c12-108">Requirements</span></span>

<span data-ttu-id="06c12-109">若要听到旁白的音频，请确保在 Windows 10 系统[](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)上的讲述人设置中打开"讲述人"应用。</span><span class="sxs-lookup"><span data-stu-id="06c12-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![打开"讲述人"](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="06c12-111">为键盘用户标记</span><span class="sxs-lookup"><span data-stu-id="06c12-111">Labeling for keyboard users</span></span>

<span data-ttu-id="06c12-112">对于使用辅助功能模式的键盘用户，如果在查看器中标记示例文档中的文本，可以使用以下键：</span><span class="sxs-lookup"><span data-stu-id="06c12-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="06c12-113">Tab：向前移动并选择下一个单词。</span><span class="sxs-lookup"><span data-stu-id="06c12-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="06c12-114">Tab + Shift：向后移动并选择上一个单词。</span><span class="sxs-lookup"><span data-stu-id="06c12-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="06c12-115">Enter： Label or removes a label from the selected word.</span><span class="sxs-lookup"><span data-stu-id="06c12-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="06c12-116">向右箭头：在所选单词中的单个字符之间向前移动。</span><span class="sxs-lookup"><span data-stu-id="06c12-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="06c12-117">向左箭头：在所选单词中的单个字符之间向后移动。</span><span class="sxs-lookup"><span data-stu-id="06c12-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="06c12-118">如果要为单个标签标记多个单词，则需要标记每个单词。</span><span class="sxs-lookup"><span data-stu-id="06c12-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="06c12-119">旁白</span><span class="sxs-lookup"><span data-stu-id="06c12-119">Narration</span></span>

<span data-ttu-id="06c12-120">对于使用辅助功能模式的讲述人用户，使用相同的键盘导航，以便键盘用户浏览查看器中的示例文档。</span><span class="sxs-lookup"><span data-stu-id="06c12-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="06c12-121">在浏览示例文档和标签字符串值时，讲述人会向用户提供以下音频提示：</span><span class="sxs-lookup"><span data-stu-id="06c12-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="06c12-122">当您使用键盘在文档查看器中导航时，讲述人音频将说明所选的字符串。</span><span class="sxs-lookup"><span data-stu-id="06c12-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="06c12-123">在选定的字符串中，讲述人音频在使用向左或向右箭头键选择每个字符时，将说明字符串中的每个字符。</span><span class="sxs-lookup"><span data-stu-id="06c12-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="06c12-124">如果选择已标记的字符串，讲述人将声明该值，然后进行"标记"。</span><span class="sxs-lookup"><span data-stu-id="06c12-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="06c12-125">例如，如果标签值为"Contoso"，它将声明"Costoso labeled"。</span><span class="sxs-lookup"><span data-stu-id="06c12-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="06c12-126">在培训选项卡中，如果在文档查看器中选择一个仅预测的字符串，讲述人音频将声明该值，然后"预测"。</span><span class="sxs-lookup"><span data-stu-id="06c12-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="06c12-127">当培训预测文件中与用户标记的值不匹配的值时，会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="06c12-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="06c12-128">在培训选项卡中，如果在文档查看器中选择已标记和预测的字符串，讲述人音频将声明值，然后进行"标记和预测"。</span><span class="sxs-lookup"><span data-stu-id="06c12-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="06c12-129">当培训成功且预测值与用户标签匹配时，会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="06c12-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="06c12-130">在查看器中标记字符串或删除标签后，讲述人音频会警告你在退出之前保存更改。</span><span class="sxs-lookup"><span data-stu-id="06c12-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="06c12-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06c12-131">See Also</span></span>

[<span data-ttu-id="06c12-132">创建提取程序</span><span class="sxs-lookup"><span data-stu-id="06c12-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="06c12-133">创建分类器</span><span class="sxs-lookup"><span data-stu-id="06c12-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



