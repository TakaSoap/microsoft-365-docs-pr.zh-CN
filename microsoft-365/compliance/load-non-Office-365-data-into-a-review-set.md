---
title: 将非 Microsoft 365 数据加载到审阅集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何将非 Microsoft 365 数据导入审阅集，以在高级电子数据展示案例中进行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903498"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>将非 Microsoft 365 数据加载到审阅集

并非所有需要在高级电子数据展示中分析的文档都位于 Microsoft 365 中。 借助高级电子数据展示中的非 Microsoft 365 数据导入功能，可以将不在 Microsoft 365 中的文档上载到审阅集。 本文介绍了如何将非 Microsoft 365 文档引入高级电子数据展示进行分析。

## <a name="requirements-to-upload-non-office-365-content"></a>上载非 Office 365 内容的要求

使用本文中所述的上载非 Microsoft 365 功能需要具备以下各项：

- 必须为要关联非 Microsoft 365 内容的所有保管人分配适当的许可证。 有关详细信息，请参阅 [高级电子数据展示入门](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。

- 现有高级电子数据展示案例。

- 必须先将保管人添加到案例，然后才能上传非 Microsoft 365 数据并将其与它们关联。

- 非 Microsoft 365 数据必须是高级电子数据展示支持的文件类型。 有关详细信息，请参阅高级 [电子数据展示](supported-filetypes-ediscovery20.md)中支持的文件类型。

- 上传到审阅集的所有文件必须位于文件夹中，其中每个文件夹与特定保管人关联。 这些文件夹的名称必须使用以下命名格式 *：alias@domainname。* alias@domainname必须是用户的 Microsoft 365 别名和域。 你可以收集根文件夹中alias@domainname文件夹。 根文件夹只能包含alias@domainname文件夹。 根文件夹中的松散文件不受支持。

   要上载的非 Microsoft 365 数据的文件夹结构与以下示例类似：

   - c：\nonO365\abraham.mcmahon@contoso.com
   - c：\nonO365\jewell.gordon@contoso.com
   - c：\nonO365\staci.gonzalez@contoso.com

   其中 abraham.mcmahon@contoso.com、jewell.gordon@contoso.com 和 staci.gonzalez@contoso.com 是本例中保管人 SMTP 地址。

   ![非 Microsoft 365 数据上载文件夹结构](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 分配给电子数据展示管理员角色组的帐户 (添加为电子数据展示管理员) 。

- AzCopy v8.1 工具安装在有权访问非 Microsoft 365 内容文件夹结构的计算机上。 若要安装 AzCopy，请参阅在 Windows 上通过 [AzCopy v8.1 传输数据](/previous-versions/azure/storage/storage-use-azcopy)。 请务必将 AzCopy 安装在默认位置，即 **%ProgramFiles (x86) %\Microsoft SDKs\Azure\AzCopy**。 必须使用 AzCopy v8.1。 在高级电子数据展示中加载非 Microsoft 365 数据时，AzCopy 的其他版本可能不起作用。


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>将非 Microsoft 365 内容上载到高级电子数据展示

1. 作为电子数据展示管理员或电子数据展示管理员，打开"高级电子数据展示"，然后转到非 Microsoft 365 数据将上载到的情况。  

2. 单击 **"审阅** 集"，然后选择将非 Microsoft 365 数据上载到的审阅集。  如果没有审阅集，可以创建一个审阅集。 
 
3. 在审阅集内，单击 **"管理审阅** 集"，然后单击"非 Microsoft **365** 数据"磁贴上的"查看上载"。

4. 单击 **"上载文件** "以启动数据导入向导。

   ![上载文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   向导的第一步是准备 Microsoft 提供的安全 Azure 存储位置，以将文件上传到该位置。  准备工作完成后，"下一步 **： 上载文件"** 按钮将变为活动状态。

   ![非 Microsoft 365 导入：准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. 单击 **"下一步：上载文件"。**

6. 在" **上载文件"** 页上，执行以下操作：

   ![非 Microsoft 365 导入：上载文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. 在 **"文件的位置** 的路径"框中，验证或键入存储要上载的非 Microsoft 365 数据的根文件夹的位置。 例如，对于"开始之前"部分中显示的示例文件的位置，请键入 **%USERPROFILE\Downloads\nonO365**。 提供正确的位置可确保正确更新路径下的框中显示的 AzCopy 命令。

   b. 单击 **"复制到剪贴板** "以复制显示在框中的命令。

7. 启动 Windows 命令提示符，粘贴在上一步中复制的命令，然后按 **Enter** 启动 AzCopy 命令。  启动命令后，非 Microsoft 365 文件将上载到步骤 4 中准备的 Azure 存储位置。

   ![非 Microsoft 365 导入：AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 如前所述，必须使用 AzCopy v8.1 成功使用"上载文件"页上 **提供** 的命令。 如果提供的 AzCopy 命令失败，请参阅高级 [电子数据展示中的 AzCopy 疑难解答](troubleshooting-azcopy.md)。

8. 返回到安全与&中心，然后单击向导中的"下一 **步： 处理** 文件"。  这将启动上载到 Azure 存储位置的非 Microsoft 365 文件的处理、文本提取和索引。  

9. 通过查看名为"将非 Microsoft  **365** 数据添加到审阅集"的作业，跟踪"处理文件"页面或"作业"选项卡上的文件处理进度。  作业完成后，新文件将在审阅集内可用。

   ![非 Microsoft 365 导入：处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 处理完成后，可以关闭向导。