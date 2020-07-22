---
title: 启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理员可以在 SharePoint 和 OneDrive 中为 Word、Excel 和 PowerPoint 文件启用敏感度标签支持。
ms.openlocfilehash: a6826be5cccf89d3b2e48e0e37df9a9263e4a8a7
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201506"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a><span data-ttu-id="000ea-103">启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="000ea-103">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>

><span data-ttu-id="000ea-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="000ea-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="000ea-105">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，不能在 web 上的 Office 中应用[敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="000ea-105">Before you enable sensitivity labels for Office files in SharePoint and OneDrive, you can't apply your [sensitivity labels](sensitivity-labels.md) in Office on the web.</span></span> <span data-ttu-id="000ea-106">您不会在功能区上看到 "**敏感度**" 按钮，也无法在状态栏上看到应用的标签名称。</span><span class="sxs-lookup"><span data-stu-id="000ea-106">You don't see the **Sensitivity** button on the ribbon, or the applied label name on the status bar.</span></span> <span data-ttu-id="000ea-107">此外，如果您使用桌面应用程序标记文件，然后将其保存在 SharePoint 或 OneDrive 中，则该服务将无法处理这些文件的内容（如果标签应用了加密）。</span><span class="sxs-lookup"><span data-stu-id="000ea-107">In addition, if you use desktop apps to label your files and then save them on SharePoint or OneDrive, the service can't process the content of these files if the label applied encryption.</span></span> <span data-ttu-id="000ea-108">在这些情况下，共同创作、eDiscovery、数据丢失防护、搜索和其他协作功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="000ea-108">Coauthoring, eDiscovery, Data Loss Prevention, search, and other collaborative features won't work under these circumstances.</span></span>

<span data-ttu-id="000ea-109">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签时，将启用所有这些功能。</span><span class="sxs-lookup"><span data-stu-id="000ea-109">When you do enable sensitivity labels for Office files in SharePoint and OneDrive, all these capabilities are enabled.</span></span> <span data-ttu-id="000ea-110">除了向用户显示敏感度标签之外，对于应用了敏感标签的新文件和已更改的文件，包括使用基于云的密钥进行加密（并且不使用[双重密钥加密](double-key-encryption.md)）：</span><span class="sxs-lookup"><span data-stu-id="000ea-110">In addition to displaying sensitivity labels to users, for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key (and doesn't use [Double Key Encryption](double-key-encryption.md)):</span></span>

- <span data-ttu-id="000ea-111">对于 Word、Excel 和 PowerPoint 文件，SharePoint 会识别该标签，现在可以处理加密文件的内容。</span><span class="sxs-lookup"><span data-stu-id="000ea-111">For Word, Excel, and PowerPoint files, SharePoint recognizes the label and is now able to process the contents of the encrypted file.</span></span>

- <span data-ttu-id="000ea-112">从 SharePoint 或 OneDrive 下载或访问这些文件时，将强制应用标签中的敏感度标签和任何加密设置，并在存储文件的任何位置保留这些设置。</span><span class="sxs-lookup"><span data-stu-id="000ea-112">When you download or access these files from SharePoint or OneDrive, the sensitivity label and any encryption settings from the label are enforced and remain with the file, wherever it is stored.</span></span> <span data-ttu-id="000ea-113">确保提供用户指南以仅使用标签来保护文档。</span><span class="sxs-lookup"><span data-stu-id="000ea-113">Ensure you provide user guidance to use only labels to protect documents.</span></span> <span data-ttu-id="000ea-114">有关详细信息，请参阅[信息权限管理（IRM）选项和敏感度标签](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="000ea-114">For more information, see [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).</span></span>

- <span data-ttu-id="000ea-115">当用户将标记和加密的文件上传到 SharePoint 时，他们必须至少具有对这些文件的查看权限。</span><span class="sxs-lookup"><span data-stu-id="000ea-115">When users upload labeled and encrypted files to SharePoint, they must have at least view rights to those files.</span></span> <span data-ttu-id="000ea-116">例如，他们可以在 SharePoint 外部打开文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-116">For example, they can open the files outside SharePoint.</span></span> <span data-ttu-id="000ea-117">如果没有合适的最小使用率，则上载将会成功，但 SharePoint 无法识别标签，也无法处理文件内容。</span><span class="sxs-lookup"><span data-stu-id="000ea-117">If they don't have this minimum usage right, the upload is successful but SharePoint doesn't recognize the label and can't process the file contents.</span></span>

- <span data-ttu-id="000ea-118">使用 web 上的 Office （Word、Excel、PowerPoint）打开和编辑具有应用加密的敏感度标签的 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-118">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="000ea-119">将强制实施通过加密分配的权限。</span><span class="sxs-lookup"><span data-stu-id="000ea-119">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="000ea-120">在 web 上使用 Word 时，您还可以在编辑这些文档时使用自动标记。</span><span class="sxs-lookup"><span data-stu-id="000ea-120">With Word on the web, you can also use auto-labeling when you edit these documents.</span></span>

- <span data-ttu-id="000ea-121">外部用户可以使用来宾帐户访问标记为加密的文档。</span><span class="sxs-lookup"><span data-stu-id="000ea-121">External users can access documents that are labeled with encryption by using guest accounts.</span></span> <span data-ttu-id="000ea-122">有关详细信息，请参阅[对外部用户的支持和带标签的内容](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。</span><span class="sxs-lookup"><span data-stu-id="000ea-122">For more information, see [Support for external users and labeled content](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).</span></span> 

- <span data-ttu-id="000ea-123">Office 365 电子数据展示支持对这些文件进行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="000ea-123">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="000ea-124">数据丢失防护（DLP）策略支持这些文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="000ea-124">Data Loss Prevention (DLP) policies support content in these files.</span></span>

> [!NOTE]
> <span data-ttu-id="000ea-125">如果加密应用了本地密钥，则密钥管理拓扑通常称为 "保留自己的密钥" （HYOK），或者通过使用[双重密钥加密](double-key-encryption.md)，用于处理文件内容的 SharePoint 行为不会发生变化。</span><span class="sxs-lookup"><span data-stu-id="000ea-125">If encryption has been applied with on-premises key, a key management topology often referred to as "hold your own key" (HYOK), or by using [Double Key Encryption](double-key-encryption.md), the SharePoint behavior for processing the file contents doesn't change.</span></span>
>
> <span data-ttu-id="000ea-126">Sharepoint 中的现有标记和加密文件的 SharePoint 行为也不会更改。</span><span class="sxs-lookup"><span data-stu-id="000ea-126">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint.</span></span> <span data-ttu-id="000ea-127">为了使这些文件受益于新功能，必须下载和上载这些文件，或者在运行命令以启用 SharePoint 和 OneDrive 的敏感度标签后对这些文件进行编辑。</span><span class="sxs-lookup"><span data-stu-id="000ea-127">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you run the command to enable sensitivity labels for SharePoint and OneDrive.</span></span> <span data-ttu-id="000ea-128">然后，SharePoint 可以处理这些文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-128">SharePoint can then process these files.</span></span> <span data-ttu-id="000ea-129">例如，它们将在搜索和电子数据展示结果中返回。</span><span class="sxs-lookup"><span data-stu-id="000ea-129">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="000ea-130">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，可使用三个新的[审核事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)来监视应用于 Sharepoint 和 onedrive 中文档的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="000ea-130">After you enable sensitivity labels for Office files in SharePoint and OneDrive, three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied to documents in SharePoint and OneDrive:</span></span>
- <span data-ttu-id="000ea-131">**已向文件应用敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="000ea-131">**Applied sensitivity label to file**</span></span>
- <span data-ttu-id="000ea-132">**已更改应用于文件的敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="000ea-132">**Changed sensitivity label applied to file**</span></span>
- <span data-ttu-id="000ea-133">**已从文件除敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="000ea-133">**Removed sensitivity label from file**</span></span>

<span data-ttu-id="000ea-134">观看以下视频（无音频）以查看操作中的新功能：</span><span class="sxs-lookup"><span data-stu-id="000ea-134">Watch the following video (no audio) to see the new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

<span data-ttu-id="000ea-135">您始终可以选择在 SharePoint 和 OneDrive 中禁用 Office 文件的敏感度[标签（随时退出。](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)</span><span class="sxs-lookup"><span data-stu-id="000ea-135">You always have the choice to disable sensitivity labels for Office files in SharePoint and OneDrive ([opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) at any time.</span></span>

<span data-ttu-id="000ea-136">如果当前通过使用 SharePoint 信息权限管理（IRM）保护 SharePoint 中的文档，请务必查看此页上的 " [SharePoint 信息权限管理（irm）和敏感度标签](#sharepoint-information-rights-management-irm-and-sensitivity-labels)" 部分。</span><span class="sxs-lookup"><span data-stu-id="000ea-136">If you are currently protecting documents in SharePoint by using SharePoint Information Rights Management (IRM), be sure to check the [SharePoint Information Rights Management (IRM) and sensitivity labels](#sharepoint-information-rights-management-irm-and-sensitivity-labels) section on this page.</span></span> 

## <a name="requirements"></a><span data-ttu-id="000ea-137">要求</span><span class="sxs-lookup"><span data-stu-id="000ea-137">Requirements</span></span>

<span data-ttu-id="000ea-138">这些新功能仅适用于[敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="000ea-138">These new capabilities work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="000ea-139">如果你当前有 Azure 信息保护标签，请首先将其迁移到敏感度标签，以便可以为上传的新文件启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="000ea-139">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="000ea-140">有关说明，请参阅[如何将 Azure 信息保护标签迁移到统一敏感度标签](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="000ea-140">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="000ea-141">在 Windows 上使用 OneDrive 同步应用程序版本19.002.0121.0008 或更高版本，在 Mac 上使用版本19.002.0107.0008 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="000ea-141">Use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="000ea-142">这两个版本都发布了2019年1月28日，并且当前已发布到所有震铃。</span><span class="sxs-lookup"><span data-stu-id="000ea-142">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="000ea-143">有关详细信息，请参阅[OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="000ea-143">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="000ea-144">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，运行较旧版本的同步应用程序的用户将被提示更新它。</span><span class="sxs-lookup"><span data-stu-id="000ea-144">After you enable sensitivity labels for Office files in SharePoint and OneDrive, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="000ea-145">限制</span><span class="sxs-lookup"><span data-stu-id="000ea-145">Limitations</span></span>

- <span data-ttu-id="000ea-146">SharePoint 不会自动将灵敏度标签应用于已使用 Azure 信息保护标签加密的现有文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-146">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="000ea-147">相反，若要在 SharePoint 和 OneDrive 中为 Office 文件启用灵敏度标签后运行这些功能，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="000ea-147">Instead, for the features to work after you enable sensitivity labels for Office files in SharePoint and OneDrive, complete these tasks:</span></span>
    
    1. <span data-ttu-id="000ea-148">确保已[将 Azure 信息保护标签迁移](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)到了敏感度标签，并[已将其](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)从 Microsoft 365 合规性中心或等效的标签管理中心进行了发布。</span><span class="sxs-lookup"><span data-stu-id="000ea-148">Make sure you have [migrated the Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) to sensitivity labels and [published them](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="000ea-149">下载这些文件，然后将其上传到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="000ea-149">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="000ea-150">当应用了加密的标签具有以下[加密配置时，](encryption-sensitivity-labels.md#configure-encryption-settings)SharePoint 将无法处理加密文件：</span><span class="sxs-lookup"><span data-stu-id="000ea-150">SharePoint can't process encrypted files when the label that applied the encryption has any of the following [configurations for encryption](encryption-sensitivity-labels.md#configure-encryption-settings):</span></span>
    - <span data-ttu-id="000ea-151">**允许用户在应用标签时分配权限**，并在**Word、PowerPoint 和 Excel 中对复选框进行提示，并在 Word、PowerPoint 和 Excel 中选中 "提示用户指定权限**"。</span><span class="sxs-lookup"><span data-stu-id="000ea-151">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="000ea-152">此设置有时称为 "用户定义的权限"。</span><span class="sxs-lookup"><span data-stu-id="000ea-152">This setting is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="000ea-153">**用户对内容的访问权限**设置为**永不**过期的值。</span><span class="sxs-lookup"><span data-stu-id="000ea-153">**User access to content expires** is set to a value other than **Never**.</span></span>
    - <span data-ttu-id="000ea-154">选择了 "**双密钥加密**"。</span><span class="sxs-lookup"><span data-stu-id="000ea-154">**Double Key Encryption** is selected.</span></span>
    
    <span data-ttu-id="000ea-155">对于具有上述任何加密配置的标签，web 上的 Office 用户不会看到这些标签。</span><span class="sxs-lookup"><span data-stu-id="000ea-155">For labels with any of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="000ea-156">此外，不能将新功能用于已拥有这些加密设置的已标记文档。</span><span class="sxs-lookup"><span data-stu-id="000ea-156">Additionally, the new capabilities can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="000ea-157">例如，这些文档不会在搜索结果中返回，即使它们已更新也是如此。</span><span class="sxs-lookup"><span data-stu-id="000ea-157">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="000ea-158">对于向用户授予编辑权限的加密文档，不能在 Office 应用程序的 web 版本中阻止复制。</span><span class="sxs-lookup"><span data-stu-id="000ea-158">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="000ea-159">不支持 Azure 信息保护文档跟踪网站。</span><span class="sxs-lookup"><span data-stu-id="000ea-159">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="000ea-160">对于标记为加密的文件，Office 桌面应用程序和移动应用程序不支持共同创作。</span><span class="sxs-lookup"><span data-stu-id="000ea-160">Office desktop apps and mobile apps don't support coauthoring for files that are labeled with encryption.</span></span> <span data-ttu-id="000ea-161">这些应用将继续以独占编辑模式打开带标签和加密的文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-161">These apps continue to open labeled and encrypted files in exclusive editing mode.</span></span>

- <span data-ttu-id="000ea-162">如果管理员更改已应用于下载到用户同步客户端的文件的已发布标签的设置，则用户可能无法在其 OneDrive 同步文件夹中保存对文件所做的更改。</span><span class="sxs-lookup"><span data-stu-id="000ea-162">If an admin changes settings for a published label that's already applied to files downloaded to users' sync client, users might be unable to save changes they make to the file in their OneDrive Sync folder.</span></span> <span data-ttu-id="000ea-163">此方案适用于使用加密标记的文件，以及当标签更改来自未对其应用加密的标签的标签时。</span><span class="sxs-lookup"><span data-stu-id="000ea-163">This scenario applies to files that are labeled with encryption, and also when the label change is from a label that didn't apply encryption to a label that does apply encryption.</span></span> <span data-ttu-id="000ea-164">用户看到一个[带有白色交叉图标错误的红色圆圈](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，并要求他们将新的更改另存为一个单独副本。</span><span class="sxs-lookup"><span data-stu-id="000ea-164">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span> <span data-ttu-id="000ea-165">而是可以关闭和重新打开文件，或使用 web 上的 Office。</span><span class="sxs-lookup"><span data-stu-id="000ea-165">Instead, they can close and reopen the file, or use Office on the web.</span></span>

- <span data-ttu-id="000ea-166">如果将带标签的文档上载到 SharePoint，并使用服务主体名称中的帐户来应用加密，则无法在 web 上的 Office 中打开该文档。</span><span class="sxs-lookup"><span data-stu-id="000ea-166">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="000ea-167">示例方案包括 Microsoft 云应用安全和通过电子邮件发送给团队的文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-167">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="000ea-168">用户可以在脱机或进入睡眠模式后遇到保存问题，而不是在使用 Office 的情况下使用 Word、Excel 或 PowerPoint 的桌面和移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="000ea-168">Users can experience save problems after going offline or into a sleep mode when instead of using Office for the web, they use the desktop and mobile apps for Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="000ea-169">对于这些用户，当他们恢复 Office 应用程序会话并尝试保存更改时，他们会看到 "上载失败" 消息，其中包含一个用于保存副本而不是保存原始文件的选项。</span><span class="sxs-lookup"><span data-stu-id="000ea-169">For these users, when they resume their Office app session and try to save changes, they see an upload failure message with an option to save a copy instead of saving the original file.</span></span> 

- <span data-ttu-id="000ea-170">以下列方式加密的文档无法在 web 上的 Office 中打开：</span><span class="sxs-lookup"><span data-stu-id="000ea-170">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="000ea-171">使用本地密钥的加密（"保留自己的密钥" 或 HYOK）</span><span class="sxs-lookup"><span data-stu-id="000ea-171">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="000ea-172">使用[双重密钥加密](double-key-encryption.md)应用的加密</span><span class="sxs-lookup"><span data-stu-id="000ea-172">Encryption that was applied by using [Double Key Encryption](double-key-encryption.md)</span></span> 
    - <span data-ttu-id="000ea-173">独立于标签（例如，通过直接应用权限管理保护模板）应用的加密。</span><span class="sxs-lookup"><span data-stu-id="000ea-173">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="000ea-174">如果您删除了应用于 SharePoint 文档的标签，而不是从适用的标签策略中删除标签，则下载的文档不会被标记或加密。</span><span class="sxs-lookup"><span data-stu-id="000ea-174">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="000ea-175">相比之下，如果标记的文档存储在 SharePoint 外部，则在删除该标签时，该文档仍保持加密。</span><span class="sxs-lookup"><span data-stu-id="000ea-175">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="000ea-176">请注意，尽管您可以在测试阶段删除标签，但很少在生产环境中删除标签。</span><span class="sxs-lookup"><span data-stu-id="000ea-176">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a><span data-ttu-id="000ea-177">如何为 SharePoint 和 OneDrive 启用敏感度标签（自愿加入）</span><span class="sxs-lookup"><span data-stu-id="000ea-177">How to enable sensitivity labels for SharePoint and OneDrive (opt-in)</span></span>

<span data-ttu-id="000ea-178">您可以通过使用 Microsoft 365 合规性中心或使用 PowerShell 来启用新功能。</span><span class="sxs-lookup"><span data-stu-id="000ea-178">You can enable the new capabilities by using the Microsoft 365 compliance center, or by using PowerShell.</span></span>

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="000ea-179">使用合规性中心启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="000ea-179">Use the compliance center to enable support for sensitivity labels</span></span>

<span data-ttu-id="000ea-180">此选项是为 SharePoint 和 OneDrive 启用敏感度标签的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="000ea-180">This option is the easiest way to enable sensitivity labels for SharePoint and OneDrive.</span></span>

<span data-ttu-id="000ea-181">组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。</span><span class="sxs-lookup"><span data-stu-id="000ea-181">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="000ea-182">如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="000ea-182">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

1. <span data-ttu-id="000ea-183">登录[Microsoft 365 合规性中心](https://compliance.microsoft.com/)，并导航到 "**解决方案**  >  **信息保护**"</span><span class="sxs-lookup"><span data-stu-id="000ea-183">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com/), and navigate to **Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="000ea-184">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="000ea-184">If you don't immediately see this option, first select **Show all**.</span></span> 

2. <span data-ttu-id="000ea-185">如果您看到一条消息，以打开在 Office online 文件中处理内容的功能，请选择 **"立即打开"**：</span><span class="sxs-lookup"><span data-stu-id="000ea-185">If you see a message to turn on the ability to process content in Office online files, select **Turn on now**:</span></span>
    
    ![启用 "立即打开" 按钮以启用 Office Online 的敏感度标签](../media/sensitivity-labels-turn-on-banner.png)
    
    <span data-ttu-id="000ea-187">该命令将立即运行，当页面下次刷新时，您将不会再看到该消息或按钮。</span><span class="sxs-lookup"><span data-stu-id="000ea-187">The command runs immediately and when the page is next refreshed, you no longer see the message or button.</span></span> 

> [!NOTE]
> <span data-ttu-id="000ea-188">如果你有 Microsoft 365 多地理位置，则必须使用 PowerShell 为你的所有地理位置启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="000ea-188">If you have Microsoft 365 Multi-Geo, you must use PowerShell to enable these capabilities for all your geo-locations.</span></span> <span data-ttu-id="000ea-189">有关详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="000ea-189">See the next section for details.</span></span>

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="000ea-190">使用 PowerShell 启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="000ea-190">Use PowerShell to enable support for sensitivity labels</span></span>

<span data-ttu-id="000ea-191">作为使用合规性中心的替代方法，可以使用 SharePoint Online PowerShell 中的[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 启用敏感度标签支持。</span><span class="sxs-lookup"><span data-stu-id="000ea-191">As an alternative to using the compliance center, you can enable support for sensitivity labels by using the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet from SharePoint Online PowerShell.</span></span> 

<span data-ttu-id="000ea-192">如果你有 Microsoft 365 多地理位置，则必须使用 PowerShell 为你的所有地理位置启用此支持。</span><span class="sxs-lookup"><span data-stu-id="000ea-192">If you have Microsoft 365 Multi-Geo, you must use PowerShell to enable this support for all your geo-locations.</span></span>

#### <a name="prepare-the-sharepoint-online-management-shell"></a><span data-ttu-id="000ea-193">准备 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="000ea-193">Prepare the SharePoint Online Management Shell</span></span>

<span data-ttu-id="000ea-194">在运行 PowerShell 命令以在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，请确保您运行的是 SharePoint Online 命令行管理程序版本16.0.19418.12000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="000ea-194">Before you run the PowerShell command to enable sensitivity labels for Office files in SharePoint and OneDrive, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or later.</span></span> <span data-ttu-id="000ea-195">如果已有最新版本，则可以跳至[下一过程](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)以运行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="000ea-195">If you already have the latest version, you can skip to [next procedure](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) to run the PowerShell command.</span></span>

1. <span data-ttu-id="000ea-196">如果已从 PowerShell 库安装早期版本的 SharePoint Online 命令行管理程序，可通过运行以下 cmdlet 来更新模块。</span><span class="sxs-lookup"><span data-stu-id="000ea-196">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="000ea-197">或者，如果您已从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到 "**添加或删除程序**"，然后卸载 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="000ea-197">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="000ea-198">在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="000ea-198">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="000ea-199">选择语言，然后单击“**下载**”。</span><span class="sxs-lookup"><span data-stu-id="000ea-199">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="000ea-200">在 x64 和 x86.msi 文件之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="000ea-200">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="000ea-201">如果运行的是64位版本的 Windows 或 x86 文件（如果运行32位版本），请下载 x64 文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-201">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="000ea-202">如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="000ea-202">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>

6. <span data-ttu-id="000ea-203">下载文件后，运行文件并按照安装向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="000ea-203">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="000ea-204">运行 PowerShell 命令以启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="000ea-204">Run the PowerShell command to enable support for sensitivity labels</span></span>

<span data-ttu-id="000ea-205">若要启用新功能，请将[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Cmdlet 与*EnableAIPIntegration*参数一起使用：</span><span class="sxs-lookup"><span data-stu-id="000ea-205">To enable the new capabilities, use the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *EnableAIPIntegration* parameter:</span></span>

1. <span data-ttu-id="000ea-206">在 Microsoft 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="000ea-206">Using a work or school account that has global administrator or SharePoint admin privileges in Microsoft 365, connect to SharePoint.</span></span> <span data-ttu-id="000ea-207">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="000ea-207">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>
    
    <span data-ttu-id="000ea-208">注意：如果你拥有 Microsoft 365 多地理位置，请使用-Url 参数和[connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，并为你的某个地理位置指定 SharePoint Online 管理中心网站 Url。</span><span class="sxs-lookup"><span data-stu-id="000ea-208">Note: If you have Microsoft 365 Multi-Geo, use the -Url parameter with [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), and specify the SharePoint Online Administration Center site URL for one of your geo-locations.</span></span>

2. <span data-ttu-id="000ea-209">运行以下命令，然后按**Y**确认：</span><span class="sxs-lookup"><span data-stu-id="000ea-209">Run the following command and press **Y** to confirm:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. <span data-ttu-id="000ea-210">对于 Microsoft 365 多地理位置：对剩下的每个地理位置重复步骤1和2。</span><span class="sxs-lookup"><span data-stu-id="000ea-210">For Microsoft 365 Multi-Geo: Repeat steps 1 and 2 for each of your remaining geo-locations.</span></span>

## <a name="publishing-and-changing-sensitivity-labels"></a><span data-ttu-id="000ea-211">发布和更改敏感度标签</span><span class="sxs-lookup"><span data-stu-id="000ea-211">Publishing and changing sensitivity labels</span></span>

<span data-ttu-id="000ea-212">当您在 SharePoint 和 OneDrive 中使用敏感度标签时，请记住，在发布新的敏感度标签或更新现有的敏感度标签时，需要允许复制时间。</span><span class="sxs-lookup"><span data-stu-id="000ea-212">When you use sensitivity labels with SharePoint and OneDrive, keep in mind that you need to allow for replication time when you publish new sensitivity labels or update existing sensitivity labels.</span></span> <span data-ttu-id="000ea-213">对于适用于加密的新标签，这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="000ea-213">This is especially important for new labels that apply encryption.</span></span>

<span data-ttu-id="000ea-214">例如：您创建并发布了一个新的敏感度标签，它将应用加密并快速显示在用户的桌面应用程序中。</span><span class="sxs-lookup"><span data-stu-id="000ea-214">For example: You create and publish a new sensitivity label that applies encryption and it very quickly appears in a user's desktop app.</span></span> <span data-ttu-id="000ea-215">用户将此标签应用于文档，然后将其上载到 SharePoint 或 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="000ea-215">The user applies this label to a document and then uploads it to SharePoint or OneDrive.</span></span> <span data-ttu-id="000ea-216">如果该服务的标签复制尚未完成，则在上载时不会对该文档应用新功能。</span><span class="sxs-lookup"><span data-stu-id="000ea-216">If the label replication hasn't completed for the service, the new capabilities won't be applied to that document on upload.</span></span> <span data-ttu-id="000ea-217">因此，不会在搜索或电子数据展示中返回该文档，也不能在 Office for web 中打开该文档。</span><span class="sxs-lookup"><span data-stu-id="000ea-217">As a result, the document won't be returned in search or for eDiscovery and the document can't be opened in Office for the web.</span></span>

- <span data-ttu-id="000ea-218">以下更改在一小时内复制：新的和删除的敏感度标签，以及包括哪些标签在策略中的敏感度标签策略设置。</span><span class="sxs-lookup"><span data-stu-id="000ea-218">The following changes replicate within one hour: New and deleted sensitivity labels, and sensitivity label policy settings that include which labels are in the policy.</span></span>

- <span data-ttu-id="000ea-219">以下更改将在24小时内复制：对现有标签的敏感度标签设置的更改。</span><span class="sxs-lookup"><span data-stu-id="000ea-219">The following changes replicate within 24 hours: Changes to sensitivity label settings for existing labels.</span></span>

<span data-ttu-id="000ea-220">由于对于新的敏感度标签，复制延迟现在仅为一小时，因此您不太可能会遇到此示例中的情形。</span><span class="sxs-lookup"><span data-stu-id="000ea-220">Because the replication delay is now only one hour for new sensitivity labels, you are unlikely to run into the scenario in the example.</span></span> <span data-ttu-id="000ea-221">但作为一项安全措施，我们建议先将新标签发布到少数测试用户，再等待一小时，然后在 SharePoint 和 OneDrive 上验证标签行为。</span><span class="sxs-lookup"><span data-stu-id="000ea-221">But as a safeguard, we recommend publishing new labels to just a few test users first, wait for an hour, and then verify the label behavior on SharePoint and OneDrive.</span></span> <span data-ttu-id="000ea-222">最后一步是，通过向现有标签策略中添加更多用户，或为标准用户将标签添加到现有的标签策略中，使更多的用户可以使用该标签。</span><span class="sxs-lookup"><span data-stu-id="000ea-222">As the final step, make the label available to more users by either adding more users to the existing label policy, or add the label to an existing label policy for your standard users.</span></span> <span data-ttu-id="000ea-223">当您的标准用户看到标签时，它已同步到 SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="000ea-223">At the time your standard users see the label, it has already synchronized to SharePoint and OneDrive.</span></span>


## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a><span data-ttu-id="000ea-224">SharePoint 信息权限管理（IRM）和敏感度标签</span><span class="sxs-lookup"><span data-stu-id="000ea-224">SharePoint Information Rights Management (IRM) and sensitivity labels</span></span>

<span data-ttu-id="000ea-225">[SharePoint 信息权限管理（IRM）](set-up-irm-in-sp-admin-center.md)是一种较旧的技术，可通过在下载文件时应用加密和限制来保护列表和库级别的文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-225">[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) is an older technology to protect files at the list and library level by applying encryption and restrictions when files are downloaded.</span></span> <span data-ttu-id="000ea-226">此较旧的保护技术旨在防止未经授权的用户在 SharePoint 外部打开该文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-226">This older protection technology is designed to prevent unauthorized users from opening the file while it's outside SharePoint.</span></span>

<span data-ttu-id="000ea-227">相比之下，敏感度标签提供了直观标记（页眉、页脚、水印）的保护设置以及加密。</span><span class="sxs-lookup"><span data-stu-id="000ea-227">In comparison, sensitivity labels provide the protection settings of visual markings (headers, footers, watermarks) in addition to encryption.</span></span> <span data-ttu-id="000ea-228">加密设置支持完全范围的[使用权限](https://docs.microsoft.com/azure/information-protection/configure-usage-rights)，以限制用户可以对内容执行的操作，并且[许多方案](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)都支持相同的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="000ea-228">The encryption settings support the full range of [usage rights](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) to restrict what users can do with the content, and the same sensitivity labels are supported for [many scenarios](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels).</span></span> <span data-ttu-id="000ea-229">在工作负载和应用中使用具有一致设置的相同保护方法将导致一致的保护策略。</span><span class="sxs-lookup"><span data-stu-id="000ea-229">Using the same protection method with consistent settings across workloads and apps results in a consistent protection strategy.</span></span>

<span data-ttu-id="000ea-230">但是，可以同时使用这两个保护解决方案，行为如下所示：</span><span class="sxs-lookup"><span data-stu-id="000ea-230">However, you can use both protection solutions together and the behavior is as follows:</span></span> 

- <span data-ttu-id="000ea-231">如果您上载的文件具有适用于加密的敏感度标签，SharePoint 将无法处理此文件，因此不能对此文件进行共同创作、电子数据展示、DLP 和搜索。</span><span class="sxs-lookup"><span data-stu-id="000ea-231">If you upload a file with a sensitivity label that applies encryption, SharePoint can't process this file so coauthoring, eDiscovery, DLP, and search don't work for this file.</span></span>

- <span data-ttu-id="000ea-232">如果使用 web 上的 Office 标记文件，则将强制应用标签中的所有加密设置。</span><span class="sxs-lookup"><span data-stu-id="000ea-232">If you label a file using Office on the web, any encryption settings from the label are enforced.</span></span> <span data-ttu-id="000ea-233">对这些文件、共同创作、电子数据展示、DLP 和搜索均受支持。</span><span class="sxs-lookup"><span data-stu-id="000ea-233">For these files, coauthoring, eDiscovery, DLP, and search are supported.</span></span>

- <span data-ttu-id="000ea-234">如果下载使用 web 上的 Office 标记的文件，则会保留标签，并强制实施标签中的所有加密设置，而不是 IRM 限制设置。</span><span class="sxs-lookup"><span data-stu-id="000ea-234">If you download a file that's labeled by using Office on the web, the label is retained and any encryption settings from the label are enforced rather than the IRM restriction settings.</span></span>

- <span data-ttu-id="000ea-235">如果下载未使用敏感度标签加密的 Office 或 PDF 文件，则会应用 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="000ea-235">If you download an Office or PDF file that isn't encrypted with a sensitivity label, IRM settings are applied.</span></span>

- <span data-ttu-id="000ea-236">如果已启用任何其他 IRM 库设置，其中包括阻止用户上载不支持 IRM 的文档，则强制实施这些设置。</span><span class="sxs-lookup"><span data-stu-id="000ea-236">If you have enabled any of the additional IRM library settings, which includes preventing users from uploading documents that don't support IRM, these settings are enforced.</span></span>

<span data-ttu-id="000ea-237">在这种情况下，您可以确信，如果下载了所有 Office 和 PDF 文件，即使这些文件不带标签，也可以防止未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="000ea-237">With this behavior, you can be assured that all Office and PDF files are protected from unauthorized access if they are downloaded, even if they aren't labeled.</span></span> <span data-ttu-id="000ea-238">但是，已上传的已标记文件不会受益于新功能。</span><span class="sxs-lookup"><span data-stu-id="000ea-238">However, labeled files that are uploaded won't benefit from the new capabilities.</span></span>

## <a name="search-for-documents-by-sensitivity-label"></a><span data-ttu-id="000ea-239">按敏感度标签搜索文档</span><span class="sxs-lookup"><span data-stu-id="000ea-239">Search for documents by sensitivity label</span></span>

<span data-ttu-id="000ea-240">使用托管属性**InformationProtectionLabelId**在 SharePoint 或 OneDrive 中查找具有特定灵敏度标签的所有文档。</span><span class="sxs-lookup"><span data-stu-id="000ea-240">Use the managed property **InformationProtectionLabelId** to find all documents in SharePoint or OneDrive that have a specific sensitivity label.</span></span> <span data-ttu-id="000ea-241">使用以下语法：`InformationProtectionLabelId:<GUID>`</span><span class="sxs-lookup"><span data-stu-id="000ea-241">Use the following syntax: `InformationProtectionLabelId:<GUID>`</span></span>

<span data-ttu-id="000ea-242">例如，若要搜索已标记为 "保密" 的所有文档，并且该标签的 GUID 为 "8faca7b8-8d20-48a3-8ea2-0f96310a848e"，请在搜索框中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="000ea-242">For example, to search for all documents that have been labeled as "Confidential", and that label has a GUID of "8faca7b8-8d20-48a3-8ea2-0f96310a848e", in the search box, type:</span></span>

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

<span data-ttu-id="000ea-243">若要获取敏感度标签的 Guid，请使用 "[获取标签](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps)" cmdlet：</span><span class="sxs-lookup"><span data-stu-id="000ea-243">To get the GUIDs for your sensitivity labels, use the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>
    
1. <span data-ttu-id="000ea-244">首先，[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="000ea-244">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> 
    
    <span data-ttu-id="000ea-245">例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录：</span><span class="sxs-lookup"><span data-stu-id="000ea-245">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. <span data-ttu-id="000ea-246">然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="000ea-246">Then run the following command:</span></span>
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

<span data-ttu-id="000ea-247">有关使用托管属性的详细信息，请参阅[在 SharePoint 中管理搜索架构](https://docs.microsoft.com/sharepoint/manage-search-schema)。</span><span class="sxs-lookup"><span data-stu-id="000ea-247">For more information about using managed properties, see [Manage the search schema in SharePoint](https://docs.microsoft.com/sharepoint/manage-search-schema).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a><span data-ttu-id="000ea-248">如何禁用 SharePoint 和 OneDrive 的敏感度标签（自愿退出）</span><span class="sxs-lookup"><span data-stu-id="000ea-248">How to disable sensitivity labels for SharePoint and OneDrive (opt-out)</span></span>

<span data-ttu-id="000ea-249">如果禁用这些新功能，则在对 SharePoint 和 OneDrive 启用敏感度标签后上载的文件将继续受标签保护，因为仍会继续强制实施标签设置。</span><span class="sxs-lookup"><span data-stu-id="000ea-249">If you disable these new capabilities, files that you uploaded after you enabled sensitivity labels for SharePoint and OneDrive continue to be protected by the label because the label settings continue to be enforced.</span></span> <span data-ttu-id="000ea-250">在禁用这些新功能之后将灵敏度标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="000ea-250">When you apply sensitivity labels to new files after you disable these new capabilities, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="000ea-251">若要禁用这些新功能，必须使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="000ea-251">To disable these new capabilities, you must use PowerShell.</span></span> <span data-ttu-id="000ea-252">使用 SharePoint Online 命令行管理程序和[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 指定相同的*EnableAIPIntegration*参数，如[使用 PowerShell 启用对灵敏度标签的支持](#use-powershell-to-enable-support-for-sensitivity-labels)部分中所述。</span><span class="sxs-lookup"><span data-stu-id="000ea-252">Using the SharePoint Online Management Shell and the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet, specify the same *EnableAIPIntegration* parameter as described in the [Use PowerShell to enable support for sensitivity labels](#use-powershell-to-enable-support-for-sensitivity-labels) section.</span></span> <span data-ttu-id="000ea-253">但这次，请将参数值设置为 false，然后按**Y**确认：</span><span class="sxs-lookup"><span data-stu-id="000ea-253">But this time, set the parameter value to false and press **Y** to confirm:</span></span>

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

<span data-ttu-id="000ea-254">如果你拥有 Microsoft 365 多地理位置，则必须为你的每个地理位置运行此命令。</span><span class="sxs-lookup"><span data-stu-id="000ea-254">If you have Microsoft 365 Multi-Geo, you must run this command for each of your geo-locations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="000ea-255">后续步骤</span><span class="sxs-lookup"><span data-stu-id="000ea-255">Next steps</span></span>

<span data-ttu-id="000ea-256">在 SharePoint 和 OneDrive 中为 Office 文件启用了敏感度标签后，请考虑使用自动标记策略自动标记这些文件。</span><span class="sxs-lookup"><span data-stu-id="000ea-256">After you've enabled sensitivity labels for Office files in SharePoint and OneDrive, consider automatically labeling these files by using auto-labeling policies.</span></span> <span data-ttu-id="000ea-257">有关详细信息，请参阅[自动将敏感度标签应用于内容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="000ea-257">For more information, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>