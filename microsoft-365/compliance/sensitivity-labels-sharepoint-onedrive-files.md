---
title: 启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签
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
ms.openlocfilehash: 5d9b5a493b44ef4453906f1601481a6aa89c3884
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288530"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="02ebd-103">启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="02ebd-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="02ebd-104">在此预览之前，当您将包含加密的敏感度标签应用于存储在 SharePoint 和 OneDrive 中的 Office 文件时，该服务无法处理这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="02ebd-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="02ebd-105">在这些情况下，合著、电子数据丢失、数据丢失防护、搜索、Delve 和其他协作功能不起作用。</span><span class="sxs-lookup"><span data-stu-id="02ebd-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="02ebd-106">此预览对应用了敏感度标签的新文件和更改的文件启用了这些功能，其中包括基于云的密钥的加密：</span><span class="sxs-lookup"><span data-stu-id="02ebd-106">This preview enables these features for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key:</span></span>

- <span data-ttu-id="02ebd-107">SharePoint 可识别应用于 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件的敏感度标签。当文件存储在 SharePoint 中时，将删除来自 Azure 信息保护的加密，以便可以处理文件内容，并然后，在下载文件时，将重新应用标签中的加密设置。</span><span class="sxs-lookup"><span data-stu-id="02ebd-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive: While the file is stored in SharePoint, the encryption from Azure Information Protection is removed so that the file contents can be processed, and then the encryption settings from the label are reapplied when the file is downloaded.</span></span> <span data-ttu-id="02ebd-108">有关在下载文档之前如何保护文档的信息，请参阅[OneDrive For business 和 SharePoint Online 中的数据加密](data-encryption-in-odb-and-spo.md)。</span><span class="sxs-lookup"><span data-stu-id="02ebd-108">For information about how documents are protected before they are downloaded, see [Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md).</span></span>
 
- <span data-ttu-id="02ebd-109">若要使 SharePoint 在上载时对文件进行解密，上载已标记和已加密文件的用户必须至少具有查看该文件的使用权限。</span><span class="sxs-lookup"><span data-stu-id="02ebd-109">For SharePoint to decrypt the file on upload, the user who uploads the labeled and encrypted file must have usage rights to at least view the file.</span></span> <span data-ttu-id="02ebd-110">SharePoint 不会对用户无法在 SharePoint 外部打开的文件进行解密。</span><span class="sxs-lookup"><span data-stu-id="02ebd-110">SharePoint doesn't decrypt files that the user can't open outside SharePoint.</span></span>

- <span data-ttu-id="02ebd-111">当您从 SharePoint 或 OneDrive 下载或访问文件时，敏感度标签和任何加密设置将随文件一起重新应用，并且在保存文件的任何位置都将强制执行这些设置。</span><span class="sxs-lookup"><span data-stu-id="02ebd-111">When you download or access the file from SharePoint or OneDrive, the sensitivity label and any encryption settings are reapplied with the file, and these settings remain enforced wherever the file is saved.</span></span>

- <span data-ttu-id="02ebd-112">使用 web 上的 Office （Word、Excel、PowerPoint）打开和编辑具有应用加密的敏感度标签的 Office 文件。</span><span class="sxs-lookup"><span data-stu-id="02ebd-112">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="02ebd-113">将强制实施通过加密分配的权限。</span><span class="sxs-lookup"><span data-stu-id="02ebd-113">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="02ebd-114">在 web 上使用 Word 时，您还可以在编辑这些文档时使用自动标签。</span><span class="sxs-lookup"><span data-stu-id="02ebd-114">With Word on the web, you can also use auto labeling when you edit these documents.</span></span>

