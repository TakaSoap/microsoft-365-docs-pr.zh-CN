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
ms.openlocfilehash: 4ce9e06bb98fb391bb9eb5ffa01491e0c85eba1f
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240297"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="5c576-103">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="5c576-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="5c576-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="5c576-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="5c576-105">创建敏感度标签时，你可以自动将该标签分配给内容（如果它符合你指定的条件）。</span><span class="sxs-lookup"><span data-stu-id="5c576-105">When you create a sensitivity label, you can automatically assign that label to content when it matches conditions that you specify.</span></span>

<span data-ttu-id="5c576-106">能否将敏感度标签自动应用于内容非常重要，这是因为：</span><span class="sxs-lookup"><span data-stu-id="5c576-106">The ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="5c576-107">无需为用户提供有关何时使用每种分类的培训。</span><span class="sxs-lookup"><span data-stu-id="5c576-107">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="5c576-108">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="5c576-108">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="5c576-109">用户不再需要了解你的策略，反而可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="5c576-109">Users no longer need to know about your policies — they can instead focus on their work.</span></span>

<span data-ttu-id="5c576-110">可通过两种不同的方法来自动应用敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="5c576-110">There are two different methods for automatically applying a sensitivity label:</span></span>

- <span data-ttu-id="5c576-111">**用户编辑文档或撰写（以及答复或转发）电子邮件时的客户端标记**：使用为 Office 应用（Word、Excel、PowerPoint 和 Outlook）的自动标记配置的标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-111">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for Office apps (Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="5c576-112">此方法支持向用户推荐标签，并自动应用标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-112">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="5c576-113">但在这两种情况下，用户都可以决定接受还是拒绝标签，以帮助确保正确标记内容。</span><span class="sxs-lookup"><span data-stu-id="5c576-113">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="5c576-114">此客户端标记的文档延迟最少，因为即使在保存文档之前也可以应用标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-114">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="5c576-115">但是，并非所有客户端应用都支持自动标记。</span><span class="sxs-lookup"><span data-stu-id="5c576-115">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="5c576-116">Azure 信息保护统一标记客户端和[某些 Office 版本](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)支持此功能。</span><span class="sxs-lookup"><span data-stu-id="5c576-116">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="5c576-117">有关配置说明，请参阅此页面上的[如何配置 Office 应用的自动标签](#how-to-configure-auto-labeling-for-office-apps)。</span><span class="sxs-lookup"><span data-stu-id="5c576-117">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="5c576-118">**当内容已保存（在 SharePoint Online 或 OneDrive for Business 中）或通过电子邮件发送（由 Exchange Online 处理）时的服务端标记**：使用自动标记策略—目前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="5c576-118">**Service-side labeling when content is already saved (in SharePoint Online or OneDrive for Business) or emailed (processed by Exchange Online)**: Use an auto-labeling policy—currently in preview.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5c576-119">请参阅预览版公告[在 Microsoft 365 服务中推出使用敏感度标签自动分类的公共预览版](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961)。</span><span class="sxs-lookup"><span data-stu-id="5c576-119">See the preview announcement, [Announcing public preview of auto classification with sensitivity labels in Microsoft 365 services](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-public-preview-of-auto-classification-with/ba-p/1279961).</span></span>
    
    <span data-ttu-id="5c576-120">此方法称为使用敏感度标签自动分类。</span><span class="sxs-lookup"><span data-stu-id="5c576-120">This method is referred to as auto classification with sensitivity labels.</span></span> <span data-ttu-id="5c576-121">你可能还会听到它称为自动标记静态数据（SharePoint 和 OneDrive 中的文档）和传输中的数据（由 Exchange 发送或接收的电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="5c576-121">You might also hear it referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange).</span></span> <span data-ttu-id="5c576-122">对于 Exchange，它不包含静态电子邮件（邮箱）。</span><span class="sxs-lookup"><span data-stu-id="5c576-122">For Exchange, it doesn't include emails at rest (mailboxes).</span></span> 
    
    <span data-ttu-id="5c576-123">由于此标记是由服务而不是应用程序应用的，因此无需担心用户拥有的应用和版本。</span><span class="sxs-lookup"><span data-stu-id="5c576-123">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="5c576-124">因此，可立即在整个组织中使用此功能，并且适合大规模标记。</span><span class="sxs-lookup"><span data-stu-id="5c576-124">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="5c576-125">自动标记策略不支持推荐的标记，因为用户不与标记过程交互。</span><span class="sxs-lookup"><span data-stu-id="5c576-125">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="5c576-126">相反，管理员将在模拟模式下运行策略，以便在实际应用标签前，帮助确保正确标记内容。</span><span class="sxs-lookup"><span data-stu-id="5c576-126">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="5c576-127">有关配置说明，请参阅此页面上的[如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。</span><span class="sxs-lookup"><span data-stu-id="5c576-127">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="5c576-128">特定于 SharePoint 和 OneDrive 的自动标记：</span><span class="sxs-lookup"><span data-stu-id="5c576-128">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="5c576-129">租户中每天最多自动标记 25,000 个文件（Word、PowerPoint 或 Excel）</span><span class="sxs-lookup"><span data-stu-id="5c576-129">Maximum of 25,000 automatically labeled files (Word, PowerPoint, or Excel) in your tenant per day</span></span>
        - <span data-ttu-id="5c576-130">每个许可用户每日自动标记的文件最多 5 个</span><span class="sxs-lookup"><span data-stu-id="5c576-130">Maximum of 5 automatically labeled files per licensed user per day</span></span>
    - <span data-ttu-id="5c576-131">所有策略中最多 10 个网站集</span><span class="sxs-lookup"><span data-stu-id="5c576-131">Maximum of 10 sites collections across all policies</span></span>
    - <span data-ttu-id="5c576-132">租户中最多 10 个策略</span><span class="sxs-lookup"><span data-stu-id="5c576-132">Maximum of 10 policies across your tenant</span></span>

    <span data-ttu-id="5c576-133">特定于 Exchange 的自动标记：</span><span class="sxs-lookup"><span data-stu-id="5c576-133">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="5c576-134">与 Office 应用的手动标记或自动标记不同，系统还会根据你在自动标记策略中指定的条件来扫描 Office 附件。</span><span class="sxs-lookup"><span data-stu-id="5c576-134">Unlike manual labeling or auto-labeling with Office apps, Office attachments are also scanned for the conditions you specify in your auto-labeling policy.</span></span> <span data-ttu-id="5c576-135">如果存在匹配项，则会标记电子邮件，但不标记附件。</span><span class="sxs-lookup"><span data-stu-id="5c576-135">When there is a match, the email is labeled but not the attachment.</span></span>
    - <span data-ttu-id="5c576-136">如果你拥有已应用 IRM 加密的 Exchange 邮件流规则或数据丢失防护 (DLP) 策略：当内容由这些规则或策略和自动标记策略标识时，将应用该标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-136">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="5c576-137">如果该标签已应用加密，则将忽略 Exchange 邮件流规则或 DLP 策略中的 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="5c576-137">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="5c576-138">但是，如果该标签未应用加密，则除了标签之外，还会应用邮件流规则或 DLP 策略中的 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="5c576-138">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="5c576-139">如果存在匹配项，则具有 IRM 加密但没有标签的电子邮件将通过自动标记替换为具有加密设置的标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-139">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="5c576-140">与自动标记条件匹配时，将标记传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5c576-140">Incoming email is labeled when there is a match with your auto-labeling conditions.</span></span> <span data-ttu-id="5c576-141">但是，如果已将标签配置为加密，则不会应用该加密。</span><span class="sxs-lookup"><span data-stu-id="5c576-141">However, if the label is configured for encryption, that encryption isn't applied.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="5c576-142">将 Office 应用的自动标记与自动标记策略进行比较</span><span class="sxs-lookup"><span data-stu-id="5c576-142">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="5c576-143">使用下表可帮助识别两种互补自动标记方法在行为上的差异：</span><span class="sxs-lookup"><span data-stu-id="5c576-143">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="5c576-144">功能或行为</span><span class="sxs-lookup"><span data-stu-id="5c576-144">Feature or behavior</span></span>|<span data-ttu-id="5c576-145">标签设置：Office 应用的自动标记</span><span class="sxs-lookup"><span data-stu-id="5c576-145">Label setting: Auto-labeling for Office apps</span></span> |<span data-ttu-id="5c576-146">策略：自动标记</span><span class="sxs-lookup"><span data-stu-id="5c576-146">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5c576-147">应用相关性</span><span class="sxs-lookup"><span data-stu-id="5c576-147">App dependency</span></span>|[<span data-ttu-id="5c576-148">是</span><span class="sxs-lookup"><span data-stu-id="5c576-148">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="5c576-149">否</span><span class="sxs-lookup"><span data-stu-id="5c576-149">No</span></span> |
|<span data-ttu-id="5c576-150">按位置限制</span><span class="sxs-lookup"><span data-stu-id="5c576-150">Restrict by location</span></span>|<span data-ttu-id="5c576-151">否</span><span class="sxs-lookup"><span data-stu-id="5c576-151">No</span></span> |<span data-ttu-id="5c576-152">是</span><span class="sxs-lookup"><span data-stu-id="5c576-152">Yes</span></span> |
|<span data-ttu-id="5c576-153">条件：可训练分类器</span><span class="sxs-lookup"><span data-stu-id="5c576-153">Conditions: Trainable classifers</span></span>|<span data-ttu-id="5c576-154">是（有限预览）</span><span class="sxs-lookup"><span data-stu-id="5c576-154">Yes (limited preview)</span></span> |<span data-ttu-id="5c576-155">否</span><span class="sxs-lookup"><span data-stu-id="5c576-155">No</span></span> |
|<span data-ttu-id="5c576-156">条件：电子邮件的共享选项和其他选项</span><span class="sxs-lookup"><span data-stu-id="5c576-156">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="5c576-157">否</span><span class="sxs-lookup"><span data-stu-id="5c576-157">No</span></span> |<span data-ttu-id="5c576-158">是</span><span class="sxs-lookup"><span data-stu-id="5c576-158">Yes</span></span> |
|<span data-ttu-id="5c576-159">建议、策略工具提示和用户重写</span><span class="sxs-lookup"><span data-stu-id="5c576-159">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="5c576-160">是</span><span class="sxs-lookup"><span data-stu-id="5c576-160">Yes</span></span> |<span data-ttu-id="5c576-161">否</span><span class="sxs-lookup"><span data-stu-id="5c576-161">No</span></span> |
|<span data-ttu-id="5c576-162">模拟模式</span><span class="sxs-lookup"><span data-stu-id="5c576-162">Simulation mode</span></span>|<span data-ttu-id="5c576-163">否</span><span class="sxs-lookup"><span data-stu-id="5c576-163">No</span></span> |<span data-ttu-id="5c576-164">是</span><span class="sxs-lookup"><span data-stu-id="5c576-164">Yes</span></span> |
|<span data-ttu-id="5c576-165">根据条件检查 Exchange 附件</span><span class="sxs-lookup"><span data-stu-id="5c576-165">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="5c576-166">否</span><span class="sxs-lookup"><span data-stu-id="5c576-166">No</span></span> | <span data-ttu-id="5c576-167">是</span><span class="sxs-lookup"><span data-stu-id="5c576-167">Yes</span></span>|
|<span data-ttu-id="5c576-168">应用视觉标记</span><span class="sxs-lookup"><span data-stu-id="5c576-168">Apply visual markings</span></span> |<span data-ttu-id="5c576-169">是</span><span class="sxs-lookup"><span data-stu-id="5c576-169">Yes</span></span> |<span data-ttu-id="5c576-170">是（仅限电子邮件）</span><span class="sxs-lookup"><span data-stu-id="5c576-170">Yes (email only)</span></span> |
|<span data-ttu-id="5c576-171">覆盖在未带标签的情况下应用的 IRM 加密</span><span class="sxs-lookup"><span data-stu-id="5c576-171">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="5c576-172">如果用户具有“导出”的最低使用权限，则为“是”</span><span class="sxs-lookup"><span data-stu-id="5c576-172">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="5c576-173">是（仅限电子邮件）</span><span class="sxs-lookup"><span data-stu-id="5c576-173">Yes (email only)</span></span> |
|<span data-ttu-id="5c576-174">标记传入电子邮件</span><span class="sxs-lookup"><span data-stu-id="5c576-174">Label incoming email</span></span>|<span data-ttu-id="5c576-175">否</span><span class="sxs-lookup"><span data-stu-id="5c576-175">No</span></span> |<span data-ttu-id="5c576-176">是（未应用加密）</span><span class="sxs-lookup"><span data-stu-id="5c576-176">Yes (encryption not applied)</span></span> |

> [!NOTE]
> <span data-ttu-id="5c576-177">手动标记内容后，该标签将永远不会被自动标记替换。</span><span class="sxs-lookup"><span data-stu-id="5c576-177">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="5c576-178">但是，自动标记策略可以替换通过使用 Office 应用的自动标记而应用的[低优先级标签](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="5c576-178">However, auto-labeling policies can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was applied by using auto-labeling for Office apps.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="5c576-179">在多个条件适用于多个标签时如何评估这些条件</span><span class="sxs-lookup"><span data-stu-id="5c576-179">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="5c576-p108">根据你在策略中为标签指定的位置按顺序对标签进行评估：位置最靠前的标签具有最低位置（最不敏感），位置最靠后的标签具有最高位置（最敏感）。有关优先级的详细信息，请参阅[标签优先级（顺序很重要）](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="5c576-p108">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="5c576-182">不要将父标签配置为自动应用或推荐使用</span><span class="sxs-lookup"><span data-stu-id="5c576-182">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="5c576-183">请记住，不可向内容应用父标签（即带子标签的标签）。</span><span class="sxs-lookup"><span data-stu-id="5c576-183">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="5c576-184">确保未在 Office 应用中将父标签配置为自动应用或推荐，并且不为自动标记策略选择父标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-184">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="5c576-185">如果执行此操作，则不会将父标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="5c576-185">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="5c576-186">若要将自动标记用于子标签，请确保同时发布父标签和子标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-186">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="5c576-187">有关父标签和子标签的更多信息，请参阅[子标签（对标签进行分组）](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="5c576-187">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="5c576-188">如何配置 Office 应用的自动标签</span><span class="sxs-lookup"><span data-stu-id="5c576-188">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="5c576-189">Azure 信息保护统一标记客户端支持适用于 Windows 的 Office 应用中的自动标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-189">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="5c576-190">对于 Office 应用中的内置标签，此功能[在某些应用中处于预览状态](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="5c576-190">For built-in labeling in Office apps, this capability is [in preview for some apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="5c576-191">[创建或编辑敏感度标签](create-sensitivity-labels.md)时，可使用 Office 应用的自动标签设置：</span><span class="sxs-lookup"><span data-stu-id="5c576-191">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md):</span></span>

![敏感度标签的自动标签选项](../media/sensitivity-labels-auto-labeling-options.png)

<span data-ttu-id="5c576-193">当内容包含特定类型的敏感信息时，可选择自动将敏感度标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="5c576-193">You can choose to apply sensitivity labels to content automatically when that content contains specific types of sensitive information.</span></span> <span data-ttu-id="5c576-194">从敏感信息类型或分类器列表中选择：</span><span class="sxs-lookup"><span data-stu-id="5c576-194">Choose from a list of sensitive info types or classifers:</span></span>

![Office 应用中的自动标签的标签条件](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> <span data-ttu-id="5c576-196">目前，“**分类器**”选项处于有限预览状态，要求你向 Microsoft 提交表单，以便为你的租户启用此功能。</span><span class="sxs-lookup"><span data-stu-id="5c576-196">Currently, the option for **Classifers** is in limited preview and requires you to submit a form to Microsoft to enable this capability for your tenant.</span></span> <span data-ttu-id="5c576-197">有关详细信息，请参阅博客文章[宣布在 Office 应用中推出使用内置分类器的自动标签 - 有限预览](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889)。</span><span class="sxs-lookup"><span data-stu-id="5c576-197">For more information, see the blog post [Announcing automatic labeling in Office Apps using built-in classifiers - Limited Preview](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).</span></span>

<span data-ttu-id="5c576-198">当自动应用此敏感度标签时，用户会在其 Office 应用中看到通知。</span><span class="sxs-lookup"><span data-stu-id="5c576-198">When this sensitivity label is automatically applied, the user sees a notification in their Office app.</span></span> <span data-ttu-id="5c576-199">例如：</span><span class="sxs-lookup"><span data-stu-id="5c576-199">For example:</span></span>

![指出文档自动应用了标签的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="5c576-201">配置标签的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="5c576-201">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="5c576-202">当你选择“**敏感信息类型**”选项时，可看到与创建数据丢失防护 (DLP) 策略时相同的敏感信息类型列表。</span><span class="sxs-lookup"><span data-stu-id="5c576-202">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="5c576-203">例如，你可以将高度机密的标签自动应用到任何包含客户个人身份信息 (PII) 的内容，如信用卡号码或社会保险号码：</span><span class="sxs-lookup"><span data-stu-id="5c576-203">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personally identifiable information (PII), such as credit card numbers or social security numbers:</span></span>

![Office 应用中的自动标签的敏感信息类型](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="5c576-205">选择敏感信息类型后，可通过更改实例计数或匹配准确度来优化条件。</span><span class="sxs-lookup"><span data-stu-id="5c576-205">After you select your sensitive information types, you can refine your condition by changing the instance count or match accuracy.</span></span> <span data-ttu-id="5c576-206">有关详细信息，请参阅[调整规则以使其更容易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="5c576-206">For more information, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="5c576-207">此外，也可选择某项条件是必须删除所有敏感信息类型还是只删除其中一种。</span><span class="sxs-lookup"><span data-stu-id="5c576-207">Further, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="5c576-208">要使条件更灵活或更复杂，可添加组并在组之间使用逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="5c576-208">And to make your conditions more flexible or complex, you can add groups and use logical operators between the groups.</span></span> <span data-ttu-id="5c576-209">有关详细信息，请参阅[分组和逻辑运算符](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="5c576-209">For more information, see [Grouping and logical operators](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

![实例计数和匹配准确度的选项](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a><span data-ttu-id="5c576-211">为标签配置分类器</span><span class="sxs-lookup"><span data-stu-id="5c576-211">Configuring classifers for a label</span></span>

<span data-ttu-id="5c576-212">当你选择“**分类器**”选项时，请选择一个或多个内置分类器：</span><span class="sxs-lookup"><span data-stu-id="5c576-212">When you select the **Classifers** option, select one or more of the built-in classifiers:</span></span>

![分类器和敏感度标签选项](../media/sensitivity-labels-classifers.png)

<span data-ttu-id="5c576-214">有关这些分类器的详细信息，请参阅[可训练分类器（预览版）入门](classifier-getting-started-with.md)。</span><span class="sxs-lookup"><span data-stu-id="5c576-214">For more information about these classifers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="5c576-215">在预览期间，以下应用支持敏感度标签的分类器：</span><span class="sxs-lookup"><span data-stu-id="5c576-215">During the preview period, the following apps support classifers for sensitivity labels:</span></span>

- <span data-ttu-id="5c576-216">适用于 Windows 的 Office 365 专业增强版桌面应用，从 [Office 预览体验成员](https://office.com/insider)：</span><span class="sxs-lookup"><span data-stu-id="5c576-216">Office 365 ProPlus desktop apps for Windows, from [Office Insider](https://office.com/insider):</span></span>
    - <span data-ttu-id="5c576-217">Word</span><span class="sxs-lookup"><span data-stu-id="5c576-217">Word</span></span>
    - <span data-ttu-id="5c576-218">Excel</span><span class="sxs-lookup"><span data-stu-id="5c576-218">Excel</span></span>
    - <span data-ttu-id="5c576-219">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="5c576-219">PowerPoint</span></span>

- <span data-ttu-id="5c576-220">Office 网页版应用 - 如果你已[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)：</span><span class="sxs-lookup"><span data-stu-id="5c576-220">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="5c576-221">Word</span><span class="sxs-lookup"><span data-stu-id="5c576-221">Word</span></span>
    - <span data-ttu-id="5c576-222">Excel</span><span class="sxs-lookup"><span data-stu-id="5c576-222">Excel</span></span>
    - <span data-ttu-id="5c576-223">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="5c576-223">PowerPoint</span></span>
    - <span data-ttu-id="5c576-224">Outlook</span><span class="sxs-lookup"><span data-stu-id="5c576-224">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label-in-office-apps"></a><span data-ttu-id="5c576-225">建议用户在 Office 应用中应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="5c576-225">Recommend that the user applies a sensitivity label in Office apps</span></span>

<span data-ttu-id="5c576-226">如果愿意，可建议你的用户应用此标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-226">If you prefer, you can recommend to your users that they apply the label.</span></span> <span data-ttu-id="5c576-227">通过此选项，你的用户可接受分类及任何相关保护，也可在标签不适合其内容时关闭建议。</span><span class="sxs-lookup"><span data-stu-id="5c576-227">With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![用于向用户建议敏感度标签的选项](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="5c576-229">下面的示例展示了 Azure 信息保护统一标记客户端在你配置条件以将标签作为建议操作应用时提供的提示，以及自定义策略提示。</span><span class="sxs-lookup"><span data-stu-id="5c576-229">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip.</span></span> <span data-ttu-id="5c576-230">可以选择在策略提示中显示什么文本。</span><span class="sxs-lookup"><span data-stu-id="5c576-230">You can choose what text is displayed in the policy tip.</span></span>

![关于应用建议标签的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied-in-office-apps"></a><span data-ttu-id="5c576-232">何时在 Office 应用中应用自动标签或建议标签</span><span class="sxs-lookup"><span data-stu-id="5c576-232">When automatic or recommended labels are applied in Office apps</span></span>

<span data-ttu-id="5c576-233">在 Office 应用中，自动标签和建议标签的实现取决于你使用的是内置于 Office 的标签，还是 Azure 信息保护统一标记客户端。</span><span class="sxs-lookup"><span data-stu-id="5c576-233">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="5c576-234">不过，在这两种情况下：</span><span class="sxs-lookup"><span data-stu-id="5c576-234">In both cases, however:</span></span>

- <span data-ttu-id="5c576-235">不可对之前已手动标记或者之前已自动标记有更高敏感度的文档和电子邮件使用自动标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-235">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity.</span></span> <span data-ttu-id="5c576-236">请记住，除了一个保留标签，另外仅可向文档或电子邮件应用一个敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-236">Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="5c576-237">都不能对之前有更高敏感度标签的文档或电子邮件使用建议标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-237">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity.</span></span> <span data-ttu-id="5c576-238">如果内容已有更高敏感度标签，用户就看不到建议操作提示和策略提示。</span><span class="sxs-lookup"><span data-stu-id="5c576-238">When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="5c576-239">特定于内置标签的注意事项：</span><span class="sxs-lookup"><span data-stu-id="5c576-239">Specific to built-in labeling:</span></span>

- <span data-ttu-id="5c576-240">并非所有 Office 应用都支持自动（和建议）标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-240">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="5c576-241">有关详细信息，请参阅[应用中的敏感度标签功能支持](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="5c576-241">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="5c576-242">对于桌面版 Word 中的建议标签，触发建议的敏感内容会被标记，这样用户就能审阅和删除敏感内容，而不用应用建议的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-242">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="5c576-243">若要详细了解如何在 Office 应用中应用这些标签、示例屏幕截图，以及如何检测敏感信息，请参阅[对 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。</span><span class="sxs-lookup"><span data-stu-id="5c576-243">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="5c576-244">特定于 Azure 信息保护统一标记客户端的注意事项：</span><span class="sxs-lookup"><span data-stu-id="5c576-244">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="5c576-245">自动标签和建议标签在你保存文档时应用于 Word、Excel 和 PowerPoint，并在你发送电子邮件时应用于 Outlook。</span><span class="sxs-lookup"><span data-stu-id="5c576-245">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="5c576-246">为了让 Outlook 支持建议标签，必须先配置[高级策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。</span><span class="sxs-lookup"><span data-stu-id="5c576-246">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="5c576-247">敏感信息可以在文档和电子邮件的正文文本和页眉、页脚中检测到，但不能在电子邮件的主题行或附件中检测到。</span><span class="sxs-lookup"><span data-stu-id="5c576-247">Sensitive information can be detected in the body text in documents and emails, and to headers and footers — but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="5c576-248">如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略</span><span class="sxs-lookup"><span data-stu-id="5c576-248">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>
> [!NOTE]
> <span data-ttu-id="5c576-249">自动标记策略将在公共预览版中逐步向租户推出，并且可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="5c576-249">Auto-labeling policies are gradually rolling out to tenants in public preview and subject to change.</span></span>

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="5c576-250">自动标记策略的先决条件</span><span class="sxs-lookup"><span data-stu-id="5c576-250">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="5c576-251">必须为模拟模式启用 Office 365 审核。</span><span class="sxs-lookup"><span data-stu-id="5c576-251">Auditing for Office 365 must be turned on for simulation mode.</span></span> <span data-ttu-id="5c576-252">如果你需要启用审核，或者不确定是否已启用审核，请参阅[启用或禁用 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="5c576-252">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="5c576-253">若要自动标记 SharePoint 和 OneDrive 中的文件：</span><span class="sxs-lookup"><span data-stu-id="5c576-253">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="5c576-254">你已[启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="5c576-254">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="5c576-255">当自动标记策略运行时，该文件不得由其他进程或用户打开。</span><span class="sxs-lookup"><span data-stu-id="5c576-255">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span>

- <span data-ttu-id="5c576-256">如果计划使用[自定义敏感信息类型](custom-sensitive-info-types.md)，而不是内置敏感度类型：</span><span class="sxs-lookup"><span data-stu-id="5c576-256">If you plan to use [custom sensitive information types](custom-sensitive-info-types.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="5c576-257">针对在保存自定义敏感度信息类型后创建的内容，评估自定义敏感度信息类型。</span><span class="sxs-lookup"><span data-stu-id="5c576-257">Custom sensitivity information types are evaluated for content that is created after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="5c576-258">若要测试新的自定义敏感信息类型，请在创建自动标记策略前创建它们，然后创建新文档（其中包含用于测试的示例数据）。</span><span class="sxs-lookup"><span data-stu-id="5c576-258">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="5c576-259">你可以为自动标记策略选择一个或多个[已创建和发布](create-sensitivity-labels.md)（至少向一个用户发布）的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="5c576-259">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policy.</span></span> <span data-ttu-id="5c576-260">对于这些标签：</span><span class="sxs-lookup"><span data-stu-id="5c576-260">For these labels:</span></span>
    - <span data-ttu-id="5c576-261">启用或禁用 Office 应用标签设置中的自动标记无关紧要，因为该标签设置会补充自动标记策略，如简介中所述。</span><span class="sxs-lookup"><span data-stu-id="5c576-261">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span> 
    - <span data-ttu-id="5c576-262">如果要用于自动标记的标签被配置为使用视觉标记（页眉、页脚、水印），请注意它们不会应用于文档。</span><span class="sxs-lookup"><span data-stu-id="5c576-262">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="5c576-263">了解模拟模式</span><span class="sxs-lookup"><span data-stu-id="5c576-263">Learn about simulation mode</span></span>

<span data-ttu-id="5c576-264">模拟模式是自动标记策略所独有的，并且已整合到工作流中。</span><span class="sxs-lookup"><span data-stu-id="5c576-264">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="5c576-265">在策略至少运行一次模拟前，无法自动标记文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5c576-265">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="5c576-266">用于自动标记策略的工作流：</span><span class="sxs-lookup"><span data-stu-id="5c576-266">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="5c576-267">创建和配置自动标记策略</span><span class="sxs-lookup"><span data-stu-id="5c576-267">Create and configure an auto-labeling policy</span></span>

2. <span data-ttu-id="5c576-268">在模拟模式下运行策略并等待至少 24 小时</span><span class="sxs-lookup"><span data-stu-id="5c576-268">Run the policy in simulation mode and wait at least 24 hours</span></span>

3. <span data-ttu-id="5c576-269">查看结果，如有必要，优化策略、重新运行模拟模式并等待至少 24 小时</span><span class="sxs-lookup"><span data-stu-id="5c576-269">Review the results, and if necessary, refine your policy, rerun simulation mode and wait at least 24 hours</span></span>

4. <span data-ttu-id="5c576-270">根据需要重复步骤 3</span><span class="sxs-lookup"><span data-stu-id="5c576-270">Repeat step 3 as needed</span></span>

5. <span data-ttu-id="5c576-271">在生产中部署</span><span class="sxs-lookup"><span data-stu-id="5c576-271">Deploy in production</span></span>

<span data-ttu-id="5c576-272">模拟部署的运行方式与 PowerShell 的 WhatIf 参数相同。</span><span class="sxs-lookup"><span data-stu-id="5c576-272">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="5c576-273">你将看到报告的结果，如同自动标记策略已使用你定义的规则应用了所选标签一样。</span><span class="sxs-lookup"><span data-stu-id="5c576-273">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="5c576-274">然后，你可以根据需要优化规则的准确性，并重新运行模拟。</span><span class="sxs-lookup"><span data-stu-id="5c576-274">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="5c576-275">但是，由于 Exchange 的自动标记适用于已发送和接收的电子邮件，而不是存储在邮箱中的电子邮件，因此不要期望模拟中的电子邮件结果保持一致，除非你能够发送和接收完全相同的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5c576-275">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="5c576-276">模拟模式还允许你在部署前逐步增加自动标记策略的范围。</span><span class="sxs-lookup"><span data-stu-id="5c576-276">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="5c576-277">例如，你可以从一个位置（如 SharePoint 网站）和一个文档库开始。</span><span class="sxs-lookup"><span data-stu-id="5c576-277">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="5c576-278">然后，使用迭代更改，将范围增大到多个网站，然后将其增加到其他位置，如 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="5c576-278">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="5c576-279">最后，可以使用模拟模式来提供运行自动标记策略所需时间的近似值，以帮助计划和安排在没有模拟模式的情况下运行自动标记策略的时间。</span><span class="sxs-lookup"><span data-stu-id="5c576-279">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="5c576-280">创建自动标记策略</span><span class="sxs-lookup"><span data-stu-id="5c576-280">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="5c576-281">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="5c576-281">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="5c576-282">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="5c576-282">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="5c576-283">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-283">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="5c576-284">选择“**自动标记(预览)**”选项卡：</span><span class="sxs-lookup"><span data-stu-id="5c576-284">Select the **Auto-labeling (preview)** tab:</span></span>
    
    ![“自动标记(预览)”选项卡](../media/auto-labeling-tab.png)

3. <span data-ttu-id="5c576-286">选择“**+ 创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-286">Select **+ Create policy**.</span></span>

4. <span data-ttu-id="5c576-287">对于“**选择要将此标签应用于的信息**”页面：选择其中一个模板，如“**财务**”或“**隐私**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-287">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="5c576-288">可使用“**显示选项**”下拉列表来优化搜索。</span><span class="sxs-lookup"><span data-stu-id="5c576-288">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="5c576-289">或者，如果模板无法满足你的要求，请选择“**自定义策略**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-289">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="5c576-290">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-290">Select **Next**.</span></span>

5. <span data-ttu-id="5c576-291">对于“**为自动标记策略命名**”页面：提供唯一的名称，并选择性地提供描述，以帮助识别自动应用的标签、位置和条件（用于标识要标记的内容）。</span><span class="sxs-lookup"><span data-stu-id="5c576-291">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="5c576-292">对于“**选择要应用标签的位置**”页面：选择并指定 Exchange、SharePoint 网站和 OneDrive 的位置。</span><span class="sxs-lookup"><span data-stu-id="5c576-292">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="5c576-293">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-293">Then select **Next**.</span></span>

7. <span data-ttu-id="5c576-294">对于“**定义策略设置**”页面：保留“**查找所包含内容**”的默认设置，以定义用于在所有选定位置标识要标记的内容的规则。</span><span class="sxs-lookup"><span data-stu-id="5c576-294">For the **Define policy settings** page: Keep the default of **Find content that contains** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="5c576-295">如果每个位置需要不同的规则，请选择“**高级设置**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-295">If you need different rules per location, select **Advanced settings**.</span></span> <span data-ttu-id="5c576-296">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-296">Then select **Next**.</span></span>
    
    <span data-ttu-id="5c576-297">这些规则使用包含敏感信息类型和共享选项的条件：</span><span class="sxs-lookup"><span data-stu-id="5c576-297">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="5c576-298">对于敏感信息类型，你可以选择内置和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="5c576-298">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="5c576-299">对于共享选项，你可以选择“**仅与组织内部人员共享**”或“**与组织外部人员共享**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-299">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="5c576-300">如果你的唯一位置是 **Exchange**，或者如果你选择“**高级设置**”，则可供选择的其他条件包括：</span><span class="sxs-lookup"><span data-stu-id="5c576-300">If your only location is **Exchange**, or if you select **Advanced settings**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="5c576-301">发件人 IP 地址为</span><span class="sxs-lookup"><span data-stu-id="5c576-301">Sender IP address is</span></span>
    - <span data-ttu-id="5c576-302">收件人域为</span><span class="sxs-lookup"><span data-stu-id="5c576-302">Recipient domain is</span></span>
    - <span data-ttu-id="5c576-303">收件人为</span><span class="sxs-lookup"><span data-stu-id="5c576-303">Recipient is</span></span>
    - <span data-ttu-id="5c576-304">附件的文件扩展名为</span><span class="sxs-lookup"><span data-stu-id="5c576-304">Attachment's file extension is</span></span>
    - <span data-ttu-id="5c576-305">附件受密码保护</span><span class="sxs-lookup"><span data-stu-id="5c576-305">Attachment is password protected</span></span>
    - <span data-ttu-id="5c576-306">文档属性为</span><span class="sxs-lookup"><span data-stu-id="5c576-306">Document property is</span></span>
    - <span data-ttu-id="5c576-307">无法扫描任何电子邮件附件的内容</span><span class="sxs-lookup"><span data-stu-id="5c576-307">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="5c576-308">任何电子邮件附件的内容均未完成扫描</span><span class="sxs-lookup"><span data-stu-id="5c576-308">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="5c576-309">对于“**设置规则以定义要标记的内容**”页面：选择“**+ 创建规则**”，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-309">For the **Set up rules to define what content is labeled** page: Select **+ Create rule** and then select **Next**.</span></span>

9. <span data-ttu-id="5c576-310">在“**创建规则**”页面上，使用敏感信息类型或共享选项命名并定义你的规则，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-310">On the **Create rule** page, name and define your rule, using sensitive information types or the sharing option, and then select **Save**.</span></span>
    
    <span data-ttu-id="5c576-311">敏感信息类型的配置选项与为 Office 应用自动标记所选的选项相同。</span><span class="sxs-lookup"><span data-stu-id="5c576-311">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="5c576-312">如果需要详细信息，请参阅[配置标签的敏感信息类型](#configuring-sensitive-info-types-for-a-label)。</span><span class="sxs-lookup"><span data-stu-id="5c576-312">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>

10. <span data-ttu-id="5c576-313">返回到“**设置规则以定义要标记的内容**”页面：如果你需要另一个规则来标识要标记的内容，请再次选择“**+ 创建规则**”，然后重复上一步。</span><span class="sxs-lookup"><span data-stu-id="5c576-313">Back on the **Set up rules to define what content is labeled** page: Select **+ Create rule** again if you need another rule to identify the content to label, and repeat the previous step.</span></span> <span data-ttu-id="5c576-314">定义所需的所有规则并确认其状态为“开启”后，请选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-314">When you have defined all the rules you need, and confirmed their status is on, select **Next**.</span></span>

11. <span data-ttu-id="5c576-315">对于“**选择要自动应用的标签**”页面：选择“**+ 选择标签**”，从“**选择敏感度标签**”窗格中选择一个标签，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-315">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="5c576-316">对于“**为策略选择模式**”页面：如果你准备立即在模拟模式下运行自动标记策略，请选择“**测试**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-316">For the **Choose a mode for the policy** page: Select **Test it out** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="5c576-317">否则，请选择“**保持禁用**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-317">Otherwise, select **Leave it turned off**.</span></span> <span data-ttu-id="5c576-318">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="5c576-318">Select **Next**.</span></span> 

13. <span data-ttu-id="5c576-319">对于“**摘要**”页面：查看自动标记策略的配置并进行所需的任何更改，然后完成向导。</span><span class="sxs-lookup"><span data-stu-id="5c576-319">For the **Summary** page: Review the configuration of the your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>
    
    <span data-ttu-id="5c576-320">与 Office 应用的自动标记不同，无单独的发布选项。</span><span class="sxs-lookup"><span data-stu-id="5c576-320">Unlike auto-labeling for Office apps, there's no separate publish option.</span></span> <span data-ttu-id="5c576-321">但是，与发布标签一样，自动标记策略最多需要 24 小时才能在整个组织中复制。</span><span class="sxs-lookup"><span data-stu-id="5c576-321">However, as with publishing labels, allow up to 24 hours for the auto-labeling policy to replicate throughout your organization.</span></span>

<span data-ttu-id="5c576-322">现在，在“**信息保护**”页面的“**自动标记(预览)**”选项卡上，你可以在“**测试**”部分中看到自动标记策略。</span><span class="sxs-lookup"><span data-stu-id="5c576-322">Now on the **Information protection** page, **Auto-labeling (preview)** tab, you see your auto-labeling policy in the **Testing** section.</span></span> <span data-ttu-id="5c576-323">选择你的策略以查看配置和状态的详细信息（例如，仍在测试或测试完成）。</span><span class="sxs-lookup"><span data-stu-id="5c576-323">Select your policy to see the details of the configuration and status (for example, still testing or test complete).</span></span> <span data-ttu-id="5c576-324">选择“**匹配的项**”选项卡，以查看与你指定的规则匹配的电子邮件或文档。</span><span class="sxs-lookup"><span data-stu-id="5c576-324">Select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="5c576-325">你可以通过选择页面顶部的“**编辑**”选项来直接从此界面修改策略。</span><span class="sxs-lookup"><span data-stu-id="5c576-325">You can modify your policy directly from this interface by selecting the **Edit** option at the top of the page.</span></span>

<span data-ttu-id="5c576-326">如果你已准备好运行策略而不进行模拟，请选择“**开启**”选项。</span><span class="sxs-lookup"><span data-stu-id="5c576-326">When you're ready to run the policy without simulation, select the **Turn On** option.</span></span>

<span data-ttu-id="5c576-327">如果你具有相应的[权限](data-classification-content-explorer.md#permissions)，则还可通过使用[内容资源管理器](data-classification-content-explorer.md)来查看自动标记策略的结果：</span><span class="sxs-lookup"><span data-stu-id="5c576-327">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="5c576-328">**内容资源管理器列表查看器**允许你查看文件的标签，而不是文件的内容。</span><span class="sxs-lookup"><span data-stu-id="5c576-328">**Content Explorer List viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="5c576-329">**内容资源管理器内容查看器**允许你查看文件的内容。</span><span class="sxs-lookup"><span data-stu-id="5c576-329">**Content Explorer Content viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="5c576-330">你还可以使用内容资源管理器来标识具有未标记文档的位置，这些文档包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="5c576-330">You can also use content explorer to identify locations that have unlabeled documents that contain sensitive information.</span></span> <span data-ttu-id="5c576-331">使用此信息，请考虑将这些位置添加到自动标记策略中，并将标识的敏感信息类型作为规则包括在内。</span><span class="sxs-lookup"><span data-stu-id="5c576-331">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>


