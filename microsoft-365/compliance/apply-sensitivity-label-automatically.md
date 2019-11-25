---
title: 将敏感度标签自动应用于内容
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: 11/01/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 创建敏感度标签时，你可以自动为文档或电子邮件分配标签，也可以提示用户选择你建议的标签。
ms.openlocfilehash: eccc60dc7a306f3e7b2eb128ed45a92af65491a5
ms.sourcegitcommit: cd748ca00088275372f51fbf8c4bc72bfd3e1437
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "39233207"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="1e5c7-103">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="1e5c7-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="1e5c7-104">创建敏感度标签时，你可以自动将该标签分配给包含敏感信息的内容，也可以提示用户应用你建议的标签。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-104">When you create a sensitivity label, you can automatically assign that label to content containing sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="1e5c7-105">能否将敏感度标签自动应用于内容非常重要，这是因为：</span><span class="sxs-lookup"><span data-stu-id="1e5c7-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="1e5c7-106">你无需为用户提供有关所有分类的培训。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="1e5c7-107">你无需依赖用户即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="1e5c7-108">用户不再需要了解你的策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-108">Users no longer need to know about your policies - they can instead focus on their work.</span></span>

<span data-ttu-id="1e5c7-109">有关许可证要求的信息，请参阅 [Office 应用中的敏感度标签](sensitivity-labels-office-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-109">For information about license requirements, see [Sensitivity labels in Office apps](sensitivity-labels-office-apps.md).</span></span>

<span data-ttu-id="1e5c7-110">在 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心的“分类”\*\*\*\* > “敏感度标签”\*\*\*\* 下创建敏感度标签时，可使用自动标签设置。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-110">The auto-labeling settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center under **Classification** > **Sensitivity labels**.</span></span>

![灵敏度标签的自动标签选项](media/Sensitivity-labels-Auto-labeling-options.png)

## <a name="apply-a-sensitivity-label-automatically-based-on-conditions"></a><span data-ttu-id="1e5c7-112">根据条件自动应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="1e5c7-112">Apply a sensitivity label automatically based on conditions</span></span>

<span data-ttu-id="1e5c7-113">敏感度标签最强大的功能之一是能够将其自动应用于符合特定条件的内容。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-113">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the sensitivity labels - Office 365 does the work for them.</span></span> <span data-ttu-id="1e5c7-114">此情况下，组织中的人员无需应用敏感度标签 - Office 365 会代为操作。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches certain conditions. In this case, people in your organization don't need to apply the sensitivity labels - Office 365 does the work for them.</span></span>

<span data-ttu-id="1e5c7-p102">当内容包含特定类型的敏感信息时，可以选择自动将敏感度标签应用于该内容。配置要自动应用的敏感度标签时，你会看到与创建数据丢失防护 (DLP) 策略时相同的敏感信息类型列表。因此，可以自动将“高度机密”标签应用于包含客户个人身份信息 (PII)（例如信用卡号或社会安全号码）的任何内容。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-p102">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information. When you configure a sensitivity label to be applied automatically, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy. So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers.</span></span>

![实例计数和匹配准确度的选项](media/Sensitivity-labels-instance-count-match-accuracy.png)

<span data-ttu-id="1e5c7-119">选择敏感信息类型后，可通过更改实例计数或匹配准确度来优化条件。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-119">After you choose your sensitive informaton types, you can refine your condition by changing the instance count or match accuracy. For more information, see Tuning rules to make them easier or harder to match.</span></span> <span data-ttu-id="1e5c7-120">有关详细信息，请参阅[调整规则以使其更容易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-120">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="1e5c7-121">此外，也可选择某项条件是必须删除所有敏感信息类型还是只删除其中一种。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-121">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="1e5c7-122">要使条件更灵活或更复杂，可添加组并在组之间使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-122">Further, you can choose whether a condition must detect all of the sensitive infromation types, or just one of them. And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups. For more information, see Grouping and logical operators.</span></span> <span data-ttu-id="1e5c7-123">有关详细信息，请参阅[分组和逻辑运算符](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-123">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

<span data-ttu-id="1e5c7-p105">当自动应用敏感度标签时，用户会在其 Office 应用中看到通知。他们可以选择“**确定**”以关闭通知。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-p105">When a sensitivity label is automatically applied, the user sees a notification in their Office app. They can choose **OK** to dismiss the notification.</span></span>

![指出文档自动应用了标签的通知](media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="1e5c7-127">建议用户应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="1e5c7-127">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="1e5c7-128">如果愿意，可建议你的用户应用此标签。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-128">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="1e5c7-129">通过此选项，你的用户可接受分类及任何相关保护，也可在标签不适合其文档或电子邮件时关闭建议。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-129">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label is not suitable for their document or email.</span></span>

<span data-ttu-id="1e5c7-130">建议的标签在 Word、PowerPoint 和 Excel 中受支持（需要安装 Azure 信息保护统一标记客户端）。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-130">Note that recommended labels are supported in Word, PowerPoint, and Excel (and require that the Azure Information Protection unified labeling client is installed). We're working on support for recommended labels in Outlook.</span></span>

![用于向用户建议敏感度标签的选项](media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="1e5c7-p107">以下示例是配置条件来将标签应用为建议操作时的提示以及自定义策略提示。你可以选择策略提示中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-p107">Here's an example of a prompt when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![关于应用建议标签的提示](media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="1e5c7-135">如何应用自动标签或建议标签</span><span class="sxs-lookup"><span data-stu-id="1e5c7-135">How automatic or recommended labels are applied</span></span>

- <span data-ttu-id="1e5c7-136">自动标记在你保存文档时应用于 Word、Excel 和 PowerPoint，在你发送电子邮件时应用于 Outlook。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-136">Automatic labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span> <span data-ttu-id="1e5c7-137">这些条件会检测文档和电子邮件的正文文本和页眉页脚中是否有敏感信息，但不检测电子邮件的主题行或附件。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-137">Automatic labeling applies to Word, Excel, and PowerPoint when documents are saved, and to Outlook when emails are sent. These conditions detect sensitive information in the body text in documents and emails, and to headers and footers -- but not in the subject line or attachments of email.</span></span>

- <span data-ttu-id="1e5c7-138">不可对之前已手动标记或者之前已自动标记有更高级分类的文档和电子邮件使用自动分类。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-138">You cannot use automatic classification for documents and emails that were previously manually labeled, or previously automatically labeled with a higher classification. Remember, a document or email can have only a single sensitivity label applied to it (in addition to a single retention label).</span></span> <span data-ttu-id="1e5c7-139">请记住，除了一个保留标签，另外仅可向文档或电子邮件应用一个敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-139">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="1e5c7-140">在保存文档时，建议分类会应用于 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-140">Recommended classification applies to Word, Excel, and PowerPoint when you save documents.</span></span>

- <span data-ttu-id="1e5c7-141">不可对之前标记有更高级分类的文档使用建议的分类。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-141">You can't use recommended classification for documents that were previously labeled with a higher classification.</span></span> <span data-ttu-id="1e5c7-142">如果内容已标记有更高级分类，则用户不会看到带有建议和策略提醒的提示。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-142">You cannot use recommended classification for documents that were previously labeled with a higher classification. In this case, when the content's already labeled with a higher classification, the user won't see the prompt with the recommendation and policy tip.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="1e5c7-143">在多个条件适用于多个标签时如何评估这些条件</span><span class="sxs-lookup"><span data-stu-id="1e5c7-143">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="1e5c7-p111">根据你在策略中为标签指定的位置按顺序对标签进行评估：位置最靠前的标签具有最低位置（最不敏感），位置最靠后的标签具有最高位置（最敏感）。有关优先级的详细信息，请参阅[标签优先级（顺序很重要）](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-p111">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="1e5c7-146">不要将父标签配置为自动应用或推荐使用</span><span class="sxs-lookup"><span data-stu-id="1e5c7-146">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="1e5c7-147">请记住，不可向内容应用父标签（即带子标签的标签）。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-147">Remember, a parent label (a label with sublabels) can't be applied to content.</span></span> <span data-ttu-id="1e5c7-148">确保未将父标签配置为自动应用或推荐使用，因为父标签不会应用于使用 Azure 信息保护统一标签客户端的 Office 应用程序中的内容。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-148">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="1e5c7-149">有关父标签和子标签的更多信息，请参阅[子标签（对标签进行分组）](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="1e5c7-149">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
