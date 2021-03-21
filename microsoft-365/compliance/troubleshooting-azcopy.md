---
title: 高级电子数据展示中的 AzCopy 疑难解答
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
description: 解决在高级电子数据展示中加载非 Office 365 数据以修正错误时 Azure AzCopy 的错误。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919288"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="7bb09-103">高级电子数据展示中的 AzCopy 疑难解答</span><span class="sxs-lookup"><span data-stu-id="7bb09-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="7bb09-104">在高级电子数据展示中加载非 Microsoft 365 数据或文档进行错误修正时，用户界面会提供 Azure AzCopy 命令，该命令包含参数，其中包含要上载的文件的存储位置以及文件将上载到的 Azure 存储位置的参数。</span><span class="sxs-lookup"><span data-stu-id="7bb09-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="7bb09-105">若要上载文档，请复制此命令，然后在本地计算机的命令提示符中运行它。</span><span class="sxs-lookup"><span data-stu-id="7bb09-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="7bb09-106">以下屏幕截图显示了 AzCopy 命令的示例：</span><span class="sxs-lookup"><span data-stu-id="7bb09-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![上载非 Microsoft 365 文件](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="7bb09-108">通常，所提供的命令在运行时有效。</span><span class="sxs-lookup"><span data-stu-id="7bb09-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="7bb09-109">但是，在某些情况下，显示的命令可能无法成功运行。</span><span class="sxs-lookup"><span data-stu-id="7bb09-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="7bb09-110">以下是一些可能的原因。</span><span class="sxs-lookup"><span data-stu-id="7bb09-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="7bb09-111">本地计算机上未安装受支持的 AzCopy 版本</span><span class="sxs-lookup"><span data-stu-id="7bb09-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="7bb09-112">此时，必须使用 AzCopy v8.1 在高级电子数据展示中加载非 Microsoft 365 数据。</span><span class="sxs-lookup"><span data-stu-id="7bb09-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="7bb09-113">如果未使用 AzCopy v8.1，则显示在上一屏幕截图中显示的"上载文件"页上的 AzCopy 命令将返回错误。 </span><span class="sxs-lookup"><span data-stu-id="7bb09-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="7bb09-114">若要安装此版本，请参阅在 Windows 上通过 [AzCopy v8.1 传输数据](/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="7bb09-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="7bb09-115">AzCopy 未安装在本地计算机上，或者未安装在默认位置</span><span class="sxs-lookup"><span data-stu-id="7bb09-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="7bb09-116">如果未安装 AzCopy 或安装在默认安装位置 (（即) ）的位置，则运行 AzCopy 命令时可能会收到以下 `%ProgramFiles(x86)%` 错误：</span><span class="sxs-lookup"><span data-stu-id="7bb09-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="7bb09-117">系统找不到指定的路径。</span><span class="sxs-lookup"><span data-stu-id="7bb09-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="7bb09-118">如果本地计算机上未安装 AzCopy，可以在 Windows 上的使用 [AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)传输数据中查找安装信息。</span><span class="sxs-lookup"><span data-stu-id="7bb09-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="7bb09-119">请务必将其安装在默认位置。</span><span class="sxs-lookup"><span data-stu-id="7bb09-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="7bb09-120">如果安装了 AzCopy，但它安装在不同于默认位置的位置，您可以复制该命令，将其粘贴到文本文件，然后将路径更改为安装 AzCopy 的位置。</span><span class="sxs-lookup"><span data-stu-id="7bb09-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="7bb09-121">例如，如果 Azcopy 位于 中，您可以将命令的第一部分 `%ProgramFiles%` 从 更改为 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。</span><span class="sxs-lookup"><span data-stu-id="7bb09-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="7bb09-122">进行此更改后，从文本文件复制它，然后运行命令提示符。</span><span class="sxs-lookup"><span data-stu-id="7bb09-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="7bb09-123">如果 AzCopy 安装在默认安装位置的其他位置，请考虑卸载它，然后在默认位置重新安装它。</span><span class="sxs-lookup"><span data-stu-id="7bb09-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="7bb09-124">这将帮助在将来避免此问题。</span><span class="sxs-lookup"><span data-stu-id="7bb09-124">This will help prevent this issue in the future.</span></span>