---
title: 修正处理数据时出现的错误
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何使用错误修正来更正高级电子数据展示中可能阻止正确处理内容的数据问题。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2067831a85e3b3a506917fac5b93acfa0b174db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906980"
---
# <a name="error-remediation-when-processing-data"></a>修正处理数据时出现的错误

错误修正允许电子数据展示管理员纠正阻止高级电子数据展示正确处理内容的数据问题。 例如，由于文件被锁定或加密，因此无法处理受密码保护的文件。 通过使用错误修正，电子数据展示管理员可以下载包含此类错误的文件，删除密码保护，然后上载修正后的文件。

使用以下工作流可修正高级电子数据展示事例中出现错误的文件。

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>创建错误修正会话以修正包含处理错误的文件

>[!NOTE]
>如果错误修正向导在下列过程中随时关闭，则可以通过在"视图"下拉菜单中选择"修正"，从"处理"选项卡返回到错误修正会话。 

1. 在"**高级** 电子数据展示"案例的"处理"选项卡上，选择"视图"下拉菜单中的"错误"，然后在"范围"下拉菜单中选择审阅集或整个案例。  此部分显示来自案例的所有错误或特定审阅集的错误。

   ![错误修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. 单击错误类型或文件类型旁边的单选按钮，选择要修正的错误。  在下面的示例中，我们将修正受密码保护的文件。

3. 单击 **"新建错误修正"。**

    错误修正工作流从准备阶段开始，其中将出错的文件复制到 Microsoft 提供的 Azure 存储位置，以便你可以将其下载到本地计算机进行修正。

    ![准备错误修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 准备工作完成后，单击"下一步 **： 下载文件** "以继续下载。

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 若要下载文件，请 **指定下载的目标路径**。 这是本地计算机上将下载文件的父文件夹的路径。  默认路径 %USERPROFILE%\Downloads\errors 指向登录用户的下载文件夹。 如果需要，可以更改此路径。 如果更改了该路径，建议您使用本地文件路径以获得最佳性能。 请勿使用远程网络路径。 例如，可以使用路径 **C：\Remediation**。 

   父文件夹的路径将自动添加到 AzCopy (**作为 /Dest** 参数的值) 。

6. 通过单击"复制到剪贴板 **"复制预定义的命令**。 打开 Windows 命令提示符，粘贴 AzCopy 命令，然后按 **Enter。**  

    ![准备错误修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > 必须使用 AzCopy v8.1 成功使用"下载文件"页上 **提供** 的命令。 还必须使用 AzCopy v8.1 上载步骤 10 中的文件。 若要安装此版本的 AzCopy，请参阅在 Windows 上使用 [AzCopy v8.1 传输数据](/previous-versions/azure/storage/storage-use-azcopy)。 如果提供的 AzCopy 命令失败，请参阅高级 [电子数据展示中的 AzCopy 疑难解答](troubleshooting-azcopy.md)。

    所选的文件将下载到步骤 5 中指定的位置。 在父文件夹 (例如 **C：\Remediation**) ，将自动创建以下子文件夹结构：

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *子文件夹 1* 使用案例或审阅集的 ID 进行命名，具体取决于在步骤 1 中所选的范围。

    - *使用下载* 的文件的文件 ID 命名子文件夹 2

    - 下载的文件位于 *Subfolder 2 中* ，并且也使用文件 ID 命名。

    下面是将项目下载到 **C：\Remediation** 父文件夹时创建的文件夹路径和错误文件名的示例：

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    如果下载了多个文件，则每个文件将下载到使用文件 ID 命名的子文件夹。

    > [!IMPORTANT]
    > 在步骤 9 和步骤 10 中上载文件时，已修复的文件必须具有相同的文件名并位于同一子文件夹结构中。 子文件夹和文件名用于将修正的文件与原始错误文件相关联。 如果更改文件夹结构或文件名，您将收到以下错误： `Cannot apply Error Remediation to the current Workingset` 。 为了防止出现任何问题，我们建议将修复的文件保留在同一父文件夹和子文件夹结构中。

7. 下载文件后，可以使用适当的工具修正它们。 对于受密码保护的文件，可以使用多个密码破解工具。 如果您知道文件的密码，可以打开它们并删除密码保护。

8. 返回到高级电子数据展示和错误修正向导，然后单击下一步 **：上载文件**。  这会移到下一个页面，现在您可以在其中上载文件。

    ![上载文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 在"文件的路径位置"文本框中指定已修正文件所在的父文件夹。 同样，父文件夹必须与下载文件时创建的子文件夹结构相同。

    父文件夹的路径会自动添加到 AzCopy (**作为 /Source** 参数的值) 。

10. 通过单击"复制到剪贴板 **"复制预定义的命令**。 打开 Windows 命令提示符，粘贴 AzCopy 命令，然后按 **Enter。** 上传文件。

    ![在 Azcopy 中成功上载修正文件的结果](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 运行 AzCopy 命令后，单击"**下一步： 处理文件"。**

    处理完成后，你可以转到查看集并查看修正的文件。 

## <a name="remediating-errors-in-container-files"></a>修正容器文件的错误

如果高级电子数据展示无法提取容器文件 (如 .zip 文件) 的内容，可以下载容器，并且内容将展开到原始容器所在的同一文件夹中。 展开的文件将属性化为父容器，就像它最初由高级电子数据展示扩展一样。 此过程的工作方式如上所述，只是将单个文件上载为替换文件。  上传修正后的文件时，请勿包含原始容器文件。

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>通过上载提取的文本修正错误

有时无法将文件修正为高级电子数据展示可以解释的本机格式。 但是，你可以将原始文件替换为文本文件，其中包含本机文件的原始文本 (称为文本覆盖) 。  为此，请按照本文中所述的步骤操作，而不是以本机格式修正原始文件，而是创建一个包含从原始文件中提取的文本的文本文件，然后使用附加了 .txt 后缀的原始文件名上载该文本文件。 例如，在文件名为 335850cc-6602-4af0-acfa-1d14d9128ca2.abc 的错误修正过程中下载文件。 在本机应用程序中打开该文件，复制文本，然后将其粘贴到名为 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt。 在这样做时，请确保从本地计算机上已修复的文件位置删除原始文件，然后再将修正的文本文件上载到高级电子数据展示。

## <a name="what-happens-when-files-are-remediated"></a>修正文件时会发生什么情况

上载修正后的文件时，将保留原始元数据，以下字段除外： 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 文本
- WordCount
- WorkingsetId

有关高级电子数据展示中所有元数据字段的定义，请参阅文档 [元数据字段](document-metadata-fields-in-advanced-ediscovery.md)。