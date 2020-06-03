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
ms.openlocfilehash: bfbebf78664cdce34d224c5cc4b24ed6a9ad0646
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470659"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="bc222-103">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="bc222-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="bc222-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="bc222-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bc222-105">创建敏感度标签时，你可以自动将该标签分配给内容（如果它符合你指定的条件）。</span><span class="sxs-lookup"><span data-stu-id="bc222-105">When you create a sensitivity label, you can automatically assign that label to content when it matches conditions that you specify.</span></span>

<span data-ttu-id="bc222-106">能否将敏感度标签自动应用于内容非常重要，这是因为：</span><span class="sxs-lookup"><span data-stu-id="bc222-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="bc222-107">无需为用户提供有关何时使用每种分类的培训。</span><span class="sxs-lookup"><span data-stu-id="bc222-107">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="bc222-108">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="bc222-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="bc222-109">用户不再需要了解你的策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="bc222-109">Users no longer need to know about your policies—they can instead focus on their work.</span></span>

<span data-ttu-id="bc222-110">可通过两种不同的方法来自动应用敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="bc222-110">There are two different methods for automatically applying a sensitivity label:</span></span>

- <span data-ttu-id="bc222-111">**用户编辑文档或撰写（以及答复或转发）电子邮件时的客户端标记**：使用为 Office 应用（Word、Excel、PowerPoint 和 Outlook）的自动标记配置的标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-111">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for Office apps (Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="bc222-112">此方法支持向用户推荐标签，并自动应用标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-112">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="bc222-113">但在这两种情况下，用户都可以决定接受还是拒绝标签，以帮助确保正确标记内容。</span><span class="sxs-lookup"><span data-stu-id="bc222-113">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="bc222-114">此客户端标记的文档延迟最少，因为即使在保存文档之前也可以应用标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-114">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="bc222-115">但是，并非所有客户端应用都支持自动标记。</span><span class="sxs-lookup"><span data-stu-id="bc222-115">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="bc222-116">Azure 信息保护统一标记客户端和[某些 Office 版本](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)支持此功能。</span><span class="sxs-lookup"><span data-stu-id="bc222-116">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="bc222-117">有关配置说明，请参阅此页面上的[如何配置 Office 应用的自动标签](#how-to-configure-auto-labeling-for-office-apps)。</span><span class="sxs-lookup"><span data-stu-id="bc222-117">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="bc222-118">**当内容已保存（在 SharePoint 或 OneDrive 中）或通过电子邮件发送（由 Exchange Online 处理）时的服务端标记**：使用自动标记策略。</span><span class="sxs-lookup"><span data-stu-id="bc222-118">**Service-side labeling when content is already saved (in SharePoint or OneDrive) or emailed (processed by Exchange Online)**: Use an auto-labeling policy.</span></span> 
    
    <span data-ttu-id="bc222-119">此方法称为使用敏感度标签自动分类。</span><span class="sxs-lookup"><span data-stu-id="bc222-119">This method is referred to as auto classification with sensitivity labels.</span></span> <span data-ttu-id="bc222-120">你可能还会听到它称为自动标记静态数据（SharePoint 和 OneDrive 中的文档）和传输中的数据（由 Exchange 发送或接收的电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="bc222-120">You might also hear it referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange).</span></span> <span data-ttu-id="bc222-121">对于 Exchange，它不包含静态电子邮件（邮箱）。</span><span class="sxs-lookup"><span data-stu-id="bc222-121">For Exchange, it doesn't include emails at rest (mailboxes).</span></span> 
    
    <span data-ttu-id="bc222-122">由于此标记是由服务而不是应用程序应用的，因此无需担心用户拥有的应用和版本。</span><span class="sxs-lookup"><span data-stu-id="bc222-122">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="bc222-123">因此，可立即在整个组织中使用此功能，并且适合大规模标记。</span><span class="sxs-lookup"><span data-stu-id="bc222-123">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="bc222-124">自动标记策略不支持推荐的标记，因为用户不与标记过程交互。</span><span class="sxs-lookup"><span data-stu-id="bc222-124">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="bc222-125">相反，管理员将在模拟模式下运行策略，以便在实际应用标签前，帮助确保正确标记内容。</span><span class="sxs-lookup"><span data-stu-id="bc222-125">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="bc222-126">有关配置说明，请参阅此页面上的[如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。</span><span class="sxs-lookup"><span data-stu-id="bc222-126">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="bc222-127">特定于 SharePoint 和 OneDrive 的自动标记：</span><span class="sxs-lookup"><span data-stu-id="bc222-127">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="bc222-128">租户中每天最多自动标记 25,000 个文件（Word、PowerPoint 或 Excel）</span><span class="sxs-lookup"><span data-stu-id="bc222-128">Maximum of 25,000 automatically labeled files (Word, PowerPoint, or Excel) in your tenant per day</span></span>
    - <span data-ttu-id="bc222-129">所有策略中最多 10 个网站集</span><span class="sxs-lookup"><span data-stu-id="bc222-129">Maximum of 10 sites collections across all policies</span></span>
    - <span data-ttu-id="bc222-130">跨租户最多 10 个策略</span><span class="sxs-lookup"><span data-stu-id="bc222-130">Maximum of 10 policies across your tenant</span></span>
    - <span data-ttu-id="bc222-131">无论是在模拟模式下还是在应用标签时，修改日期都不会因自动标记策略而更改</span><span class="sxs-lookup"><span data-stu-id="bc222-131">Modified date is not changed as a result of auto-labeling policies—for both simulation mode and when labels are applied</span></span>

    <span data-ttu-id="bc222-132">特定于 Exchange 的自动标记：</span><span class="sxs-lookup"><span data-stu-id="bc222-132">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="bc222-133">与 Office 应用的手动标记或自动标记不同，系统还会根据你在自动标记策略中指定的条件来扫描 Office 附件。</span><span class="sxs-lookup"><span data-stu-id="bc222-133">Unlike manual labeling or auto-labeling with Office apps, Office attachments are also scanned for the conditions you specify in your auto-labeling policy.</span></span> <span data-ttu-id="bc222-134">如果存在匹配项，则会标记电子邮件，但不标记附件。</span><span class="sxs-lookup"><span data-stu-id="bc222-134">When there is a match, the email is labeled but not the attachment.</span></span>
    - <span data-ttu-id="bc222-135">如果你拥有已应用 IRM 加密的 Exchange 邮件流规则或数据丢失防护 (DLP) 策略：当内容由这些规则或策略和自动标记策略标识时，将应用该标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-135">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="bc222-136">如果该标签已应用加密，则将忽略 Exchange 邮件流规则或 DLP 策略中的 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="bc222-136">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="bc222-137">但是，如果该标签未应用加密，则除了标签之外，还会应用邮件流规则或 DLP 策略中的 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="bc222-137">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="bc222-138">如果存在匹配项，则具有 IRM 加密但没有标签的电子邮件将通过自动标记替换为具有加密设置的标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-138">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="bc222-139">与自动标记条件匹配时，将标记传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bc222-139">Incoming email is labeled when there is a match with your auto-labeling conditions.</span></span> <span data-ttu-id="bc222-140">但是，如果已将标签配置为加密，则不会应用该加密。</span><span class="sxs-lookup"><span data-stu-id="bc222-140">However, if the label is configured for encryption, that encryption isn't applied.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="bc222-141">将 Office 应用的自动标记与自动标记策略进行比较</span><span class="sxs-lookup"><span data-stu-id="bc222-141">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="bc222-142">使用下表可帮助识别两种互补自动标记方法在行为上的差异：</span><span class="sxs-lookup"><span data-stu-id="bc222-142">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="bc222-143">功能或行为</span><span class="sxs-lookup"><span data-stu-id="bc222-143">Feature or behavior</span></span>|<span data-ttu-id="bc222-144">标签设置：Office 应用的自动标记</span><span class="sxs-lookup"><span data-stu-id="bc222-144">Label setting: Auto-labeling for Office apps</span></span> |<span data-ttu-id="bc222-145">策略：自动标记</span><span class="sxs-lookup"><span data-stu-id="bc222-145">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc222-146">应用相关性</span><span class="sxs-lookup"><span data-stu-id="bc222-146">App dependency</span></span>|[<span data-ttu-id="bc222-147">是</span><span class="sxs-lookup"><span data-stu-id="bc222-147">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="bc222-148">否</span><span class="sxs-lookup"><span data-stu-id="bc222-148">No</span></span> |
|<span data-ttu-id="bc222-149">按位置限制</span><span class="sxs-lookup"><span data-stu-id="bc222-149">Restrict by location</span></span>|<span data-ttu-id="bc222-150">否</span><span class="sxs-lookup"><span data-stu-id="bc222-150">No</span></span> |<span data-ttu-id="bc222-151">是</span><span class="sxs-lookup"><span data-stu-id="bc222-151">Yes</span></span> |
|<span data-ttu-id="bc222-152">条件：可训练分类器</span><span class="sxs-lookup"><span data-stu-id="bc222-152">Conditions: Trainable classifiers</span></span>|<span data-ttu-id="bc222-153">是</span><span class="sxs-lookup"><span data-stu-id="bc222-153">Yes</span></span> |<span data-ttu-id="bc222-154">否</span><span class="sxs-lookup"><span data-stu-id="bc222-154">No</span></span> |
|<span data-ttu-id="bc222-155">条件：电子邮件的共享选项和其他选项</span><span class="sxs-lookup"><span data-stu-id="bc222-155">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="bc222-156">否</span><span class="sxs-lookup"><span data-stu-id="bc222-156">No</span></span> |<span data-ttu-id="bc222-157">是</span><span class="sxs-lookup"><span data-stu-id="bc222-157">Yes</span></span> |
|<span data-ttu-id="bc222-158">建议、策略工具提示和用户重写</span><span class="sxs-lookup"><span data-stu-id="bc222-158">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="bc222-159">是</span><span class="sxs-lookup"><span data-stu-id="bc222-159">Yes</span></span> |<span data-ttu-id="bc222-160">否</span><span class="sxs-lookup"><span data-stu-id="bc222-160">No</span></span> |
|<span data-ttu-id="bc222-161">模拟模式</span><span class="sxs-lookup"><span data-stu-id="bc222-161">Simulation mode</span></span>|<span data-ttu-id="bc222-162">否</span><span class="sxs-lookup"><span data-stu-id="bc222-162">No</span></span> |<span data-ttu-id="bc222-163">是</span><span class="sxs-lookup"><span data-stu-id="bc222-163">Yes</span></span> |
|<span data-ttu-id="bc222-164">根据条件检查 Exchange 附件</span><span class="sxs-lookup"><span data-stu-id="bc222-164">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="bc222-165">否</span><span class="sxs-lookup"><span data-stu-id="bc222-165">No</span></span> | <span data-ttu-id="bc222-166">是</span><span class="sxs-lookup"><span data-stu-id="bc222-166">Yes</span></span>|
|<span data-ttu-id="bc222-167">应用视觉标记</span><span class="sxs-lookup"><span data-stu-id="bc222-167">Apply visual markings</span></span> |<span data-ttu-id="bc222-168">是</span><span class="sxs-lookup"><span data-stu-id="bc222-168">Yes</span></span> |<span data-ttu-id="bc222-169">是（仅限电子邮件）</span><span class="sxs-lookup"><span data-stu-id="bc222-169">Yes (email only)</span></span> |
|<span data-ttu-id="bc222-170">覆盖在未带标签的情况下应用的 IRM 加密</span><span class="sxs-lookup"><span data-stu-id="bc222-170">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="bc222-171">如果用户具有“导出”的最低使用权限，则为“是”</span><span class="sxs-lookup"><span data-stu-id="bc222-171">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="bc222-172">是（仅限电子邮件）</span><span class="sxs-lookup"><span data-stu-id="bc222-172">Yes (email only)</span></span> |
|<span data-ttu-id="bc222-173">标记传入电子邮件</span><span class="sxs-lookup"><span data-stu-id="bc222-173">Label incoming email</span></span>|<span data-ttu-id="bc222-174">否</span><span class="sxs-lookup"><span data-stu-id="bc222-174">No</span></span> |<span data-ttu-id="bc222-175">是（未应用加密）</span><span class="sxs-lookup"><span data-stu-id="bc222-175">Yes (encryption not applied)</span></span> |

> [!NOTE]
> <span data-ttu-id="bc222-176">手动标记内容后，该标签将永远不会被自动标记替换。</span><span class="sxs-lookup"><span data-stu-id="bc222-176">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="bc222-177">但是，自动标记策略可以替换通过使用 Office 应用的自动标记而应用的[低优先级标签](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="bc222-177">However, auto-labeling policies can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was applied by using auto-labeling for Office apps.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="bc222-178">在多个条件适用于多个标签时如何评估这些条件</span><span class="sxs-lookup"><span data-stu-id="bc222-178">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="bc222-p108">根据你在策略中为标签指定的位置按顺序对标签进行评估：位置最靠前的标签具有最低位置（最不敏感），位置最靠后的标签具有最高位置（最敏感）。有关优先级的详细信息，请参阅[标签优先级（顺序很重要）](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="bc222-p108">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="bc222-181">不要将父标签配置为自动应用或推荐使用</span><span class="sxs-lookup"><span data-stu-id="bc222-181">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="bc222-182">请记住，不可向内容应用父标签（即带子标签的标签）。</span><span class="sxs-lookup"><span data-stu-id="bc222-182">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="bc222-183">确保未在 Office 应用中将父标签配置为自动应用或推荐，并且不为自动标记策略选择父标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-183">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="bc222-184">如果执行此操作，则不会将父标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="bc222-184">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="bc222-185">若要将自动标记用于子标签，请确保同时发布父标签和子标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-185">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="bc222-186">有关父标签和子标签的更多信息，请参阅[子标签（对标签进行分组）](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="bc222-186">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="bc222-187">如何配置 Office 应用的自动标签</span><span class="sxs-lookup"><span data-stu-id="bc222-187">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="bc222-188">Azure 信息保护统一标记客户端支持适用于 Windows 的 Office 应用中的自动标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-188">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bc222-189">对于 Office 应用中的内置标签，此功能[在某些应用中处于预览状态](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="bc222-189">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="bc222-190">[创建或编辑敏感度标签](create-sensitivity-labels.md)时，可使用 Office 应用的自动标签设置。</span><span class="sxs-lookup"><span data-stu-id="bc222-190">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md).</span></span> <span data-ttu-id="bc222-191">可选择在检测到敏感信息时自动将敏感度标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="bc222-191">You can choose to apply sensitivity labels to content automatically when sensitive information is detected.</span></span> <span data-ttu-id="bc222-192">从敏感信息类型或可训练分类器列表中选择：</span><span class="sxs-lookup"><span data-stu-id="bc222-192">Choose from a list of sensitive info types or trainable classifiers:</span></span>

![Office 应用中的自动标签的标签条件](../media/sensitivity-labels-conditions.png)

<span data-ttu-id="bc222-194">当自动应用此敏感度标签时，用户会在其 Office 应用中看到通知。</span><span class="sxs-lookup"><span data-stu-id="bc222-194">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="bc222-195">例如：</span><span class="sxs-lookup"><span data-stu-id="bc222-195">For example:</span></span>

![指出文档自动应用了标签的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="bc222-197">配置标签的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="bc222-197">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="bc222-198">当你选择“**敏感信息类型**”选项时，可看到与创建数据丢失防护 (DLP) 策略时相同的敏感信息类型列表。</span><span class="sxs-lookup"><span data-stu-id="bc222-198">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="bc222-199">例如，你可以将高度机密的标签自动应用到任何包含客户个人身份信息 (PII) 的内容，如信用卡号码或社会保险号码：</span><span class="sxs-lookup"><span data-stu-id="bc222-199">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Office 应用中的自动标签的敏感信息类型](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="bc222-201">选择敏感信息类型后，可通过更改实例计数或匹配准确度来优化条件。</span><span class="sxs-lookup"><span data-stu-id="bc222-201">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="bc222-202">有关详细信息，请参阅[调整规则以使其更容易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="bc222-202">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="bc222-203">此外，也可选择某项条件是必须删除所有敏感信息类型还是只删除其中一种。</span><span class="sxs-lookup"><span data-stu-id="bc222-203">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="bc222-204">要使条件更灵活或更复杂，可添加组并在组之间使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="bc222-204">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="bc222-205">有关详细信息，请参阅[分组和逻辑运算符](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="bc222-205">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![实例计数和匹配准确度的选项](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-trainable-classifiers-for-a-label"></a><span data-ttu-id="bc222-207">为标签配置可训练分类器</span><span class="sxs-lookup"><span data-stu-id="bc222-207">Configuring trainable classifiers for a label</span></span>

<span data-ttu-id="bc222-208">当你选择“**可训练分类器**”选项时，请从 Microsoft 中选择一个或多个内置的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="bc222-208">When you select the **Trainable classifiers** option, select one or more of the built-in trainable classifiers from Microsoft.</span></span> <span data-ttu-id="bc222-209">如果你创建了自己的自定义可训练分类器，也可以选择：</span><span class="sxs-lookup"><span data-stu-id="bc222-209">If you've created your own custom trainable classifiers, these are also available to select:</span></span>

![可训练分类器和敏感度标签选项](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> <span data-ttu-id="bc222-211">我们正在弃用**冒犯性语言**内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="bc222-211">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="bc222-212">请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。</span><span class="sxs-lookup"><span data-stu-id="bc222-212">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="bc222-213">我们建议改用**针对性的骚扰**、**侮辱**和**猥亵**内置分类器。</span><span class="sxs-lookup"><span data-stu-id="bc222-213">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="bc222-214">有关这些分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="bc222-214">For more information about these classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="bc222-215">在预览期间，以下应用支持敏感度标签的可训练分类器：</span><span class="sxs-lookup"><span data-stu-id="bc222-215">During the preview period, the following apps support trainable classifiers for sensitivity labels:</span></span>

- <span data-ttu-id="bc222-216">适用于 Windows 的 Microsoft 365 企业应用版（以前称为 Office 365 专业增强版），从 [Office 预览体验计划](https://office.com/insider)：</span><span class="sxs-lookup"><span data-stu-id="bc222-216">Microsoft 365 Apps for enterprise (formerly Office 365 ProPlus) for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="bc222-217">Word</span><span class="sxs-lookup"><span data-stu-id="bc222-217">Word</span></span>
    - <span data-ttu-id="bc222-218">Excel</span><span class="sxs-lookup"><span data-stu-id="bc222-218">Excel</span></span>
    - <span data-ttu-id="bc222-219">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bc222-219">PowerPoint</span></span>

- <span data-ttu-id="bc222-220">Office 网页版应用（如果你已[在 SharePoint 和 OneDrive 中启用 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)）：</span><span class="sxs-lookup"><span data-stu-id="bc222-220">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="bc222-221">Word</span><span class="sxs-lookup"><span data-stu-id="bc222-221">Word</span></span>
    - <span data-ttu-id="bc222-222">Excel</span><span class="sxs-lookup"><span data-stu-id="bc222-222">Excel</span></span>
    - <span data-ttu-id="bc222-223">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bc222-223">PowerPoint</span></span>
    - <span data-ttu-id="bc222-224">Outlook</span><span class="sxs-lookup"><span data-stu-id="bc222-224">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a><span data-ttu-id="bc222-225">建议用户应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="bc222-225">Recommend that the user applies a sensitivity label</span></span>

<span data-ttu-id="bc222-226">如果愿意，可建议你的用户应用此标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-226">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="bc222-227">通过此选项，你的用户可接受分类及任何相关保护，也可在标签不适合其内容时关闭建议。</span><span class="sxs-lookup"><span data-stu-id="bc222-227">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![用于向用户建议敏感度标签的选项](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="bc222-229">下面的示例展示了 Azure 信息保护统一标记客户端在你配置条件以将标签作为建议操作应用时提供的提示，以及自定义策略提示。</span><span class="sxs-lookup"><span data-stu-id="bc222-229">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip.</span></span> <span data-ttu-id="bc222-230">可以选择在策略提示中显示什么文本。</span><span class="sxs-lookup"><span data-stu-id="bc222-230">You can choose what text is displayed in the policy tip.</span></span>

![关于应用建议标签的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="bc222-232">何时应用自动标签或建议标签</span><span class="sxs-lookup"><span data-stu-id="bc222-232">When automatic or recommended labels are applied</span></span>

<span data-ttu-id="bc222-233">在 Office 应用中，自动标签和建议标签的实现取决于你使用的是内置于 Office 的标签，还是 Azure 信息保护统一标记客户端。</span><span class="sxs-lookup"><span data-stu-id="bc222-233">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="bc222-234">不过，在这两种情况下：</span><span class="sxs-lookup"><span data-stu-id="bc222-234">In both cases, however:</span></span>

- <span data-ttu-id="bc222-235">不可对之前已手动标记或者之前已自动标记有更高敏感度的文档和电子邮件使用自动标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-235">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="bc222-236">请记住，除了一个保留标签，另外仅可向文档或电子邮件应用一个敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-236">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="bc222-237">都不能对之前有更高敏感度标签的文档或电子邮件使用建议标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-237">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="bc222-238">如果内容已有更高敏感度标签，用户就看不到建议操作提示和策略提示。</span><span class="sxs-lookup"><span data-stu-id="bc222-238">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="bc222-239">特定于内置标签的注意事项：</span><span class="sxs-lookup"><span data-stu-id="bc222-239">Specific to built-in labeling:</span></span>

- <span data-ttu-id="bc222-240">并非所有 Office 应用都支持自动（和建议）标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-240">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="bc222-241">有关详细信息，请参阅[应用中的敏感度标签功能支持](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="bc222-241">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="bc222-242">对于桌面版 Word 中的建议标签，触发建议的敏感内容会被标记，这样用户就能审阅和删除敏感内容，而不用应用建议的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-242">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="bc222-243">若要详细了解如何在 Office 应用中应用这些标签、示例屏幕截图，以及如何检测敏感信息，请参阅[对 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/zh-CN/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。</span><span class="sxs-lookup"><span data-stu-id="bc222-243">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/zh-CN/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="bc222-244">特定于 Azure 信息保护统一标记客户端的注意事项：</span><span class="sxs-lookup"><span data-stu-id="bc222-244">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="bc222-245">自动标签和建议标签在你保存文档时应用于 Word、Excel 和 PowerPoint，并在你发送电子邮件时应用于 Outlook。</span><span class="sxs-lookup"><span data-stu-id="bc222-245">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="bc222-246">为了让 Outlook 支持建议标签，必须先配置[高级策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。</span><span class="sxs-lookup"><span data-stu-id="bc222-246">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="bc222-247">敏感信息可以在文档和电子邮件的正文文本和页眉、页脚中检测到，但无法在电子邮件的主题行或附件中检测到。</span><span class="sxs-lookup"><span data-stu-id="bc222-247">Sensitive information can be detected in the body text in documents and emails, and to headers and footers—but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="bc222-248">如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略</span><span class="sxs-lookup"><span data-stu-id="bc222-248">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>

<span data-ttu-id="bc222-249">在配置自动标记策略前，请确保你了解这些先决条件。</span><span class="sxs-lookup"><span data-stu-id="bc222-249">Make sure you're aware of the prerequisites before you configure auto-labeling policies.</span></span> 

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="bc222-250">自动标记策略的先决条件</span><span class="sxs-lookup"><span data-stu-id="bc222-250">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="bc222-251">模拟模式：</span><span class="sxs-lookup"><span data-stu-id="bc222-251">Simulation mode:</span></span>
    - <span data-ttu-id="bc222-252">必须启用 Microsoft 365 审核。</span><span class="sxs-lookup"><span data-stu-id="bc222-252">Auditing for Microsoft 365 must be turned on.</span></span> <span data-ttu-id="bc222-253">如果你需要启用审核，或者不确定是否已启用审核，请参阅[启用或禁用审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="bc222-253">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
    - <span data-ttu-id="bc222-254">要在源视图中查看文件内容（电子邮件不支持），如果你不是全局管理员，则必须具有**内容浏览器内容查看器**角色。如果你没有此权限，则从“**匹配项**”选项卡中选择一个项时，将看不到“预览器”窗格。</span><span class="sxs-lookup"><span data-stu-id="bc222-254">To view file contents in the source view (not supported for emails), you must have the **Content Explorer Content viewer** role if you're not a global admin. If you don't have this permission, you don't see the previewer pane when you select an item from the **Matched Items** tab.</span></span>

- <span data-ttu-id="bc222-255">若要自动标记 SharePoint 和 OneDrive 中的文件：</span><span class="sxs-lookup"><span data-stu-id="bc222-255">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="bc222-256">你已[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="bc222-256">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="bc222-257">当自动标记策略运行时，该文件不得由其他进程或用户打开。</span><span class="sxs-lookup"><span data-stu-id="bc222-257">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span>

- <span data-ttu-id="bc222-258">如果计划使用[自定义敏感信息类型](custom-sensitive-info-types.md)，而不是内置敏感度类型：</span><span class="sxs-lookup"><span data-stu-id="bc222-258">If you plan to use [custom sensitive information types](custom-sensitive-info-types.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="bc222-259">针对在保存自定义敏感度信息类型后创建的内容，评估自定义敏感度信息类型。</span><span class="sxs-lookup"><span data-stu-id="bc222-259">Custom sensitivity information types are evaluated for content that is created after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="bc222-260">若要测试新的自定义敏感信息类型，请在创建自动标记策略前创建它们，然后创建新文档（其中包含用于测试的示例数据）。</span><span class="sxs-lookup"><span data-stu-id="bc222-260">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="bc222-261">你可以为自动标记策略选择一个或多个[已创建和发布](create-sensitivity-labels.md)（至少向一个用户发布）的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="bc222-261">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policies.</span></span> <span data-ttu-id="bc222-262">对于这些标签：</span><span class="sxs-lookup"><span data-stu-id="bc222-262">For these labels:</span></span>
    - <span data-ttu-id="bc222-263">启用或禁用 Office 应用标签设置中的自动标记无关紧要，因为该标签设置会补充自动标记策略，如简介中所述。</span><span class="sxs-lookup"><span data-stu-id="bc222-263">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span> 
    - <span data-ttu-id="bc222-264">如果要用于自动标记的标签被配置为使用视觉标记（页眉、页脚、水印），请注意它们不会应用于文档。</span><span class="sxs-lookup"><span data-stu-id="bc222-264">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>
    - <span data-ttu-id="bc222-265">如果标签应用加密，必须为标签配置“立即指定权限”\*\*\*\* 设置。</span><span class="sxs-lookup"><span data-stu-id="bc222-265">If the labels apply encryption, they must be configured for the **Assign permissions now** setting.</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="bc222-266">了解模拟模式</span><span class="sxs-lookup"><span data-stu-id="bc222-266">Learn about simulation mode</span></span>

<span data-ttu-id="bc222-267">模拟模式是自动标记策略所独有的，并且已整合到工作流中。</span><span class="sxs-lookup"><span data-stu-id="bc222-267">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="bc222-268">在策略至少运行一次模拟前，无法自动标记文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bc222-268">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="bc222-269">用于自动标记策略的工作流：</span><span class="sxs-lookup"><span data-stu-id="bc222-269">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="bc222-270">创建和配置自动标记策略</span><span class="sxs-lookup"><span data-stu-id="bc222-270">Create and configure an auto-labeling policy</span></span>

2. <span data-ttu-id="bc222-271">在模拟模式下运行策略并等待至少 24 小时</span><span class="sxs-lookup"><span data-stu-id="bc222-271">Run the policy in simulation mode and wait at least 24 hours</span></span>

3. <span data-ttu-id="bc222-272">查看结果，如有必要，优化策略、重新运行模拟模式并等待至少 24 小时</span><span class="sxs-lookup"><span data-stu-id="bc222-272">Review the results, and if necessary, refine your policy, rerun simulation mode and wait at least 24 hours</span></span>

4. <span data-ttu-id="bc222-273">根据需要重复步骤 3</span><span class="sxs-lookup"><span data-stu-id="bc222-273">Repeat step 3 as needed</span></span>

5. <span data-ttu-id="bc222-274">在生产中部署</span><span class="sxs-lookup"><span data-stu-id="bc222-274">Deploy in production</span></span>

<span data-ttu-id="bc222-275">模拟部署的运行方式与 PowerShell 的 WhatIf 参数相同。</span><span class="sxs-lookup"><span data-stu-id="bc222-275">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="bc222-276">你将看到报告的结果，如同自动标记策略已使用你定义的规则应用了所选标签一样。</span><span class="sxs-lookup"><span data-stu-id="bc222-276">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="bc222-277">然后，你可以根据需要优化规则的准确性，并重新运行模拟。</span><span class="sxs-lookup"><span data-stu-id="bc222-277">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="bc222-278">但是，由于 Exchange 的自动标记适用于已发送和接收的电子邮件，而不是存储在邮箱中的电子邮件，因此不要期望模拟中的电子邮件结果保持一致，除非你能够发送和接收完全相同的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="bc222-278">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="bc222-279">模拟模式还允许你在部署前逐步增加自动标记策略的范围。</span><span class="sxs-lookup"><span data-stu-id="bc222-279">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="bc222-280">例如，你可以从一个位置（如 SharePoint 网站）和一个文档库开始。</span><span class="sxs-lookup"><span data-stu-id="bc222-280">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="bc222-281">然后，使用迭代更改，将范围增大到多个网站，然后将其增加到其他位置，如 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="bc222-281">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="bc222-282">最后，可以使用模拟模式来提供运行自动标记策略所需时间的近似值，以帮助计划和安排在没有模拟模式的情况下运行自动标记策略的时间。</span><span class="sxs-lookup"><span data-stu-id="bc222-282">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="bc222-283">创建自动标记策略</span><span class="sxs-lookup"><span data-stu-id="bc222-283">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="bc222-284">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="bc222-284">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="bc222-285">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="bc222-285">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="bc222-286">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-286">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="bc222-287">选择“**自动标记**”选项卡：</span><span class="sxs-lookup"><span data-stu-id="bc222-287">Select the **Auto-labeling** tab:</span></span>
    
    ![“自动标记”选项卡](../media/auto-labeling-tab.png)
    

3. <span data-ttu-id="bc222-289">选择“**+ 创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-289">Select **+ Create policy**.</span></span>

4. <span data-ttu-id="bc222-290">对于“**选择要将此标签应用于的信息**”页面：选择其中一个模板，如“**财务**”或“**隐私**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-290">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="bc222-291">可使用“**显示选项**”下拉列表来优化搜索。</span><span class="sxs-lookup"><span data-stu-id="bc222-291">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="bc222-292">或者，如果模板无法满足你的要求，请选择“**自定义策略**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-292">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="bc222-293">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-293">Select **Next**.</span></span>

5. <span data-ttu-id="bc222-294">对于“**为自动标记策略命名**”页面：提供唯一的名称，并选择性地提供描述，以帮助识别自动应用的标签、位置和条件（用于标识要标记的内容）。</span><span class="sxs-lookup"><span data-stu-id="bc222-294">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="bc222-295">对于“**选择要应用标签的位置**”页面：选择并指定 Exchange、SharePoint 网站和 OneDrive 的位置。</span><span class="sxs-lookup"><span data-stu-id="bc222-295">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="bc222-296">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-296">Then select **Next**.</span></span>
    
    <span data-ttu-id="bc222-297">对于 OneDrive，必须指定单独的帐户。</span><span class="sxs-lookup"><span data-stu-id="bc222-297">For OneDrive, you must specify individual accounts.</span></span> <span data-ttu-id="bc222-298">用户的 OneDrive URL 采用以下格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="bc222-298">The URL for a user's OneDrive is in the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>
    
    <span data-ttu-id="bc222-299">例如，对于 contoso 租户中用户名为“rsimone”的用户：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="bc222-299">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>
    
    <span data-ttu-id="bc222-300">要验证租户的语法并标识用户的 URL，请参阅[获取组织中所有用户 OneDrive URL 的列表](https://docs.microsoft.com/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="bc222-300">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

7. <span data-ttu-id="bc222-301">对于“**定义策略设置**”页面：保留“**查找所包含内容**”的默认设置，以定义用于在所有选定位置标识要标记的内容的规则。</span><span class="sxs-lookup"><span data-stu-id="bc222-301">For the **Define policy settings** page: Keep the default of **Find content that contains** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="bc222-302">如果每个位置需要不同的规则，请选择“**高级设置**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-302">If you need different rules per location, select **Advanced settings**.</span></span> <span data-ttu-id="bc222-303">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-303">Then select **Next**.</span></span>
    
    <span data-ttu-id="bc222-304">这些规则使用包含敏感信息类型和共享选项的条件：</span><span class="sxs-lookup"><span data-stu-id="bc222-304">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="bc222-305">对于敏感信息类型，你可以选择内置和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="bc222-305">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="bc222-306">对于共享选项，你可以选择“**仅与组织内部人员共享**”或“**与组织外部人员共享**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-306">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="bc222-307">如果你的唯一位置是 **Exchange**，或者如果你选择“**高级设置**”，则可供选择的其他条件包括：</span><span class="sxs-lookup"><span data-stu-id="bc222-307">If your only location is **Exchange**, or if you select **Advanced settings**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="bc222-308">发件人 IP 地址为</span><span class="sxs-lookup"><span data-stu-id="bc222-308">Sender IP address is</span></span>
    - <span data-ttu-id="bc222-309">收件人域为</span><span class="sxs-lookup"><span data-stu-id="bc222-309">Recipient domain is</span></span>
    - <span data-ttu-id="bc222-310">收件人为</span><span class="sxs-lookup"><span data-stu-id="bc222-310">Recipient is</span></span>
    - <span data-ttu-id="bc222-311">附件的文件扩展名为</span><span class="sxs-lookup"><span data-stu-id="bc222-311">Attachment's file extension is</span></span>
    - <span data-ttu-id="bc222-312">附件受密码保护</span><span class="sxs-lookup"><span data-stu-id="bc222-312">Attachment is password protected</span></span>
    - <span data-ttu-id="bc222-313">无法扫描任何电子邮件附件的内容</span><span class="sxs-lookup"><span data-stu-id="bc222-313">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="bc222-314">任何电子邮件附件的内容均未完成扫描</span><span class="sxs-lookup"><span data-stu-id="bc222-314">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="bc222-315">对于“**设置规则以定义要标记的内容**”页面：选择“**+ 创建规则**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-315">For the **Set up rules to define what content is labeled** page: Select **+ Create rule** and then select **Next**.</span></span>

9. <span data-ttu-id="bc222-316">在“**创建规则**”页面上，使用敏感信息类型或共享选项命名并定义你的规则，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-316">On the **Create rule** page, name and define your rule, using sensitive information types or the sharing option, and then select **Save**.</span></span>
    
    <span data-ttu-id="bc222-317">敏感信息类型的配置选项与为 Office 应用自动标记所选的选项相同。</span><span class="sxs-lookup"><span data-stu-id="bc222-317">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="bc222-318">如果需要详细信息，请参阅[配置标签的敏感信息类型](#configuring-sensitive-info-types-for-a-label)。</span><span class="sxs-lookup"><span data-stu-id="bc222-318">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>

10. <span data-ttu-id="bc222-319">返回到“**设置规则以定义要标记的内容**”页面：如果你需要另一个规则来标识要标记的内容，请再次选择“**+ 创建规则**”，然后重复上一步。</span><span class="sxs-lookup"><span data-stu-id="bc222-319">Back on the **Set up rules to define what content is labeled** page: Select **+ Create rule** again if you need another rule to identify the content to label, and repeat the previous step.</span></span> <span data-ttu-id="bc222-320">定义所需的所有规则并确认其状态为“开启”后，请选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-320">When you have defined all the rules you need, and confirmed their status is on, select **Next**.</span></span>

11. <span data-ttu-id="bc222-321">对于“**选择要自动应用的标签**”页面：选择“**+ 选择标签**”，从“**选择敏感度标签**”窗格中选择一个标签，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-321">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="bc222-322">对于**决定立即或稍后运行策略模拟**页面：如果现在准备好运行自动标记策略，在模拟模式中选择“**在模拟模式中运行策略**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-322">For the **Decide if you want to run policy simulation now or later** page: Select **Run policy in simulation mode** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="bc222-323">否则，请选择“**保持禁用策略**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-323">Otherwise, select **Leave policy turned off**.</span></span> <span data-ttu-id="bc222-324">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc222-324">Select **Next**.</span></span> 

13. <span data-ttu-id="bc222-325">对于“摘要”\*\*\*\* 页：审阅自动标记策略的配置，并进行所需的任何更改，然后完成向导。</span><span class="sxs-lookup"><span data-stu-id="bc222-325">For the **Summary** page: Review the configuration of your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>
    
    <span data-ttu-id="bc222-326">与 Office 应用的自动标记不同，无单独的发布选项。</span><span class="sxs-lookup"><span data-stu-id="bc222-326">Unlike auto-labeling for Office apps, there's no separate publish option.</span></span> <span data-ttu-id="bc222-327">但是，与发布标签一样，自动标记策略最多需要 24 小时才能在整个组织中复制。</span><span class="sxs-lookup"><span data-stu-id="bc222-327">However, as with publishing labels, allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.</span></span>

<span data-ttu-id="bc222-328">现在，在“**信息保护**”页面上，“**自动标记**”选项卡，可在“**模拟**”或“**禁用**”部分看到自动标记策略，取决于是否选择在模拟模式下运行它。</span><span class="sxs-lookup"><span data-stu-id="bc222-328">Now on the **Information protection** page, **Auto-labeling** tab, you see your auto-labeling policy in the **Simulation** or **Off** section, depending on whether you chose to run it in simulation mode or not.</span></span> <span data-ttu-id="bc222-329">选择你的策略以查看配置和状态的详细信息（例如，**策略模拟仍在运行**），</span><span class="sxs-lookup"><span data-stu-id="bc222-329">Select your policy to see the details of the configuration and status (for example, **Policy simulation is still running**).</span></span> <span data-ttu-id="bc222-330">对于模拟模式中的策略，选择“**匹配的项**”选项卡，以查看与你指定的规则匹配的电子邮件或文档。</span><span class="sxs-lookup"><span data-stu-id="bc222-330">For policies in simulation mode, select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="bc222-331">可直接从此界面修改策略：</span><span class="sxs-lookup"><span data-stu-id="bc222-331">You can modify your policy directly from this interface:</span></span>

- <span data-ttu-id="bc222-332">对于“**禁用**”部分中的策略，选择“**编辑策略**”按钮。</span><span class="sxs-lookup"><span data-stu-id="bc222-332">For a policy in the **Off** section, select the **Edit policy** button.</span></span>

- <span data-ttu-id="bc222-333">对于“**模拟**”部分中的“策略”，从以下任一选项卡中，选择页面顶部的“**编辑**”选项：</span><span class="sxs-lookup"><span data-stu-id="bc222-333">For policy in the **Simulation** section, select the **Edit** option at the top of the page, from either tab:</span></span>
    
    ![启用自动标记策略选项](../media/auto-labeling-edit.png)
    
    <span data-ttu-id="bc222-335">如果你已准备好运行策略而不进行模拟，请选择“**启用策略**”选项。</span><span class="sxs-lookup"><span data-stu-id="bc222-335">When you're ready to run the policy without simulation, select the **Turn on policy** option.</span></span>

<span data-ttu-id="bc222-336">如果你具有相应的[权限](data-classification-content-explorer.md#permissions)，则还可通过使用[内容资源管理器](data-classification-content-explorer.md)来查看自动标记策略的结果：</span><span class="sxs-lookup"><span data-stu-id="bc222-336">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="bc222-337">**内容资源管理器列表查看器**允许你查看文件的标签，而不是文件的内容。</span><span class="sxs-lookup"><span data-stu-id="bc222-337">**Content Explorer List viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="bc222-338">**内容资源管理器内容查看器**允许你查看文件的内容。</span><span class="sxs-lookup"><span data-stu-id="bc222-338">**Content Explorer Content viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="bc222-339">你还可以使用内容资源管理器来标识具有包含敏感信息的未标记文档的位置。</span><span class="sxs-lookup"><span data-stu-id="bc222-339">You can also use content explorer to identify locations that have documents with sensitive information, but are unlabeled.</span></span> <span data-ttu-id="bc222-340">使用此信息，请考虑将这些位置添加到自动标记策略中，并将标识的敏感信息类型作为规则包括在内。</span><span class="sxs-lookup"><span data-stu-id="bc222-340">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>