- <span data-ttu-id="02ebd-115">Office 365 电子数据展示支持对这些文件进行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="02ebd-115">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="02ebd-116">数据丢失防护（DLP）策略涵盖这些文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="02ebd-116">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="02ebd-117">有三个新的[审核事件](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities)可用于监视使用 web 上的 Office 应用的敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="02ebd-117">Three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied using Office on the web:</span></span>
  - <span data-ttu-id="02ebd-118">**已向文件应用敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="02ebd-118">**Applied sensitivity label to file**</span></span>
  - <span data-ttu-id="02ebd-119">**已更改应用于文件的敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="02ebd-119">**Changed sensitivity label applied to file**</span></span>
  - <span data-ttu-id="02ebd-120">**已从文件除敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="02ebd-120">**Removed sensitivity label from file**</span></span>

> [!NOTE]
> <span data-ttu-id="02ebd-121">如果加密尚未应用于基于云的密钥，而是本地密钥，则密钥管理拓扑通常称为 "保留自己的密钥" （HYOK），SharePoint 行为在此预览中不会更改。</span><span class="sxs-lookup"><span data-stu-id="02ebd-121">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span>
>
> <span data-ttu-id="02ebd-122">在启用预览之前，sharepoint 行为也不会对 SharePoint 中的现有标记和加密文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="02ebd-122">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint before you enable the preview.</span></span> <span data-ttu-id="02ebd-123">为了让这些文件受益于新功能，必须下载和上载这些文件，或在启用预览后再对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="02ebd-123">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you enable the preview.</span></span> <span data-ttu-id="02ebd-124">例如，它们将在搜索和电子数据展示结果中返回。</span><span class="sxs-lookup"><span data-stu-id="02ebd-124">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="02ebd-125">现在，您还可以将灵敏度标签应用于 Microsoft 团队、Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="02ebd-125">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="02ebd-126">有关此单独预览的详细信息，请参阅[使用敏感度标签与 Microsoft 团队、Office 365 组和 SharePoint 网站（公共预览版）](sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="02ebd-126">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="02ebd-127">你随时都可以选择退出此预览。</span><span class="sxs-lookup"><span data-stu-id="02ebd-127">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="02ebd-128">观看以下视频（无音频）以查看这些新功能的操作：</span><span class="sxs-lookup"><span data-stu-id="02ebd-128">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="02ebd-129">要求</span><span class="sxs-lookup"><span data-stu-id="02ebd-129">Requirements</span></span>

<span data-ttu-id="02ebd-130">这些功能仅适用于[敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="02ebd-130">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="02ebd-131">如果你当前有 Azure 信息保护标签，请首先将其迁移到敏感度标签，以便可以为上传的新文件启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="02ebd-131">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="02ebd-132">有关说明，请参阅[如何将 Azure 信息保护标签迁移到统一敏感度标签](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="02ebd-132">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="02ebd-133">对于此预览，请在 Windows 上使用 OneDrive 同步应用版本19.002.0121.0008 或更高版本，并在 Mac 上使用版本19.002.0107.0008 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="02ebd-133">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="02ebd-134">这两个版本都发布了2019年1月28日，并且当前已发布到所有震铃。</span><span class="sxs-lookup"><span data-stu-id="02ebd-134">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="02ebd-135">有关详细信息，请参阅[OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="02ebd-135">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="02ebd-136">启用此预览后，系统会提示运行较旧版本的同步应用程序的用户对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="02ebd-136">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="02ebd-137">限制</span><span class="sxs-lookup"><span data-stu-id="02ebd-137">Limitations</span></span>

- <span data-ttu-id="02ebd-138">如果启用此预览，则在 OneDrive 同步文件夹中更改文件上的标签的用户可能无法保存对该文件所做的其他更改。</span><span class="sxs-lookup"><span data-stu-id="02ebd-138">When you enable this preview, users who change a label on a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="02ebd-139">用户看到一个[带有白色交叉图标错误的红色圆圈](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)，并要求他们将新的更改另存为一个单独副本。</span><span class="sxs-lookup"><span data-stu-id="02ebd-139">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="02ebd-140">除了用户启动的标签更改之外，如果管理员更改已应用于下载到用户同步客户端的文件的已发布标签的设置，也会发生相同的行为。</span><span class="sxs-lookup"><span data-stu-id="02ebd-140">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="02ebd-141">若要避免在这些情况下丢失工作，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="02ebd-141">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="02ebd-142">若要应用标签，请使用 Office 应用的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="02ebd-142">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="02ebd-143">在应用标签后关闭文件，然后重新打开该文件以进行其他更改。</span><span class="sxs-lookup"><span data-stu-id="02ebd-143">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="02ebd-144">SharePoint 不会自动将灵敏度标签应用于已使用 Azure 信息保护标签加密的现有文件。</span><span class="sxs-lookup"><span data-stu-id="02ebd-144">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="02ebd-145">若要在启用此预览后获取要运行的功能，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="02ebd-145">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="02ebd-146">确保已将 Azure 信息保护标签迁移到了敏感度标签，并已将其从 Microsoft 365 合规性中心或等效的标签管理中心进行了发布。</span><span class="sxs-lookup"><span data-stu-id="02ebd-146">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="02ebd-147">下载文件并将其上载到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="02ebd-147">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="02ebd-148">当应用了加密的标签具有以下加密配置之一时，SharePoint 将无法处理加密文件：</span><span class="sxs-lookup"><span data-stu-id="02ebd-148">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="02ebd-149">**允许用户在应用标签**和**Word、PowerPoint 和 Excel 中分配权限，提示用户指定权限**</span><span class="sxs-lookup"><span data-stu-id="02ebd-149">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="02ebd-150">**用户对内容的访问权限**设置为**永不**过期的值。</span><span class="sxs-lookup"><span data-stu-id="02ebd-150">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="02ebd-151">对于向用户授予编辑权限的加密文档，不能在 Office 应用程序的 web 版本中阻止复制。</span><span class="sxs-lookup"><span data-stu-id="02ebd-151">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="02ebd-152">不支持 Azure 信息保护文档跟踪网站。</span><span class="sxs-lookup"><span data-stu-id="02ebd-152">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="02ebd-153">Office 桌面应用程序和移动应用程序不支持共同创作。</span><span class="sxs-lookup"><span data-stu-id="02ebd-153">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="02ebd-154">相反，这些应用将继续以独占编辑模式打开文件。</span><span class="sxs-lookup"><span data-stu-id="02ebd-154">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="02ebd-155">如果标签包括加密，Microsoft 云应用安全性无法读取 SharePoint 中文件的标签信息。</span><span class="sxs-lookup"><span data-stu-id="02ebd-155">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

- <span data-ttu-id="02ebd-156">如果将带标签的文档上载到 SharePoint，并使用服务主体名称中的帐户来应用加密，则无法在 web 上的 Office 中打开该文档。</span><span class="sxs-lookup"><span data-stu-id="02ebd-156">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="02ebd-157">示例方案包括 Microsoft 云应用安全和通过电子邮件发送给团队的文件。</span><span class="sxs-lookup"><span data-stu-id="02ebd-157">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="02ebd-158">以下列方式加密的文档无法在 web 上的 Office 中打开：</span><span class="sxs-lookup"><span data-stu-id="02ebd-158">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="02ebd-159">使用本地密钥的加密（"保留自己的密钥" 或 HYOK）</span><span class="sxs-lookup"><span data-stu-id="02ebd-159">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="02ebd-160">独立于标签（例如，通过直接应用权限管理保护模板）应用的加密。</span><span class="sxs-lookup"><span data-stu-id="02ebd-160">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="02ebd-161">如果您删除了应用于 SharePoint 文档的标签，而不是从适用的标签策略中删除标签，则下载的文档不会被标记或加密。</span><span class="sxs-lookup"><span data-stu-id="02ebd-161">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="02ebd-162">相比之下，如果标记的文档存储在 SharePoint 外部，则在删除该标签时，该文档仍保持加密。</span><span class="sxs-lookup"><span data-stu-id="02ebd-162">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="02ebd-163">请注意，尽管您可以在测试阶段删除标签，但很少在生产环境中删除标签。</span><span class="sxs-lookup"><span data-stu-id="02ebd-163">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="02ebd-164">为预览准备 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="02ebd-164">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="02ebd-165">在启用预览之前，请确保您运行的是 SharePoint Online 命令行管理程序版本16.0.19418.12000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="02ebd-165">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="02ebd-166">如果已有最新版本，可以继续并启用预览。</span><span class="sxs-lookup"><span data-stu-id="02ebd-166">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="02ebd-167">如果已从 PowerShell 库安装了早期版本的 SharePoint Online 命令行管理程序，则可以通过运行以下 cmdlet 来更新模块。</span><span class="sxs-lookup"><span data-stu-id="02ebd-167">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="02ebd-168">或者，如果您已从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到 "**添加或删除程序**"，然后卸载 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="02ebd-168">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="02ebd-169">在 Web 浏览器中，转到“下载中心”页面，[下载最新的 SharePoint Online 命令行管理程序](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="02ebd-169">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="02ebd-170">选择语言，然后单击“**下载**”。</span><span class="sxs-lookup"><span data-stu-id="02ebd-170">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="02ebd-171">在 x64 和 x86.msi 文件之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="02ebd-171">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="02ebd-172">如果运行的是64位版本的 Windows 或 x86 文件（如果运行32位版本），请下载 x64 文件。</span><span class="sxs-lookup"><span data-stu-id="02ebd-172">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="02ebd-173">如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="02ebd-173">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="02ebd-174">下载文件后，运行文件并按照安装向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="02ebd-174">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="02ebd-175">使用 Microsoft PowerShell 启用预览（自愿加入）</span><span class="sxs-lookup"><span data-stu-id="02ebd-175">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="02ebd-176">若要启用预览，请使用 Set-spotenant cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02ebd-176">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="02ebd-177">在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="02ebd-177">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="02ebd-178">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="02ebd-178">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="02ebd-179">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="02ebd-179">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="02ebd-180">创建或更改敏感度标签后计划回滚</span><span class="sxs-lookup"><span data-stu-id="02ebd-180">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="02ebd-181">在 Microsoft 365 合规性中心中创建或更改灵敏度标签后，请分阶段发布它。</span><span class="sxs-lookup"><span data-stu-id="02ebd-181">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="02ebd-182">如果您发布尚未完全同步的标签，则当用户将标签应用于文件并将其上传到 SharePoint 时，将无法在 Office 应用程序的 web 版本中打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="02ebd-182">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="02ebd-183">搜索和电子数据展示也不适用于这些文件。</span><span class="sxs-lookup"><span data-stu-id="02ebd-183">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="02ebd-184">我们建议您按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="02ebd-184">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="02ebd-185">仅将新的或修改的敏感度标签发布给一个或两个人。</span><span class="sxs-lookup"><span data-stu-id="02ebd-185">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="02ebd-186">在初始发布后至少等待24小时。</span><span class="sxs-lookup"><span data-stu-id="02ebd-186">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="02ebd-187">验证标签是否已完全同步。</span><span class="sxs-lookup"><span data-stu-id="02ebd-187">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="02ebd-188">更广泛地发布标签。</span><span class="sxs-lookup"><span data-stu-id="02ebd-188">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="02ebd-189">使用 Microsoft PowerShell 禁用预览（自愿退出）</span><span class="sxs-lookup"><span data-stu-id="02ebd-189">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="02ebd-190">如果禁用此预览，则在预览过程中上载的文件将继续受标签保护。</span><span class="sxs-lookup"><span data-stu-id="02ebd-190">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="02ebd-191">将继续强制实施相应的设置。</span><span class="sxs-lookup"><span data-stu-id="02ebd-191">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="02ebd-192">在禁用预览后将标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="02ebd-192">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="02ebd-193">若要禁用预览，请使用 Set-spotenant cmdlet：</span><span class="sxs-lookup"><span data-stu-id="02ebd-193">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="02ebd-194">在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="02ebd-194">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="02ebd-195">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="02ebd-195">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="02ebd-196">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="02ebd-196">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
