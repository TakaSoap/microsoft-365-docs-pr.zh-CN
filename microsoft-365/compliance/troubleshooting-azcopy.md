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
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>解决高级电子数据展示中的 AzCopy

在高级电子数据展示中加载非 Microsoft 365 数据或文档以进行错误修正时，用户界面提供了一个 Azure AzCopy 命令，其中包含的参数包含要上载的文件的位置，以及文件将上载到的 Azure 存储位置。 若要上传文档，请复制此命令，然后在本地计算机上的命令提示符处运行它。  下面的屏幕截图显示了 AzCopy 命令的示例：

![上传非 Microsoft 365 文件](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

在运行时，通常提供的命令是有效的。 但是，在某些情况下，所显示的命令将无法成功运行。 以下是几个可能的原因。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>本地计算机上未安装支持的 AzCopy 版本

目前，您必须使用 AzCopy？8.1 在高级电子数据展示中加载非 Microsoft 365 数据。 如果您不使用 AzCopy ue-v 8.1，则在前面的屏幕截图中显示的 " **上载文件** " 页上显示的 AzCopy 命令将返回错误。 若要安装此版本，请参阅 [在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy 未安装在本地计算机上，或者未安装在默认位置

如果未安装 AzCopy 或安装在默认安装位置之外的某个位置 (这是 `%ProgramFiles(x86)%`) 的，则在运行 AzCopy 命令时，可能会收到以下错误消息：

> 系统找不到指定的路径。

如果本地计算机上未安装 AzCopy，则可以在 [Windows 上查找使用 AzCopy 中的的传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)的安装信息。 请务必将其安装在默认位置。

如果已安装 AzCopy，但其安装在与默认位置不同的位置，则可以复制命令，将其粘贴到文本文件，然后将路径更改为安装 AzCopy 的位置。 例如，如果 Azcopy 位于 `%ProgramFiles%` ，则可以将命令的第一部分从更改 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` 为 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。 在进行此更改后，从文本文件中复制该文件，然后运行命令提示符。

> [!TIP]
> 如果 AzCopy 安装在默认安装位置之外的其他位置，请考虑将其卸载，然后在默认位置重新安装它。 这将有助于防止将来出现此问题。
