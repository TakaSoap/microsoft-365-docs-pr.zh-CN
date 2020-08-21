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
description: 管理员可以为 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件启用敏感度标签支持。
ms.openlocfilehash: d049cdd61d2155267f4e55c612885929e27adaaa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845718"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a><span data-ttu-id="79185-103">启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="79185-103">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>

><span data-ttu-id="79185-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="79185-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="79185-105">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签之前，无法在 Office [网页](sensitivity-labels.md) 版中应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="79185-105">Before you enable sensitivity labels for Office files in SharePoint and OneDrive, you can't apply your [sensitivity labels](sensitivity-labels.md) in Office on the web.</span></span> <span data-ttu-id="79185-106">功能区上不会看到 **"敏感度"** 按钮，也不会在状态栏上看到已应用的标签名称。</span><span class="sxs-lookup"><span data-stu-id="79185-106">You don't see the **Sensitivity** button on the ribbon, or the applied label name on the status bar.</span></span> <span data-ttu-id="79185-107">此外，如果你使用桌面应用程序标记文件，然后将其保存到 SharePoint 或 OneDrive 上，那么如果标签已应用加密，则服务将无法处理这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="79185-107">In addition, if you use desktop apps to label your files and then save them on SharePoint or OneDrive, the service can't process the content of these files if the label applied encryption.</span></span> <span data-ttu-id="79185-108">共同创作、电子数据展示、数据丢失防护、搜索和其他协作功能在这些情况下将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="79185-108">Coauthoring, eDiscovery, Data Loss Prevention, search, and other collaborative features won't work under these circumstances.</span></span>

