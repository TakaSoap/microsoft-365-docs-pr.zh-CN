---
title: 修正处理数据时出现的错误
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
description: ''
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2019
ms.locfileid: "37074963"
---
# <a name="error-remediation-when-processing-data"></a>修正处理数据时出现的错误

错误修正使电子数据展示管理员能够修正阻止高级电子数据展示的数据问题，从而无法正确处理内容。 例如，由于文件被锁定或加密，因此无法处理受密码保护的文件。 使用错误修正，电子数据展示管理员可以下载具有此类错误的文件，删除密码保护，然后上传修正的文件。

使用以下工作流修正高级电子数据展示事例中有错误的文件。

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>创建错误修正会话以修正带有处理错误的文件

>[!NOTE]
>如果在以下过程中随时关闭错误修正向导，则可以通过在 "**视图**" 下拉菜单中选择 " **Remediations** " 从 "**处理**" 选项卡返回到错误修正会话。

1. 在高级电子数据展示事例的 "**处理**" 选项卡上，选择 "**视图**" 下拉菜单中的 "**错误**"，然后选择 "**范围**" 下拉菜单中的 "检查集" 或 "整个事例"。 此部分显示来自特定审阅集的事例或错误中的所有错误。

   ![错误修正](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. 通过单击 "错误类型" 或 "文件类型" 旁边的单选按钮，选择要修正的错误。  在下面的示例中，我们正在修正受密码保护的文件。

3. 单击 "**新建错误修正**"。

    错误修正工作流从准备阶段开始，其中有错误的文件复制到 Microsoft 提供的 Azure 存储位置，以便您可以将其下载到本地计算机以进行修正。

    ![准备错误修正](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 准备完成后，单击 "**下一步：下载文件**" 以继续下载。

    ![下载文件](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 若要下载文件，请指定**下载的目标路径**。 这是您的本地计算机上的父文件夹的路径，将在该文件夹中下载文件。  默认路径 "%USERPROFILE%\Downloads\errors" 指向已登录用户的 "下载" 文件夹。 如果需要，可以更改此路径。 如果您确实要更改它，建议使用本地文件路径以获得最佳性能。 请勿使用远程网络路径。 例如，可以使用路径**C:\Remediation**。 

   父文件夹的路径将自动添加到 AzCopy 命令（作为 **/Dest**参数的值）。

6. 通过单击 "**复制到剪贴板**" 复制预定义命令。 打开 Windows 命令提示符，粘贴 "AzCopy" 命令，然后按**enter**。  

    ![准备进行错误修正](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > 必须使用 AzCopy app-v 8.1 才能成功使用 "**下载文件**" 页上提供的命令。 此外，还必须使用 AzCopy 中的第10步上载文件。 若要安装此版本的 AzCopy，请参阅[在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。 如果提供的 AzCopy 命令失败，请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。

    您选择的文件将下载到您在步骤5中指定的位置。 在父文件夹（例如， **C:\Remediation**）中，将自动创建以下子文件夹结构：

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *子文件夹 1*以事例或审阅集的 ID 命名，具体取决于您在步骤1中选择的范围。

    - *子文件夹 2*以下载文件的文件 ID 命名

    - 下载的文件位于*子文件夹 2*中，也用文件 ID 命名。

    下面的示例展示了在将项目下载到**C:\Remediation**父文件夹时创建的文件夹路径和错误文件名：

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    如果下载了多个文件，则会将每个文件下载到一个以文件 ID 命名的子文件夹中。

    > [!IMPORTANT]
    > 当您在步骤9和步骤10中上传文件时，修正的文件必须具有相同的文件名，并且位于相同的子文件夹结构中。 子文件夹和文件名用于将修正的文件与原始错误文件相关联。 如果文件夹结构或文件名称已更改，您将收到以下错误： `Cannot apply Error Remediation to the current Workingset`。 为了防止出现任何问题，我们建议将修正的文件保留在相同的父文件夹和子文件夹结构中。

7. 下载文件后，可以使用适当的工具对它们进行修正。 对于受密码保护的文件，可以使用几种密码破解工具。 如果您知道这些文件的密码，则可以打开它们并删除密码保护。

8. 返回到高级电子数据展示和错误修正向导，然后单击 "**下一步：上传文件**"。  这将移到下一个页面，你现在可以在这里上传文件。

    ![上传文件](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 在 "**文件的位置**" 文本框的 "路径" 中，指定修正文件所在的父文件夹。 同样，父文件夹的子文件夹结构必须与下载文件时创建的子文件夹结构相同。

    父文件夹的路径将自动添加到 AzCopy 命令（作为 **/source**参数的值）。

10. 通过单击 "**复制到剪贴板**" 复制预定义命令。 打开 Windows 命令提示符，粘贴 "AzCopy" 命令，然后按**enter**。 上传文件。

    ![ff2ff691-629f-4065-9b37-5333f937daf6](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 运行 AzCopy 命令后，单击 "**下一步：处理文件**"。

    处理完成后，可以转到 "查看" 设置并查看修正的文件。 

## <a name="what-happens-when-files-are-remediated"></a>修正文件时会发生什么情况

当上载修正的文件时，原始元数据将保留，但以下字段除外： 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 文本
- WordCount
- WorkingsetId

有关高级电子数据展示中所有元数据字段的定义，请参阅[Document metadata fields](document-metadata-fields.md)。
