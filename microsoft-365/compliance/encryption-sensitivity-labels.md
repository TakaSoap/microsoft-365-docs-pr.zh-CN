---
title: 通过敏感度标签应用加密，从而限制对内容的访问
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 配置加密的敏感度标签，以便通过限制访问和使用来保护你的数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae9131b4cd70cfca4cc32116a651bf4642ed94f1
ms.sourcegitcommit: c4a7b227f7d9abd666dfb93e3ded78ba8288e649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229432"
---
# <a name="restrict-access-to-content-by-using-sensitivity-labels-to-apply-encryption"></a><span data-ttu-id="033bd-103">通过敏感度标签应用加密，从而限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="033bd-103">Restrict access to content by using sensitivity labels to apply encryption</span></span> 

><span data-ttu-id="033bd-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="033bd-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="033bd-p101">创建敏感度标签时，可以限制对将要应用标签的内容的访问。例如，通过敏感度标签的加密设置，可以保护内容，以便：</span><span class="sxs-lookup"><span data-stu-id="033bd-p101">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="033bd-107">只有组织中的用户才能打开机密文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="033bd-108">只有市场部的用户才能编辑和打印促销声明文档或电子邮件，而组织中的所有其他用户只能阅读它。</span><span class="sxs-lookup"><span data-stu-id="033bd-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="033bd-109">用户无法转发电子邮件或从中复制包含有关内部组织的新闻的信息。</span><span class="sxs-lookup"><span data-stu-id="033bd-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="033bd-110">发送到业务合作伙伴的当前价目表在指定日期后无法打开。</span><span class="sxs-lookup"><span data-stu-id="033bd-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="033bd-111">当文档或电子邮件被加密时，对内容的访问将受到限制，以便它：</span><span class="sxs-lookup"><span data-stu-id="033bd-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="033bd-112">只能由标签的加密设置授权的用户解密。</span><span class="sxs-lookup"><span data-stu-id="033bd-112">Can be decrypted only by users authorized by the label's encryption settings.</span></span>
- <span data-ttu-id="033bd-113">无论其所在位置（组织内部或外部）如何，仍保持加密状态，即使该文件被重命名也是如此。</span><span class="sxs-lookup"><span data-stu-id="033bd-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file's renamed.</span></span>
- <span data-ttu-id="033bd-114">静态加密（例如，在 OneDrive 帐户中）和传输加密（例如，正在通过 Internet 传输的电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="033bd-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, email as it traverses the internet).</span></span>

<span data-ttu-id="033bd-115">最后，作为管理员，你在配置敏感度标签来应用加密时可选择执行下述任一操作：</span><span class="sxs-lookup"><span data-stu-id="033bd-115">Finally, as an admin, when you configure a sensitivity label to apply encryption, you can choose either to:</span></span>

- <span data-ttu-id="033bd-116">**立即分配权限**，以便准确确定哪些用户获得了带有该标签的内容的哪些权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-116">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="033bd-117">在用户将此标签应用到内容时**允许用户分配权限**。</span><span class="sxs-lookup"><span data-stu-id="033bd-117">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="033bd-118">这样，即可让组织内部人员在协作处理和完成任务时具有可能需要的一定程度的灵活性。</span><span class="sxs-lookup"><span data-stu-id="033bd-118">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="033bd-119">在 Microsoft 365 合规中心、Microsoft 365 安全中心或安全与合规中心[创建敏感度标签](create-sensitivity-labels.md)时，可使用加密设置。</span><span class="sxs-lookup"><span data-stu-id="033bd-119">The encryption settings are available when you [create a sensitivity label](create-sensitivity-labels.md) in the Microsoft 365 compliance center, Microsoft 365 security center, or the Security & Compliance Center.</span></span>

## <a name="understand-how-the-encryption-works"></a><span data-ttu-id="033bd-120">了解加密的工作方式</span><span class="sxs-lookup"><span data-stu-id="033bd-120">Understand how the encryption works</span></span>

<span data-ttu-id="033bd-121">加密使用了 Azure 信息保护中的 Azure 权限管理服务 (Azure RMS)。</span><span class="sxs-lookup"><span data-stu-id="033bd-121">Encryption uses the Azure Rights Management service (Azure RMS) from Azure Information Protection.</span></span> <span data-ttu-id="033bd-122">该保护解决方案使用了加密、标识和身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="033bd-122">This protection solution uses encryption, identity, and authorization policies.</span></span> <span data-ttu-id="033bd-123">要了解详细信息，请参阅 Azure 信息保护文档中的[什么是 Azure 权限管理？](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="033bd-123">To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) from the Azure Information Protection documentation.</span></span> 

