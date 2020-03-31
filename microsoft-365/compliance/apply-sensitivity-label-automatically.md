---
title: 将敏感度标签自动应用于内容
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 创建敏感度标签时，你可以自动为文档或电子邮件分配标签，也可以提示用户选择你建议的标签。
ms.openlocfilehash: 7edfa83648ecb86ab23a898299edb63df851d123
ms.sourcegitcommit: 7eaecb91c7cb1f8679f99882563f5c1149175992
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "43022929"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="7909d-103">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="7909d-103">Apply a sensitivity label to content automatically</span></span>

<span data-ttu-id="7909d-104">创建敏感度标签时，你可以自动将该标签分配给内容（如果它包含敏感信息），也可以提示用户应用你建议的标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-104">When you create a sensitivity label, you can automatically assign that label to content when it contains sensitive information, or you can prompt users to apply the label that you recommend.</span></span>

<span data-ttu-id="7909d-105">能否将敏感度标签自动应用于内容非常重要，这是因为：</span><span class="sxs-lookup"><span data-stu-id="7909d-105">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="7909d-106">你无需为用户提供有关所有分类的培训。</span><span class="sxs-lookup"><span data-stu-id="7909d-106">You don't need to train your users on all of your classifications.</span></span>

- <span data-ttu-id="7909d-107">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="7909d-107">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="7909d-108">用户不再需要了解你的策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="7909d-108">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="7909d-109">Azure 信息保护统一标记客户端支持适用于 Windows 的 Office 应用中的自动标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-109">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7909d-110">对于 Office 应用中的内置标签，此功能[在某些应用中处于预览状态](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="7909d-110">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="7909d-111">[创建或编辑敏感度标签](create-sensitivity-labels.md)时，可使用 Office 应用的自动标签设置：</span><span class="sxs-lookup"><span data-stu-id="7909d-111">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![敏感度标签的自动标签选项](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="7909d-113">如何配置 Office 应用的自动标签</span><span class="sxs-lookup"><span data-stu-id="7909d-113">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="7909d-114">敏感度标签最强大的功能之一是，能够自动应用于符合特定条件的内容。</span><span class="sxs-lookup"><span data-stu-id="7909d-114">One of the most powerful features of sensitivity labels is the ability to apply them automatically to content that matches specific conditions.</span></span> <span data-ttu-id="7909d-115">此情况下，组织中的人员无需应用敏感度标签 - Office 365 会代为操作。</span><span class="sxs-lookup"><span data-stu-id="7909d-115">In this case, people in your organization don't need to apply the sensitivity labels — Office 365 does the work for them.</span></span>

<span data-ttu-id="7909d-116">当内容包含特定类型的敏感信息时，可选择自动将敏感度标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="7909d-116">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="7909d-117">从敏感信息类型或分类器列表中选择：</span><span class="sxs-lookup"><span data-stu-id="7909d-117">Choose from a list of sensitive info types or classifers:</span></span>

![Office 应用中的自动标签的标签条件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="7909d-119">目前，“**分类器**”选项处于有限预览状态，要求你向 Microsoft 提交表单，以便为你的租户启用此功能。</span><span class="sxs-lookup"><span data-stu-id="7909d-119">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="7909d-120">有关详细信息，请参阅博客文章[宣布在 Office 应用中推出使用内置分类器的自动标签 - 有限预览](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)。</span><span class="sxs-lookup"><span data-stu-id="7909d-120">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="7909d-121">当自动应用此敏感度标签时，用户会在其 Office 应用中看到通知。</span><span class="sxs-lookup"><span data-stu-id="7909d-121">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="7909d-122">例如：</span><span class="sxs-lookup"><span data-stu-id="7909d-122">For example:</span></span>

![指出文档自动应用了标签的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="7909d-124">配置标签的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="7909d-124">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="7909d-125">当你选择“**敏感信息类型**”选项时，可看到与创建数据丢失防护 (DLP) 策略时相同的敏感信息类型列表。</span><span class="sxs-lookup"><span data-stu-id="7909d-125">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="7909d-126">例如，你可以将高度机密的标签自动应用到任何包含客户个人身份信息 (PII) 的内容，如信用卡号码或社会保险号码：</span><span class="sxs-lookup"><span data-stu-id="7909d-126">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Office 应用中的自动标签的敏感信息类型](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="7909d-128">选择敏感信息类型后，可通过更改实例计数或匹配准确度来优化条件。</span><span class="sxs-lookup"><span data-stu-id="7909d-128">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="7909d-129">有关详细信息，请参阅[调整规则以使其更容易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="7909d-129">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="7909d-130">此外，也可选择某项条件是必须删除所有敏感信息类型还是只删除其中一种。</span><span class="sxs-lookup"><span data-stu-id="7909d-130">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="7909d-131">要使条件更灵活或更复杂，可添加组并在组之间使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="7909d-131">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="7909d-132">有关详细信息，请参阅[分组和逻辑运算符](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="7909d-132">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![实例计数和匹配准确度的选项](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="7909d-134">为标签配置分类器</span><span class="sxs-lookup"><span data-stu-id="7909d-134">Configuring classifers for a label</span></span>

<span data-ttu-id="7909d-135">当你选择“**分类器**”选项时，请选择一个或多个内置分类器：</span><span class="sxs-lookup"><span data-stu-id="7909d-135">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![分类器和敏感度标签选项](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="7909d-137">有关这些分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="7909d-137">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="7909d-138">在预览期间，以下应用支持敏感度标签的分类器：</span><span class="sxs-lookup"><span data-stu-id="7909d-138">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="7909d-139">适用于 Windows 的 Office 365 专业增强版桌面应用，从 [Office 预览体验成员](https://office.com/insider)：</span><span class="sxs-lookup"><span data-stu-id="7909d-139">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="7909d-140">Word</span><span class="sxs-lookup"><span data-stu-id="7909d-140">Word</span></span>
    - <span data-ttu-id="7909d-141">Excel</span><span class="sxs-lookup"><span data-stu-id="7909d-141">Excel</span></span>
    - <span data-ttu-id="7909d-142">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7909d-142">PowerPoint</span></span>

- <span data-ttu-id="7909d-143">Office 网页版应用 - 如果你已[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)：</span><span class="sxs-lookup"><span data-stu-id="7909d-143">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="7909d-144">Word</span><span class="sxs-lookup"><span data-stu-id="7909d-144">Word</span></span>
    - <span data-ttu-id="7909d-145">Excel</span><span class="sxs-lookup"><span data-stu-id="7909d-145">Excel</span></span>
    - <span data-ttu-id="7909d-146">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7909d-146">PowerPoint</span></span>
    - <span data-ttu-id="7909d-147">Outlook</span><span class="sxs-lookup"><span data-stu-id="7909d-147">Outlook</span></span>

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a><span data-ttu-id="7909d-148">建议用户应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="7909d-148">Recommend that the user apply a sensitivity label</span></span>

<span data-ttu-id="7909d-149">如果愿意，可建议你的用户应用此标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-149">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="7909d-150">通过此选项，你的用户可接受分类及任何相关保护，也可在标签不适合其内容时关闭建议。</span><span class="sxs-lookup"><span data-stu-id="7909d-150">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![用于向用户建议敏感度标签的选项](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="7909d-152">下面的示例展示了 Azure 信息保护统一标记客户端在你配置条件以将标签作为建议操作应用时提供的提示，以及自定义策略提示。</span><span class="sxs-lookup"><span data-stu-id="7909d-152">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip.</span></span> <span data-ttu-id="7909d-153">可以选择在策略提示中显示什么文本。</span><span class="sxs-lookup"><span data-stu-id="7909d-153">You can choose what text is displayed in the policy tip.</span></span>

![关于应用建议标签的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="7909d-155">如何应用自动标签或建议标签</span><span class="sxs-lookup"><span data-stu-id="7909d-155">How automatic or recommended labels are applied</span></span>

<span data-ttu-id="7909d-156">在 Office 应用中，自动标签和建议标签的实现取决于你使用的是内置于 Office 的标签，还是 Azure 信息保护统一标记客户端。</span><span class="sxs-lookup"><span data-stu-id="7909d-156">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7909d-157">不过，在这两种情况下：</span><span class="sxs-lookup"><span data-stu-id="7909d-157">In both cases, however:</span></span>

- <span data-ttu-id="7909d-158">不可对之前已手动标记或者之前已自动标记有更高敏感度的文档和电子邮件使用自动标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-158">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="7909d-159">请记住，除了一个保留标签，另外仅可向文档或电子邮件应用一个敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-159">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="7909d-160">都不能对之前有更高敏感度标签的文档或电子邮件使用建议标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-160">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="7909d-161">如果内容已有更高敏感度标签，用户就看不到建议操作提示和策略提示。</span><span class="sxs-lookup"><span data-stu-id="7909d-161">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="7909d-162">特定于内置标签的注意事项：</span><span class="sxs-lookup"><span data-stu-id="7909d-162">Specific to built-in labeling:</span></span>

- <span data-ttu-id="7909d-163">并非所有 Office 应用都支持自动（和建议）标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-163">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="7909d-164">有关详细信息，请参阅[应用中的敏感度标签功能支持](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="7909d-164">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="7909d-165">对于桌面版 Word 中的建议标签，触发建议的敏感内容会被标记，这样用户就能审阅和删除敏感内容，而不用应用建议的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="7909d-165">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="7909d-166">若要详细了解如何在 Office 应用中应用这些标签、示例屏幕截图，以及如何检测敏感信息，请参阅[对 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。</span><span class="sxs-lookup"><span data-stu-id="7909d-166">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="7909d-167">特定于 Azure 信息保护统一标记客户端的注意事项：</span><span class="sxs-lookup"><span data-stu-id="7909d-167">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="7909d-168">自动标签和建议标签在你保存文档时应用于 Word、Excel 和 PowerPoint，并在你发送电子邮件时应用于 Outlook。</span><span class="sxs-lookup"><span data-stu-id="7909d-168">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="7909d-169">为了让 Outlook 支持建议标签，必须先配置[高级策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。</span><span class="sxs-lookup"><span data-stu-id="7909d-169">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="7909d-170">敏感信息可以在文档和电子邮件的正文文本和页眉、页脚中检测到，但不能在电子邮件的主题行或附件中检测到。</span><span class="sxs-lookup"><span data-stu-id="7909d-170">Sensitive information can be detected in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="7909d-171">在多个条件适用于多个标签时如何评估这些条件</span><span class="sxs-lookup"><span data-stu-id="7909d-171">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="7909d-p115">根据你在策略中为标签指定的位置按顺序对标签进行评估：位置最靠前的标签具有最低位置（最不敏感），位置最靠后的标签具有最高位置（最敏感）。有关优先级的详细信息，请参阅[标签优先级（顺序很重要）](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="7909d-p115">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="7909d-174">不要将父标签配置为自动应用或推荐使用</span><span class="sxs-lookup"><span data-stu-id="7909d-174">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="7909d-175">请记住，不可向内容应用父标签（即带子标签的标签）。</span><span class="sxs-lookup"><span data-stu-id="7909d-175">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="7909d-176">确保未将父标签配置为自动应用或推荐使用，因为父标签不会应用于使用 Azure 信息保护统一标签客户端的 Office 应用程序中的内容。</span><span class="sxs-lookup"><span data-stu-id="7909d-176">Make sure that you don't configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7909d-177">有关父标签和子标签的更多信息，请参阅[子标签（对标签进行分组）](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="7909d-177">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>