<span data-ttu-id="79185-109">为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签时，会启用所有这些功能。</span><span class="sxs-lookup"><span data-stu-id="79185-109">When you do enable sensitivity labels for Office files in SharePoint and OneDrive, all these capabilities are enabled.</span></span> <span data-ttu-id="79185-110">除了向用户显示敏感度标签，不仅是为应用了敏感度标签的新文件和已更改的文件，该标签包含通过基于云的密钥 (加密，并且不使用 [双密钥加密](double-key-encryption.md)) ：</span><span class="sxs-lookup"><span data-stu-id="79185-110">In addition to displaying sensitivity labels to users, for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key (and doesn't use [Double Key Encryption](double-key-encryption.md)):</span></span>

- <span data-ttu-id="79185-111">对于 Word、Excel 和 PowerPoint 文件，SharePoint 可识别标签，并且现在能够处理加密文件的内容。</span><span class="sxs-lookup"><span data-stu-id="79185-111">For Word, Excel, and PowerPoint files, SharePoint recognizes the label and is now able to process the contents of the encrypted file.</span></span>

- <span data-ttu-id="79185-112">从 SharePoint 或 OneDrive 下载或访问这些文件时，将强制执行敏感度标签及标签中任何加密设置，且不随着文件存储在何处保留。</span><span class="sxs-lookup"><span data-stu-id="79185-112">When you download or access these files from SharePoint or OneDrive, the sensitivity label and any encryption settings from the label are enforced and remain with the file, wherever it is stored.</span></span> <span data-ttu-id="79185-113">确保提供用户指导，以仅使用标签来保护文档。</span><span class="sxs-lookup"><span data-stu-id="79185-113">Ensure you provide user guidance to use only labels to protect documents.</span></span> <span data-ttu-id="79185-114">有关详细信息，请参阅 [IRM 文件和 () 标签管理工具包的信息权限管理](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="79185-114">For more information, see [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).</span></span>

- <span data-ttu-id="79185-115">当用户将标记的和加密文件上载到 SharePoint 时，必须至少对这些文件拥有查看权限。</span><span class="sxs-lookup"><span data-stu-id="79185-115">When users upload labeled and encrypted files to SharePoint, they must have at least view rights to those files.</span></span> <span data-ttu-id="79185-116">例如，用户可以在 SharePoint 外部打开文件。</span><span class="sxs-lookup"><span data-stu-id="79185-116">For example, they can open the files outside SharePoint.</span></span> <span data-ttu-id="79185-117">如果它们没有此最低使用权限，则上传会成功，但 SharePoint 不会识别标签并且无法处理文件内容。</span><span class="sxs-lookup"><span data-stu-id="79185-117">If they don't have this minimum usage right, the upload is successful but SharePoint doesn't recognize the label and can't process the file contents.</span></span>

- <span data-ttu-id="79185-118">使用 Office 网页版 (Word、Excel、PowerPoint) 打开和编辑具有应用加密的敏感度标签的 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="79185-118">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="79185-119">强制实施通过加密分配的权限。</span><span class="sxs-lookup"><span data-stu-id="79185-119">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="79185-120">在 Word 网页版中，你还可以在编辑这些文档时使用自动标记功能。</span><span class="sxs-lookup"><span data-stu-id="79185-120">With Word on the web, you can also use auto-labeling when you edit these documents.</span></span>

- <span data-ttu-id="79185-121">外部用户可以通过使用来宾帐户访问标记为加密的文档。</span><span class="sxs-lookup"><span data-stu-id="79185-121">External users can access documents that are labeled with encryption by using guest accounts.</span></span> <span data-ttu-id="79185-122">有关详细信息，请参阅 [支持外部用户和标记内容](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content)。</span><span class="sxs-lookup"><span data-stu-id="79185-122">For more information, see [Support for external users and labeled content](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).</span></span>

- <span data-ttu-id="79185-123">Office 365 电子数据展示支持对这些文件和数据丢失防 (DLP 策略) 制支持这些文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="79185-123">Office 365 eDiscovery supports full-text search for these files and Data Loss Prevention (DLP) policies support content in these files.</span></span>

> [!NOTE]
> <span data-ttu-id="79185-124">如果已通过本地密钥 (应用加密是一种通常称为"保留自己的密钥"或 HYOK) 的密钥管理拓扑，或者使用 [双键](double-key-encryption.md)加密，则用于处理文件内容的 SharePoint 行为不会改变。</span><span class="sxs-lookup"><span data-stu-id="79185-124">If encryption has been applied with an on-premises key (a key management topology often referred to as "hold your own key" or HYOK), or by using [Double Key Encryption](double-key-encryption.md), the SharePoint behavior for processing the file contents doesn't change.</span></span>
>
> <span data-ttu-id="79185-125">对于 SharePoint 中使用单个基于 Azure 的密钥加密进行了标记的现有文件，SharePoint 行为也不会发生改变。</span><span class="sxs-lookup"><span data-stu-id="79185-125">The SharePoint behavior also doesn't change for existing files in SharePoint that are labeled with encryption using a single Azure-based key.</span></span> <span data-ttu-id="79185-126">为了使这些文件能够受益于在 SharePoint 和 OneDrive 中为 Office 文件启用了敏感度标签后，必须重新下载和上传这些文件或进行编辑。</span><span class="sxs-lookup"><span data-stu-id="79185-126">For these files to benefit from the new capabilities after you enable sensitivity labels for Office files in SharePoint and OneDrive, the files must be either downloaded and uploaded again, or edited.</span></span> <span data-ttu-id="79185-127">例如，在搜索结果中将返回它们。</span><span class="sxs-lookup"><span data-stu-id="79185-127">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="79185-128">在 SharePoint 和 OneDrive 中为 Office 文件启用敏感度标签后，SharePoint 和 OneDrive 中的文档可用于监视敏感度标签的三种新的审核事件： [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)</span><span class="sxs-lookup"><span data-stu-id="79185-128">After you enable sensitivity labels for Office files in SharePoint and OneDrive, three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied to documents in SharePoint and OneDrive:</span></span>

- <span data-ttu-id="79185-129">**已向文件应用敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="79185-129">**Applied sensitivity label to file**</span></span>
- <span data-ttu-id="79185-130">**已更改应用于文件的敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="79185-130">**Changed sensitivity label applied to file**</span></span>
- <span data-ttu-id="79185-131">**已从文件除敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="79185-131">**Removed sensitivity label from file**</span></span>

<span data-ttu-id="79185-132">观看以下没有 (视频，) 查看当前运行的新功能：</span><span class="sxs-lookup"><span data-stu-id="79185-132">Watch the following video (no audio) to see the new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

<span data-ttu-id="79185-133">始终可以选择为 SharePoint 和 OneDrive 中的 Office 文件禁用敏感度标签， ([选择退](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) 出。</span><span class="sxs-lookup"><span data-stu-id="79185-133">You always have the choice to disable sensitivity labels for Office files in SharePoint and OneDrive ([opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) at any time.</span></span>

<span data-ttu-id="79185-134">如果当前正使用 SharePoint 信息权限管理 (IRM) 来保护 SharePoint 中的文档，请务必查看此 [页面上的"SharePoint 信息权限管理 (IRM) ](#sharepoint-information-rights-management-irm-and-sensitivity-labels) 和敏感度标签"部分。</span><span class="sxs-lookup"><span data-stu-id="79185-134">If you are currently protecting documents in SharePoint by using SharePoint Information Rights Management (IRM), be sure to check the [SharePoint Information Rights Management (IRM) and sensitivity labels](#sharepoint-information-rights-management-irm-and-sensitivity-labels) section on this page.</span></span>

## <a name="requirements"></a><span data-ttu-id="79185-135">Requirements</span><span class="sxs-lookup"><span data-stu-id="79185-135">Requirements</span></span>

<span data-ttu-id="79185-136">这些新功能 [仅适用于敏感度标签](sensitivity-labels.md) 。</span><span class="sxs-lookup"><span data-stu-id="79185-136">These new capabilities work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="79185-137">如果目前拥有 Azure 信息保护标签，请首先将它们迁移到敏感度标签，以便为上传的新文件启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="79185-137">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="79185-138">有关说明， [请参阅"如何将 Azure 信息保护标签迁移到统一敏感度标签"](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="79185-138">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="79185-139">在 Windows 上使用 OneDrive 同步应用版本 19.002.0121.0008 或更高版本，以及 Mac 版本 19.002.0107.0008 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="79185-139">Use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="79185-140">这两个版本是 2019 年 1 月 28 日发布的，目前已向所有圈发布。</span><span class="sxs-lookup"><span data-stu-id="79185-140">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="79185-141">有关详细信息，请参阅 [OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="79185-141">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="79185-142">为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后，系统会提示运行较早版本的同步应用的用户进行更新。</span><span class="sxs-lookup"><span data-stu-id="79185-142">After you enable sensitivity labels for Office files in SharePoint and OneDrive, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="79185-143">限制</span><span class="sxs-lookup"><span data-stu-id="79185-143">Limitations</span></span>

- <span data-ttu-id="79185-144">SharePoint 不会自动将敏感度标签应用于已使用 Azure 信息保护标签加密的现有文件。</span><span class="sxs-lookup"><span data-stu-id="79185-144">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="79185-145">相反，为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后，这些功能的工作方式就完成了以下任务：</span><span class="sxs-lookup"><span data-stu-id="79185-145">Instead, for the features to work after you enable sensitivity labels for Office files in SharePoint and OneDrive, complete these tasks:</span></span>

    1. <span data-ttu-id="79185-146">确保已将 [Azure 信息保护标签迁移到](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 敏感度标签，并 [从](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) Microsoft 365 合规中心或等效标签管理中心发布了这些标签。</span><span class="sxs-lookup"><span data-stu-id="79185-146">Make sure you have [migrated the Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) to sensitivity labels and [published them](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>

    2. <span data-ttu-id="79185-147">下载文件，然后将其上载到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="79185-147">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="79185-148">当应用加密的标签具有以下加密配置之一时，SharePoint 无法 [处理加密的文件](encryption-sensitivity-labels.md#configure-encryption-settings)：</span><span class="sxs-lookup"><span data-stu-id="79185-148">SharePoint can't process encrypted files when the label that applied the encryption has any of the following [configurations for encryption](encryption-sensitivity-labels.md#configure-encryption-settings):</span></span>

  - <span data-ttu-id="79185-149">**允许用户在应用标签时分配权限** ，并在 **Word、PowerPoint** 和 Excel 中提示用户指定权限。</span><span class="sxs-lookup"><span data-stu-id="79185-149">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="79185-150">此设置有时称为"用户定义权限"。</span><span class="sxs-lookup"><span data-stu-id="79185-150">This setting is sometimes referred to as "user-defined permissions".</span></span>
  - <span data-ttu-id="79185-151">**将用户访问内容的到** 期时间设置为非"从不 **"的值**。</span><span class="sxs-lookup"><span data-stu-id="79185-151">**User access to content expires** is set to a value other than **Never**.</span></span>
  - <span data-ttu-id="79185-152">**选择双密钥** 加密。</span><span class="sxs-lookup"><span data-stu-id="79185-152">**Double Key Encryption** is selected.</span></span>

  <span data-ttu-id="79185-153">对于具有其中任意一种加密配置的标签，标签不会向 Office 网页版中的用户显示。</span><span class="sxs-lookup"><span data-stu-id="79185-153">For labels with any of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="79185-154">此外，新功能不能与已经具有这些加密设置的已标记文档一起使用。</span><span class="sxs-lookup"><span data-stu-id="79185-154">Additionally, the new capabilities can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="79185-155">例如，即使这些文档已更新，搜索结果也不会返回至这些文档。</span><span class="sxs-lookup"><span data-stu-id="79185-155">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="79185-156">对于向用户授予编辑权限的加密文档，不能在 Office 应用的 Web 版本中阻止复制。</span><span class="sxs-lookup"><span data-stu-id="79185-156">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="79185-157">不支持 Azure 信息保护文档跟踪网站。</span><span class="sxs-lookup"><span data-stu-id="79185-157">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="79185-158">Office 桌面应用程序和移动应用程序不支持合著文件，但它们具有加密标记。</span><span class="sxs-lookup"><span data-stu-id="79185-158">Office desktop apps and mobile apps don't support coauthoring for files that are labeled with encryption.</span></span> <span data-ttu-id="79185-159">这些应用继续在独占编辑模式下打开已标记和加密的文件。</span><span class="sxs-lookup"><span data-stu-id="79185-159">These apps continue to open labeled and encrypted files in exclusive editing mode.</span></span>

- <span data-ttu-id="79185-160">如果管理员更改已应用于已下载到用户同步客户端的文件的已发布标签的设置，用户可能无法将对文件所做的更改保存在 OneDrive 同步文件夹中。</span><span class="sxs-lookup"><span data-stu-id="79185-160">If an admin changes settings for a published label that's already applied to files downloaded to users' sync client, users might be unable to save changes they make to the file in their OneDrive Sync folder.</span></span> <span data-ttu-id="79185-161">此方案适用于使用加密标记的文件，而且标签更改情况也适用于未对应用加密应用加密的标签应用加密的标签。</span><span class="sxs-lookup"><span data-stu-id="79185-161">This scenario applies to files that are labeled with encryption, and also when the label change is from a label that didn't apply encryption to a label that does apply encryption.</span></span> <span data-ttu-id="79185-162">用户会 [看到一个带白色交叉图标错误的](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)红色圆圈，他们会要求将新更改保存为单独的副本。</span><span class="sxs-lookup"><span data-stu-id="79185-162">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span> <span data-ttu-id="79185-163">相反，他们可以关闭并重新打开文件，或使用 Office 网页版。</span><span class="sxs-lookup"><span data-stu-id="79185-163">Instead, they can close and reopen the file, or use Office on the web.</span></span>

- <span data-ttu-id="79185-164">如果标签的文档上传到 SharePoint，且标签使用服务主体名称帐户的帐户应用了加密，则无法在 Office 网页版中打开该文档。</span><span class="sxs-lookup"><span data-stu-id="79185-164">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="79185-165">示例方案包括 Microsoft Cloud App Security 和通过电子邮件发送到 Teams 的文件。</span><span class="sxs-lookup"><span data-stu-id="79185-165">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="79185-166">在脱机运行后或进入睡眠模式而不使用 Office 网页版时，用户可能会遇到保存问题，而对 Word、Excel 或 PowerPoint 使用桌面和移动应用。</span><span class="sxs-lookup"><span data-stu-id="79185-166">Users can experience save problems after going offline or into a sleep mode when instead of using Office for the web, they use the desktop and mobile apps for Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="79185-167">对于这些用户，当用户恢复其 Office 应用会话并尝试保存更改时，他们会看到上传失败消息，其中会显示一条上传失败消息，提供保存副本的选项，而不是保存原始文件。</span><span class="sxs-lookup"><span data-stu-id="79185-167">For these users, when they resume their Office app session and try to save changes, they see an upload failure message with an option to save a copy instead of saving the original file.</span></span>

- <span data-ttu-id="79185-168">在 Office 网页版中，无法以以下方式打开已通过以下方式加密的文档：</span><span class="sxs-lookup"><span data-stu-id="79185-168">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>

  - <span data-ttu-id="79185-169">使用本地密钥的加密 ("保留自己的密钥"或 HYOK) </span><span class="sxs-lookup"><span data-stu-id="79185-169">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
  - <span data-ttu-id="79185-170">通过双密钥加密 [应用的加密](double-key-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="79185-170">Encryption that was applied by using [Double Key Encryption](double-key-encryption.md)</span></span>
  - <span data-ttu-id="79185-171">独立于标签应用的加密（例如，通过直接应用权限管理保护模板）。</span><span class="sxs-lookup"><span data-stu-id="79185-171">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="79185-172">如果从共享中删除已应用到文档的标签，而不是从适用标签策略中删除标签，下载的文档将不会标记或加密。</span><span class="sxs-lookup"><span data-stu-id="79185-172">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="79185-173">相比之下，如果标签的文档存储在 SharePoint 外部，则该文档将保持加密状态（如果删除了标签）。</span><span class="sxs-lookup"><span data-stu-id="79185-173">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="79185-174">请注意，虽然在测试阶段可能会删除标签，但删除生产环境中的标签非常少。</span><span class="sxs-lookup"><span data-stu-id="79185-174">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a><span data-ttu-id="79185-175">如何为 SharePoint 和 OneDrive 文件启用敏感度 (选择加入) </span><span class="sxs-lookup"><span data-stu-id="79185-175">How to enable sensitivity labels for SharePoint and OneDrive (opt-in)</span></span>

<span data-ttu-id="79185-176">可以使用 Microsoft 365 合规中心或使用 PowerShell 启用新功能。</span><span class="sxs-lookup"><span data-stu-id="79185-176">You can enable the new capabilities by using the Microsoft 365 compliance center, or by using PowerShell.</span></span>

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="79185-177">使用合规中心启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="79185-177">Use the compliance center to enable support for sensitivity labels</span></span>

<span data-ttu-id="79185-178">此选项是为 SharePoint 和 OneDrive 启用敏感度标签的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="79185-178">This option is the easiest way to enable sensitivity labels for SharePoint and OneDrive.</span></span>

<span data-ttu-id="79185-179">组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。</span><span class="sxs-lookup"><span data-stu-id="79185-179">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="79185-180">如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="79185-180">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

1. <span data-ttu-id="79185-181">登录到 Microsoft [365 合规中心，](https://compliance.microsoft.com/)然后导航到**Solutions**解决方案  >  **信息保护**</span><span class="sxs-lookup"><span data-stu-id="79185-181">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com/), and navigate to **Solutions** > **Information protection**</span></span>

    <span data-ttu-id="79185-182">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="79185-182">If you don't immediately see this option, first select **Show all**.</span></span>

2. <span data-ttu-id="79185-183">如果看到一条消息显示用于处理 Office 在线文件中的内容，请选择 **"立即启用"**</span><span class="sxs-lookup"><span data-stu-id="79185-183">If you see a message to turn on the ability to process content in Office online files, select **Turn on now**:</span></span>

    ![打开"立即"按钮以为 Office Online 启用敏感度标签](../media/sensitivity-labels-turn-on-banner.png)

    <span data-ttu-id="79185-185">命令立即运行，并且下次刷新页面时，您不再看到消息或按钮。</span><span class="sxs-lookup"><span data-stu-id="79185-185">The command runs immediately and when the page is next refreshed, you no longer see the message or button.</span></span>

> [!NOTE]
> <span data-ttu-id="79185-186">如果你拥有 Microsoft 365 多地理位置，则必须使用 PowerShell 为所有地理位置启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="79185-186">If you have Microsoft 365 Multi-Geo, you must use PowerShell to enable these capabilities for all your geo-locations.</span></span> <span data-ttu-id="79185-187">有关详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="79185-187">See the next section for details.</span></span>

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="79185-188">使用 PowerShell 启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="79185-188">Use PowerShell to enable support for sensitivity labels</span></span>

<span data-ttu-id="79185-189">作为使用合规中心的替代方法，你可以在 SharePoint Online PowerShell 中使用 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 启用对敏感度标签的支持。</span><span class="sxs-lookup"><span data-stu-id="79185-189">As an alternative to using the compliance center, you can enable support for sensitivity labels by using the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet from SharePoint Online PowerShell.</span></span>

<span data-ttu-id="79185-190">如果你拥有 Microsoft 365 多地理位置，则必须使用 PowerShell 支持所有地理位置。</span><span class="sxs-lookup"><span data-stu-id="79185-190">If you have Microsoft 365 Multi-Geo, you must use PowerShell to enable this support for all your geo-locations.</span></span>

#### <a name="prepare-the-sharepoint-online-management-shell"></a><span data-ttu-id="79185-191">准备 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="79185-191">Prepare the SharePoint Online Management Shell</span></span>

<span data-ttu-id="79185-192">在运行 PowerShell 命令以启用 SharePoint 和 OneDrive 中的 Office 文件的敏感度标签之前，请确保你正在运行 SharePoint Online 命令行管理程序版本 16.0.19418.12000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="79185-192">Before you run the PowerShell command to enable sensitivity labels for Office files in SharePoint and OneDrive, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or later.</span></span> <span data-ttu-id="79185-193">如果已有最新版本，可跳到 [下一过程以](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) 运行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="79185-193">If you already have the latest version, you can skip to [next procedure](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) to run the PowerShell command.</span></span>

1. <span data-ttu-id="79185-194">如果已从 PowerShell 库安装早期版本的 SharePoint Online 命令行管理程序，可通过运行以下 cmdlet 来更新模块。</span><span class="sxs-lookup"><span data-stu-id="79185-194">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="79185-195">或者，如果从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到" **添加或删除程序"，** 然后卸载 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="79185-195">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="79185-196">在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="79185-196">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="79185-197">选择语言，然后单击“**下载**”。</span><span class="sxs-lookup"><span data-stu-id="79185-197">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="79185-198">在 x64 和 x86.msi 文件之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="79185-198">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="79185-199">如果运行 64 位版本的 Windows，请下载 x64 文件;如果运行 32 位版本，请下载 x86 文件。</span><span class="sxs-lookup"><span data-stu-id="79185-199">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="79185-200">如果你不知道，请参阅 [我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="79185-200">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>

6. <span data-ttu-id="79185-201">下载文件后，运行该文件并按照安装向导中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="79185-201">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a><span data-ttu-id="79185-202">运行 PowerShell 命令启用敏感度标签支持</span><span class="sxs-lookup"><span data-stu-id="79185-202">Run the PowerShell command to enable support for sensitivity labels</span></span>

<span data-ttu-id="79185-203">要启用新功能，请将 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 与 *EnableAIPIntegration 参数一起* 使用：</span><span class="sxs-lookup"><span data-stu-id="79185-203">To enable the new capabilities, use the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *EnableAIPIntegration* parameter:</span></span>

1. <span data-ttu-id="79185-204">使用在 Microsoft 365 中拥有全局管理员或 SharePoint 管理员权限的工作或学校帐户，连接到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="79185-204">Using a work or school account that has global administrator or SharePoint admin privileges in Microsoft 365, connect to SharePoint.</span></span> <span data-ttu-id="79185-205">若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="79185-205">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

    <span data-ttu-id="79185-206">注意：如果你有 Microsoft 365 多地理位置，请将 -Url 参数与 [Connect-SPOService 结合使用](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)，并为一个地理位置指定 SharePoint Online 管理中心网站 URL。</span><span class="sxs-lookup"><span data-stu-id="79185-206">Note: If you have Microsoft 365 Multi-Geo, use the -Url parameter with [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), and specify the SharePoint Online Administration Center site URL for one of your geo-locations.</span></span>

2. <span data-ttu-id="79185-207">运行以下命令，然后按 **Y** 以确认：</span><span class="sxs-lookup"><span data-stu-id="79185-207">Run the following command and press **Y** to confirm:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```

3. <span data-ttu-id="79185-208">对于 Microsoft 365 多地理位置：为其余每个地理位置重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="79185-208">For Microsoft 365 Multi-Geo: Repeat steps 1 and 2 for each of your remaining geo-locations.</span></span>

## <a name="publishing-and-changing-sensitivity-labels"></a><span data-ttu-id="79185-209">发布和更改敏感度标签</span><span class="sxs-lookup"><span data-stu-id="79185-209">Publishing and changing sensitivity labels</span></span>

<span data-ttu-id="79185-210">将敏感度标签与 SharePoint 和 OneDrive 一起使用时，请记住，在发布新的敏感度标签或更新现有敏感度标签时，你需要允许复制。</span><span class="sxs-lookup"><span data-stu-id="79185-210">When you use sensitivity labels with SharePoint and OneDrive, keep in mind that you need to allow for replication time when you publish new sensitivity labels or update existing sensitivity labels.</span></span> <span data-ttu-id="79185-211">这一点对于应用加密的新标签尤其重要。</span><span class="sxs-lookup"><span data-stu-id="79185-211">This is especially important for new labels that apply encryption.</span></span>

<span data-ttu-id="79185-212">例如：你创建并发布一个应用加密的新敏感度标签，此标签会很快地显示在用户的桌面应用中。</span><span class="sxs-lookup"><span data-stu-id="79185-212">For example: You create and publish a new sensitivity label that applies encryption and it very quickly appears in a user's desktop app.</span></span> <span data-ttu-id="79185-213">用户为文档应用此标签，再将其上传到 SharePoint 或 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="79185-213">The user applies this label to a document and then uploads it to SharePoint or OneDrive.</span></span> <span data-ttu-id="79185-214">如果服务未完成标签复制，则上传时不会向该文档应用新功能。</span><span class="sxs-lookup"><span data-stu-id="79185-214">If the label replication hasn't completed for the service, the new capabilities won't be applied to that document on upload.</span></span> <span data-ttu-id="79185-215">因此，不会在搜索中或对电子数据展示返回文档，并且无法在 Office 网页版中打开文档。</span><span class="sxs-lookup"><span data-stu-id="79185-215">As a result, the document won't be returned in search or for eDiscovery and the document can't be opened in Office for the web.</span></span>

- <span data-ttu-id="79185-216">以下更改在一小时内复制："新建和删除的敏感度标签"以及包含标签在策略中的敏感度标签策略设置。</span><span class="sxs-lookup"><span data-stu-id="79185-216">The following changes replicate within one hour: New and deleted sensitivity labels, and sensitivity label policy settings that include which labels are in the policy.</span></span>

- <span data-ttu-id="79185-217">以下更改在 24 小时内复制：对现有标签的敏感度标签设置的更改。</span><span class="sxs-lookup"><span data-stu-id="79185-217">The following changes replicate within 24 hours: Changes to sensitivity label settings for existing labels.</span></span>

<span data-ttu-id="79185-218">因为对于新的敏感度标签，复制延迟现在仅保留一小时，因此在示例中不可能遇到此方案。</span><span class="sxs-lookup"><span data-stu-id="79185-218">Because the replication delay is now only one hour for new sensitivity labels, you are unlikely to run into the scenario in the example.</span></span> <span data-ttu-id="79185-219">但作为一项安全措值，建议首先只向少量测试用户发布新标签，等待一小时，然后验证 SharePoint 和 OneDrive 上的标签行为。</span><span class="sxs-lookup"><span data-stu-id="79185-219">But as a safeguard, we recommend publishing new labels to just a few test users first, wait for an hour, and then verify the label behavior on SharePoint and OneDrive.</span></span> <span data-ttu-id="79185-220">最后，通过向现有标签策略添加更多用户，或将标签添加到标准用户的现有标签策略，使更多用户也可以使用标签。</span><span class="sxs-lookup"><span data-stu-id="79185-220">As the final step, make the label available to more users by either adding more users to the existing label policy, or add the label to an existing label policy for your standard users.</span></span> <span data-ttu-id="79185-221">当标准用户看到标签时，它已同步到 SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="79185-221">At the time your standard users see the label, it has already synchronized to SharePoint and OneDrive.</span></span>

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a><span data-ttu-id="79185-222">SharePoint IRM 文件和 () 标签 (SharePoint 信息权限管理</span><span class="sxs-lookup"><span data-stu-id="79185-222">SharePoint Information Rights Management (IRM) and sensitivity labels</span></span>

<span data-ttu-id="79185-223">[SharePoint 信息权限管理 (IRM) ](set-up-irm-in-sp-admin-center.md) 一种较旧的技术，它在下载文件时应用加密和限制来保护列表和库级别的文件。</span><span class="sxs-lookup"><span data-stu-id="79185-223">[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) is an older technology to protect files at the list and library level by applying encryption and restrictions when files are downloaded.</span></span> <span data-ttu-id="79185-224">这种较旧的保护技术旨在防止未经授权的用户在文件位于 SharePoint 外部时打开该文件。</span><span class="sxs-lookup"><span data-stu-id="79185-224">This older protection technology is designed to prevent unauthorized users from opening the file while it's outside SharePoint.</span></span>

<span data-ttu-id="79185-225">敏感度标签相比之下，敏感度标签除了加密， (邮件标记、页脚和水印) 保护设置。</span><span class="sxs-lookup"><span data-stu-id="79185-225">In comparison, sensitivity labels provide the protection settings of visual markings (headers, footers, watermarks) in addition to encryption.</span></span> <span data-ttu-id="79185-226">加密设置支持整套使用 [权限来](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) 限制用户可以对内容执行的操作，并且许多情况下均支持相同的 [敏感度标签](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="79185-226">The encryption settings support the full range of [usage rights](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) to restrict what users can do with the content, and the same sensitivity labels are supported for [many scenarios](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels).</span></span> <span data-ttu-id="79185-227">使用相同保护方法，使用跨工作负载和应用的一致设置，将导致一致的保护策略。</span><span class="sxs-lookup"><span data-stu-id="79185-227">Using the same protection method with consistent settings across workloads and apps results in a consistent protection strategy.</span></span>

<span data-ttu-id="79185-228">但是，你可以一起使用两种保护解决方案，且其行为如下所示：</span><span class="sxs-lookup"><span data-stu-id="79185-228">However, you can use both protection solutions together and the behavior is as follows:</span></span>

- <span data-ttu-id="79185-229">如果上载包含应用加密的敏感度标签的文件，SharePoint 就不能处理此文件以便共同创作、电子数据展示、DLP 和搜索将不适用于此文件。</span><span class="sxs-lookup"><span data-stu-id="79185-229">If you upload a file with a sensitivity label that applies encryption, SharePoint can't process this file so coauthoring, eDiscovery, DLP, and search don't work for this file.</span></span>

- <span data-ttu-id="79185-230">如果使用 Office 网页版标记文件，则将强制执行标签中任何加密设置。</span><span class="sxs-lookup"><span data-stu-id="79185-230">If you label a file using Office on the web, any encryption settings from the label are enforced.</span></span> <span data-ttu-id="79185-231">支持对这些文件进行共同创作、电子数据展示、DLP 和搜索。</span><span class="sxs-lookup"><span data-stu-id="79185-231">For these files, coauthoring, eDiscovery, DLP, and search are supported.</span></span>

- <span data-ttu-id="79185-232">如果下载一个使用 Office 网页版标签的文件，将保留标签，并强制实施标签中任何加密设置，而不要强制执行 IRM 限制设置。</span><span class="sxs-lookup"><span data-stu-id="79185-232">If you download a file that's labeled by using Office on the web, the label is retained and any encryption settings from the label are enforced rather than the IRM restriction settings.</span></span>

- <span data-ttu-id="79185-233">如果下载未使用敏感度标签加密的 Office 或 PDF 文件，则将应用 IRM 设置。</span><span class="sxs-lookup"><span data-stu-id="79185-233">If you download an Office or PDF file that isn't encrypted with a sensitivity label, IRM settings are applied.</span></span>

- <span data-ttu-id="79185-234">如果已启用任何其他 IRM 库设置（包括防止用户上载不支持 IRM 的文档），则将强制执行这些设置。</span><span class="sxs-lookup"><span data-stu-id="79185-234">If you have enabled any of the additional IRM library settings, which includes preventing users from uploading documents that don't support IRM, these settings are enforced.</span></span>

<span data-ttu-id="79185-235">通过此行为，你可以确保所有 Office 和 PDF 文件在已下载时受未经授权的访问，即使未进行标记也能受到未授权的访问的影响。</span><span class="sxs-lookup"><span data-stu-id="79185-235">With this behavior, you can be assured that all Office and PDF files are protected from unauthorized access if they are downloaded, even if they aren't labeled.</span></span> <span data-ttu-id="79185-236">但是，上传的已标记文件不会从新功能中受益。</span><span class="sxs-lookup"><span data-stu-id="79185-236">However, labeled files that are uploaded won't benefit from the new capabilities.</span></span>

## <a name="search-for-documents-by-sensitivity-label"></a><span data-ttu-id="79185-237">按敏感度标签搜索文档</span><span class="sxs-lookup"><span data-stu-id="79185-237">Search for documents by sensitivity label</span></span>

<span data-ttu-id="79185-238">使用托管属性 **InformationProtectionLabelId** 来查找 SharePoint 或 OneDrive 中具有特定敏感度标签的所有文档。</span><span class="sxs-lookup"><span data-stu-id="79185-238">Use the managed property **InformationProtectionLabelId** to find all documents in SharePoint or OneDrive that have a specific sensitivity label.</span></span> <span data-ttu-id="79185-239">使用以下语法： `InformationProtectionLabelId:<GUID>`</span><span class="sxs-lookup"><span data-stu-id="79185-239">Use the following syntax: `InformationProtectionLabelId:<GUID>`</span></span>

<span data-ttu-id="79185-240">例如，要搜索所有已标记为"机密"的文档，并且该标签的 GUID 为"8faca7b8-8d20-48a3-8ea2-0f96310a848e"，请在搜索框中键入：</span><span class="sxs-lookup"><span data-stu-id="79185-240">For example, to search for all documents that have been labeled as "Confidential", and that label has a GUID of "8faca7b8-8d20-48a3-8ea2-0f96310a848e", in the search box, type:</span></span>

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

<span data-ttu-id="79185-241">若要获取敏感度标签的 GUID，请使用 [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet：</span><span class="sxs-lookup"><span data-stu-id="79185-241">To get the GUIDs for your sensitivity labels, use the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>

1. <span data-ttu-id="79185-242">首先，[连接到 Office 365 安全与合规中心 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="79185-242">First, [connect to Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

    <span data-ttu-id="79185-243">例如，在以管理员身份运行的 PowerShell 会话中，使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="79185-243">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account.</span></span>

2. <span data-ttu-id="79185-244">然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="79185-244">Then run the following command:</span></span>

    ```powershell
    Get-Label |ft Name, Guid
    ```

<span data-ttu-id="79185-245">有关使用托管属性的详细信息，请参阅"管理[SharePoint 中的搜索架构"。](https://docs.microsoft.com/sharepoint/manage-search-schema)</span><span class="sxs-lookup"><span data-stu-id="79185-245">For more information about using managed properties, see [Manage the search schema in SharePoint](https://docs.microsoft.com/sharepoint/manage-search-schema).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a><span data-ttu-id="79185-246">如何禁用 SharePoint 和 OneDrive 的敏感度标签 (退出) </span><span class="sxs-lookup"><span data-stu-id="79185-246">How to disable sensitivity labels for SharePoint and OneDrive (opt-out)</span></span>

<span data-ttu-id="79185-247">如果禁用这些新功能，在为 SharePoint 和 OneDrive 启用敏感度标签后上传的文件会继续受标签保护，因为标签设置会继续强制实施。</span><span class="sxs-lookup"><span data-stu-id="79185-247">If you disable these new capabilities, files that you uploaded after you enabled sensitivity labels for SharePoint and OneDrive continue to be protected by the label because the label settings continue to be enforced.</span></span> <span data-ttu-id="79185-248">如果在禁用这些新功能后，将敏感度标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="79185-248">When you apply sensitivity labels to new files after you disable these new capabilities, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="79185-249">若要禁用这些新功能，必须使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="79185-249">To disable these new capabilities, you must use PowerShell.</span></span> <span data-ttu-id="79185-250">使用 SharePoint Online 命令行管理程序和 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet 指定相同的 *EnableAIPIntegration* 参数，如 [使用 PowerShell 启用敏感度标签部分中](#use-powershell-to-enable-support-for-sensitivity-labels) 所述。</span><span class="sxs-lookup"><span data-stu-id="79185-250">Using the SharePoint Online Management Shell and the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet, specify the same *EnableAIPIntegration* parameter as described in the [Use PowerShell to enable support for sensitivity labels](#use-powershell-to-enable-support-for-sensitivity-labels) section.</span></span> <span data-ttu-id="79185-251">但这次，请将该参数值设置为 false，并按 **Y** 进行确认：</span><span class="sxs-lookup"><span data-stu-id="79185-251">But this time, set the parameter value to false and press **Y** to confirm:</span></span>

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

<span data-ttu-id="79185-252">如果你有 Microsoft 365 多地理位置，则必须针对每个地理位置运行此命令。</span><span class="sxs-lookup"><span data-stu-id="79185-252">If you have Microsoft 365 Multi-Geo, you must run this command for each of your geo-locations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="79185-253">后续步骤</span><span class="sxs-lookup"><span data-stu-id="79185-253">Next steps</span></span>

<span data-ttu-id="79185-254">为 SharePoint 和 OneDrive 中的 Office 文件启用敏感度标签后，请考虑使用自动标记策略自动标记这些文件。</span><span class="sxs-lookup"><span data-stu-id="79185-254">After you've enabled sensitivity labels for Office files in SharePoint and OneDrive, consider automatically labeling these files by using auto-labeling policies.</span></span> <span data-ttu-id="79185-255">有关详细信息，请参阅["将敏感度标签自动应用于内容"。](apply-sensitivity-label-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="79185-255">For more information, see [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).</span></span>
