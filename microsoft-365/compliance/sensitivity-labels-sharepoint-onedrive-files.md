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
ms.openlocfilehash: bb35d4ed287e87ba17780c0e7106b837beb9666a
ms.sourcegitcommit: 758263ad484e00f5a561a47c8c22d5787af7671e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44170911"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a><span data-ttu-id="065f3-103">启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="065f3-103">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>

><span data-ttu-id="065f3-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="065f3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="065f3-105">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，不能在 web 上的 Office 中应用[敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="065f3-105">Before you enable sensitivity labels for Office files in SharePoint and OneDrive, you can't apply your [sensitivity labels](sensitivity-labels.md) in Office on the web.</span></span> <span data-ttu-id="065f3-106">您不会在功能区上看到 "**敏感度**" 按钮，也无法在状态栏上看到应用的标签名称。</span><span class="sxs-lookup"><span data-stu-id="065f3-106">You don't see the **Sensitivity** button on the ribbon, or the applied label name on the status bar.</span></span> <span data-ttu-id="065f3-107">此外，如果您使用桌面应用程序标记文件，然后将其保存在 SharePoint 或 OneDrive 中，则该服务将无法处理这些文件的内容（如果标签应用了加密）。</span><span class="sxs-lookup"><span data-stu-id="065f3-107">In addition, if you use desktop apps to label your files and then save them on SharePoint or OneDrive, the service can't process the content of these files if the label applied encryption.</span></span> <span data-ttu-id="065f3-108">在这些情况下，共同创作、eDiscovery、数据丢失防护、搜索和其他协作功能将不起作用。</span><span class="sxs-lookup"><span data-stu-id="065f3-108">Coauthoring, eDiscovery, Data Loss Prevention, search, and other collaborative features won't work under these circumstances.</span></span>

<span data-ttu-id="065f3-109">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签时，将启用所有这些功能。</span><span class="sxs-lookup"><span data-stu-id="065f3-109">When you do enable sensitivity labels for Office files in SharePoint and OneDrive, all these capabilities are enabled.</span></span> <span data-ttu-id="065f3-110">除了向用户显示敏感度标签之外，对于应用了敏感标签的新文件和已更改文件，包括使用基于云的密钥进行加密：</span><span class="sxs-lookup"><span data-stu-id="065f3-110">In addition to displaying sensitivity labels to users, for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key:</span></span>

- <span data-ttu-id="065f3-111">SharePoint 可识别应用于 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件的敏感度标签。当文件存储在 SharePoint 中时，将删除来自 Azure 信息保护的加密，以便可以对文件内容进行处理。</span><span class="sxs-lookup"><span data-stu-id="065f3-111">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive: While the file is stored in SharePoint, the encryption from Azure Information Protection is removed so that the file contents can be processed.</span></span> <span data-ttu-id="065f3-112">有关在将文档存储在 SharePoint 中时如何保护文档的信息，请参阅[OneDrive For business 和 SharePoint Online 中的数据加密](data-encryption-in-odb-and-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="065f3-112">For information about how documents are protected while they are stored in SharePoint, see [Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md).</span></span>

- <span data-ttu-id="065f3-113">从 SharePoint 或 OneDrive 下载或访问此文件时，标签中的敏感度标签和任何加密设置都会重新应用于该文件，并且在保存文件的任何位置都将强制执行这些设置。</span><span class="sxs-lookup"><span data-stu-id="065f3-113">When you download or access this file from SharePoint or OneDrive, the sensitivity label and any encryption settings from the label are reapplied with the file, and these settings remain enforced wherever the file is saved.</span></span> <span data-ttu-id="065f3-114">由于此行为，请确保提供仅使用标签来保护文档的用户指南。</span><span class="sxs-lookup"><span data-stu-id="065f3-114">Because of this behavior, ensure you provide user guidance to use only labels to protect documents.</span></span> <span data-ttu-id="065f3-115">有关详细信息，请参阅[信息权限管理（IRM）选项和敏感度标签](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="065f3-115">For more information, see [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).</span></span>

- <span data-ttu-id="065f3-116">为了使 SharePoint 能够在上载时从文件中删除加密，上载已标记和已加密文件的用户必须至少具有查看该文件的使用权限。</span><span class="sxs-lookup"><span data-stu-id="065f3-116">For SharePoint to remove the encryption from the file on upload, the user who uploads the labeled and encrypted file must have usage rights to at least view the file.</span></span> <span data-ttu-id="065f3-117">如果用户无法在 SharePoint 外部打开加密，则 SharePoint 不会从文件中删除加密。</span><span class="sxs-lookup"><span data-stu-id="065f3-117">SharePoint doesn't remove encryption from files if the user can't open them outside SharePoint.</span></span>

- <span data-ttu-id="065f3-118">使用 web 上的 Office （Word、Excel、PowerPoint）打开和编辑具有应用加密的敏感度标签的 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-118">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="065f3-119">将强制实施通过加密分配的权限。</span><span class="sxs-lookup"><span data-stu-id="065f3-119">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="065f3-120">在 web 上使用 Word 时，您还可以在编辑这些文档时使用自动标记。</span><span class="sxs-lookup"><span data-stu-id="065f3-120">With Word on the web, you can also use auto-labeling when you edit these documents.</span></span>

- <span data-ttu-id="065f3-121">Office 365 电子数据展示支持对这些文件进行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="065f3-121">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="065f3-122">数据丢失防护（DLP）策略涵盖这些文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="065f3-122">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

> [!NOTE]
> <span data-ttu-id="065f3-123">如果加密尚未应用于基于云的密钥，而是本地密钥，则密钥管理拓扑通常称为 "保留自己的密钥" （HYOK），用于处理文件内容的 SharePoint 行为不会发生变化。</span><span class="sxs-lookup"><span data-stu-id="065f3-123">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior for processing the file contents doesn't change.</span></span>
>
> <span data-ttu-id="065f3-124">Sharepoint 中的现有标记和加密文件的 SharePoint 行为也不会更改。</span><span class="sxs-lookup"><span data-stu-id="065f3-124">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint.</span></span> <span data-ttu-id="065f3-125">为了使这些文件受益于新功能，必须下载和上载这些文件，或者在运行命令以启用 SharePoint 和 OneDrive 的敏感度标签后对这些文件进行编辑。</span><span class="sxs-lookup"><span data-stu-id="065f3-125">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you run the command to enable sensitivity labels for SharePoint and OneDrive.</span></span> <span data-ttu-id="065f3-126">例如，它们将在搜索和电子数据展示结果中返回。</span><span class="sxs-lookup"><span data-stu-id="065f3-126">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="065f3-127">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，可使用三个新的[审核事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)来监视应用于 Sharepoint 和 onedrive 中文档的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="065f3-127">After you enable sensitivity labels for Office files in SharePoint and OneDrive, three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied to documents in SharePoint and OneDrive:</span></span>
- <span data-ttu-id="065f3-128">**已向文件应用敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="065f3-128">**Applied sensitivity label to file**</span></span>
- <span data-ttu-id="065f3-129">**已更改应用于文件的敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="065f3-129">**Changed sensitivity label applied to file**</span></span>
- <span data-ttu-id="065f3-130">**已从文件除敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="065f3-130">**Removed sensitivity label from file**</span></span>

<span data-ttu-id="065f3-131">观看以下视频（无音频）以查看操作中的新功能：</span><span class="sxs-lookup"><span data-stu-id="065f3-131">Watch the following video (no audio) to see the new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

<span data-ttu-id="065f3-132">您始终可以选择在 SharePoint 和 OneDrive 中禁用 Office 文件的敏感度[标签（随时退出。](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)</span><span class="sxs-lookup"><span data-stu-id="065f3-132">You always have the choice to disable sensitivity labels for Office files in SharePoint and OneDrive ([opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="065f3-133">要求</span><span class="sxs-lookup"><span data-stu-id="065f3-133">Requirements</span></span>

<span data-ttu-id="065f3-134">这些新功能仅适用于[敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="065f3-134">These new capabilities work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="065f3-135">如果你当前有 Azure 信息保护标签，请首先将其迁移到敏感度标签，以便可以为上传的新文件启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="065f3-135">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="065f3-136">有关说明，请参阅[如何将 Azure 信息保护标签迁移到统一敏感度标签](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="065f3-136">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="065f3-137">在 Windows 上使用 OneDrive 同步应用程序版本19.002.0121.0008 或更高版本，在 Mac 上使用版本19.002.0107.0008 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="065f3-137">Use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="065f3-138">这两个版本都发布了2019年1月28日，并且当前已发布到所有震铃。</span><span class="sxs-lookup"><span data-stu-id="065f3-138">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="065f3-139">有关详细信息，请参阅[OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="065f3-139">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="065f3-140">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，运行较旧版本的同步应用程序的用户将被提示更新它。</span><span class="sxs-lookup"><span data-stu-id="065f3-140">After you enable sensitivity labels for Office files in SharePoint and OneDrive, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="065f3-141">限制</span><span class="sxs-lookup"><span data-stu-id="065f3-141">Limitations</span></span>

- <span data-ttu-id="065f3-142">SharePoint 不会自动将灵敏度标签应用于已使用 Azure 信息保护标签加密的现有文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-142">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="065f3-143">相反，若要在为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后运行这些功能，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="065f3-143">Instead, to get the features to work after you enable sensitivity labels for Office files in SharePoint and OneDrive, complete these tasks:</span></span>
    
    1. <span data-ttu-id="065f3-144">确保已[将 Azure 信息保护标签迁移](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)到了敏感度标签，并[已将其](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)从 Microsoft 365 合规性中心或等效的标签管理中心进行了发布。</span><span class="sxs-lookup"><span data-stu-id="065f3-144">Make sure you have [migrated the Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) to sensitivity labels and [published them](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="065f3-145">下载这些文件，然后将其上传到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="065f3-145">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="065f3-146">当应用了加密的标签具有以下[加密配置](encryption-sensitivity-labels.md#configure-encryption-settings)之一时，SharePoint 将无法处理加密文件：</span><span class="sxs-lookup"><span data-stu-id="065f3-146">SharePoint can't process encrypted files when the label that applied the encryption has either of the following [configurations for encryption](encryption-sensitivity-labels.md#configure-encryption-settings):</span></span>
    - <span data-ttu-id="065f3-147">**允许用户在应用标签时分配权限**，并在**Word、PowerPoint 和 Excel 中对复选框进行提示，并在 Word、PowerPoint 和 Excel 中选中 "提示用户指定权限**"。</span><span class="sxs-lookup"><span data-stu-id="065f3-147">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="065f3-148">此设置有时称为 "用户定义的权限"。</span><span class="sxs-lookup"><span data-stu-id="065f3-148">This setting is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="065f3-149">**用户对内容的访问权限**设置为**永不**过期的值。</span><span class="sxs-lookup"><span data-stu-id="065f3-149">**User access to content expires** is set to a value other than **Never**.</span></span>
    
    <span data-ttu-id="065f3-150">对于具有上述任一加密配置的标签，web 上的 Office 用户不会看到这些标签。</span><span class="sxs-lookup"><span data-stu-id="065f3-150">For labels with either of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="065f3-151">此外，不能将新功能用于已拥有这些加密设置的已标记文档。</span><span class="sxs-lookup"><span data-stu-id="065f3-151">Additionally, the new capabilities can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="065f3-152">例如，这些文档不会在搜索结果中返回，即使它们已更新也是如此。</span><span class="sxs-lookup"><span data-stu-id="065f3-152">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="065f3-153">对于向用户授予编辑权限的加密文档，不能在 Office 应用程序的 web 版本中阻止复制。</span><span class="sxs-lookup"><span data-stu-id="065f3-153">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="065f3-154">不支持 Azure 信息保护文档跟踪网站。</span><span class="sxs-lookup"><span data-stu-id="065f3-154">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="065f3-155">对于标记为加密的文件，Office 桌面应用程序和移动应用程序不支持共同创作。</span><span class="sxs-lookup"><span data-stu-id="065f3-155">Office desktop apps and mobile apps don't support coauthoring for files that are labeled with encryption.</span></span> <span data-ttu-id="065f3-156">这些应用将继续以独占编辑模式打开带标签和加密的文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-156">These apps continue to open labeled and encrypted files in exclusive editing mode.</span></span>

- <span data-ttu-id="065f3-157">如果管理员更改已应用于下载到用户同步客户端的文件的已发布标签的设置，则用户可能无法在其 OneDrive 同步文件夹中保存对文件所做的更改。</span><span class="sxs-lookup"><span data-stu-id="065f3-157">If an admin changes settings for a published label that's already applied to files downloaded to users' sync client, users might be unable to save changes they make to the file in their OneDrive Sync folder.</span></span> <span data-ttu-id="065f3-158">此方案适用于使用加密标记的文件，以及当标签更改来自未对其应用加密的标签的标签时。</span><span class="sxs-lookup"><span data-stu-id="065f3-158">This scenario applies to files that are labeled with encryption, and also when the label change is from a label that didn't apply encryption to a label that does apply encryption.</span></span> <span data-ttu-id="065f3-159">用户看到一个[带有白色交叉图标错误的红色圆圈](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，并要求他们将新的更改另存为一个单独副本。</span><span class="sxs-lookup"><span data-stu-id="065f3-159">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span> <span data-ttu-id="065f3-160">而是可以关闭和重新打开文件，或使用 web 上的 Office。</span><span class="sxs-lookup"><span data-stu-id="065f3-160">Instead, they can close and reopen the file, or use Office on the web.</span></span>

- <span data-ttu-id="065f3-161">如果将带标签的文档上载到 SharePoint，并使用服务主体名称中的帐户来应用加密，则无法在 web 上的 Office 中打开该文档。</span><span class="sxs-lookup"><span data-stu-id="065f3-161">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="065f3-162">示例方案包括 Microsoft 云应用安全和通过电子邮件发送给团队的文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-162">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="065f3-163">用户可以在脱机或进入睡眠模式后遇到保存问题，而不是在使用 Office 的情况下使用 Word、Excel 或 PowerPoint 的桌面和移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="065f3-163">Users can experience save problems after going offline or into a sleep mode when instead of using Office for the web, they use the desktop and mobile apps for Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="065f3-164">对于这些用户，当他们恢复 Office 应用程序会话并尝试保存更改时，他们会看到 "上载失败" 消息，其中包含一个用于保存副本而不是保存原始文件的选项。</span><span class="sxs-lookup"><span data-stu-id="065f3-164">For these users, when they resume their Office app session and try to save changes, they see an upload failure message with an option to save a copy instead of saving the original file.</span></span> 

- <span data-ttu-id="065f3-165">以下列方式加密的文档无法在 web 上的 Office 中打开：</span><span class="sxs-lookup"><span data-stu-id="065f3-165">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="065f3-166">使用本地密钥的加密（"保留自己的密钥" 或 HYOK）</span><span class="sxs-lookup"><span data-stu-id="065f3-166">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="065f3-167">独立于标签（例如，通过直接应用权限管理保护模板）应用的加密。</span><span class="sxs-lookup"><span data-stu-id="065f3-167">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="065f3-168">如果您删除了应用于 SharePoint 文档的标签，而不是从适用的标签策略中删除标签，则下载的文档不会被标记或加密。</span><span class="sxs-lookup"><span data-stu-id="065f3-168">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="065f3-169">相比之下，如果标记的文档存储在 SharePoint 外部，则在删除该标签时，该文档仍保持加密。</span><span class="sxs-lookup"><span data-stu-id="065f3-169">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="065f3-170">请注意，尽管您可以在测试阶段删除标签，但很少在生产环境中删除标签。</span><span class="sxs-lookup"><span data-stu-id="065f3-170">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a><span data-ttu-id="065f3-171">如何为 SharePoint 和 OneDrive 启用敏感度标签（自愿加入）</span><span class="sxs-lookup"><span data-stu-id="065f3-171">How to enable sensitivity labels for SharePoint and OneDrive (opt-in)</span></span>

<span data-ttu-id="065f3-172">您可以通过使用 Microsoft 365 合规性中心或使用 PowerShell 来启用新功能。</span><span class="sxs-lookup"><span data-stu-id="065f3-172">You can enable the new capabilities by using the Microsoft 365 compliance center, or by using PowerShell.</span></span>

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="065f3-173">使用合规性中心启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="065f3-173">Use the compliance center to enable support for sensitivity labels</span></span>

<span data-ttu-id="065f3-174">此选项是为 SharePoint 和 OneDrive 启用敏感度标签的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="065f3-174">This option is the easiest way to enable sensitivity labels for SharePoint and OneDrive.</span></span>

<span data-ttu-id="065f3-175">组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。</span><span class="sxs-lookup"><span data-stu-id="065f3-175">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="065f3-176">如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="065f3-176">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

1. <span data-ttu-id="065f3-177">登录[Microsoft 365 合规性中心](https://compliance.microsoft.com/)，并导航到 "**解决方案** > **信息保护**"</span><span class="sxs-lookup"><span data-stu-id="065f3-177">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com/), and navigate to **Solutions** > **Information protection**</span></span>
    
    <span data-ttu-id="065f3-178">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="065f3-178">If you don't immediately see this option, first select **Show all**.</span></span> 

2. <span data-ttu-id="065f3-179">如果您看到一条消息，以打开在 Office online 文件中处理内容的功能，请选择 **"立即打开"**：</span><span class="sxs-lookup"><span data-stu-id="065f3-179">If you see a message to turn on the ability to process content in Office online files, select **Turn on now**:</span></span>
    
    ![启用 "立即打开" 按钮以启用 Office Online 的敏感度标签](../media/sensitivity-labels-turn-on-banner.png)
    
    <span data-ttu-id="065f3-181">该命令将立即运行，当页面下次刷新时，您将不会再看到该消息或按钮。</span><span class="sxs-lookup"><span data-stu-id="065f3-181">The command runs immediately and when the page is next refreshed, you no longer see the message or button.</span></span> 

> [!NOTE]
> <span data-ttu-id="065f3-182">如果你有 Office 365 多地理位置，则必须使用 PowerShell 为你的所有地理位置启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="065f3-182">If you have Office 365 Multi-Geo, you must use PowerShell to enable these capabilities for all your geo-locations.</span></span> <span data-ttu-id="065f3-183">有关详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="065f3-183">See the next section for details.</span></span>

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="065f3-184">使用 PowerShell 启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="065f3-184">Use PowerShell to enable support for sensitivity labels</span></span>

<span data-ttu-id="065f3-185">作为使用合规性中心的替代方法，可以使用 SharePoint Online PowerShell 中的[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 启用敏感度标签支持。</span><span class="sxs-lookup"><span data-stu-id="065f3-185">As an alternative to using the compliance center, you can enable support for sensitivity labels by using the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet from SharePoint Online PowerShell.</span></span> 

<span data-ttu-id="065f3-186">如果你有 Office 365 多地理位置，则必须使用 PowerShell 为你的所有地理位置启用此支持。</span><span class="sxs-lookup"><span data-stu-id="065f3-186">If you have Office 365 Multi-Geo, you must use PowerShell to enable this support for all your geo-locations.</span></span>

#### <a name="prepare-the-sharepoint-online-management-shell"></a><span data-ttu-id="065f3-187">准备 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="065f3-187">Prepare the SharePoint Online Management Shell</span></span>

<span data-ttu-id="065f3-188">在运行 PowerShell 命令以在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，请确保您运行的是 SharePoint Online 命令行管理程序版本16.0.19418.12000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="065f3-188">Before you run the PowerShell command to enable sensitivity labels for Office files in SharePoint and OneDrive, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or later.</span></span> <span data-ttu-id="065f3-189">如果已有最新版本，则可以跳至[下一过程](#run-the-powershell-command-to-enable-support-for-sensitivity-labels)以运行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="065f3-189">If you already have the latest version, you can skip to [next procedure](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) to run the PowerShell command.</span></span>

1. <span data-ttu-id="065f3-190">如果已从 PowerShell 库安装早期版本的 SharePoint Online 命令行管理程序，可通过运行以下 cmdlet 来更新模块。</span><span class="sxs-lookup"><span data-stu-id="065f3-190">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="065f3-191">或者，如果您已从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到 "**添加或删除程序**"，然后卸载 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="065f3-191">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="065f3-192">在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="065f3-192">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="065f3-193">选择语言，然后单击“**下载**”。</span><span class="sxs-lookup"><span data-stu-id="065f3-193">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="065f3-194">在 x64 和 x86.msi 文件之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="065f3-194">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="065f3-195">如果运行的是64位版本的 Windows 或 x86 文件（如果运行32位版本），请下载 x64 文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-195">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="065f3-196">如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="065f3-196">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>

6. <span data-ttu-id="065f3-197">下载文件后，运行文件并按照安装向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="065f3-197">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="065f3-198">运行 PowerShell 命令以启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="065f3-198">Run the PowerShell command to enable support for sensitivity labels</span></span>

<span data-ttu-id="065f3-199">若要启用新功能，请将[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Cmdlet 与*EnableAIPIntegration*参数一起使用：</span><span class="sxs-lookup"><span data-stu-id="065f3-199">To enable the new capabilities, use the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *EnableAIPIntegration* parameter:</span></span>

1. <span data-ttu-id="065f3-200">在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="065f3-200">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="065f3-201">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="065f3-201">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>
    
    <span data-ttu-id="065f3-202">注意：如果你拥有 Office 365 多地理位置，请使用-Url 参数和[connect-sposervice](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，并为你的某个地理位置指定 SharePoint Online 管理中心网站 Url。</span><span class="sxs-lookup"><span data-stu-id="065f3-202">Note: If you have Office 365 Multi-Geo, use the -Url parameter with [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), and specify the SharePoint Online Administration Center site URL for one of your geo-locations.</span></span>

2. <span data-ttu-id="065f3-203">运行以下命令，然后按**Y**确认：</span><span class="sxs-lookup"><span data-stu-id="065f3-203">Run the following command and press **Y** to confirm:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. <span data-ttu-id="065f3-204">对于 Office 365 多地理位置：对剩下的每个地理位置重复步骤1和2。</span><span class="sxs-lookup"><span data-stu-id="065f3-204">For Office 365 Multi-Geo: Repeat steps 1 and 2 for each of your remaining geo-locations.</span></span>

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="065f3-205">创建或更改敏感度标签后计划回滚</span><span class="sxs-lookup"><span data-stu-id="065f3-205">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="065f3-206">在 Microsoft 365 合规性中心中创建或更改灵敏度标签后，请分阶段发布它。</span><span class="sxs-lookup"><span data-stu-id="065f3-206">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="065f3-207">如果您发布尚未完全同步的标签，则当用户将标签应用于文件并将其上传到 SharePoint 时，将无法在 Office 应用程序的 web 版本中打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-207">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="065f3-208">搜索和电子数据展示也不适用于这些文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-208">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="065f3-209">我们建议您按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="065f3-209">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="065f3-210">仅将新的或修改的敏感度标签发布给一个或两个人。</span><span class="sxs-lookup"><span data-stu-id="065f3-210">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="065f3-211">在初始发布后至少等待24小时。</span><span class="sxs-lookup"><span data-stu-id="065f3-211">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="065f3-212">验证标签是否已完全同步。</span><span class="sxs-lookup"><span data-stu-id="065f3-212">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="065f3-213">更广泛地发布标签。</span><span class="sxs-lookup"><span data-stu-id="065f3-213">Publish the label more broadly.</span></span>

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a><span data-ttu-id="065f3-214">如何禁用 SharePoint 和 OneDrive 的敏感度标签（自愿退出）</span><span class="sxs-lookup"><span data-stu-id="065f3-214">How to disable sensitivity labels for SharePoint and OneDrive (opt-out)</span></span>

<span data-ttu-id="065f3-215">如果禁用这些新功能，则在对 SharePoint 和 OneDrive 启用敏感度标签后上载的文件将继续受标签保护，因为仍会继续强制实施标签设置。</span><span class="sxs-lookup"><span data-stu-id="065f3-215">If you disable these new capabilities, files that you uploaded after you enabled sensitivity labels for SharePoint and OneDrive continue to be protected by the label because the label settings continue to be enforced.</span></span> <span data-ttu-id="065f3-216">在禁用这些新功能之后将灵敏度标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="065f3-216">When you apply sensitivity labels to new files after you disable these new capabilities, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="065f3-217">若要禁用这些新功能，必须使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="065f3-217">To disable these new capabilities, you must use PowerShell.</span></span> <span data-ttu-id="065f3-218">使用 SharePoint Online 命令行管理程序和[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 指定相同的*EnableAIPIntegration*参数，如[使用 PowerShell 启用对灵敏度标签的支持](#use-powershell-to-enable-support-for-sensitivity-labels)部分中所述。</span><span class="sxs-lookup"><span data-stu-id="065f3-218">Using the SharePoint Online Management Shell and the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet, specify the same *EnableAIPIntegration* parameter as described in the [Use PowerShell to enable support for sensitivity labels](#use-powershell-to-enable-support-for-sensitivity-labels) section.</span></span> <span data-ttu-id="065f3-219">但这次，请将参数值设置为 false，然后按**Y**确认：</span><span class="sxs-lookup"><span data-stu-id="065f3-219">But this time, set the parameter value to false and press **Y** to confirm:</span></span>

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

<span data-ttu-id="065f3-220">如果你有 Office 365 多地理位置，则必须对每个地理位置运行此命令。</span><span class="sxs-lookup"><span data-stu-id="065f3-220">If you have Office 365 Multi-Geo, you must run this command for each of your geo-locations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="065f3-221">后续步骤</span><span class="sxs-lookup"><span data-stu-id="065f3-221">Next steps</span></span>

<span data-ttu-id="065f3-222">在 SharePoint 和 OneDrive 中为 Office 文件启用了敏感度标签后，请考虑使用自动标记策略自动标记这些文件。</span><span class="sxs-lookup"><span data-stu-id="065f3-222">After you've enabled sensitivity labels for Office files in SharePoint and OneDrive, consider automatically labeling these files by using auto-labeling policies.</span></span> <span data-ttu-id="065f3-223">有关详细信息，请参阅[自动将敏感度标签应用于内容](apply-sensitivity-label-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="065f3-223">For more information, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>