---
title: 启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 管理员可以在 SharePoint 和 OneDrive 中为 Word、Excel 和 PowerPoint 文件启用敏感度标签支持。
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802825"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="9cbd7-103">启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="9cbd7-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="9cbd7-104">以前，在对存储在 SharePoint 和 OneDrive 中的 Office 文件应用包含加密的敏感度标签时，该服务无法处理这些文件的内容。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="9cbd7-105">在这些情况下，合著、电子数据丢失、数据丢失防护、搜索、Delve 和其他协作功能不起作用。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="9cbd7-106">此预览启用以下功能：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-106">This preview enables these features:</span></span>

- <span data-ttu-id="9cbd7-107">SharePoint 识别应用于 SharePoint 和 OneDrive 中的 Word、Excel 和 PowerPoint 文件的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="9cbd7-108">SharePoint 还强制实施与每个标签对应的设置。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="9cbd7-109">从 SharePoint 或 OneDrive 下载文件时，敏感度标签与文件一起移动，并且设置仍将强制实施。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="9cbd7-110">将敏感度标签应用于 Office 文件，并使用 Word、Excel 和 PowerPoint 的 web 版本打开和编辑已应用灵敏度标签的文件（如果标签的权限允许）。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="9cbd7-111">在 web 上使用 Word 时，您还可以在编辑文档时使用自动标签。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="9cbd7-112">Office 365 电子数据展示支持在应用了灵敏度标签的文件中进行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="9cbd7-113">数据丢失防护（DLP）策略涵盖这些文件中的内容。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="9cbd7-114">有三个新的审核事件可用于监视敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="9cbd7-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="9cbd7-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="9cbd7-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="9cbd7-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="9cbd7-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="9cbd7-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="9cbd7-118">现在，您还可以将灵敏度标签应用于 Microsoft 团队、Office 365 组和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="9cbd7-119">[了解详细信息](sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="9cbd7-120">如有必要，可随时退出预览。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="9cbd7-121">Requirements</span><span class="sxs-lookup"><span data-stu-id="9cbd7-121">Requirements</span></span>

<span data-ttu-id="9cbd7-122">这些功能仅适用于[敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="9cbd7-123">如果你使用的是 Azure 信息保护标签，则可以将其转换为敏感度标签，以对你上载的新文件启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="9cbd7-124">了解方法</span><span class="sxs-lookup"><span data-stu-id="9cbd7-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="9cbd7-125">对于此预览，请在 Windows 和版本19.002.0107.0008 或更高版本的 Mac 上使用 OneDrive 同步应用版本19.002.0121.0008 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="9cbd7-126">这两个版本都是在2019年1月28日发布的，并且当前已发布到所有震铃。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="9cbd7-127">[请参阅 OneDrive 发行说明](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="9cbd7-128">启用此预览后，将提示运行较早版本的同步应用的用户进行更新。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="9cbd7-129">限制</span><span class="sxs-lookup"><span data-stu-id="9cbd7-129">Limitations</span></span>

- <span data-ttu-id="9cbd7-130">如果启用此预览，则使用 Office 桌面或移动应用将标签应用于文件的用户可能无法保存对文件所做的其他更改。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="9cbd7-131">相反，应用程序会提示用户另存为或放弃本地更改。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="9cbd7-132">若要避免丢失工作，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="9cbd7-133">若要应用标签，请使用 Office 应用的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="9cbd7-134">在应用标签后关闭文件，然后重新打开该文件以进行其他更改。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="9cbd7-135">SharePoint 不会自动将新标签应用于已使用 Azure 信息保护标签加密的现有文件。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="9cbd7-136">若要在启用此预览后获取要运行的功能，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="9cbd7-137">将 Azure 信息保护标签转换为敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="9cbd7-138">下载文件并将其上载到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="9cbd7-139">SharePoint 无法处理带有过期日期的自定义权限和标签的标签。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="9cbd7-140">当用户拥有编辑权限时，无论标签中的副本策略设置如何，Office 应用程序的 web 版本都允许复制。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="9cbd7-141">不支持 RMS 吊销、跟踪和报告。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="9cbd7-142">Office 桌面应用程序和移动应用程序不支持共同创作。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="9cbd7-143">相反，这些应用将继续以独占编辑模式打开文件。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="9cbd7-144">如果标签包括加密，Microsoft 云应用安全性无法读取 SharePoint 中文件的标签信息。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="9cbd7-145">为预览准备 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="9cbd7-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="9cbd7-146">在启用预览之前，请确保您运行的是 SharePoint Online 命令行管理程序版本16.0.19418.12000 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-146">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="9cbd7-147">如果已有最新版本，可以继续并启用预览。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="9cbd7-148">如果已从 PowerShell 库安装了早期版本的 SharePoint Online 命令行管理程序，则可以通过运行以下 cmdlet 来更新模块。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-148">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="9cbd7-149">或者，如果您已从 Microsoft 下载中心安装了早期版本的 SharePoint Online 命令行管理程序，则还可以转到 "**添加或删除程序**"，然后卸载 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-149">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="9cbd7-150">在 web 浏览器中，转到 "下载中心" 页面并[下载最新的 SharePoint Online 命令行管理](https://go.microsoft.com/fwlink/p/?LinkId=255251)程序。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="9cbd7-151">选择您的语言，然后单击 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-151">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="9cbd7-152">在 x64 和 x86 .msi 文件之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="9cbd7-153">如果运行的是64位版本的 Windows 或 x86 文件（如果运行32位版本），请下载 x64 文件。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="9cbd7-154">如果您不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="9cbd7-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="9cbd7-155">下载文件后，运行文件并按照安装向导中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-155">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="9cbd7-156">使用 Microsoft PowerShell 启用预览（自愿加入）</span><span class="sxs-lookup"><span data-stu-id="9cbd7-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="9cbd7-157">若要启用预览，请使用 Set-spotenant cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="9cbd7-158">在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="9cbd7-159">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="9cbd7-160">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="9cbd7-161">创建或更改敏感度标签后计划回滚</span><span class="sxs-lookup"><span data-stu-id="9cbd7-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="9cbd7-162">在 Microsoft 365 合规性中心中创建或更改灵敏度标签后，请分阶段发布它。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="9cbd7-163">如果您发布尚未完全同步的标签，则当用户将标签应用于文件并将其上传到 SharePoint 时，将无法在 Office 应用程序的 web 版本中打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="9cbd7-164">搜索和电子数据展示也不适用于这些文件。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="9cbd7-165">我们建议您按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="9cbd7-166">仅将新的或修改的敏感度标签发布给一个或两个人。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="9cbd7-167">在初始发布后至少等待24小时。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="9cbd7-168">验证标签是否已完全同步。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="9cbd7-169">更广泛地发布标签。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="9cbd7-170">使用 Microsoft PowerShell 禁用预览（自愿退出）</span><span class="sxs-lookup"><span data-stu-id="9cbd7-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="9cbd7-171">如果禁用此预览，则在预览过程中上载的文件将继续受标签保护。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="9cbd7-172">将继续强制实施相应的设置。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="9cbd7-173">在禁用预览后将标签应用于新文件时，全文搜索、电子数据展示和共同创作将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="9cbd7-174">若要禁用预览，请使用 Set-spotenant cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="9cbd7-175">在 Office 365 中使用具有全局管理员或 SharePoint 管理员权限的工作或学校帐户连接到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="9cbd7-176">若要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。</span><span class="sxs-lookup"><span data-stu-id="9cbd7-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="9cbd7-177">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9cbd7-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
