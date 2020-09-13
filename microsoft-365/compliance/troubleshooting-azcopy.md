---
title: 解决高级电子数据展示中的 AzCopy
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在加载非 Office 365 数据以进行高级电子数据展示中的错误修正时，对 Azure AzCopy 的错误进行故障排除。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4a4499bb9790ffeaec6a2be36b5eaff030afc010
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546452"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="abe12-103">解决高级电子数据展示中的 AzCopy</span><span class="sxs-lookup"><span data-stu-id="abe12-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="abe12-104">在高级电子数据展示中加载非 Microsoft 365 数据或文档以进行错误修正时，用户界面提供了一个 Azure AzCopy 命令，其中包含的参数包含要上载的文件的位置，以及文件将上载到的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="abe12-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="abe12-105">若要上传文档，请复制此命令，然后在本地计算机上的命令提示符处运行它。</span><span class="sxs-lookup"><span data-stu-id="abe12-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="abe12-106">下面的屏幕截图显示了 AzCopy 命令的示例：</span><span class="sxs-lookup"><span data-stu-id="abe12-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![上传非 Microsoft 365 文件](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="abe12-108">在运行时，通常提供的命令是有效的。</span><span class="sxs-lookup"><span data-stu-id="abe12-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="abe12-109">但是，在某些情况下，所显示的命令将无法成功运行。</span><span class="sxs-lookup"><span data-stu-id="abe12-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="abe12-110">以下是几个可能的原因。</span><span class="sxs-lookup"><span data-stu-id="abe12-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="abe12-111">本地计算机上未安装支持的 AzCopy 版本</span><span class="sxs-lookup"><span data-stu-id="abe12-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="abe12-112">目前，您必须使用 AzCopy？8.1 在高级电子数据展示中加载非 Microsoft 365 数据。</span><span class="sxs-lookup"><span data-stu-id="abe12-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="abe12-113">如果您不使用 AzCopy ue-v 8.1，则在前面的屏幕截图中显示的 " **上载文件** " 页上显示的 AzCopy 命令将返回错误。</span><span class="sxs-lookup"><span data-stu-id="abe12-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="abe12-114">若要安装此版本，请参阅 [在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="abe12-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="abe12-115">AzCopy 未安装在本地计算机上，或者未安装在默认位置</span><span class="sxs-lookup"><span data-stu-id="abe12-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="abe12-116">如果未安装 AzCopy 或安装在默认安装位置之外的某个位置 (这是 `%ProgramFiles(x86)%`) 的，则在运行 AzCopy 命令时，可能会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="abe12-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="abe12-117">系统找不到指定的路径。</span><span class="sxs-lookup"><span data-stu-id="abe12-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="abe12-118">如果本地计算机上未安装 AzCopy，则可以在 [Windows 上查找使用 AzCopy 中的的传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)的安装信息。</span><span class="sxs-lookup"><span data-stu-id="abe12-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="abe12-119">请务必将其安装在默认位置。</span><span class="sxs-lookup"><span data-stu-id="abe12-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="abe12-120">如果已安装 AzCopy，但其安装在与默认位置不同的位置，则可以复制命令，将其粘贴到文本文件，然后将路径更改为安装 AzCopy 的位置。</span><span class="sxs-lookup"><span data-stu-id="abe12-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="abe12-121">例如，如果 Azcopy 位于 `%ProgramFiles%` ，则可以将命令的第一部分从更改 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` 为 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。</span><span class="sxs-lookup"><span data-stu-id="abe12-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="abe12-122">在进行此更改后，从文本文件中复制该文件，然后运行命令提示符。</span><span class="sxs-lookup"><span data-stu-id="abe12-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="abe12-123">如果 AzCopy 安装在默认安装位置之外的其他位置，请考虑将其卸载，然后在默认位置重新安装它。</span><span class="sxs-lookup"><span data-stu-id="abe12-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="abe12-124">这将有助于防止将来出现此问题。</span><span class="sxs-lookup"><span data-stu-id="abe12-124">This will help prevent this issue in the future.</span></span>