<span data-ttu-id="033bd-124">使用此加密解决方案时，**超级用户**功能确保了获得授权的用户和服务始终可读取和检测已针对你的组织进行加密的数据。</span><span class="sxs-lookup"><span data-stu-id="033bd-124">When you use this encryption solution, the **super user** feature ensures that authorized people and services can always read and inspect the data that has been encrypted for your organization.</span></span> <span data-ttu-id="033bd-125">必要时，可删除或更改加密。</span><span class="sxs-lookup"><span data-stu-id="033bd-125">If necessary, the encryption can then be removed or changed.</span></span> <span data-ttu-id="033bd-126">有关详细信息，请参阅[为 Azure 信息保护和发现服务或数据恢复配置超级用户](https://docs.microsoft.com/azure/information-protection/configure-super-users)。</span><span class="sxs-lookup"><span data-stu-id="033bd-126">For more information, see [Configuring super users for Azure Information Protection and discovery services or data recovery](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

## <a name="how-to-configure-a-label-for-encryption"></a><span data-ttu-id="033bd-127">如何配置加密标签</span><span class="sxs-lookup"><span data-stu-id="033bd-127">How to configure a label for encryption</span></span>

<span data-ttu-id="033bd-128">[创建或编辑敏感度标签](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)，然后在向导的**加密**页面上选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="033bd-128">[Create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels), and on the **Encryption** page of the wizard, select one of the following options:</span></span>

- <span data-ttu-id="033bd-129">**无**：新标签的默认设置。</span><span class="sxs-lookup"><span data-stu-id="033bd-129">**None**: The default setting for a new label.</span></span> <span data-ttu-id="033bd-130">不应用新加密。</span><span class="sxs-lookup"><span data-stu-id="033bd-130">No new encryption is applied.</span></span>
- <span data-ttu-id="033bd-131">**应用**：启用加密，然后指定加密设置。</span><span class="sxs-lookup"><span data-stu-id="033bd-131">**Apply**: Turns on encryption, and you then specify encryption settings.</span></span>
- <span data-ttu-id="033bd-132">**删除**：如果文档或电子邮件已加密，则删除加密。</span><span class="sxs-lookup"><span data-stu-id="033bd-132">**Remove**: Removes encryption if the document or email is encrypted.</span></span>

> [!NOTE]
> <span data-ttu-id="033bd-133">只有 Azure 信息保护统一标记客户端支持“**删除**”选项。</span><span class="sxs-lookup"><span data-stu-id="033bd-133">The **Remove** option is supported by the Azure Information Protection unified labeling client only.</span></span> <span data-ttu-id="033bd-134">使用内置标签时，Office 应用和服务中显示了具有此选项的标签；如果选中，则加密行为与“**无**”选项的行为相同。</span><span class="sxs-lookup"><span data-stu-id="033bd-134">When you use built-in labeling, a label with this option is visible in Office apps and services and if selected, the encryption behavior is the same as **None**.</span></span>

<span data-ttu-id="033bd-135">配置加密选项：</span><span class="sxs-lookup"><span data-stu-id="033bd-135">Configuring the encryption options:</span></span>

![用于加密的敏感度标签选项](../media/encrytion-options-sensitivity-label.png)


### <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="033bd-137">应用标签后，现有加密会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="033bd-137">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="033bd-138">如果向未加密的内容应用敏感度标签，则你可选择的加密选项的结果一目了然。</span><span class="sxs-lookup"><span data-stu-id="033bd-138">If a sensitivity label is applied to unencrypted content, the outcome of the encryption options you can select is self-explanatory.</span></span> <span data-ttu-id="033bd-139">例如，如果加密设置为“**无**”，则内容保持在未加密状态。</span><span class="sxs-lookup"><span data-stu-id="033bd-139">For example, if encryption is set to **None**, the content remains unencrypted.</span></span>

<span data-ttu-id="033bd-140">但是，内容可能已经加密。</span><span class="sxs-lookup"><span data-stu-id="033bd-140">However, the content might be already encrypted.</span></span> <span data-ttu-id="033bd-141">例如，其他用户可能已应用以下内容：</span><span class="sxs-lookup"><span data-stu-id="033bd-141">For example, another user might have applied:</span></span>

- <span data-ttu-id="033bd-142">其自己的权限，包括在标签提示时提供的用户定义的权限、Azure 信息保护客户端提供的自定义权限，以及 Office 应用中的**受限访问**文档保护。</span><span class="sxs-lookup"><span data-stu-id="033bd-142">Their own permissions, which include user-defined permissions when prompted by a label, custom permissions by the Azure Information Protection client, and the **Restricted Access** document protection from within an Office app.</span></span>
- <span data-ttu-id="033bd-143">在不使用标签的情况下加密内容的 Azure 权限管理保护模板。</span><span class="sxs-lookup"><span data-stu-id="033bd-143">An Azure Rights Management protection template that encrypts the content independently from a label.</span></span> <span data-ttu-id="033bd-144">此类别包括通过权限保护应用加密的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="033bd-144">This category includes mail flow rules that apply encryption by using rights protection.</span></span>
- <span data-ttu-id="033bd-145">使用管理员分配的权限应用加密的标签。</span><span class="sxs-lookup"><span data-stu-id="033bd-145">A label that applies encryption with permissions assigned by the administrator.</span></span>

<span data-ttu-id="033bd-146">下表说明了在向该内容应用敏感度标签后现有加密发生的情况：</span><span class="sxs-lookup"><span data-stu-id="033bd-146">The following table identifies what happens to existing encryption when a sensitivity label is applied to that content:</span></span>

| |<span data-ttu-id="033bd-147">**加密：无**</span><span class="sxs-lookup"><span data-stu-id="033bd-147">**Encryption: None**</span></span>|<span data-ttu-id="033bd-148">**加密：应用**</span><span class="sxs-lookup"><span data-stu-id="033bd-148">**Encryption: Apply**</span></span>|<span data-ttu-id="033bd-149">**加密：删除**</span><span class="sxs-lookup"><span data-stu-id="033bd-149">**Encryption: Remove**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="033bd-150">**用户指定的权限**</span><span class="sxs-lookup"><span data-stu-id="033bd-150">**Permissions specified by a user**</span></span>|<span data-ttu-id="033bd-151">保留原有加密</span><span class="sxs-lookup"><span data-stu-id="033bd-151">Original encryption is preserved</span></span>|<span data-ttu-id="033bd-152">应用新的标签加密</span><span class="sxs-lookup"><span data-stu-id="033bd-152">New label encryption is applied</span></span>|<span data-ttu-id="033bd-153">删除原有加密</span><span class="sxs-lookup"><span data-stu-id="033bd-153">Original encryption is removed</span></span>|
|<span data-ttu-id="033bd-154">**保护模板**</span><span class="sxs-lookup"><span data-stu-id="033bd-154">**Protection template**</span></span>|<span data-ttu-id="033bd-155">保留原有加密</span><span class="sxs-lookup"><span data-stu-id="033bd-155">Original encryption is preserved</span></span>|<span data-ttu-id="033bd-156">应用新的标签加密</span><span class="sxs-lookup"><span data-stu-id="033bd-156">New label encryption is applied</span></span>|<span data-ttu-id="033bd-157">删除原有加密</span><span class="sxs-lookup"><span data-stu-id="033bd-157">Original encryption is removed</span></span>|
|<span data-ttu-id="033bd-158">**具有管理员定义的权限的标签**</span><span class="sxs-lookup"><span data-stu-id="033bd-158">**Label with administator-defined permissions**</span></span>|<span data-ttu-id="033bd-159">删除原有加密</span><span class="sxs-lookup"><span data-stu-id="033bd-159">Original encryption is removed</span></span>|<span data-ttu-id="033bd-160">应用新的标签加密</span><span class="sxs-lookup"><span data-stu-id="033bd-160">New label encryption is applied</span></span>|<span data-ttu-id="033bd-161">删除原有加密</span><span class="sxs-lookup"><span data-stu-id="033bd-161">Original encryption is removed</span></span>|

<span data-ttu-id="033bd-162">请注意，如果应用了新的标签加密或删除了原有加密，则仅在应用标签的用户具有支持此操作的使用权限或角色时才会发生此情况：</span><span class="sxs-lookup"><span data-stu-id="033bd-162">Note that in the cases where the new label encryption is applied or the original encryption is removed, this happens only if the user applying the label has a usage right or role that supports this action:</span></span>
- <span data-ttu-id="033bd-163">“导出”或“完全控制”[使用权限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="033bd-163">The [usage right](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Export or Full Control.</span></span>
- <span data-ttu-id="033bd-164">[权限管理颁发者/权限管理所有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)或[超级用户](https://docs.microsoft.com/azure/information-protection/configure-super-users)角色。</span><span class="sxs-lookup"><span data-stu-id="033bd-164">The role of [Rights Management issuer or Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner), or [super user](https://docs.microsoft.com/azure/information-protection/configure-super-users).</span></span>

<span data-ttu-id="033bd-165">如果用户没有上述权限或角色之一，则无法应用标签，因此原有加密将保留。</span><span class="sxs-lookup"><span data-stu-id="033bd-165">If the user doesn't have one of these rights or roles, the label can't be applied and so the original encryption is preserved.</span></span> <span data-ttu-id="033bd-166">用户会看到以下消息：**你无权对敏感度标签进行此更改。请联系内容所有者。**</span><span class="sxs-lookup"><span data-stu-id="033bd-166">The user sees the following message: **You don't have permission to make this change to the sensitivity label. Please contact the content owner.**</span></span>

<span data-ttu-id="033bd-167">例如，向电子邮件应用“请勿转发”标签的用户可重新标记会话，以替换或删除加密，因为他们是该电子邮件的权限管理所有者。</span><span class="sxs-lookup"><span data-stu-id="033bd-167">For example, the person who applies Do Not Forward to an email message can relabel the thread to replace the encryption or remove it, because they are the Rights Management owner for the email.</span></span> <span data-ttu-id="033bd-168">但除了超级用户外，此电子邮件的收件人无法对其重新标记，因为他们没有必需的使用权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-168">But with the exception of super users, recipients of this email can't relabel it because they don't have the required usage rights.</span></span>

#### <a name="email-attachments-for-encrypted-email-messages"></a><span data-ttu-id="033bd-169">加密电子邮件的电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="033bd-169">Email attachments for encrypted email messages</span></span>

<span data-ttu-id="033bd-170">通过任何方式加密电子邮件时，附加到该电子邮件的所有未加密的 Office 文档都将自动继承相同的加密设置。</span><span class="sxs-lookup"><span data-stu-id="033bd-170">When an email message is encrypted by any method, any unencrypted Office documents that are attached to the email automatically inherit the same encryption settings.</span></span>

<span data-ttu-id="033bd-171">已加密且随后添加为附件的文档始终保留其原有加密。</span><span class="sxs-lookup"><span data-stu-id="033bd-171">Documents that are already encrypted and then added as attachments always preserve their original encryption.</span></span> 

## <a name="configure-encryption-settings"></a><span data-ttu-id="033bd-172">配置加密设置</span><span class="sxs-lookup"><span data-stu-id="033bd-172">Configure encryption settings</span></span>

<span data-ttu-id="033bd-173">在向导的“**加密**”页面上选择“**应用**”来创建或编辑敏感度标签时，选择是否要：</span><span class="sxs-lookup"><span data-stu-id="033bd-173">When you select **Apply** on the **Encryption** page of the wizard to create or edit a sensitivity label, choose whether to:</span></span>

- <span data-ttu-id="033bd-174">**立即分配权限**，以便可准确确定哪些用户对已应用标签的内容具有哪些权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-174">**Assign permissions now**, so that you can determine exactly which users get which permissions to content that has the label applied.</span></span> <span data-ttu-id="033bd-175">有关详细信息，请参阅下一部分：[立即分配权限](#assign-permissions-now)。</span><span class="sxs-lookup"><span data-stu-id="033bd-175">For more information, see the next section [Assign permissions now](#assign-permissions-now).</span></span>
- <span data-ttu-id="033bd-176">在用户向内容应用标签时**允许用户分配权限**。</span><span class="sxs-lookup"><span data-stu-id="033bd-176">**Let users assign permissions** when your users apply the label to content.</span></span> <span data-ttu-id="033bd-177">通过此选项，可使组织内部人员在协作处理和完成任务时具有一定程度可能需要的灵活性。</span><span class="sxs-lookup"><span data-stu-id="033bd-177">With this option, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="033bd-178">有关详细信息，请参阅下述部分：[允许用户分配权限](#let-users-assign-permissions)。</span><span class="sxs-lookup"><span data-stu-id="033bd-178">For more information, see the [Let users assign permissions](#let-users-assign-permissions) section on this page.</span></span>

<span data-ttu-id="033bd-179">例如，如果你有一个名为“**高度机密**”的敏感度标签，它将应用于你的大部分敏感内容，则你可能需要决定谁对该内容获得哪种类型的权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-179">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you might want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="033bd-180">或者，如果你有一个名为“**商业合同**”的敏感度标签，而你所在组织的工作流要员工临时与不同人员协作处理此内容，则你可能需要允许用户在分配此标签时决定由谁获得权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-180">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you might want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="033bd-181">这种灵活性都能帮助你的用户保持高效，同时减少管理员要更新或新建敏感度标签来应对特定场景的请求。</span><span class="sxs-lookup"><span data-stu-id="033bd-181">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

<span data-ttu-id="033bd-182">选择是要立即分配权限还是允许用户分配权限：</span><span class="sxs-lookup"><span data-stu-id="033bd-182">Choosing whether to assign permissions now or let users assign permissions:</span></span> 

![用于添加用户或管理员定义的权限的选项](../media/sensitivity-label-user-or-admin-defined-permissions.png)


## <a name="assign-permissions-now"></a><span data-ttu-id="033bd-184">立即分配权限</span><span class="sxs-lookup"><span data-stu-id="033bd-184">Assign permissions now</span></span>

<span data-ttu-id="033bd-185">使用下述选项来控制哪些人员可访问应用了此标签的电子邮件或文档。</span><span class="sxs-lookup"><span data-stu-id="033bd-185">Use the following options to control who can access email or documents to which this label is applied.</span></span> <span data-ttu-id="033bd-186">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="033bd-186">You can:</span></span>

- <span data-ttu-id="033bd-p116">**允许对标记的内容的访问权限过期**（在某个特定日期或在应用标签后的特定天数后）。在此时间后，用户将无法打开标记的项。如果指定某个日期，则它将于该日期午夜（在你的当前时区）生效。请注意，某些电子邮件客户端由于其缓存机制，可能不强制过期，仍显示过期的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-p116">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won't be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients might not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>

- <span data-ttu-id="033bd-p117">**允许脱机访问**（从不、始终或在应用标签后的特定天后）。如果将脱机访问限制为从不或一定天数，则当达到该阈值时，必须对用户重新进行身份验证并记录其访问。有关详细信息，请参阅下一部分有关 Rights Management 使用许可证的内容。</span><span class="sxs-lookup"><span data-stu-id="033bd-p117">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

<span data-ttu-id="033bd-194">加密内容的访问控制设置：</span><span class="sxs-lookup"><span data-stu-id="033bd-194">Settings for access control for encrypted content:</span></span>

![有关管理员定义的权限的设置](../media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="033bd-196">针对脱机访问的 Rights Management 使用许可证</span><span class="sxs-lookup"><span data-stu-id="033bd-196">Rights Management use license for offline access</span></span>

<span data-ttu-id="033bd-197">当用户打开受 Azure 权限管理服务加密保护的文档或电子邮件时，将向该用户授予对该内容的 Azure 权限管理使用许可证。</span><span class="sxs-lookup"><span data-stu-id="033bd-197">When a user opens a document or email that's been protected by encryption from the Azure Rights Management service, an Azure Rights Management use license for that content is granted to the user.</span></span> <span data-ttu-id="033bd-198">此使用许可证是一种证书，其中包含用户对文档或电子邮件的使用权限，以及用于加密内容的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="033bd-198">This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content.</span></span> <span data-ttu-id="033bd-199">此使用许可证还包含过期日期（若已设置）及其有效时长。</span><span class="sxs-lookup"><span data-stu-id="033bd-199">The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="033bd-p119">如果尚未设置任何到期日期，则针对租户的默认使用许可证有效期为 30 天。在使用许可证有效期内，无需就内容对用户重新进行身份验证或授权。这使用户无需具有 Internet 连接即可继续打开受保护的文档或电子邮件。当用户许可有效期到期后，在用户下次访问受保护的文档或电子邮件时，必须对用户重新进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="033bd-p119">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This process lets the user continue to open the protected document or email without an internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="033bd-204">除重新进行身份验证以外，还将重新评估策略和用户组成员身份。</span><span class="sxs-lookup"><span data-stu-id="033bd-204">In addition to reauthentication, the encryption settings and user group membership is reevaluated.</span></span> <span data-ttu-id="033bd-205">这意味着，如果自他们最后一次访问内容时在加密设置或组成员身份中出现更改，则对于同一文档或电子邮件，他们可能会收到不同的访问结果。</span><span class="sxs-lookup"><span data-stu-id="033bd-205">This means that users could experience different access results for the same document or email if there are changes in the encryption settings or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="033bd-206">若要了解如何更改默认的 30 天设置，请参阅 [Rights Management 使用许可证](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license)。</span><span class="sxs-lookup"><span data-stu-id="033bd-206">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="033bd-207">向特定用户或组分配权限</span><span class="sxs-lookup"><span data-stu-id="033bd-207">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="033bd-208">可向特定人员授予权限，只允许这些人员与标记的内容进行交互：</span><span class="sxs-lookup"><span data-stu-id="033bd-208">You can grant permissions to specific people so that only they can interact with the labeled content:</span></span>

1. <span data-ttu-id="033bd-209">首先，添加将向其分配对标记的内容具有访问权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="033bd-209">First, add users or groups that will be assigned permissions to the labeled content.</span></span>

2. <span data-ttu-id="033bd-210">然后，选择这些用户应对标记的内容具有的权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-210">Then, choose which permissions those users should have for the labeled content.</span></span>

<span data-ttu-id="033bd-211">分配权限：</span><span class="sxs-lookup"><span data-stu-id="033bd-211">Assigning permissions:</span></span>

![向用户分配权限的选项](../media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="033bd-213">添加用户或组</span><span class="sxs-lookup"><span data-stu-id="033bd-213">Add users or groups</span></span>

<span data-ttu-id="033bd-214">分配权限时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="033bd-214">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="033bd-p121">组织中的任何人（所有租户成员）。此设置不包括来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="033bd-p121">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>

- <span data-ttu-id="033bd-217">所有经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="033bd-217">Any authenticated users.</span></span> <span data-ttu-id="033bd-218">选择前，请确保你了解此设置的相关[要求和限制](#requirements-and-limitations-for-add-any-authenticated-users)。</span><span class="sxs-lookup"><span data-stu-id="033bd-218">Make sure you understand the [requirements and limitations](#requirements-and-limitations-for-add-any-authenticated-users) of this setting before selecting it.</span></span>

- <span data-ttu-id="033bd-219">Azure AD 中的任何特定用户或启用了电子邮件的安全组、通讯组、或 Microsoft 365 组（[旧称为“Office 365 组”](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)）。</span><span class="sxs-lookup"><span data-stu-id="033bd-219">Any specific user or email-enabled security group, distribution group, or Microsoft 365 group ([formerly Office 365 group](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) in Azure AD.</span></span> <span data-ttu-id="033bd-220">Microsoft 365 组可以有静态或[动态成员资格](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)。</span><span class="sxs-lookup"><span data-stu-id="033bd-220">The Microsoft 365 group can have static or [dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="033bd-221">请注意，不能使用[来自 Exchange 的动态通讯组](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups?view=exchserver-2019)，因为此组类型不会同步到 Azure AD，并且不能使用未启用电子邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="033bd-221">Note that you can't use a [dynamic distribution group from Exchange](https://docs.microsoft.com/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups?view=exchserver-2019) because this group type isn't synchronized to Azure AD, and you can't use a security group that isn't email-enabled.</span></span>

- <span data-ttu-id="033bd-222">任何电子邮件地址或域。</span><span class="sxs-lookup"><span data-stu-id="033bd-222">Any email address or domain.</span></span> <span data-ttu-id="033bd-223">借助此选项，通过输入 Azure AD 使用的另一组织中的任何域名，指定该组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="033bd-223">Use this option to specify all users in another organization who uses Azure AD, by entering any domain name from that organization.</span></span> <span data-ttu-id="033bd-224">你可使用此选项处理社交提供商，方式是输入其域名，例如 **gmail.com**、**hotmail.com**或 **outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="033bd-224">You can also use this option for social providers, by entering their domain name such as **gmail.com**, **hotmail.com**, or **outlook.com**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="033bd-225">如果从使用 Azure AD 的组织中指定一个域，则无法将访问权限局限于该特定域。</span><span class="sxs-lookup"><span data-stu-id="033bd-225">If you specify a domain from an organization that uses Azure AD, you can't restrict access to that specific domain.</span></span> <span data-ttu-id="033bd-226">转而对于拥有你指定的域名的租户来说，会自动包含 Azure AD 中已经过验证的所有域。</span><span class="sxs-lookup"><span data-stu-id="033bd-226">Instead, all verified domains in Azure AD are automatically included for the tenant that owns the domain name you specify.</span></span>

<span data-ttu-id="033bd-227">选择组织中的所有用户和组或浏览目录时，这些用户或组必须具有电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="033bd-227">When you choose all users and groups in your organization or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="033bd-p126">最佳做法是使用组，而不是使用用户。此策略可使你的配置更为简单。</span><span class="sxs-lookup"><span data-stu-id="033bd-p126">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

##### <a name="requirements-and-limitations-for-add-any-authenticated-users"></a><span data-ttu-id="033bd-230">有关**添加任何经过身份验证的用户**的要求和限制</span><span class="sxs-lookup"><span data-stu-id="033bd-230">Requirements and limitations for **Add any authenticated users**</span></span>

<span data-ttu-id="033bd-231">此设置不会限制谁可访问标签加密的内容，但仍会加密内容并向你提供用来限制内容使用方式（权限）和访问方式（过期和脱机访问）的选项。</span><span class="sxs-lookup"><span data-stu-id="033bd-231">This setting doesn't restrict who can access the content that the label encrypts, while still encrypting the content and providing you with options to restrict how the content can be used (permissions), and accessed (expiry and offline access).</span></span> <span data-ttu-id="033bd-232">但是，打开加密内容的应用程序必须能够支持正在使用的身份验证。</span><span class="sxs-lookup"><span data-stu-id="033bd-232">However, the application opening the encrypted content must be able to support the authentication being used.</span></span> <span data-ttu-id="033bd-233">由此，联合社交提供商（如 Google）和一次性密码身份验证仅适用于电子邮件，且仅在你使用 Exchange Online 时才适用。</span><span class="sxs-lookup"><span data-stu-id="033bd-233">For this reason, federated social providers such as Google, and onetime passcode authentication work for email only, and only when you use Exchange Online.</span></span> <span data-ttu-id="033bd-234">Microsoft 帐户可与 Office 365 应用和 [Azure 信息保护查看器](https://portal.azurerms.com/#/download)一起使用。</span><span class="sxs-lookup"><span data-stu-id="033bd-234">Microsoft accounts can be used with Office 365 apps and the [Azure Information Protection viewer](https://portal.azurerms.com/#/download).</span></span>

<span data-ttu-id="033bd-235">“所有经过身份验证的用户”设置的一些典型场景：</span><span class="sxs-lookup"><span data-stu-id="033bd-235">Some typical scenarios for the any authenticated users setting:</span></span>
- <span data-ttu-id="033bd-236">你不在乎谁会查看内容，但你想要限制内容使用方式。</span><span class="sxs-lookup"><span data-stu-id="033bd-236">You don't mind who views the content, but you want to restrict how it is used.</span></span> <span data-ttu-id="033bd-237">例如，你不希望内容遭到编辑、复制或打印。</span><span class="sxs-lookup"><span data-stu-id="033bd-237">For example, you don't want the content to be edited, copied, or printed.</span></span>
- <span data-ttu-id="033bd-238">你不需要限制谁有权访问内容，但你想要能够确定谁可打开内容。</span><span class="sxs-lookup"><span data-stu-id="033bd-238">You don't need to restrict who accesses the content, but you want to be able to confirm who opens it.</span></span>
- <span data-ttu-id="033bd-239">你要求内容必须在静态和传输中经过加密，但不要求访问权限控制。</span><span class="sxs-lookup"><span data-stu-id="033bd-239">You have a requirement that the content must be encrypted at rest and in transit, but it doesn't require access controls.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="033bd-240">选择权限</span><span class="sxs-lookup"><span data-stu-id="033bd-240">Choose permissions</span></span>

<span data-ttu-id="033bd-241">选择允许为这些用户或组使用哪些权限时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="033bd-241">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="033bd-242">具有预设权限组的[预定义权限级别](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，例如共同创作或审阅者。</span><span class="sxs-lookup"><span data-stu-id="033bd-242">A [predefined permissions level](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="033bd-243">自定义权限，可在其中选择一个或多个使用权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-243">Custom permissions, where you choose one or more usage rights.</span></span>

<span data-ttu-id="033bd-244">有关帮助你选择适当权限的详细信息，请参阅[使用权限和说明](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="033bd-244">For more information to help you select the appropriate permissions, see [Usage rights and descriptions](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![选择预设权限或自定义权限的选项。](../media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="033bd-p129">请注意，同一标签可向不同用户授予不同的权限。例如，一个标签可将某些用户分配为审阅者，并可将其他用户分配为共同创作，如下所示。</span><span class="sxs-lookup"><span data-stu-id="033bd-p129">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown in the following screenshot.</span></span>

<span data-ttu-id="033bd-p130">为此，添加用户或组、向其分配权限并保存这些设置。然后重复这些步骤，添加用户并向其分配权限、每次保存设置。可以根据需要经常重复此配置，以便为不同用户定义不同权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-p130">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can repeat this configuration as often as necessary, to define different permissions for different users.</span></span>

![具有不同权限的不同用户](../media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="033bd-252">Rights Management 颁发者（应用敏感度标签的用户）始终具有完全控制</span><span class="sxs-lookup"><span data-stu-id="033bd-252">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="033bd-253">敏感度标签加密使用了 Azure 信息保护中的 Azure 权限管理服务。</span><span class="sxs-lookup"><span data-stu-id="033bd-253">Encryption for a sensitivity label uses the Azure Rights Management service from Azure Information Protection.</span></span> <span data-ttu-id="033bd-254">当用户通过加密应用敏感度标签来保护文档或电子邮件时，该用户就成为了该内容的权限管理颁发者。</span><span class="sxs-lookup"><span data-stu-id="033bd-254">When a user applies a sensitivity label to protect a document or email by using encryption, that user becomes the Rights Management issuer for that content.</span></span>

<span data-ttu-id="033bd-255">权限管理颁发者始终具有对文档或电子邮件的完全控制权限；此外：</span><span class="sxs-lookup"><span data-stu-id="033bd-255">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="033bd-256">如果加密设置包含过期日期，权限管理颁发者在该日期后仍可打开和编辑文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-256">If the encryption settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="033bd-257">Rights Management 颁发者可以始终在脱机状态下访问文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-257">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="033bd-258">在文档被撤销后，Rights Management 颁发者仍然可以打开该文档。</span><span class="sxs-lookup"><span data-stu-id="033bd-258">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="033bd-259">有关详细信息，请参阅 [Rights Management 颁发者和 Rights Management 所有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。</span><span class="sxs-lookup"><span data-stu-id="033bd-259">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

### <a name="double-key-encryption"></a><span data-ttu-id="033bd-260">双密钥加密</span><span class="sxs-lookup"><span data-stu-id="033bd-260">Double Key Encryption</span></span>

> [!NOTE]
> <span data-ttu-id="033bd-261">此功能目前在公共预览版中推出。</span><span class="sxs-lookup"><span data-stu-id="033bd-261">This feature is currently rolling out in public preview.</span></span> <span data-ttu-id="033bd-262">有关详细信息，请参阅[公布 Microsoft 365 双密钥加密的公共预览版](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-public-preview-of-double-key-encryption-for-microsoft/ba-p/1534451)。</span><span class="sxs-lookup"><span data-stu-id="033bd-262">For more information, see [Announcing public preview of Double Key Encryption for Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-public-preview-of-double-key-encryption-for-microsoft/ba-p/1534451).</span></span>

<span data-ttu-id="033bd-263">只有配置了双密钥加密服务，并且需要为应用了此标签的文档和电子邮件使用此双密钥加密后，才可选择此选项。</span><span class="sxs-lookup"><span data-stu-id="033bd-263">Select this option only after you have configured the Double Key Encryption service and you need to use this double key encryption for the documents and emails that will have this label applied.</span></span>

<span data-ttu-id="033bd-264">了解更多信息、先决条件、以及配置说明，请参阅[双密钥加密 (DKE)](double-key-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="033bd-264">For more information, prerequisites, and configuration instructions, see [Double Key Encryption (DKE)](double-key-encryption.md).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="033bd-265">允许用户分配权限</span><span class="sxs-lookup"><span data-stu-id="033bd-265">Let users assign permissions</span></span>

<span data-ttu-id="033bd-266">可使用下述选项来允许用户在向内容手动应用敏感度标签时分配权限：</span><span class="sxs-lookup"><span data-stu-id="033bd-266">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="033bd-267">在 Outlook 中，用户可为其所选收件人选择与“[请勿转发](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails)”选项等效的限制。</span><span class="sxs-lookup"><span data-stu-id="033bd-267">In Outlook, a user can select restrictions equivalent to the [Do Not Forward](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) option for their chosen recipients.</span></span>

- <span data-ttu-id="033bd-268">在 Word、PowerPoint 和 Excel 中，系统会提示用户为特定用户、组或组织选择他们自己的权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-268">In Word, PowerPoint, and Excel, a user is prompted to select their own permissions for specific users, groups, or organizations.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="033bd-269">Azure 信息保护统一标记客户端支持对 Word、PowerPoint 和 Excel 使用此选项。</span><span class="sxs-lookup"><span data-stu-id="033bd-269">This option for Word, PowerPoint, and Excel is supported by the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="033bd-270">对于使用内置标记的应用，[检查哪些应用支持它](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)。</span><span class="sxs-lookup"><span data-stu-id="033bd-270">For apps that use built-in labeling, [check which apps support it](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint).</span></span>
    > 
    > <span data-ttu-id="033bd-271">如果已选中此选项，但用户的应用不支持这一选项，则该标签不会向用户显示，或者会显示标签以确保一致性，但无法随说明消息一起应用到用户。</span><span class="sxs-lookup"><span data-stu-id="033bd-271">If this option is selected but isn't supported for a user's app, either that label doesn't display to the user, or the label displays for consistency, but it can't be applied with an explanation message to users.</span></span>

<span data-ttu-id="033bd-272">在这些选择受到支持时，请使用以下标签确定用户何时回看到敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="033bd-272">When the options are supported, use the following table to identify when users see the sensitivity label:</span></span>

|<span data-ttu-id="033bd-273">设置</span><span class="sxs-lookup"><span data-stu-id="033bd-273">Setting</span></span> |<span data-ttu-id="033bd-274">标签在 Outlook 中可见</span><span class="sxs-lookup"><span data-stu-id="033bd-274">Label visible in Outlook</span></span>|<span data-ttu-id="033bd-275">标签在 Word、Excel 和 PowerPoint 中可见</span><span class="sxs-lookup"><span data-stu-id="033bd-275">Label visible in Word, Excel, PowerPoint</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="033bd-276">**在 Outlook 中，强制实施与“请勿转发”选项等效的限制**</span><span class="sxs-lookup"><span data-stu-id="033bd-276">**In Outlook, enforce restrictions equivalent to the Do Not Forward option**</span></span>|<span data-ttu-id="033bd-277">是</span><span class="sxs-lookup"><span data-stu-id="033bd-277">Yes</span></span> |<span data-ttu-id="033bd-278">否</span><span class="sxs-lookup"><span data-stu-id="033bd-278">No</span></span> |
|<span data-ttu-id="033bd-279">**在 Word、PowerPoint 和 Excel 中提示用户指定权限**</span><span class="sxs-lookup"><span data-stu-id="033bd-279">**In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>|<span data-ttu-id="033bd-280">否</span><span class="sxs-lookup"><span data-stu-id="033bd-280">No</span></span> |<span data-ttu-id="033bd-281">是</span><span class="sxs-lookup"><span data-stu-id="033bd-281">Yes</span></span>|

<span data-ttu-id="033bd-282">同时选中这两个选项时，标签在 Outlook 和 Word、Exce、PowerPoint 中都可见。</span><span class="sxs-lookup"><span data-stu-id="033bd-282">When both settings are selected, the label is therefore visible in both Outlook and in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="033bd-283">允许用户分配权限的敏感度标签仅可由用户手动应用于内容；它不能自动应用，也不能用作建议的标签。</span><span class="sxs-lookup"><span data-stu-id="033bd-283">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

<span data-ttu-id="033bd-284">配置用户分配的权限：</span><span class="sxs-lookup"><span data-stu-id="033bd-284">Configuring the user-assigned permissions:</span></span>

![有关用户定义的权限的加密设置](../media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="033bd-286">Outlook 限制</span><span class="sxs-lookup"><span data-stu-id="033bd-286">Outlook restrictions</span></span>

<span data-ttu-id="033bd-287">在 Outlook 中，当用户向邮件应用允许其分配权限的敏感度标签时，需遵守的限制与“请勿转发”选项相同。</span><span class="sxs-lookup"><span data-stu-id="033bd-287">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="033bd-288">用户将在邮件顶部看到标签名称和说明，这表示正在保护该内容。</span><span class="sxs-lookup"><span data-stu-id="033bd-288">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="033bd-289">与 Word、PowerPoint 和 Excel 不同（详见[下一部分](#word-powerpoint-and-excel-permissions)），系统不会提示用户选择特定权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-289">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![应用于 Outlook 中的邮件的敏感度标签](../media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="033bd-291">向电子邮件应用“请勿转发”选项时，电子邮件将被加密，且收件人必须通过身份验证。</span><span class="sxs-lookup"><span data-stu-id="033bd-291">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="033bd-292">其次，收件人不得转发、打印和复制该邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-292">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="033bd-293">例如，在 Outlook 客户端中，“转发”按钮不可用，“另存为”和“打印”菜单选项也不可用，并且你不可在“收件人”、“抄送”和“密件抄送”框中添加或更改收件人。</span><span class="sxs-lookup"><span data-stu-id="033bd-293">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="033bd-294">自动附加到电子邮件但未加密的 Office 文档会自动继承相同的限制。</span><span class="sxs-lookup"><span data-stu-id="033bd-294">Unencrypted Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="033bd-295">应用于这些文档的使用权限为“编辑内容”、“编辑”，“保存”，“视图”、“打开”、“阅读”，以及“允许宏”。</span><span class="sxs-lookup"><span data-stu-id="033bd-295">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="033bd-296">如果用户对附件实施其他使用权限，或者附件并非支持该继承权限的 Office 文档，则用户需要在将文件附加到电子邮件之前保护该文件。</span><span class="sxs-lookup"><span data-stu-id="033bd-296">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="033bd-297">Word、PowerPoint 和 Excel 权限</span><span class="sxs-lookup"><span data-stu-id="033bd-297">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="033bd-298">在 Word、PowerPoint 和 Excel 中，当用户向文档应用允许其分配权限的敏感度标签时，系统会提示他们在应用加密时指定其对用户和权限的选择。</span><span class="sxs-lookup"><span data-stu-id="033bd-298">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to specify their choice of users and permissions when the encryption is applied.</span></span>

<span data-ttu-id="033bd-299">例如，用户可通过 Azure 信息保护统一标记客户端：</span><span class="sxs-lookup"><span data-stu-id="033bd-299">For example, with the Azure Information Protection unified labeling client, users can:</span></span>

- <span data-ttu-id="033bd-300">选择权限级别，例如查看者（可分配“仅查看”权限）或合著者（可分配“查看”、“编辑”、“复制”和“打印”权限）。</span><span class="sxs-lookup"><span data-stu-id="033bd-300">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="033bd-301">选择用户、组或组织。</span><span class="sxs-lookup"><span data-stu-id="033bd-301">Select users, groups, or organizations.</span></span> <span data-ttu-id="033bd-302">这可包括你所在组织内部或外部的人员。</span><span class="sxs-lookup"><span data-stu-id="033bd-302">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="033bd-303">设置到期日期，所选用户在该日期后不可访问内容。</span><span class="sxs-lookup"><span data-stu-id="033bd-303">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="033bd-304">有关详细信息，请参阅上一部分：[针对脱机访问的 Rights Management 使用许可证](#rights-management-use-license-for-offline-access)。</span><span class="sxs-lookup"><span data-stu-id="033bd-304">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![供用户通过自定义权限进行保护的选项](../media/sensitivity-aip-custom-permissions-dialog.png)

<span data-ttu-id="033bd-306">对于内置标签，用户在选择以下项时也会看到此对话框：</span><span class="sxs-lookup"><span data-stu-id="033bd-306">For built-in labeling, users see the same dialog box if they select the following:</span></span>

- <span data-ttu-id="033bd-307">Windows：“**文件**”选项卡 >“**信息**” > “**保护文档**” > “**限制访问**” > “**受限访问**”</span><span class="sxs-lookup"><span data-stu-id="033bd-307">Windows: **File** tab > **Info** > **Protect Document** > **Restrict Access** > **Restricted Access**</span></span>

- <span data-ttu-id="033bd-308">MacOS：“**查看**”选项卡 >“**保护**” > “**权限**” > “**受限访问**”</span><span class="sxs-lookup"><span data-stu-id="033bd-308">MacOS: **Review** tab > **Protection** > **Permissions** > **Restricted Access**</span></span>


## <a name="example-configurations-for-the-encryption-settings"></a><span data-ttu-id="033bd-309">加密设置的配置示例</span><span class="sxs-lookup"><span data-stu-id="033bd-309">Example configurations for the encryption settings</span></span>

<span data-ttu-id="033bd-310">对于后面的每个示例，请在[创建或编辑敏感度标签](create-sensitivity-labels.md#create-and-configure-sensitivity-labels)时通过“**加密**”页面进行配置。</span><span class="sxs-lookup"><span data-stu-id="033bd-310">For each example that follows, do the configuration from the **Encryption** page of the wizard when you [create or edit a sensitivity label](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span> <span data-ttu-id="033bd-311">首先，请确保“**加密**”设置为“**应用**”：</span><span class="sxs-lookup"><span data-stu-id="033bd-311">First make sure that the **Encryption** is set to **Apply**:</span></span>

![应用敏感度标签向导中的加密选项](../media/apply-encryption-option.png)

### <a name="example-1-label-that-applies-do-not-forward-to-send-an-encrypted-email-to-a-gmail-account"></a><span data-ttu-id="033bd-313">示例 1：应用“请勿转发”以将加密的电子邮件发送至 Gmail 帐户的标签</span><span class="sxs-lookup"><span data-stu-id="033bd-313">Example 1: Label that applies Do Not Forward to send an encrypted email to a Gmail account</span></span>

<span data-ttu-id="033bd-314">此标签仅显示 Outlook 和 Outlook 网页版，且你必须使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="033bd-314">This label displays only in Outlook and Outlook on the web, and you must use Exchange Online.</span></span> <span data-ttu-id="033bd-315">在用户需要向使用 Gmail 帐户（或你组织外部的任何其他电子邮件帐户）的人员发送加密电子邮件时，指示这些用户选择此标签。</span><span class="sxs-lookup"><span data-stu-id="033bd-315">Instruct users to select this label when they need to send an encrypted email to people using a Gmail account (or any other email account outside your organization).</span></span> 

<span data-ttu-id="033bd-316">用户需在“**收件人**”框中键入 Gmail 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="033bd-316">Your users type the Gmail email address in the **To** box.</span></span>  <span data-ttu-id="033bd-317">然后选中该标签，“请勿转发”选项会自动添加到电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="033bd-317">Then, they select the label and the Do Not Forward option is automatically added to the email.</span></span> <span data-ttu-id="033bd-318">这样的话，收件人就无法转发、打印或复制该电子邮件，也不能使用“**另存为**”选项在其邮箱之外保存该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-318">The result is that recipients cannot forward the email, or print it, copy from it, or save the email outside their mailbox by using the **Save As** option.</span></span> 

1. <span data-ttu-id="033bd-319">在“**加密**”页面上：对于“**立即分配权限还是让用户决定?**”，选择“**允许用户在应用标签时自行分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-319">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Let users assign permissions when they apply the label**.</span></span>

3. <span data-ttu-id="033bd-320">选择复选框：**在 Outlook 中，强制实施与“请勿转发”选项等效的限制**。</span><span class="sxs-lookup"><span data-stu-id="033bd-320">Select the checkbox: **In Outlook, enforce restrictions equivalent to the Do Not Forward option**.</span></span>

4. <span data-ttu-id="033bd-321">如果选中，请清除复选框：**在 Word、PowerPoint 和 Excel 中提示用户指定权限**。</span><span class="sxs-lookup"><span data-stu-id="033bd-321">If selected, clear the checkbox: **In Word, PowerPoint, and Excel, prompt users to specify permissions**.</span></span>

5. <span data-ttu-id="033bd-322">选择“**下一步**”并完成向导。</span><span class="sxs-lookup"><span data-stu-id="033bd-322">Select **Next** and complete the wizard.</span></span>


### <a name="example-2-label-that-restricts-read-only-permission-to-all-users-in-another-organization"></a><span data-ttu-id="033bd-323">示例 2：将只读权限局限于另一组织中的所有用户的标签</span><span class="sxs-lookup"><span data-stu-id="033bd-323">Example 2: Label that restricts read-only permission to all users in another organization</span></span>

<span data-ttu-id="033bd-324">此标签适用于以只读形式共享非常敏感的文档，文档始终需要 Internet 连接才能查看。</span><span class="sxs-lookup"><span data-stu-id="033bd-324">This label is suitable for sharing very sensitive documents as read-only, and the documents always require an internet connection to view them.</span></span>

<span data-ttu-id="033bd-325">此标签不适用于电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-325">This label is not suitable for emails.</span></span>

1. <span data-ttu-id="033bd-326">在“**加密**”页面上：对于“**立即分配权限还是让用户决定?**”，选择“**立即分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-326">On the **Encryption** page: For **Assign permissions now or let users decide?** select **Assign permissions now**.</span></span>

3. <span data-ttu-id="033bd-327">对于“**允许脱机访问**”，选择“**从不**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-327">For **Allow offline access**, select **Never**.</span></span>

4. <span data-ttu-id="033bd-328">选择“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-328">Select **Assign permissions**.</span></span>

3. <span data-ttu-id="033bd-329">在“**分配权限**”窗格上，选择“**添加特定电子邮件地址或域**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-329">On the **Assign permissions** pane, select **Add specific email addresses or domains**.</span></span>

4. <span data-ttu-id="033bd-330">在文本框中，输入另一组织中的域的名称，例如 **fabrikam.com**。</span><span class="sxs-lookup"><span data-stu-id="033bd-330">In the text box, enter the name of a domain from the other organization, for example, **fabrikam.com**.</span></span> <span data-ttu-id="033bd-331">然后，选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-331">Then select **Add**.</span></span>

5. <span data-ttu-id="033bd-332">选择“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-332">Select **Choose permissions**.</span></span>

6. <span data-ttu-id="033bd-333">在“**选择权限**”窗格中，选择下拉框，选择“**查看者**”，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-333">On the **Choose permissions** pane, select the dropdown box, select **Viewer**, and then select **Save**.</span></span>

6. <span data-ttu-id="033bd-334">返回到“**分配权限**”窗格中，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-334">Back on the **Assign Permissions** pane, select **Save**.</span></span>

7. <span data-ttu-id="033bd-335">在“**加密**”窗格上，选择“**下一步**”并完成向导。</span><span class="sxs-lookup"><span data-stu-id="033bd-335">On the **Encryption** page, select **Next** and complete the wizard.</span></span>


### <a name="example-3-add-external-users-to-an-existing-label-that-encrypts-content"></a><span data-ttu-id="033bd-336">示例 3：将外部用户添加到加密内容的现有标签</span><span class="sxs-lookup"><span data-stu-id="033bd-336">Example 3: Add external users to an existing label that encrypts content</span></span>

<span data-ttu-id="033bd-337">添加的新用户将能够打开已使用此标签保护的文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-337">The new users that you add will be able open documents and emails that have already been protected with this label.</span></span> <span data-ttu-id="033bd-338">授予这些用户的权限可能与现有用户拥有的权限不同。</span><span class="sxs-lookup"><span data-stu-id="033bd-338">The permissions that you grant these users can be different from the permissions that the existing users have.</span></span>

1. <span data-ttu-id="033bd-339">在“**加密**”页面上：对于“**立即分配权限还是让用户决定?**”，确保选中“**立即分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-339">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="033bd-340">选择“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-340">Select **Assign permissions**.</span></span>

3. <span data-ttu-id="033bd-341">在“**分配权限**”窗格上，选择“**添加特定电子邮件地址或域**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-341">On the **Assign permissions** pane, select **Add specific email addresses or domains**.</span></span>

4. <span data-ttu-id="033bd-342">在文本框中，输入要添加的第一名用户（或组）的电子邮件地址，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-342">In the text box, enter the email address of the first user (or group) to add, and then select **Add**.</span></span>

5. <span data-ttu-id="033bd-343">选择“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-343">Select **Choose permissions**.</span></span>

6. <span data-ttu-id="033bd-344">在“**选择权限**”窗格中，选择此用户（或组）的权限，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-344">On the **Choose permissions** pane, select the permissions for this user (or group), and then select **Save**.</span></span>

7. <span data-ttu-id="033bd-345">返回到“**分配权限**”窗格，对要添加到此标签的每位用户（或组）重复步骤 3 到步骤 6。</span><span class="sxs-lookup"><span data-stu-id="033bd-345">Back on the **Assign Permissions** pane, repeat steps 3 through 6 for each user (or group) that you want to add to this label.</span></span> <span data-ttu-id="033bd-346">然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-346">Then click **Save**.</span></span>

8. <span data-ttu-id="033bd-347">在“**加密**”窗格上，选择“**下一步**”并完成向导。</span><span class="sxs-lookup"><span data-stu-id="033bd-347">On the **Encryption** page, select **Next** and complete the wizard.</span></span>


### <a name="example-4-label-that-encrypts-content-but-doesnt-restrict-who-can-access-it"></a><span data-ttu-id="033bd-348">示例 4：对内容进行加密但不限制可访问的人员的标签</span><span class="sxs-lookup"><span data-stu-id="033bd-348">Example 4: Label that encrypts content but doesn't restrict who can access it</span></span>

<span data-ttu-id="033bd-349">此配置的优势在于，你无需指定用户、组或域即可加密电子邮件或文档。</span><span class="sxs-lookup"><span data-stu-id="033bd-349">This configuration has the advantage that you don't need to specify users, groups, or domains to encrypt an email or document.</span></span> <span data-ttu-id="033bd-350">内容仍将被加密，但你仍可指定使用权限、过期日期和脱机访问权限。</span><span class="sxs-lookup"><span data-stu-id="033bd-350">The content will still be encrypted and you can still specify usage rights, an expiry date, and offline access.</span></span> 

<span data-ttu-id="033bd-351">仅在无需限制谁可打开受保护的文档或电子邮件时才使用此配置。</span><span class="sxs-lookup"><span data-stu-id="033bd-351">Use this configuration only when you do not need to restrict who can open the protected document or email.</span></span> [<span data-ttu-id="033bd-352">有关此设置的详细信息</span><span class="sxs-lookup"><span data-stu-id="033bd-352">More information about this setting</span></span>](#requirements-and-limitations-for-add-any-authenticated-users)

1. <span data-ttu-id="033bd-353">在“**加密**”页面上：对于“**立即分配权限还是让用户决定?**”，确保选中“**立即分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-353">On the **Encryption** page: For **Assign permissions now or let users decide?** make sure **Assign permissions now** is selected.</span></span>

2. <span data-ttu-id="033bd-354">根据需要配置“**用户访问内容的权限过期**”和“**允许脱机访问**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-354">Configure settings for **User access to content expires** and **Allow offline access** as required.</span></span>

3. <span data-ttu-id="033bd-355">选择“**分配权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-355">Select **Assign permissions**.</span></span>

4. <span data-ttu-id="033bd-356">在“**分配权限**”窗格中，选择“**添加任何经过身份验证的用户**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-356">On the **Assign permissions** pane, select **Add any authenticated users**.</span></span> 
    
    <span data-ttu-id="033bd-357">对于“**用户和组**”，你将看到**认证用户**已自动添加。</span><span class="sxs-lookup"><span data-stu-id="033bd-357">For **Users and groups**, you see **Authenticated users** automatically added.</span></span> <span data-ttu-id="033bd-358">无法更改此值，只能将其删除，但这会取消选择“**添加任何经过身份验证的用户**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-358">You can't change this value, only delete it, which cancels the **Add any authenticated users** selection.</span></span>

5. <span data-ttu-id="033bd-359">选择“**选择权限**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-359">Select **Choose permissions**.</span></span>

6. <span data-ttu-id="033bd-360">在“**选择权限**”窗格中，选择下拉框，选择所需的权限，然后选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-360">On the **Choose permissions** pane, select the dropdown box, select the permissions you want, and then select **Save**.</span></span>

7. <span data-ttu-id="033bd-361">返回到“**分配权限**”窗格中，选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-361">Back on the **Assign Permissions** pane, select **Save**.</span></span>

8. <span data-ttu-id="033bd-362">在“**加密**”窗格上，选择“**下一步**”并完成向导。</span><span class="sxs-lookup"><span data-stu-id="033bd-362">On the **Encryption** page, select **Next** and complete the wizard.</span></span>

## <a name="considerations-for-encrypted-content"></a><span data-ttu-id="033bd-363">有关加密内容的注意事项</span><span class="sxs-lookup"><span data-stu-id="033bd-363">Considerations for encrypted content</span></span>

<span data-ttu-id="033bd-364">加密最敏感的文档和电子邮件有助于确保只有授权人员可访问此数据。</span><span class="sxs-lookup"><span data-stu-id="033bd-364">Encrypting your most sensitive documents and emails helps to ensure that only authorized people can access this data.</span></span> <span data-ttu-id="033bd-365">但是，需要考虑以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="033bd-365">However, there are some considerations to take into account:</span></span>

- <span data-ttu-id="033bd-366">如果你的组织未[启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签](sensitivity-labels-sharepoint-onedrive-files.md)：</span><span class="sxs-lookup"><span data-stu-id="033bd-366">If your organization hasn't [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):</span></span>
    
    - <span data-ttu-id="033bd-367">“搜索”、“电子数据展示”和 Delve 将无法用于加密文件。</span><span class="sxs-lookup"><span data-stu-id="033bd-367">Search, eDiscovery, and Delve will not work for encrypted files.</span></span>
    - <span data-ttu-id="033bd-368">DLP 策略适用于这些加密文件的元数据（包括保留标签信息），但不适用于这些文件的内容（如文件内的信用卡号）。</span><span class="sxs-lookup"><span data-stu-id="033bd-368">DLP policies work for the metadata of these encrypted files (including retention label information) but not the content of these files (such as credit card numbers within files).</span></span>
    - <span data-ttu-id="033bd-369">用户无法使用 Office 网页版打开加密文件。</span><span class="sxs-lookup"><span data-stu-id="033bd-369">Users can't open encrypted files using Office on the web.</span></span> <span data-ttu-id="033bd-370">如果在 SharePoint 和 OneDrive 中为 Office 文件启用了敏感度标签，则用户可使用 Office 网页版打开加密文件，但存在一些[限制](sensitivity-labels-sharepoint-onedrive-files.md#limitations)，包括已通过本地密钥应用的加密（称为“保留自己的密钥”(HYOK)）、[双密钥加密](#double-key-encryption)以及在不使用敏感度标签的情况下应用的加密。</span><span class="sxs-lookup"><span data-stu-id="033bd-370">When sensitivity labels for Office files in SharePoint and OneDrive are enabled, users can use Office on the web to open encrypted files, with some [limitations](sensitivity-labels-sharepoint-onedrive-files.md#limitations) that include encryption that has been applied with an on-premises key (known as "hold your own key", or HYOK), [double key encryption](#double-key-encryption), and encryption that has been applied independently from a sensitivity label.</span></span>

- <span data-ttu-id="033bd-371">要使多名用户同时编辑一个加密文件，这些用户必须全都在使用 Web 版 Office。</span><span class="sxs-lookup"><span data-stu-id="033bd-371">For multiple users to edit an encrypted file at the same time, they must all be using Office for the web.</span></span> <span data-ttu-id="033bd-372">如果不是这种情况且文件已打开：</span><span class="sxs-lookup"><span data-stu-id="033bd-372">If this isn't the case, and the file is already open:</span></span>
    
    - <span data-ttu-id="033bd-373">在 Office 应用（Windows、Mac、Android 和 iOS）中，用户会看到一条“**文件正在使用中**”消息，其中包含签出该文件的用户的姓名。</span><span class="sxs-lookup"><span data-stu-id="033bd-373">In Office apps (Windows, Mac, Android, and iOS), users see a **File In Use** message with the name of the person who has checked out the file.</span></span> <span data-ttu-id="033bd-374">然后，他们可查看只读副本或保存和编辑文件副本，并可在文件可用时收到通知。</span><span class="sxs-lookup"><span data-stu-id="033bd-374">They can then view a read-only copy or save and edit a copy of the file, and receive notification when the file is available.</span></span>
    - <span data-ttu-id="033bd-375">在 Web 版 Office 中，用户会看到一则错误消息，其中指出他们可与其他人一起编辑文档。</span><span class="sxs-lookup"><span data-stu-id="033bd-375">In Office for the web, users see an error message that they can't edit the document with other people.</span></span> <span data-ttu-id="033bd-376">然后，他们可选择“**在阅读视图中打开**”。</span><span class="sxs-lookup"><span data-stu-id="033bd-376">They can then select **Open in Reading View**.</span></span>

- <span data-ttu-id="033bd-377">已对加密文件禁用 Office 应用（Windows、Mac、Android 和 iOS）的[自动保存](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5)功能。</span><span class="sxs-lookup"><span data-stu-id="033bd-377">The [AutoSave](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) functionality in Office apps (Windows, Mac, Android, and iOS) is disabled for encrypted files.</span></span> <span data-ttu-id="033bd-378">用户会看到一条消息，其中指出文件具有受限权限且必须删除此权限才能启用“自动保存”。</span><span class="sxs-lookup"><span data-stu-id="033bd-378">Users see a message that the file has restricted permissions that must be removed before AutoSave can be turned on.</span></span>

- <span data-ttu-id="033bd-379">在 Office 应用（Windows、Mac、Android 和 iOS）中打开加密文件可能需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="033bd-379">Encrypted files might take longer to open in Office apps (Windows, Mac, Android, and iOS).</span></span>

- <span data-ttu-id="033bd-380">Office 应用（Windows、Mac、Android 和 iOS）不支持对加密文件进行以下操作，并且用户将看到一则错误消息指出出现了错误。</span><span class="sxs-lookup"><span data-stu-id="033bd-380">The following actions for encrypted files aren't supported from Office apps (Windows, Mac, Android, and iOS), and users see an error message that something went wrong.</span></span> <span data-ttu-id="033bd-381">但是，可将 SharePoint 功能用作替代项：</span><span class="sxs-lookup"><span data-stu-id="033bd-381">However, SharePoint functionality can be used as an alternative:</span></span>
    
    - <span data-ttu-id="033bd-382">查看、还原和保存之前版本的副本。</span><span class="sxs-lookup"><span data-stu-id="033bd-382">View, restore, and save copies of previous versions.</span></span> <span data-ttu-id="033bd-383">或者，在你[为列表或库启用和配置版本控制](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37)后，用户可使用 Office 网页版执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="033bd-383">As an alternative, users can do these actions using Office on the web when you [enable and configure versioning for a list or library](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).</span></span> 
    - <span data-ttu-id="033bd-384">更改文件的名称或位置。</span><span class="sxs-lookup"><span data-stu-id="033bd-384">Change the name or location of files.</span></span> <span data-ttu-id="033bd-385">或者，用户可在 SharePoint 中[对文档库中的文件、文件夹或链接重命名](https://support.microsoft.com/zh-CN/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185)。</span><span class="sxs-lookup"><span data-stu-id="033bd-385">As an alternative, users can [rename a file, folder, or link in a document library](https://support.microsoft.com/zh-CN/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185) in SharePoint.</span></span>

<span data-ttu-id="033bd-386">为了在已用敏感度标签加密的文件上获得更佳的协作体验，建议使用 [SharePoint 和 OneDrive中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)并使用 Web 版 Office。</span><span class="sxs-lookup"><span data-stu-id="033bd-386">For the best collaboration experience for files that are encrypted by a sensitivity label, we recommend you use [sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) and Office for the web.</span></span> 

## <a name="important-prerequisites"></a><span data-ttu-id="033bd-387">重要先决条件</span><span class="sxs-lookup"><span data-stu-id="033bd-387">Important prerequisites</span></span>

<span data-ttu-id="033bd-388">可能需要执行一些配置任务，然后才可使用加密。</span><span class="sxs-lookup"><span data-stu-id="033bd-388">Before you can use encryption, you might need to do some configuration tasks.</span></span>

### <a name="activate-protection-from-azure-information-protection"></a><span data-ttu-id="033bd-389">激活 Azure 信息保护中的保护</span><span class="sxs-lookup"><span data-stu-id="033bd-389">Activate protection from Azure Information Protection</span></span>

<span data-ttu-id="033bd-390">要使敏感度标签应用加密，必须为租户激活 Azure 信息保护中的保护服务（即 Azure 权限管理）。</span><span class="sxs-lookup"><span data-stu-id="033bd-390">For sensitivity labels to apply encryption, the protection service (Azure Rights Management) from Azure Information Protection must be activated for your tenant.</span></span> <span data-ttu-id="033bd-391">在较新的租户中，这是默认设置，但你可能需要手动激活该服务。</span><span class="sxs-lookup"><span data-stu-id="033bd-391">In newer tenants, this is the default setting, but you might need to manually activate the service.</span></span> <span data-ttu-id="033bd-392">有关详细信息，请参阅[激活 Azure 信息保护中的保护服务](https://docs.microsoft.com/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="033bd-392">For more information, see [Activating the protection service from Azure Information Protection](https://docs.microsoft.com/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="033bd-393">配置用于 Azure 信息保护的 Exchange</span><span class="sxs-lookup"><span data-stu-id="033bd-393">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="033bd-394">无需针对 Azure 信息保护进行配置，用户即可在 Outlook 中应用标签来加密其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="033bd-394">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to encrypt their emails.</span></span> <span data-ttu-id="033bd-395">但是，除非已针对 Azure 信息保护进行了配置，否则无法通过 Exchange 获得使用 Azure 权限管理保护的完整功能。</span><span class="sxs-lookup"><span data-stu-id="033bd-395">However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="033bd-396">例如，用户无法查看移动电话或 Outlook 网页版上机密的电子邮件，无法索引加密的电子邮件用于搜索，并且无法针对 Rights Management 保护配置 Exchange Online DLP。</span><span class="sxs-lookup"><span data-stu-id="033bd-396">For example, users cannot view encrypted emails on mobile phones or with Outlook on the web, encrypted emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="033bd-397">为确保 Exchange 可以支持这些其他应用场景，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="033bd-397">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="033bd-398">对于 Exchange Online，请参阅 [Exchange Online：IRM 配置](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration)的说明。</span><span class="sxs-lookup"><span data-stu-id="033bd-398">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/azure/information-protection/configure-office365#exchangeonline-irm-configuration).</span></span>
- <span data-ttu-id="033bd-399">对于本地 Exchange，必须部署 [RMS 连接器并配置你的 Exchange 服务器](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector)。</span><span class="sxs-lookup"><span data-stu-id="033bd-399">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector).</span></span> 
