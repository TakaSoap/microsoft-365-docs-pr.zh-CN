---
title: 将敏感度标签自动应用于 Microsoft 365 中的内容
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
ms.openlocfilehash: 4c39e5895c3315d77d7bfc211f0ba3e65f06659b
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769289"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a><span data-ttu-id="10f95-103">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="10f95-103">Apply a sensitivity label to content automatically</span></span>

><span data-ttu-id="10f95-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="10f95-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="10f95-105">有关在 Azure Purview 中对数据进行分类和标记的详细信息，请参阅当前处于预览中的[在 Azure Purview 中自动标记内容](/azure/purview/create-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="10f95-105">For information about automatically applying a sensitivity label in Azure Purview (preview), see [Automatically label your content in Azure Purview](/azure/purview/create-sensitivity-label).</span></span>

<span data-ttu-id="10f95-106">创建敏感度标签时，你可以自动将该标签分配给内容（如果它符合你指定的条件）。</span><span class="sxs-lookup"><span data-stu-id="10f95-106">When you create a sensitivity label, you can automatically assign that label to files and emails when it matches conditions that you specify.</span></span>

<span data-ttu-id="10f95-107">能否将敏感度标签自动应用于内容非常重要，这是因为：</span><span class="sxs-lookup"><span data-stu-id="10f95-107">This ability to apply sensitivity labels to content automatically is important because:</span></span>

- <span data-ttu-id="10f95-108">无需为用户提供有关何时使用每种分类的培训。</span><span class="sxs-lookup"><span data-stu-id="10f95-108">You don't need to train your users when to use each of your classifications.</span></span>

- <span data-ttu-id="10f95-109">无需依赖用户，即可对全部内容进行正确分类。</span><span class="sxs-lookup"><span data-stu-id="10f95-109">You don't need to rely on users to classify all content correctly.</span></span>

- <span data-ttu-id="10f95-110">用户不再需要了解你的策略，可以专注于自己的工作。</span><span class="sxs-lookup"><span data-stu-id="10f95-110">Users no longer need to know about your policies—they can instead focus on their work.</span></span>

<span data-ttu-id="10f95-111">手动标记内容后，该标签将永远不会被自动标记替换。</span><span class="sxs-lookup"><span data-stu-id="10f95-111">When content has been manually labeled, that label will never be replaced by automatic labeling.</span></span> <span data-ttu-id="10f95-112">但是，自动标签可能会替代之前被自动应用的[低优先级标签](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="10f95-112">However, automatic labeling can replace a [lower priority label](sensitivity-labels.md#label-priority-order-matters) that was automatically applied.</span></span>

<span data-ttu-id="10f95-113">有两种不同的方法可以自动将敏感度标签应用于 Microsoft 365 中的内容：</span><span class="sxs-lookup"><span data-stu-id="10f95-113">There are two different methods for automatically applying a sensitivity label to content in Microsoft 365:</span></span>

- <span data-ttu-id="10f95-114">**用户编辑文档或撰写（以及答复或转发）电子邮件时的客户端标记**：使用为 Office 应用（Word、Excel、PowerPoint 和 Outlook）的自动标记配置的标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-114">**Client-side labeling when users edit documents or compose (also reply or forward) emails**: Use a label that's configured for auto-labeling for files and emails (includes Word, Excel, PowerPoint, and Outlook).</span></span> 
    
    <span data-ttu-id="10f95-115">此方法支持向用户推荐标签，并自动应用标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-115">This method supports recommending a label to users, as well as automatically applying a label.</span></span> <span data-ttu-id="10f95-116">但在这两种情况下，用户都可以决定接受还是拒绝标签，以帮助确保正确标记内容。</span><span class="sxs-lookup"><span data-stu-id="10f95-116">But in both cases, the user decides whether to accept or reject the label, to help ensure the correct labeling of content.</span></span> <span data-ttu-id="10f95-117">此客户端标记的文档延迟最少，因为即使在保存文档之前也可以应用标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-117">This client-side labeling has minimal delay for documents because the label can be applied even before the document is saved.</span></span> <span data-ttu-id="10f95-118">但是，并非所有客户端应用都支持自动标记。</span><span class="sxs-lookup"><span data-stu-id="10f95-118">However, not all client apps support auto-labeling.</span></span> <span data-ttu-id="10f95-119">Azure 信息保护统一标记客户端和[某些 Office 版本](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)支持此功能。</span><span class="sxs-lookup"><span data-stu-id="10f95-119">This capability is supported by the Azure Information Protection unified labeling client, and [some versions of Office](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span> 
    
    <span data-ttu-id="10f95-120">有关配置说明，请参阅此页面上的[如何配置 Office 应用的自动标签](#how-to-configure-auto-labeling-for-office-apps)。</span><span class="sxs-lookup"><span data-stu-id="10f95-120">For configuration instructions, see [How to configure auto-labeling for Office apps](#how-to-configure-auto-labeling-for-office-apps) on this page.</span></span>

- <span data-ttu-id="10f95-121">**当内容已保存（在 SharePoint 或 OneDrive 中）或通过电子邮件发送（由 Exchange Online 处理）时的服务端标记**：使用自动标记策略。</span><span class="sxs-lookup"><span data-stu-id="10f95-121">**Service-side labeling when content is already saved (in SharePoint or OneDrive) or emailed (processed by Exchange Online)**: Use an auto-labeling policy.</span></span> 
    
    <span data-ttu-id="10f95-p103">你可能还听过该方法的另外一种称呼方式，即自动标记静态数据（SharePoint 和 OneDrive 中的文档）和传输中的数据（由 Exchange 发送或接收的电子邮件）。对于 Exchange，它不包含静态电子邮件（邮箱）。</span><span class="sxs-lookup"><span data-stu-id="10f95-p103">You might also hear this method referred to as auto-labeling for data at rest (documents in SharePoint and OneDrive) and data in transit (email that is sent or received by Exchange). For Exchange, it doesn't include emails at rest (mailboxes).</span></span>
    
    <span data-ttu-id="10f95-124">由于此标记是由服务而不是应用程序应用的，因此无需担心用户拥有的应用和版本。</span><span class="sxs-lookup"><span data-stu-id="10f95-124">Because this labeling is applied by services rather than by applications, you don't need to worry about what apps users have and what version.</span></span> <span data-ttu-id="10f95-125">因此，可立即在整个组织中使用此功能，并且适合大规模标记。</span><span class="sxs-lookup"><span data-stu-id="10f95-125">As a result, this capability is immediately available throughout your organization and suitable for labeling at scale.</span></span> <span data-ttu-id="10f95-126">自动标记策略不支持推荐的标记，因为用户不与标记过程交互。</span><span class="sxs-lookup"><span data-stu-id="10f95-126">Auto-labeling policies don't support recommended labeling because the user doesn't interact with the labeling process.</span></span> <span data-ttu-id="10f95-127">相反，管理员将在模拟模式下运行策略，以便在实际应用标签前，帮助确保正确标记内容。</span><span class="sxs-lookup"><span data-stu-id="10f95-127">Instead, the administrator runs the policies in simulation mode to help ensure the correct labeling of content before actually applying the label.</span></span>
    
    <span data-ttu-id="10f95-128">有关配置说明，请参阅此页面上的[如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)。</span><span class="sxs-lookup"><span data-stu-id="10f95-128">For configuration instructions, see [How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) on this page.</span></span>
    
    <span data-ttu-id="10f95-129">特定于 SharePoint 和 OneDrive 的自动标记：</span><span class="sxs-lookup"><span data-stu-id="10f95-129">Specific to auto-labeling for SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="10f95-p105">支持 Word、PowerPoint 和 Excel 的 Office 檔案。支持 Open XML 格式（如 .docx 和 .xlsx），但不支持 Microsoft Office 97-2003 格式（如 .doc 和 .xls）。</span><span class="sxs-lookup"><span data-stu-id="10f95-p105">Office files for Word, PowerPoint, and Excel are supported. Open XML format is supported (such as .docx and .xlsx) but not Microsoft Office 97-2003 format (such as .doc and .xls).</span></span>
        - <span data-ttu-id="10f95-132">创建自动标签策略之前或之后，这些文件可自动标记。</span><span class="sxs-lookup"><span data-stu-id="10f95-132">These files can be auto-labeled at rest before or after the auto-labeling policies are created.</span></span> <span data-ttu-id="10f95-133">请注意，如果文件是打开的会话的一部分（文件已打开），则不能自动标记它们。</span><span class="sxs-lookup"><span data-stu-id="10f95-133">Note that files cannot be auto-labeled if they are part of an open session (the file is open).</span></span>
    - <span data-ttu-id="10f95-134">租户中每天最多自动标记 25,000 个文件。</span><span class="sxs-lookup"><span data-stu-id="10f95-134">Maximum of 25,000 automatically labeled files in your tenant per day.</span></span>
    - <span data-ttu-id="10f95-135">每个租户最多可自动标记 10 个策略，每个策略最多针对 10 个网站（SharePoint 或 OneDrive）。</span><span class="sxs-lookup"><span data-stu-id="10f95-135">Maximum of 10 auto-labeling policies per tenant, each targeting up to 10 sites (SharePoint or OneDrive).</span></span>
    - <span data-ttu-id="10f95-136">无论是在模拟模式下还是在应用标签时，可修改的现有值、修改者和修改日期都不会因自动标记策略而发生变化。</span><span class="sxs-lookup"><span data-stu-id="10f95-136">Existing values for modified, modified by, and the date are not changed as a result of auto-labeling policies—for both simulation mode and when labels are applied.</span></span>
    - <span data-ttu-id="10f95-137">标签应用加密时，[权限管理颁发者和权限管理所有者](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)是最后修改文件的帐户。</span><span class="sxs-lookup"><span data-stu-id="10f95-137">When the label applies encryption, the [Rights Management issuer and Rights Management owner](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) is the account that last modified the file.</span></span>

    <span data-ttu-id="10f95-138">特定于 Exchange 的自动标记：</span><span class="sxs-lookup"><span data-stu-id="10f95-138">Specific to auto-labeling for Exchange:</span></span>
    - <span data-ttu-id="10f95-p107">与 Office 应用的手动标记或自动标记不同，系统还会根据你在自动标记策略中指定的条件来扫描 PDF 附件和 Office 附件（Word、Excel 和 PowerPoint 文件）。如果存在匹配项，则会标记电子邮件，但不标记附件。</span><span class="sxs-lookup"><span data-stu-id="10f95-p107">Unlike manual labeling or auto-labeling with Office apps, PDF attachments as well as Office attachments (Word, Excel, and PowerPoint files) are also scanned for the conditions you specify in your auto-labeling policy. When there is a match, the email is labeled but not the attachment.</span></span>
        - <span data-ttu-id="10f95-141">对于 PDF 文件，如果标签应用加密，则当租户[启用 PDF 附件](ome-faq.yml#are-pdf-file-attachments-supported-)时，这些文件将被加密。</span><span class="sxs-lookup"><span data-stu-id="10f95-141">For PDF files, if the label applies encryption, these files are encrypted when your tenant is [enabled for PDF attachments](ome-faq.yml#are-pdf-file-attachments-supported-).</span></span>
        - <span data-ttu-id="10f95-p108">对于这些 Office 文件，支持 Open XML 格式（例如 .docx 和 .xlsx），但不支持 Microsoft Office 97-2003 格式（例如 .doc 和 .xls）。如果标签应用加密，则这些文件将被加密。</span><span class="sxs-lookup"><span data-stu-id="10f95-p108">For these Office files, Open XML format is supported (such as .docx and .xlsx) but not Microsoft Office 97-2003 format (such as .doc and .xls). If the label applies encryption, these files are encrypted.</span></span>
    - <span data-ttu-id="10f95-144">如果你拥有已应用 IRM 加密的 Exchange 邮件流规则或数据丢失防护 (DLP) 策略：当内容由这些规则或策略和自动标记策略标识时，将应用该标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-144">If you have Exchange mail flow rules or data loss prevention (DLP) policies that apply IRM encryption: When content is identified by these rules or policies and an auto-labeling policy, the label is applied.</span></span> <span data-ttu-id="10f95-145">如果该标签已应用加密，则将忽略 Exchange 邮件流规则或 DLP 策略中的 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="10f95-145">If that label applies encryption, the IRM settings from the Exchange mail flow rules or DLP policies are ignored.</span></span> <span data-ttu-id="10f95-146">但是，如果该标签未应用加密，则除了标签之外，还会应用邮件流规则或 DLP 策略中的 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="10f95-146">However, if that label doesn't apply encryption, the IRM settings from the mail flow rules or DLP policies are applied in addition to the label.</span></span>
    - <span data-ttu-id="10f95-147">如果存在匹配项，则具有 IRM 加密但没有标签的电子邮件将通过自动标记替换为具有加密设置的标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-147">Email that has IRM encryption with no label will be replaced by a label with any encryption settings when there is a match by using auto-labeling.</span></span>
    - <span data-ttu-id="10f95-148">与自动标记条件匹配时，将标记传入电子邮件：</span><span class="sxs-lookup"><span data-stu-id="10f95-148">Incoming email is labeled when there is a match with your auto-labeling conditions:</span></span>
        - <span data-ttu-id="10f95-149">如果已将标签配置为[加密](encryption-sensitivity-labels.md)，则会应用该加密。</span><span class="sxs-lookup"><span data-stu-id="10f95-149">If the label is configured for [encryption](encryption-sensitivity-labels.md), that encryption is applied.</span></span> <span data-ttu-id="10f95-150">不过，目前尚不支持此配置。</span><span class="sxs-lookup"><span data-stu-id="10f95-150">However, this configuration isn't currently supported.</span></span>
        - <span data-ttu-id="10f95-151">如果标签配置为应用[动态标记](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)，请注意，这可能会影响组织外部人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="10f95-151">If the label is configured to apply [dynamic markings](sensitivity-labels-office-apps.md#dynamic-markings-with-variables), be aware that this can result in the names of people outside your organization.</span></span>
    - <span data-ttu-id="10f95-152">如果标签应用了加密，则[权限管理颁发者和权限管理所有者](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)是发送电子邮件的人。</span><span class="sxs-lookup"><span data-stu-id="10f95-152">When the label applies encryption, the [Rights Management issuer and Rights Management owner](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) is the person who sends the email.</span></span> <span data-ttu-id="10f95-153">目前无法为自动加密的所有传入电子邮件设置权限管理器所有者。</span><span class="sxs-lookup"><span data-stu-id="10f95-153">There currently isn't a way to set a Rights Manager owner for all incoming email messages that are automatically encrypted.</span></span>
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a><span data-ttu-id="10f95-154">将 Office 应用的自动标记与自动标记策略进行比较</span><span class="sxs-lookup"><span data-stu-id="10f95-154">Compare auto-labeling for Office apps with auto-labeling policies</span></span>

<span data-ttu-id="10f95-155">使用下表可帮助识别两种互补自动标记方法在行为上的差异：</span><span class="sxs-lookup"><span data-stu-id="10f95-155">Use the following table to help you identify the differences in behavior for the two complementary automatic labeling methods:</span></span>

|<span data-ttu-id="10f95-156">功能或行为</span><span class="sxs-lookup"><span data-stu-id="10f95-156">Feature or behavior</span></span>|<span data-ttu-id="10f95-157">标签设置：文件和电子邮件的自动标记</span><span class="sxs-lookup"><span data-stu-id="10f95-157">Label setting: Auto-labeling for files and emails</span></span>  |<span data-ttu-id="10f95-158">策略：自动标记</span><span class="sxs-lookup"><span data-stu-id="10f95-158">Policy: Auto-labeling</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10f95-159">应用相关性</span><span class="sxs-lookup"><span data-stu-id="10f95-159">App dependency</span></span>|[<span data-ttu-id="10f95-160">是</span><span class="sxs-lookup"><span data-stu-id="10f95-160">Yes</span></span>](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |<span data-ttu-id="10f95-161">否 \*</span><span class="sxs-lookup"><span data-stu-id="10f95-161">No \*</span></span> |
|<span data-ttu-id="10f95-162">按位置限制</span><span class="sxs-lookup"><span data-stu-id="10f95-162">Restrict by location</span></span>|<span data-ttu-id="10f95-163">否</span><span class="sxs-lookup"><span data-stu-id="10f95-163">No</span></span> |<span data-ttu-id="10f95-164">是</span><span class="sxs-lookup"><span data-stu-id="10f95-164">Yes</span></span> |
|<span data-ttu-id="10f95-165">条件：可训练分类器</span><span class="sxs-lookup"><span data-stu-id="10f95-165">Conditions: Trainable classifiers</span></span>|<span data-ttu-id="10f95-166">是</span><span class="sxs-lookup"><span data-stu-id="10f95-166">Yes</span></span> |<span data-ttu-id="10f95-167">否</span><span class="sxs-lookup"><span data-stu-id="10f95-167">No</span></span> |
|<span data-ttu-id="10f95-168">条件：电子邮件的共享选项和其他选项</span><span class="sxs-lookup"><span data-stu-id="10f95-168">Conditions: Sharing options and additional options for email</span></span>|<span data-ttu-id="10f95-169">否</span><span class="sxs-lookup"><span data-stu-id="10f95-169">No</span></span> |<span data-ttu-id="10f95-170">是</span><span class="sxs-lookup"><span data-stu-id="10f95-170">Yes</span></span> |
|<span data-ttu-id="10f95-171">建议、策略工具提示和用户重写</span><span class="sxs-lookup"><span data-stu-id="10f95-171">Recommendations, policy tooltip, and user overrides</span></span>|<span data-ttu-id="10f95-172">是</span><span class="sxs-lookup"><span data-stu-id="10f95-172">Yes</span></span> |<span data-ttu-id="10f95-173">否</span><span class="sxs-lookup"><span data-stu-id="10f95-173">No</span></span> |
|<span data-ttu-id="10f95-174">模拟模式</span><span class="sxs-lookup"><span data-stu-id="10f95-174">Simulation mode</span></span>|<span data-ttu-id="10f95-175">否</span><span class="sxs-lookup"><span data-stu-id="10f95-175">No</span></span> |<span data-ttu-id="10f95-176">是</span><span class="sxs-lookup"><span data-stu-id="10f95-176">Yes</span></span> |
|<span data-ttu-id="10f95-177">根据条件检查 Exchange 附件</span><span class="sxs-lookup"><span data-stu-id="10f95-177">Exchange attachments checked for conditions</span></span>|<span data-ttu-id="10f95-178">否</span><span class="sxs-lookup"><span data-stu-id="10f95-178">No</span></span> | <span data-ttu-id="10f95-179">是</span><span class="sxs-lookup"><span data-stu-id="10f95-179">Yes</span></span>|
|<span data-ttu-id="10f95-180">应用视觉标记</span><span class="sxs-lookup"><span data-stu-id="10f95-180">Apply visual markings</span></span> |<span data-ttu-id="10f95-181">是</span><span class="sxs-lookup"><span data-stu-id="10f95-181">Yes</span></span> |<span data-ttu-id="10f95-182">是（仅限电子邮件）</span><span class="sxs-lookup"><span data-stu-id="10f95-182">Yes (email only)</span></span> |
|<span data-ttu-id="10f95-183">覆盖在未带标签的情况下应用的 IRM 加密</span><span class="sxs-lookup"><span data-stu-id="10f95-183">Override IRM encryption applied without a label</span></span>|<span data-ttu-id="10f95-184">如果用户具有“导出”的最低使用权限，则为“是”</span><span class="sxs-lookup"><span data-stu-id="10f95-184">Yes if the user has the minimum usage right of Export</span></span> |<span data-ttu-id="10f95-185">是（仅限电子邮件）</span><span class="sxs-lookup"><span data-stu-id="10f95-185">Yes (email only)</span></span> |
|<span data-ttu-id="10f95-186">标记传入电子邮件</span><span class="sxs-lookup"><span data-stu-id="10f95-186">Label incoming email</span></span>|<span data-ttu-id="10f95-187">否</span><span class="sxs-lookup"><span data-stu-id="10f95-187">No</span></span> |<span data-ttu-id="10f95-188">是</span><span class="sxs-lookup"><span data-stu-id="10f95-188">Yes</span></span>|

<span data-ttu-id="10f95-189">\*自动标记当前在所有区域中均不可用。</span><span class="sxs-lookup"><span data-stu-id="10f95-189">\* Auto-labeling isn't currently available in all regions.</span></span> <span data-ttu-id="10f95-190">如果你的租户不支持此功能，则管理员标记中心中的“自动标记”选项卡将不可见。</span><span class="sxs-lookup"><span data-stu-id="10f95-190">If your tenant can't support this functionality, the Auto-labeling tab isn't visible in the admin labeling center.</span></span>

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a><span data-ttu-id="10f95-191">在多个条件适用于多个标签时如何评估这些条件</span><span class="sxs-lookup"><span data-stu-id="10f95-191">How multiple conditions are evaluated when they apply to more than one label</span></span>

<span data-ttu-id="10f95-p113">根据你在策略中为标签指定的位置按顺序对标签进行评估：位置最靠前的标签具有最低位置（最不敏感），位置最靠后的标签具有最高位置（最敏感）。有关优先级的详细信息，请参阅[标签优先级（顺序很重要）](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="10f95-p113">The labels are ordered for evaluation according to their position that you specify in the policy: The label positioned first has the lowest position (least sensitive) and the label positioned last has the highest position (most sensitive). For more information on priority, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters).</span></span>

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a><span data-ttu-id="10f95-194">不要将父标签配置为自动应用或推荐使用</span><span class="sxs-lookup"><span data-stu-id="10f95-194">Don't configure a parent label to be applied automatically or recommended</span></span>

<span data-ttu-id="10f95-195">请记住，不可向内容应用父标签（即带子标签的标签）。</span><span class="sxs-lookup"><span data-stu-id="10f95-195">Remember, you can't apply a parent label (a label with sublabels) to content.</span></span> <span data-ttu-id="10f95-196">确保未在 Office 应用中将父标签配置为自动应用或推荐，并且不为自动标记策略选择父标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-196">Make sure that you don't configure a parent label to be auto-applied or recommended in Office apps, and don't select a parent label for an auto-labeling policy.</span></span> <span data-ttu-id="10f95-197">如果执行此操作，则不会将父标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="10f95-197">If you do, the parent label won't be applied to content.</span></span>

<span data-ttu-id="10f95-198">若要将自动标记用于子标签，请确保同时发布父标签和子标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-198">To use automatic labeling with sublabels, make sure you publish both the parent label and the sublabel.</span></span>

<span data-ttu-id="10f95-199">有关父标签和子标签的更多信息，请参阅[子标签（对标签进行分组）](sensitivity-labels.md#sublabels-grouping-labels)。</span><span class="sxs-lookup"><span data-stu-id="10f95-199">For more information on parent labels and sublabels, see [Sublabels (grouping labels)](sensitivity-labels.md#sublabels-grouping-labels).</span></span>

## <a name="how-to-configure-auto-labeling-for-office-apps"></a><span data-ttu-id="10f95-200">如何配置 Office 应用的自动标签</span><span class="sxs-lookup"><span data-stu-id="10f95-200">How to configure auto-labeling for Office apps</span></span>

<span data-ttu-id="10f95-201">Azure 信息保护统一标记客户端支持适用于 Windows 的 Office 应用中的自动标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-201">Automatic labeling in Office apps for Windows is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="10f95-202">对于 Office 应用中的内置标记，此功能[在不同应用程序中有不同的可用性阶段](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="10f95-202">For built-in labeling in Office apps, this capability is in [different stages of availability for different apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

<span data-ttu-id="10f95-203">[创建或编辑敏感度标签](create-sensitivity-labels.md)时，可使用 Office 应用的自动标签设置。</span><span class="sxs-lookup"><span data-stu-id="10f95-203">The auto-labeling settings for Office apps are available when you [create or edit a sensitivity label](create-sensitivity-labels.md).</span></span> <span data-ttu-id="10f95-204">请确保为标签的范围选择了 **“文件和电子邮件”**：</span><span class="sxs-lookup"><span data-stu-id="10f95-204">Make sure **Files & emails** is selected for the label's scope:</span></span> 

![文件和电子邮件的敏感度标签范围选项](../media/filesandemails-scope-options-sensitivity-label.png)

<span data-ttu-id="10f95-206">在向导中移动时，你将看到 Office 应用的 **自动标记** 页面，可在其中选择敏感信息类型或可训练的分类器列表：</span><span class="sxs-lookup"><span data-stu-id="10f95-206">As you move through the wizard, you see the **Auto-labeling for files and emails** page where you can choose from a list of sensitive info types or trainable classifiers:</span></span>

![Office 应用中的自动标签的标签条件](../media/sensitivity-labels-conditions.png)

<span data-ttu-id="10f95-p117">当自动应用此敏感度标签时，用户会在其 Office 应用中看到通知。例如：</span><span class="sxs-lookup"><span data-stu-id="10f95-p117">When this sensitivity label is automatically applied, the user sees a notification in their Office app. For example:</span></span>

![指出文档自动应用了标签的通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a><span data-ttu-id="10f95-211">配置标签的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="10f95-211">Configuring sensitive info types for a label</span></span>

<span data-ttu-id="10f95-212">当你选择“**敏感信息类型**”选项时，可看到与创建数据丢失防护 (DLP) 策略时相同的敏感信息类型列表。</span><span class="sxs-lookup"><span data-stu-id="10f95-212">When you select the **Sensitive info types** option, you see the same list of sensitive information types as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="10f95-213">例如，你可以将“高度机密”标签自动应用到任何包含客户个人信息的内容（如信用卡号、社会保险号码或护照号码）：</span><span class="sxs-lookup"><span data-stu-id="10f95-213">So you can, for example, automatically apply a Highly Confidential label to any content that contains customers' personal information, such as credit card numbers, social security numbers, or passport numbers:</span></span>

![Office 应用中的自动标签的敏感信息类型](../media/sensitivity-labels-sensitive-info-types.png)

<span data-ttu-id="10f95-p119">与配置 DLP 策略时类似，你可以通过更改实例计数和匹配准确度来优化条件。例如：</span><span class="sxs-lookup"><span data-stu-id="10f95-p119">Similarly to when you configure DLP policies, you can then refine your condition by changing the instance count and match accuracy. For example:</span></span>

![匹配准确度和实例计数选项](../media/sit-confidence-level.png)

<span data-ttu-id="10f95-218">可通过以下 DLP 文档了解有关这些配置选项的详细信息：[调整规则，使它们更易或更难匹配](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)。</span><span class="sxs-lookup"><span data-stu-id="10f95-218">You can learn more about these configuration options from the DLP documentation: [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>

<span data-ttu-id="10f95-219">同样与配置 DLP 策略时类似的是，你可以选择某项条件是必须删除所有敏感信息类型还是只删除其中一种。</span><span class="sxs-lookup"><span data-stu-id="10f95-219">Also similarly to DLP policy configuration, you can choose whether a condition must detect all sensitive information types, or just one of them.</span></span> <span data-ttu-id="10f95-220">要使条件更灵活或更复杂，可添加[组并在组之间使用逻辑运算符](data-loss-prevention-policies.md#grouping-and-logical-operators)。</span><span class="sxs-lookup"><span data-stu-id="10f95-220">And to make your conditions more flexible or complex, you can add [groups and use logical operators between the groups](data-loss-prevention-policies.md#grouping-and-logical-operators).</span></span>

### <a name="configuring-trainable-classifiers-for-a-label"></a><span data-ttu-id="10f95-221">为标签配置可训练分类器</span><span class="sxs-lookup"><span data-stu-id="10f95-221">Configuring trainable classifiers for a label</span></span>

<span data-ttu-id="10f95-222">此选项目前处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="10f95-222">This option is currently in preview.</span></span> <span data-ttu-id="10f95-223">如果使用此选项，请确保你已在租户中发布至少一个其他针对自动标记和 [敏感信息类型选项](#configuring-sensitive-info-types-for-a-label)配置的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-223">If you use this option, make sure you have published in your tenant at least one other sensitivity label that's configured for auto-labeling and the [sensitive info types option](#configuring-sensitive-info-types-for-a-label).</span></span>

<span data-ttu-id="10f95-224">当你选择“**可训练分类器**”选项时，请从 Microsoft 中选择一个或多个内置的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="10f95-224">When you select the **Trainable classifiers** option, select one or more of the built-in trainable classifiers from Microsoft.</span></span> <span data-ttu-id="10f95-225">如果你创建了自己的自定义可训练分类器，也可以选择：</span><span class="sxs-lookup"><span data-stu-id="10f95-225">If you've created your own custom trainable classifiers, these are also available to select:</span></span>

![可训练分类器和敏感度标签选项](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> <span data-ttu-id="10f95-227">我们正在弃用 **冒犯性语言** 内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="10f95-227">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="10f95-228">请不要使用此内置分类器，如果你正在使用它，则应将其业务流程中移出。</span><span class="sxs-lookup"><span data-stu-id="10f95-228">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="10f95-229">我们建议改用 **针对性的骚扰**、**侮辱** 和 **猥亵** 内置分类器。</span><span class="sxs-lookup"><span data-stu-id="10f95-229">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="10f95-230">有关这些分类器的详细信息，请参阅 [了解可训练分类器（预览版）](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="10f95-230">For more information about these classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="10f95-231">在此选项的预览期间，以下应用支持敏感度标签的可训练分类器：</span><span class="sxs-lookup"><span data-stu-id="10f95-231">During the preview period for this option, the following apps support trainable classifiers for sensitivity labels:</span></span>

- <span data-ttu-id="10f95-232">适用于 Windows 的 Microsoft 365 企业应用版（[以前的 Office 365 专业增强版](/deployoffice/name-change)），现已推出到版本 2006 及更高版本中的[当前频道](/deployoffice/overview-update-channels#current-channel-overview)：</span><span class="sxs-lookup"><span data-stu-id="10f95-232">Microsoft 365 Apps for enterprise ([formerly Office 365 ProPlus](/deployoffice/name-change)) for Windows, now rolling out to the [Current Channel](/deployoffice/overview-update-channels#current-channel-overview) in version 2006 and later:</span></span>
    - <span data-ttu-id="10f95-233">Word</span><span class="sxs-lookup"><span data-stu-id="10f95-233">Word</span></span>
    - <span data-ttu-id="10f95-234">Excel</span><span class="sxs-lookup"><span data-stu-id="10f95-234">Excel</span></span>
    - <span data-ttu-id="10f95-235">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="10f95-235">PowerPoint</span></span>

- <span data-ttu-id="10f95-236">Office 网页版应用（如果你已[在 SharePoint 和 OneDrive 中启用 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)）：</span><span class="sxs-lookup"><span data-stu-id="10f95-236">Office for the web apps, when you have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    - <span data-ttu-id="10f95-237">Word</span><span class="sxs-lookup"><span data-stu-id="10f95-237">Word</span></span>
    - <span data-ttu-id="10f95-238">Excel</span><span class="sxs-lookup"><span data-stu-id="10f95-238">Excel</span></span>
    - <span data-ttu-id="10f95-239">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="10f95-239">PowerPoint</span></span>
    - <span data-ttu-id="10f95-240">Outlook</span><span class="sxs-lookup"><span data-stu-id="10f95-240">Outlook</span></span>

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a><span data-ttu-id="10f95-241">建议用户应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="10f95-241">Recommend that the user applies a sensitivity label</span></span>

<span data-ttu-id="10f95-p124">如果愿意，可建议你的用户应用此标签。通过此选项，你的用户可接受分类及任何相关保护，也可在标签不适合其内容时关闭建议。</span><span class="sxs-lookup"><span data-stu-id="10f95-p124">If you prefer, you can recommend to your users that they apply the label. With this option, your users can accept the classification and any associated protection, or dismiss the recommendation if the label isn't suitable for their content.</span></span>

![用于向用户建议敏感度标签的选项](../media/Sensitivity-labels-Recommended-label-option.png)

<span data-ttu-id="10f95-p125">下面的示例展示了 Azure 信息保护统一标记客户端在你配置条件以将标签作为建议操作应用时提供的提示，以及自定义策略提示。可以选择在策略提示中显示什么文本。</span><span class="sxs-lookup"><span data-stu-id="10f95-p125">Here's an example of a prompt from the Azure Information Protection unified labeling client when you configure a condition to apply a label as a recommended action, with a custom policy tip. You can choose what text is displayed in the policy tip.</span></span>

![关于应用建议标签的提示](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a><span data-ttu-id="10f95-248">何时应用自动标签或建议标签</span><span class="sxs-lookup"><span data-stu-id="10f95-248">When automatic or recommended labels are applied</span></span>

<span data-ttu-id="10f95-p126">在 Office 应用中，自动标签和建议标签的实现取决于你使用的是内置于 Office 的标签，还是 Azure 信息保护统一标记客户端。然而，在这两种情况下：</span><span class="sxs-lookup"><span data-stu-id="10f95-p126">The implementation of automatic and recommended labeling in Office apps depend on whether you're using labeling that's built into Office, or the Azure Information Protection unified labeling client. In both cases, however:</span></span>

- <span data-ttu-id="10f95-p127">不可对之前已手动标记或者之前已自动标记有更高敏感度的文档和电子邮件使用自动标签。请记住，除了一个保留标签，另外仅可向文档或电子邮件应用一个敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-p127">You can't use automatic labeling for documents and emails that were previously manually labeled, or previously automatically labeled with a higher sensitivity. Remember, you can only apply a single sensitivity label to a document or email (in addition to a single retention label).</span></span>

- <span data-ttu-id="10f95-p128">不能对之前有更高敏感度标签的文档或电子邮件使用建议标签。如果内容已标记有更高敏感度，则用户不会看到带有建议和策略提醒的提示。</span><span class="sxs-lookup"><span data-stu-id="10f95-p128">You can't use recommended labeling for documents or emails that were previously labeled with a higher sensitivity. When the content's already labeled with a higher sensitivity, the user won't see the prompt with the recommendation and policy tip.</span></span>

<span data-ttu-id="10f95-255">特定于内置标签的注意事项：</span><span class="sxs-lookup"><span data-stu-id="10f95-255">Specific to built-in labeling:</span></span>

- <span data-ttu-id="10f95-256">并非所有 Office 应用都支持自动（和建议）标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-256">Not all Office apps support automatic (and recommended) labeling.</span></span> <span data-ttu-id="10f95-257">有关详细信息，请参阅[应用中的敏感度标签功能支持](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。</span><span class="sxs-lookup"><span data-stu-id="10f95-257">For more information, see [Support for sensitivity label capabilities in apps](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).</span></span>

- <span data-ttu-id="10f95-258">对于桌面版 Word 中的建议标签，触发建议的敏感内容会被标记，这样用户就能审阅和删除敏感内容，而不用应用建议的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-258">For recommended labels in the desktop versions of Word, the sensitive content that triggered the recommendation is flagged so that users can review and remove the sensitive content instead of applying the recommended sensitivity label.</span></span>

- <span data-ttu-id="10f95-259">若要详细了解如何在 Office 应用中应用这些标签、示例屏幕截图，以及如何检测敏感信息，请参阅[对 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)。</span><span class="sxs-lookup"><span data-stu-id="10f95-259">For details about how these labels are applied in Office apps, example screenshots, and how sensitive information is detected, see [Automatically apply or recommend sensitivity labels to your files and emails in Office](https://support.office.com/en-us/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1).</span></span>

<span data-ttu-id="10f95-260">特定于 Azure 信息保护统一标记客户端的注意事项：</span><span class="sxs-lookup"><span data-stu-id="10f95-260">Specific to the Azure Information Protection unified labeling client:</span></span>

-  <span data-ttu-id="10f95-261">自动标签和建议标签在你保存文档时应用于 Word、Excel 和 PowerPoint，并在你发送电子邮件时应用于 Outlook。</span><span class="sxs-lookup"><span data-stu-id="10f95-261">Automatic and recommended labeling applies to Word, Excel, and PowerPoint when you save a document, and to Outlook when you send an email.</span></span>

- <span data-ttu-id="10f95-262">为了让 Outlook 支持建议标签，必须先配置[高级策略设置](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)。</span><span class="sxs-lookup"><span data-stu-id="10f95-262">For Outlook to support recommended labeling, you must first configure an [advanced policy setting](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook).</span></span>

- <span data-ttu-id="10f95-263">敏感信息可以在文档和电子邮件的正文文本和页眉、页脚中检测到，但无法在电子邮件的主题行或附件中检测到。</span><span class="sxs-lookup"><span data-stu-id="10f95-263">Sensitive information can be detected in the body text in documents and emails, and to headers and footers—but not in the subject line or attachments of email.</span></span>

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a><span data-ttu-id="10f95-264">如何为 SharePoint、OneDrive 和 Exchange 配置自动标记策略</span><span class="sxs-lookup"><span data-stu-id="10f95-264">How to configure auto-labeling policies for SharePoint, OneDrive, and Exchange</span></span>

<span data-ttu-id="10f95-265">在配置自动标记策略前，请确保你了解这些先决条件。</span><span class="sxs-lookup"><span data-stu-id="10f95-265">Make sure you're aware of the prerequisites before you configure auto-labeling policies.</span></span> 

### <a name="prerequisites-for-auto-labeling-policies"></a><span data-ttu-id="10f95-266">自动标记策略的先决条件</span><span class="sxs-lookup"><span data-stu-id="10f95-266">Prerequisites for auto-labeling policies</span></span>

- <span data-ttu-id="10f95-267">模拟模式：</span><span class="sxs-lookup"><span data-stu-id="10f95-267">Simulation mode:</span></span>
    - <span data-ttu-id="10f95-268">必须启用 Microsoft 365 审核。</span><span class="sxs-lookup"><span data-stu-id="10f95-268">Auditing for Microsoft 365 must be turned on.</span></span> <span data-ttu-id="10f95-269">如果你需要启用审核，或者不确定是否已启用审核，请参阅[启用或禁用审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="10f95-269">If you need to turn on auditing or you're not sure whether auditing is already on, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
    - <span data-ttu-id="10f95-270">若要在源视图中查看文件或电子邮件内容，必须具有 **内容浏览器内容查看器** 角色。</span><span class="sxs-lookup"><span data-stu-id="10f95-270">To view file or email contents in the source view, you must have the **Content Explorer Content Viewer** role.</span></span> <span data-ttu-id="10f95-271">默认情况下，全局管理员不具有此角色。</span><span class="sxs-lookup"><span data-stu-id="10f95-271">Global admins don't have this role by default.</span></span> <span data-ttu-id="10f95-272">如果你没有此权限，在“**匹配项**”选项卡中选择一个项目时，将不会看到预览器窗格。</span><span class="sxs-lookup"><span data-stu-id="10f95-272">If you don't have this permission, you don't see the preview pane when you select an item from the **Matched Items** tab.</span></span>

- <span data-ttu-id="10f95-273">如何自动标记 SharePoint 和 OneDrive 中的文件：</span><span class="sxs-lookup"><span data-stu-id="10f95-273">To auto-label files in SharePoint and OneDrive:</span></span>
    - <span data-ttu-id="10f95-274">你已[启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)。</span><span class="sxs-lookup"><span data-stu-id="10f95-274">You have [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>
    - <span data-ttu-id="10f95-275">当自动标记策略运行时，该文件不得由其他进程或用户打开。</span><span class="sxs-lookup"><span data-stu-id="10f95-275">At the time the auto-labeling policy runs, the file mustn't be open by another process or user.</span></span> <span data-ttu-id="10f95-276">签出以供进行编辑的文件属于此类别。</span><span class="sxs-lookup"><span data-stu-id="10f95-276">A file that's checked out for editing falls into this category.</span></span>

- <span data-ttu-id="10f95-277">如果计划使用[自定义敏感信息类型](sensitive-information-type-learn-about.md)，而不是内置敏感度类型：</span><span class="sxs-lookup"><span data-stu-id="10f95-277">If you plan to use [custom sensitive information types](sensitive-information-type-learn-about.md) rather than the built-in sensitivity types:</span></span> 
    - <span data-ttu-id="10f95-278">自定义敏感性信息类型在保存自定义敏感性信息类型之后，会对添加到 SharePoint 或 OneDrive 的内容进行评估。</span><span class="sxs-lookup"><span data-stu-id="10f95-278">Custom sensitivity information types are evaluated for content that is added to SharePoint or OneDrive after the custom sensitivity information types are saved.</span></span> 
    - <span data-ttu-id="10f95-279">若要测试新的自定义敏感信息类型，请在创建自动标记策略前创建它们，然后创建新文档（其中包含用于测试的示例数据）。</span><span class="sxs-lookup"><span data-stu-id="10f95-279">To test new custom sensitive information types, create them before you create your auto-labeling policy, and then create new documents with sample data for testing.</span></span>

- <span data-ttu-id="10f95-280">你可以为自动标记策略选择一个或多个[已创建和发布](create-sensitivity-labels.md)（至少向一个用户发布）的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-280">One or more sensitivity labels [created and published](create-sensitivity-labels.md) (to at least one user) that you can select for your auto-labeling policies.</span></span> <span data-ttu-id="10f95-281">对于这些标签：</span><span class="sxs-lookup"><span data-stu-id="10f95-281">For these labels:</span></span>
    - <span data-ttu-id="10f95-282">启用或禁用 Office 应用标签设置中的自动标记无关紧要，因为该标签设置会补充自动标记策略，如简介中所述。</span><span class="sxs-lookup"><span data-stu-id="10f95-282">It doesn't matter if the auto-labeling in Office apps label setting is turned on or off, because that label setting supplements auto-labeling policies, as explained in the introduction.</span></span>
    - <span data-ttu-id="10f95-283">如果要用于自动标记的标签被配置为使用视觉标记（页眉、页脚、水印），请注意它们不会应用于文档。</span><span class="sxs-lookup"><span data-stu-id="10f95-283">If the labels you want to use for auto-labeling are configured to use visual markings (headers, footers, watermarks), note that these are not applied to documents.</span></span>
    - <span data-ttu-id="10f95-284">如果标签应用“[加密](encryption-sensitivity-labels.md)”：</span><span class="sxs-lookup"><span data-stu-id="10f95-284">If the labels apply [encryption](encryption-sensitivity-labels.md):</span></span>
        - <span data-ttu-id="10f95-285">当自动标签策略包括 SharePoint 或 OneDrive 的位置时，标签必须为“**立即分配权限**”设置进行配置。</span><span class="sxs-lookup"><span data-stu-id="10f95-285">When the auto-labeling policy includes locations for SharePoint or OneDrive, the label must be configured for the **Assign permissions now** setting.</span></span>
        - <span data-ttu-id="10f95-286">当自动标签策略仅应用于 Exchange 时，标签可以为“**立即分配权限**”或“**让用户分配权限**”进行配置（对于“不转发”或“只加密”选项）。</span><span class="sxs-lookup"><span data-stu-id="10f95-286">When the auto-labeling policy is just for Exchange, the label can be configured for either **Assign permissions now** or **Let users assign permissions** (for the Do Not Forward or Encrypt-Only options).</span></span>

### <a name="learn-about-simulation-mode"></a><span data-ttu-id="10f95-287">了解模拟模式</span><span class="sxs-lookup"><span data-stu-id="10f95-287">Learn about simulation mode</span></span>

<span data-ttu-id="10f95-288">模拟模式是自动标记策略所独有的，并且已整合到工作流中。</span><span class="sxs-lookup"><span data-stu-id="10f95-288">Simulation mode is unique to auto-labeling policies and woven into the workflow.</span></span> <span data-ttu-id="10f95-289">在策略至少运行一次模拟前，无法自动标记文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="10f95-289">You can't automatically label documents and emails until your policy has run at least one simulation.</span></span>

<span data-ttu-id="10f95-290">用于自动标记策略的工作流：</span><span class="sxs-lookup"><span data-stu-id="10f95-290">Workflow for an auto-labeling policy:</span></span>

1. <span data-ttu-id="10f95-291">创建和配置自动标记策略。</span><span class="sxs-lookup"><span data-stu-id="10f95-291">Create and configure an auto-labeling policy.</span></span>

2. <span data-ttu-id="10f95-292">以模拟模式运行该策略，可能需要 48 小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="10f95-292">Run the policy in simulation mode, which can take 48 hours to complete.</span></span>

3. <span data-ttu-id="10f95-293">查看结果，并在必要时优化策略。</span><span class="sxs-lookup"><span data-stu-id="10f95-293">Review the results, and if necessary, refine your policy.</span></span> <span data-ttu-id="10f95-294">重新运行模拟模式，并等待其再次完成。</span><span class="sxs-lookup"><span data-stu-id="10f95-294">Rerun simulation mode and wait for it to complete again.</span></span>

4. <span data-ttu-id="10f95-295">根据需要重复步骤 3。</span><span class="sxs-lookup"><span data-stu-id="10f95-295">Repeat step 3 as needed.</span></span>

5. <span data-ttu-id="10f95-296">在生产环境中部署。</span><span class="sxs-lookup"><span data-stu-id="10f95-296">Deploy in production.</span></span>

<span data-ttu-id="10f95-297">模拟部署的运行方式与 PowerShell 的 WhatIf 参数相同。</span><span class="sxs-lookup"><span data-stu-id="10f95-297">The simulated deployment runs like the WhatIf parameter for PowerShell.</span></span> <span data-ttu-id="10f95-298">你将看到报告的结果，如同自动标记策略已使用你定义的规则应用了所选标签一样。</span><span class="sxs-lookup"><span data-stu-id="10f95-298">You see results reported as if the auto-labeling policy had applied your selected label, using the rules that you defined.</span></span> <span data-ttu-id="10f95-299">然后，你可以根据需要优化规则的准确性，并重新运行模拟。</span><span class="sxs-lookup"><span data-stu-id="10f95-299">You can then refine your rules for accuracy if needed, and rerun the simulation.</span></span> <span data-ttu-id="10f95-300">但是，由于 Exchange 的自动标记适用于已发送和接收的电子邮件，而不是存储在邮箱中的电子邮件，因此不要期望模拟中的电子邮件结果保持一致，除非你能够发送和接收完全相同的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="10f95-300">However, because auto-labeling for Exchange applies to emails that are sent and received, rather than emails stored in mailboxes, don't expect results for email in a simulation to be consistent unless you're able to send and receive the exact same email messages.</span></span>

<span data-ttu-id="10f95-301">模拟模式还允许你在部署前逐步增加自动标记策略的范围。</span><span class="sxs-lookup"><span data-stu-id="10f95-301">Simulation mode also lets you gradually increase the scope of your auto-labeling policy before deployment.</span></span> <span data-ttu-id="10f95-302">例如，你可以从一个位置（如 SharePoint 网站）和一个文档库开始。</span><span class="sxs-lookup"><span data-stu-id="10f95-302">For example, you might start with a single location, such as a SharePoint site, with a single document library.</span></span> <span data-ttu-id="10f95-303">然后，使用迭代更改，将范围增大到多个网站，然后将其增加到其他位置，如 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="10f95-303">Then, with iterative changes, increase the scope to multiple sites, and then to another location, such as OneDrive.</span></span>

<span data-ttu-id="10f95-304">最后，可以使用模拟模式来提供运行自动标记策略所需时间的近似值，以帮助计划和安排在没有模拟模式的情况下运行自动标记策略的时间。</span><span class="sxs-lookup"><span data-stu-id="10f95-304">Finally, you can use simulation mode to provide an approximation of the time needed to run your auto-labeling policy, to help you plan and schedule when to run it without simulation mode.</span></span>

### <a name="creating-an-auto-labeling-policy"></a><span data-ttu-id="10f95-305">创建自动标记策略</span><span class="sxs-lookup"><span data-stu-id="10f95-305">Creating an auto-labeling policy</span></span>

1. <span data-ttu-id="10f95-306">在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)，导航到敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="10f95-306">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="10f95-307">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="10f95-307">**Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="10f95-308">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-308">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="10f95-309">选择“**自动标记**”选项卡：</span><span class="sxs-lookup"><span data-stu-id="10f95-309">Select the **Auto-labeling** tab:</span></span>
    
    ![“自动标记”选项卡](../media/auto-labeling-tab.png)
    
    > [!NOTE]
    > <span data-ttu-id="10f95-311">如果看不到“**自动标记**”选项卡，则此功能当前在你的区域中不可用。</span><span class="sxs-lookup"><span data-stu-id="10f95-311">If you don't see the **Auto-labeling** tab, this functionality isn't currently available in your region.</span></span>

3. <span data-ttu-id="10f95-312">选择“**+ 创建自动标记策略**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-312">Select **+ Create auto-labeling policy**.</span></span> <span data-ttu-id="10f95-313">这将启动“新建策略向导”：</span><span class="sxs-lookup"><span data-stu-id="10f95-313">This starts the New policy wizard:</span></span>
    
    ![<span data-ttu-id="10f95-314">用于实现自动标记的“新建策略向导”</span><span class="sxs-lookup"><span data-stu-id="10f95-314">New policy wizard for auto-labeling</span></span> ](../media/auto-labeling-wizard.png)

4. <span data-ttu-id="10f95-315">对于“**选择要将此标签应用于的信息**”页面：选择其中一个模板，如“**财务**”或“**隐私**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-315">For the page **Choose info you want this label applied to**: Select one of the templates, such as **Financial** or **Privacy**.</span></span> <span data-ttu-id="10f95-316">可使用“**显示选项**”下拉列表来优化搜索。</span><span class="sxs-lookup"><span data-stu-id="10f95-316">You can refine your search by using the **Show options for** dropdown.</span></span> <span data-ttu-id="10f95-317">或者，如果模板无法满足你的要求，请选择“**自定义策略**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-317">Or, select **Custom policy** if the templates don't meet your requirements.</span></span> <span data-ttu-id="10f95-318">选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-318">Select **Next**.</span></span>

5. <span data-ttu-id="10f95-319">对于“**为自动标记策略命名**”页面：提供唯一的名称，并选择性地提供描述，以帮助识别自动应用的标签、位置和条件（用于标识要标记的内容）。</span><span class="sxs-lookup"><span data-stu-id="10f95-319">For the page **Name your auto-labeling policy**: Provide a unique name, and optionally a description to help identify the automatically applied label, locations, and conditions that identify the content to label.</span></span>

6. <span data-ttu-id="10f95-320">对于“**选择要应用标签的位置**”页面：选择并指定 Exchange、SharePoint 网站和 OneDrive 的位置。</span><span class="sxs-lookup"><span data-stu-id="10f95-320">For the page **Choose locations where you want to apply the label**: Select and specify locations for Exchange, SharePoint sites, and OneDrive.</span></span> <span data-ttu-id="10f95-321">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-321">Then select **Next**.</span></span>
    
    ![<span data-ttu-id="10f95-322">选择位置页面自动标记向导</span><span class="sxs-lookup"><span data-stu-id="10f95-322">Choose locations page auto-labelingwizard</span></span> ](../media/locations-auto-labeling-wizard.png)
    
    <span data-ttu-id="10f95-323">必须指定单独的 SharePoint 网站和 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="10f95-323">You must specify individual SharePoint sites and OneDrive accounts.</span></span> <span data-ttu-id="10f95-324">对于 OneDrive，用户的 OneDrive 帐户的 URL 采用以下格式：`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span><span class="sxs-lookup"><span data-stu-id="10f95-324">For OneDrive, the URL for a user's OneDrive account is in the following format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`</span></span>
    
    <span data-ttu-id="10f95-325">例如，对于 contoso 租户中用户名为“rsimone”的用户：`https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span><span class="sxs-lookup"><span data-stu-id="10f95-325">For example, for a user in the contoso tenant that has a user name of "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`</span></span>
    
    <span data-ttu-id="10f95-326">要验证租户的语法并标识用户的 URL，请参阅[获取组织中所有用户 OneDrive URL 的列表](/onedrive/list-onedrive-urls)。</span><span class="sxs-lookup"><span data-stu-id="10f95-326">To verify the syntax for your tenant and identify URLs for users, see [Get a list of all user OneDrive URLs in your organization](/onedrive/list-onedrive-urls).</span></span>

7. <span data-ttu-id="10f95-327">对于“**设置常用或高级规则**”页面：保留“**常用规则**”的默认设置，以定义用于在所有选定位置标识要标记的内容的规则。</span><span class="sxs-lookup"><span data-stu-id="10f95-327">For the **Set up common or advanced rules** page: Keep the default of **Common rules** to define rules that identify content to label across all your selected locations.</span></span> <span data-ttu-id="10f95-328">如果需要针对每个位置使用不同的规则，请选择“**高级规则**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-328">If you need different rules per location, select **Advanced rules**.</span></span> <span data-ttu-id="10f95-329">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-329">Then select **Next**.</span></span>
    
    <span data-ttu-id="10f95-330">这些规则使用包含敏感信息类型和共享选项的条件：</span><span class="sxs-lookup"><span data-stu-id="10f95-330">The rules use conditions that include sensitive information types and sharing options:</span></span>
    - <span data-ttu-id="10f95-331">对于敏感信息类型，你可以选择内置和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="10f95-331">For sensitive information types, you can select both built-in and custom sensitive information types.</span></span>
    - <span data-ttu-id="10f95-332">对于共享选项，你可以选择“**仅与组织内部人员共享**”或“**与组织外部人员共享**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-332">For the shared options, you can choose **only with people inside my organization** or **with people outside my organization**.</span></span>
    
    <span data-ttu-id="10f95-333">如果你的唯一位置是 **Exchange**，或者如果你选择“**高级规则**”，则还可以选择其他条件：</span><span class="sxs-lookup"><span data-stu-id="10f95-333">If your only location is **Exchange**, or if you select **Advanced rules**, there are additional conditions that you can select:</span></span>
    - <span data-ttu-id="10f95-334">发件人 IP 地址为</span><span class="sxs-lookup"><span data-stu-id="10f95-334">Sender IP address is</span></span>
    - <span data-ttu-id="10f95-335">收件人域为</span><span class="sxs-lookup"><span data-stu-id="10f95-335">Recipient domain is</span></span>
    - <span data-ttu-id="10f95-336">收件人为</span><span class="sxs-lookup"><span data-stu-id="10f95-336">Recipient is</span></span>
    - <span data-ttu-id="10f95-337">附件的文件扩展名为</span><span class="sxs-lookup"><span data-stu-id="10f95-337">Attachment's file extension is</span></span>
    - <span data-ttu-id="10f95-338">附件受密码保护</span><span class="sxs-lookup"><span data-stu-id="10f95-338">Attachment is password protected</span></span>
    - <span data-ttu-id="10f95-339">无法扫描任何电子邮件附件的内容</span><span class="sxs-lookup"><span data-stu-id="10f95-339">Any email attachment's content could not be scanned</span></span>
    - <span data-ttu-id="10f95-340">任何电子邮件附件的内容均未完成扫描</span><span class="sxs-lookup"><span data-stu-id="10f95-340">Any email attachment's content didn't complete scanning</span></span>

8. <span data-ttu-id="10f95-341">根据先前的选择，你现在有机会使用条件和例外来创建新规则。</span><span class="sxs-lookup"><span data-stu-id="10f95-341">Depending on your previous choices, you'll now have an opportunity to create new rules by using conditions and exceptions.</span></span>
    
    <span data-ttu-id="10f95-342">敏感信息类型的配置选项与为 Office 应用自动标记所选的选项相同。</span><span class="sxs-lookup"><span data-stu-id="10f95-342">The configuration options for sensitive information types are the same as those you select for auto-labeling for Office apps.</span></span> <span data-ttu-id="10f95-343">如果需要详细信息，请参阅[配置标签的敏感信息类型](#configuring-sensitive-info-types-for-a-label)。</span><span class="sxs-lookup"><span data-stu-id="10f95-343">If you need more information, see [Configuring sensitive info types for a label](#configuring-sensitive-info-types-for-a-label).</span></span>
    
    <span data-ttu-id="10f95-344">定义所需的所有规则并确认其状态为“开启”后，请选择“**下一步**”，以继续选择要自动应用的标签。</span><span class="sxs-lookup"><span data-stu-id="10f95-344">When you have defined all the rules you need, and confirmed their status is on, select **Next** to move on to choosing a label to auto-apply.</span></span>

11. <span data-ttu-id="10f95-345">对于“**选择要自动应用的标签**”页面：选择“**+ 选择标签**”，从“**选择敏感度标签**”窗格中选择一个标签，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-345">For the **Choose a label to auto-apply** page: Select **+ Choose a label**, select a label from the **Choose a sensitivity label** pane, and then select **Next**.</span></span>

12. <span data-ttu-id="10f95-346">对于“**决定是立即还是以后测试策略**”页面：如果现在已准备好运行自动标记策略，请在模拟模式中选择“**在模拟模式下运行策略**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-346">For the **Decide if you want to test out the policy now or later** page: Select **Run policy in simulation mode** if you're ready to run the auto-labeling policy now, in simulation mode.</span></span> <span data-ttu-id="10f95-347">否则，请选择“**保持策略关闭**”。</span><span class="sxs-lookup"><span data-stu-id="10f95-347">Otherwise, select **Leave policy turned off**.</span></span> <span data-ttu-id="10f95-348">选择“**下一步**”：</span><span class="sxs-lookup"><span data-stu-id="10f95-348">Select **Next**:</span></span> 
    
    ![测试策略自动标记向导](../media/simulation-mode-auto-labeling-wizard.png)

13. <span data-ttu-id="10f95-350">对于“摘要”页：审阅自动标记策略的配置，并进行所需的任何更改，然后完成向导。</span><span class="sxs-lookup"><span data-stu-id="10f95-350">For the **Summary** page: Review the configuration of your auto-labeling policy and make any changes that needed, and complete the wizard.</span></span>

<span data-ttu-id="10f95-351">现在，在“**信息保护**” > “**自动标记**”页面上，可在“**模拟**”或“**关闭**”部分看到自动标记策略，具体哪个部分取决于是否选择在模拟模式下运行它。</span><span class="sxs-lookup"><span data-stu-id="10f95-351">Now on the **Information protection** > **Auto-labeling** page, you see your auto-labeling policy in the **Simulation** or **Off** section, depending on whether you chose to run it in simulation mode or not.</span></span> <span data-ttu-id="10f95-352">选择你的策略以查看配置和状态的详细信息（例如，**策略模拟仍在运行**），</span><span class="sxs-lookup"><span data-stu-id="10f95-352">Select your policy to see the details of the configuration and status (for example, **Policy simulation is still running**).</span></span> <span data-ttu-id="10f95-353">对于模拟模式中的策略，选择“**匹配的项**”选项卡，以查看与你指定的规则匹配的电子邮件或文档。</span><span class="sxs-lookup"><span data-stu-id="10f95-353">For policies in simulation mode, select the **Matched items** tab to see which emails or documents matched the rules that you specified.</span></span>

<span data-ttu-id="10f95-354">可直接从此界面修改策略：</span><span class="sxs-lookup"><span data-stu-id="10f95-354">You can modify your policy directly from this interface:</span></span>

- <span data-ttu-id="10f95-355">对于“**禁用**”部分中的策略，选择“**编辑策略**”按钮。</span><span class="sxs-lookup"><span data-stu-id="10f95-355">For a policy in the **Off** section, select the **Edit policy** button.</span></span>

- <span data-ttu-id="10f95-356">对于“**模拟**”部分中的策略，从以下任一选项卡中，选择页面顶部的“**编辑** 策略”选项：</span><span class="sxs-lookup"><span data-stu-id="10f95-356">For policy in the **Simulation** section, select the **Edit policy** option at the top of the page, from either tab:</span></span>
    
    ![启用自动标记策略选项](../media/auto-labeling-edit.png)
    
    <span data-ttu-id="10f95-358">如果你已准备好运行策略而不进行模拟，请选择“**启用策略**”选项。</span><span class="sxs-lookup"><span data-stu-id="10f95-358">When you're ready to run the policy without simulation, select the **Turn on policy** option.</span></span>

<span data-ttu-id="10f95-359">自动策略将持续运行，直至删除。</span><span class="sxs-lookup"><span data-stu-id="10f95-359">Your auto-policies run continuously until they are deleted.</span></span> <span data-ttu-id="10f95-360">例如，新建和已修改的文档将包含在当前的策略设置中。</span><span class="sxs-lookup"><span data-stu-id="10f95-360">For example, new and modified documents will be included with the current policy settings.</span></span>

<span data-ttu-id="10f95-361">如果你具有相应的[权限](data-classification-content-explorer.md#permissions)，则还可通过使用[内容资源管理器](data-classification-content-explorer.md)来查看自动标记策略的结果：</span><span class="sxs-lookup"><span data-stu-id="10f95-361">You can also see the results of your auto-labeling policy by using [content explorer](data-classification-content-explorer.md) when you have the appropriate [permissions](data-classification-content-explorer.md#permissions):</span></span>
- <span data-ttu-id="10f95-362">**内容浏览器列表查看器** 允许你查看文件的标签，而不是文件的内容。</span><span class="sxs-lookup"><span data-stu-id="10f95-362">**Content Explorer List Viewer** lets you see a file's label but not the file's contents.</span></span>
- <span data-ttu-id="10f95-363">**内容浏览器内容查看器** 允许你查看文件的内容。</span><span class="sxs-lookup"><span data-stu-id="10f95-363">**Content Explorer Content Viewer** lets you see the file's contents.</span></span>

> [!TIP]
> <span data-ttu-id="10f95-364">你还可以使用内容资源管理器来标识具有包含敏感信息的未标记文档的位置。</span><span class="sxs-lookup"><span data-stu-id="10f95-364">You can also use content explorer to identify locations that have documents with sensitive information, but are unlabeled.</span></span> <span data-ttu-id="10f95-365">使用此信息，请考虑将这些位置添加到自动标记策略中，并将标识的敏感信息类型作为规则包括在内。</span><span class="sxs-lookup"><span data-stu-id="10f95-365">Using this information, consider adding these locations to your auto-labeling policy, and include the identified sensitive information types as rules.</span></span>

### <a name="use-powershell-for-auto-labeling-policies"></a><span data-ttu-id="10f95-366">使用 PowerShell 自动标记策略</span><span class="sxs-lookup"><span data-stu-id="10f95-366">Use PowerShell for auto-labeling policies</span></span>

<span data-ttu-id="10f95-367">可使用[安全&合规中心 PowerShell](/powershell/exchange/scc-powershell)创建和配置自动标记策略。</span><span class="sxs-lookup"><span data-stu-id="10f95-367">You can use [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell) to create and configure auto-labeling policies.</span></span> <span data-ttu-id="10f95-368">这意味着可以完全编写创建和维护的自动标签策略，这也为OneDrive和SharePoint位置指定多个URL提供了更有效的方法。</span><span class="sxs-lookup"><span data-stu-id="10f95-368">This means you can fully script the creation and maintenance of your auto-labeling policies, which also provides a more efficient method of specifying multiple URLs for OneDrive and SharePoint locations.</span></span>

<span data-ttu-id="10f95-369">在 PowerShell 中运行命令之前，必须先[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="10f95-369">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="10f95-370">若要创建新的自动标记策略：</span><span class="sxs-lookup"><span data-stu-id="10f95-370">To create a new auto-labeling policy:</span></span> 

```powershell
New-AutoSensitivityLabelPolicy -Name <AutoLabelingPolicyName> -SharePointLocation "<SharePointSiteLocation>" -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```
<span data-ttu-id="10f95-371">此命令将为你指定的 SharePoint 网站创建一个自动标记策略。</span><span class="sxs-lookup"><span data-stu-id="10f95-371">This command creates an auto-labeling policy for a SharePoint site that you specify.</span></span> <span data-ttu-id="10f95-372">对于 OneDrive 位置，请改为使用 *OneDriveLocation* 参数。</span><span class="sxs-lookup"><span data-stu-id="10f95-372">For a OneDrive location, use the *OneDriveLocation* parameter, instead.</span></span> 

<span data-ttu-id="10f95-373">若要将其他网站添加到现有的自动标记策略中：</span><span class="sxs-lookup"><span data-stu-id="10f95-373">To add additional sites to an existing auto-labeling policy:</span></span>

```powershell
$spoLocations = @("<SharePointSiteLocation1>","<SharePointSiteLocation2>")
Set-AutoSensitivityLabelPolicy -Identity <AutoLabelingPolicyName> -AddSharePointLocation $spoLocations -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```

<span data-ttu-id="10f95-374">此命令在变量中指定其他 SharePoint URL，然后将其添加到现有的自动标记策略中。</span><span class="sxs-lookup"><span data-stu-id="10f95-374">This command specifies the additional SharePoint URLs in a variable that is then added to an existing auto-labeling policy.</span></span> <span data-ttu-id="10f95-375">若要改为添加 OneDrive 位置，请使用 *AddOneDriveLocation* 参数和其他变量，例如 *$OneDriveLocations*。</span><span class="sxs-lookup"><span data-stu-id="10f95-375">To add OneDrive locations instead, use the *AddOneDriveLocation* parameter with a different variable, such as *$OneDriveLocations*.</span></span>

<span data-ttu-id="10f95-376">若要创建新的自动标记策略规则：</span><span class="sxs-lookup"><span data-stu-id="10f95-376">To create a new auto-labeling policy rule:</span></span>

```powershell
New-AutoSensitivityLabelRule -Policy <AutoLabelingPolicyName> -Name <AutoLabelingRuleName> -ContentContainsSensitiveInformation @{"name"= "a44669fe-0d48-453d-a9b1-2cc83f2cba77"; "mincount" = "2"} -Workload SharePoint
```

<span data-ttu-id="10f95-377">对于现有的自动标记策略，此命令将创建新的策略规则以检测 **美国社会保险号 (SSN)**，其实体 ID 为 a44669fe-0d48-453d-a9b1-2cc83f2cba77。</span><span class="sxs-lookup"><span data-stu-id="10f95-377">For an existing auto-labeling policy, this command creates a new policy rule to detect the sensitive information type of **U.S. social security number (SSN)**, which has an entity ID of a44669fe-0d48-453d-a9b1-2cc83f2cba77.</span></span> <span data-ttu-id="10f95-378">要查找其他敏感信息类型的实体 ID，请参阅[敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="10f95-378">To find the entity IDs for other sensitive information types, refer to [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="10f95-379">有关支持自动标记策略的 PowerShell cmdlet、其可用参数和一些示例的更多信息，请参阅以下 cmdlet 帮助：</span><span class="sxs-lookup"><span data-stu-id="10f95-379">For more information about the PowerShell cmdlets that support auto-labeling policies, their available parameters and some examples, see the following cmdlet help:</span></span>

- [<span data-ttu-id="10f95-380">Get-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="10f95-380">Get-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [<span data-ttu-id="10f95-381">New-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="10f95-381">New-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [<span data-ttu-id="10f95-382">New-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="10f95-382">New-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/new-autosensitivitylabelrule)
- [<span data-ttu-id="10f95-383">Remove-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="10f95-383">Remove-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [<span data-ttu-id="10f95-384">Remove-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="10f95-384">Remove-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/remove-autosensitivitylabelrule)
- [<span data-ttu-id="10f95-385">Set-AutoSensitivityLabelPolicy</span><span class="sxs-lookup"><span data-stu-id="10f95-385">Set-AutoSensitivityLabelPolicy</span></span>](/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [<span data-ttu-id="10f95-386">Set-AutoSensitivityLabelRule</span><span class="sxs-lookup"><span data-stu-id="10f95-386">Set-AutoSensitivityLabelRule</span></span>](/powershell/module/exchange/set-autosensitivitylabelrule)