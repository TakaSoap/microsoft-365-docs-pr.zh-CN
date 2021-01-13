---
title: 导出内容搜索结果
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 将搜索结果从 Microsoft 365 合规中心的内容搜索导出到本地计算机。 电子邮件结果导出为 PST 文件。 SharePoint 和 OneDrive for Business 网站中的内容导出为本机 Office 文档。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12c8755d4ca8b5ff97582b879c07fe103c996ecf
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799699"
---
# <a name="export-content-search-results"></a>导出内容搜索结果

成功运行内容搜索后，您可以将搜索结果导出到本地计算机。 导出电子邮件结果时，它们作为 PST 文件下载到计算机。 从 SharePoint 和 OneDrive for Business 网站导出内容时，将导出本机 Office 文档的副本。 导出的搜索结果中包含其他文档和报告。
  
导出内容搜索结果涉及准备结果，然后将结果下载到本地计算机。
  
## <a name="before-you-export-content-search-results"></a>导出内容搜索结果之前

- 若要导出搜索结果，您必须在安全与合规中心内&导出管理角色。 此角色分配给内置电子数据展示管理员角色组。 它没有默认分配至组织管理角色组。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。

- 用于导出搜索结果的计算机必须满足以下系统要求：
  
  - 32 位或 64 位版本的 Windows 7 和更高版本
  
  - Microsoft .NET Framework 4.7
  
- 您必须使用以下受支持的浏览器之一来运行电子数据展示导出工具<sup>1：</sup>

  - Microsoft Edge <sup>2</sup>
  
    OR

  - Microsoft Internet Explorer 10及更高版本
  
  > [!NOTE]
  > <sup>1</sup> Microsoft 不为应用程序制作第三方扩展ClickOnce加载项。 不支持使用具有第三方扩展或加载项的不受支持浏览器导出搜索结果。<br/>
  > <sup>2</sup> 由于最近对 Microsoft Edge 所做的更改，ClickOnce不再启用支持。 有关在 Edge 中ClickOnce支持的说明，请参阅使用 [Microsoft Edge 中的电子数据展示导出工具](configure-edge-to-export-search-results.md)。
  
- 我们建议将搜索结果下载到本地计算机。 但是，若要消除公司防火墙或代理基础结构在下载搜索结果时导致问题，可以考虑将搜索结果下载到网络外部的虚拟桌面。 这可以减少导出大量文件时 Azure 数据连接中发生的超时。 有关虚拟桌面详细信息，请参阅 Windows [虚拟桌面](https://azure.microsoft.com/services/virtual-desktop)。 

- 若要在下载搜索结果时提高性能，请考虑将返回大量结果的搜索划分为较小的搜索。 例如，您可以在搜索查询中使用日期范围返回一组可以更快下载的较小结果。
  
- 导出搜索结果时，数据会临时存储在 Microsoft 提供的 Microsoft 云中的 Azure 存储位置中，然后再下载到本地计算机。 请确保你的组织可以连接到 Azure 中的终结点，即 **\* .blob.core.windows.net (** 通配符表示导出服务的唯一) 。 搜索结果数据在创建两周后从 Azure 存储位置删除。 
  
- 如果您的组织使用代理服务器与 Internet 进行通信，则需要在用于导出搜索结果 (的计算机上定义代理服务器设置，以便代理服务器可以验证导出工具) 。 为此，请打开machine.config Windows 版本匹配的位置中的文件。 
  
  - **32 位：**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64 位：**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    将以下行添加到machine.config标记之间的 `<configuration>` 位置 `</configuration>` 。 请务必替换你的组织，并替换为  `ProxyServer`  `Port` 正确的值;例如，  `proxy01.contoso.com:80` 。 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

## <a name="step-1-prepare-search-results-for-export"></a>第 1 步：准备要导出的搜索结果

第一步是要准备用于导出的搜索结果。 在准备结果时，它们上传到 Microsoft 提供的 Microsoft 云中的 Azure 存储位置。 从邮箱和网站上载的内容的最大速率为每小时 2 GB。
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
  
2. 使用工作或学校帐户进行登录。
  
3. 在安全与合规中心的&，单击 **"搜索** \> **内容"搜索**。
  
4. 在 **"内容搜索"** 页上，选择搜索。 
  
5. 在详细信息窗格中的“将结果导出到计算机”下，单击“开始导出”。
  
    > [!NOTE]
    > 如果搜索结果超过 7 天，将提示你更新搜索结果。如果发生这种情况，取消导出，单击选定搜索的详细信息窗格中的“更新搜索结果”，然后在结果更新后再次启动导出。  
  
6. 在 **"导出搜索结果"** 页上的 **"输出选项**"下，选择下列选项之一：
  
    - 所有项目（不包括具有无法识别的格式的项目）都经过加密，或者出于其他原因未编制索引
  
    - 所有项目（包括无法识别的格式的项目）都经过加密，或者出于其他原因未编制索引
  
    - 只有具有无法识别的格式、已加密或出于其他原因未编制索引的项目
  
    请参阅 ["详细信息"](#more-information) 部分，了解有关如何导出部分索引项的说明。 有关部分索引项详细信息，请参阅 [内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)。
  
7. 在 **"将 Exchange 内容导出为**"下，选择下列选项之一：
  
    - **每个邮箱一个 PST 文件：** 为包含搜索结果的每个用户邮箱导出一个 PST 文件。 来自用户存档邮箱的任何结果都包含在同一 PST 文件中。 此选项从源邮箱重现邮箱文件夹结构。
  
    - **一个包含所有邮件的 PST 文件：** 导出名为 *Exchange.pst* (一) PST 文件，其中包含搜索中包含的所有源邮箱的搜索结果。 此选项可重现每封邮件的邮箱文件夹结构。
  
    - **一个 PST 文件，其中包含单个文件夹中的所有邮件：** 将搜索结果导出到单个 PST 文件，其中所有邮件都位于单个顶级文件夹中。 此选项允许审阅者按时间顺序审阅项目， (项目按发送日期) 排序，而无需导航每个项目的原始邮箱文件夹结构。
  
    - **单个邮件：** 使用 .msg 格式将搜索结果导出为单个电子邮件。 如果选择此选项，电子邮件搜索结果将导出到文件系统中的文件夹。 单个邮件的文件夹路径与将结果导出到 PST 文件时所使用的文件夹路径相同。
  
      > [!IMPORTANT]
      > 若要在导出受 RMS 保护的邮件时解密这些邮件，必须将电子邮件搜索结果导出为单个邮件。 如果将搜索结果导出为 PST 文件，加密的邮件将保持加密状态。 有关详细信息，请参阅本文中解密 [受 RMS](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments) 保护的电子邮件和加密的文件附件。
  
8. 单击 **"启用重复数据删除"** 复选框以排除重复邮件。 此选项仅在搜索的内容源包括 Exchange 邮箱或公用文件夹时显示。 
  
    如果选择此选项，即使在搜索的邮箱中发现了同一邮件的多个副本，也只会导出邮件的一个副本。 导出结果报告 (Results.csv) 将包含重复邮件每个副本的行，以便您可以标识包含重复邮件副本的邮箱 (或公用文件夹) 。 有关重复数据删除以及如何标识重复项的信息，请参阅电子数据展示搜索结果中的重复 [数据删除](de-duplication-in-ediscovery-search-results.md)。
  
9. 单击 **"包含 SharePoint 文档版本"** 复选框以导出所有版本的 SharePoint 文档。 此选项仅在搜索内容源包括 SharePoint 或 OneDrive for Business 网站时显示。 
  
10. 单击 **压缩文件夹中的"** 导出 (压缩) 复选框，将搜索结果导出到压缩文件夹。 此选项仅在选择将 Exchange 项目导出为单个邮件以及搜索结果包括 SharePoint 或 OneDrive 文档时可用。 此选项主要用于在导出项目时绕开 Windows 文件路径名称中的 260 个字符限制。 请参阅"详细信息"部分中的"导出项目的 [文件名](#more-information) "。 
  
11. 单击“开始导出”。 搜索结果已准备下载，这意味着它们被上传到 Microsoft 云中的 Azure 存储位置。 这可能需要几分钟。

有关下载导出的搜索结果的说明，请参阅下一节。
  
## <a name="step-2-download-the-search-results"></a>第 2 步：下载搜索结果

下一步是将搜索结果从 Azure 存储位置下载到本地计算机。
  
1. 在" **内容搜索"** 页上，单击"导出 **"** 选项卡。 
  
   您可能必须单击 **"刷新"** 来更新导出作业的列表，以便它显示您创建的导出作业。 导出作业与相应的搜索具有相同的名称，_Export附加到搜索名称。
  
2. 选择在步骤 1 中创建的导出作业。

3. 在"导出密钥 **"下的飞** 出页上，**单击"复制到剪贴板"。** 在步骤 6 中使用此密钥可下载搜索结果。
  
4. 单击“下载结果”。

5. 如果系统提示您安装 **电子数据展示导出工具**，请单击"**安装"。**

6. 在 **电子数据展示导出工具中**，执行以下操作：

   ![电子数据展示导出工具](../media/eDiscoveryExportTool.png)

   1. 将步骤 3 中复制的导出密钥粘贴到相应的框中。
  
   2. 单击“**浏览**”指定要下载搜索结果文件的位置。
  
      > [!NOTE]
      > 由于读取和写入 (磁盘活动) ，您应将搜索结果下载到本地磁盘驱动器;不要将它们下载到映射的网络驱动器或其他网络位置。 
  
6. 单击“启动”将搜索结果下载到计算机。
  
    **电子数据展示工具** 显示有关导出过程的状态信息，包括要下载的剩余项的估计数量（和大小）。 导出过程完成后，可以访问文件下载位置中的文件。

## <a name="more-information"></a>更多信息

下面详细了解如何导出搜索结果。
  
[导出限制](#export-limits)
  
[导出报告](#export-reports)
  
[导出部分索引项](#exporting-partially-indexed-items)

[导出单个邮件或 PST 文件](#exporting-individual-messages-or-pst-files)
  
[从 100，000 多个邮箱导出结果](#exporting-results-from-more-than-100000-mailboxes)

[解密受 RMS 保护的电子邮件和加密的文件附件](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[导出项目的文件名](#filenames-of-exported-items)  
  
[其他](#miscellaneous)
  
### <a name="export-limits"></a>导出限制

有关导出内容搜索结果时的限制的信息，请参阅内容搜索限制中的"导出 [限制"部分](limits-for-content-search.md#export-limits)。

### <a name="export-reports"></a>导出报告
  
- 导出搜索结果时，除了搜索结果之外，还包括以下报告。
  
  - **导出摘要** 包含导出摘要的 Excel 文档。 这包括诸如已搜索的内容源数量、搜索结果的估计和下载大小以及已导出项目的估计和下载数量等信息。
  
  - **清单** 清单文件 (XML 格式) ，其中包含有关搜索结果中包含的每个项目的信息。
  
  - **结果** 包含有关作为搜索结果下载的每个项目的信息的 Excel 文档。 对于电子邮件，结果日志包含有关每封邮件的信息，包括：
  
    - 邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。
  
    - 发送或接收邮件的日期。

    - 邮件的主题行。

    - 邮件的发件人和收件人。

    - 如果在导出搜索结果时启用了重复数据删除选项，则邮件是否是重复邮件。 重复邮件的" **重复项"列中** 有一个值，该值将邮件标识为重复邮件。 "重复 **项"列中的值** 包含已导出的邮件的项目标识。 有关详细信息，请参阅电子数据展示搜索结果中的重复 [数据消除](de-duplication-in-ediscovery-search-results.md)。

      对于 SharePoint 和 OneDrive for Business 网站中的文档，结果日志包含有关每个文档的信息，包括：

      - 文档的 URL。

      - 文档所在的网站集的 URL 。

      - 上次修改文档的日期。

      - 文档的名称（位于结果日志中的主题列）。

  - **未索引项目** 包含有关搜索结果中将包含的任何部分索引项的信息的 Excel 文档。 如果在生成搜索结果报告时不包含部分索引项，则此报告仍将下载，但为空。

  - **错误和警告** 包含导出过程中遇到的文件的错误和警告。 有关特定于每个错误或警告的信息，请参阅"错误详细信息"列。

  - **跳过的项目** 从 SharePoint 和 OneDrive for Business 网站导出搜索结果时，导出通常包括跳过的项目报告 (SkippedItems.csv) 。 此报告中引用的项目通常是无法下载的项目，例如文件夹或文档集。 不导出这些类型的项目是设计使的。 对于已跳过的其他项目，跳过的项目报告中的"错误类型"和"错误详细信息"字段会显示跳过项目且未与其他搜索结果一起下载的原因。

  - **跟踪日志** 包含有关导出过程的详细日志记录信息，有助于在导出过程中发现问题。
  
    > [!NOTE]
    > 您可以只导出这些文档，而无需导出实际搜索结果。 请参阅 ["导出内容搜索"报告](export-a-content-search-report.md)。 
  
### <a name="exporting-partially-indexed-items"></a>导出部分索引项
  
- 如果要从返回搜索结果 (中所有邮箱项目的内容搜索中导出邮箱项目，因为搜索查询) 中不包含任何关键字，则部分索引项目不会复制到包含未编制索引的项目的 PST 文件中。 这是因为所有项目（包括任何部分索引项）都会自动包含在常规搜索结果中。 这意味着部分索引项目将包含在 PST 文件中 (或作为包含其他) 索引项的单个邮件。

    如果同时导出索引项和部分索引项，或者只从返回所有项目的内容搜索中导出索引项，将下载相同数量的项目。 即使安全 & 合规中心) 中的搜索统计信息中显示的内容搜索 (的估计搜索结果仍包括部分索引项目数的单独估计值，也会发生这种情况。 例如，假设包含搜索查询) 中没有任何关键字的所有项目 (搜索的估计值显示找到了 1，000 个项目，并且还找到了 200 个部分索引项。 在这种情况下，1，000 个项目包含部分索引项，因为搜索将返回所有项目。 换句话说，搜索总共返回 1，000 个项目，而不是 1，200 个项目 (预期) 。 如果导出此搜索结果并选择导出已编制索引和部分索引的项目 (或仅导出部分索引项) ，则下载 1，000 个项目。 同样，这是因为使用空白搜索查询返回所有项目时，常规 (索引项目) 索引的项目包含在结果中。 在同一示例中，如果选择仅导出部分索引项，则仅下载 200 个未编制索引的项目。

    另请注意，在上一示例 (中，导出索引项和部分索引项或仅导出索引项) 时，导出搜索结果中包含的导出摘要报告将列出 1，000 个项目估计项目和 1，000 个已下载项目，原因与前面所述相同。 

- 如果要导出结果的搜索是组织中特定内容位置或所有内容位置的搜索，则仅导出包含与搜索条件匹配的项的内容位置的部分项目。 换句话说，如果在邮箱或网站中未找到搜索结果，则将不会导出该邮箱或网站中任何部分索引的项目。 这是因为从组织中很多位置导出部分索引项可能会增加导出错误的可能性，并增加导出和下载搜索结果所花的时间。

    若要从搜索的所有内容位置导出部分索引项，请通过从搜索查询) 中删除任何关键字，将搜索配置为返回所有项目 (，然后在导出搜索结果时仅导出部分索引项。

    ![使用第三个导出选项仅导出未索引的项目](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- 从 SharePoint 或 OneDrive for Business 网站导出搜索结果时，导出未编制索引的项目的能力还取决于选择的导出选项，以及搜索的网站是否包含与搜索条件匹配的索引项。 例如，如果搜索特定 SharePoint 或 OneDrive for Business 网站，但没有找到搜索结果，那么如果您选择第二个导出选项来同时导出已编制索引的项目和未编制索引的项目，则不导出这些网站中的未编制索引的项目。 如果网站中的索引项与搜索条件匹配，那么在导出已编制索引的项目和未编制索引的项目时，将导出该网站的所有未编制索引的项目。 下图介绍基于网站是否包含与搜索条件匹配的索引项的导出选项。

    ![根据网站是否包含与搜索条件匹配的索引项选择导出选项](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    1. 只导出与搜索条件匹配的索引项。 不导出部分索引项。

    2. 如果网站中的索引项与搜索条件不匹配，则不导出来自同一网站的部分索引项。 如果搜索结果中返回了网站的索引项，则导出该网站中的部分索引项。 换句话说，只导出包含与搜索条件匹配的项的网站中的部分索引项。

    3. 将导出搜索中所有网站的所有部分索引项，无论网站是否包含与搜索条件匹配的项目。

    如果选择导出部分索引项目，则部分索引的邮箱项目将导出到单独的 PST 文件中，而不管在"导出 Exchange 内容"下选择 **的选项如何**。

- 如果在搜索结果中返回部分索引项 (因为部分索引项的其他属性与搜索条件) 匹配，则这些部分索引项会与常规搜索结果一起导出。 因此，如果您选择通过选择"所有项目"导出已编制索引的项目和部分索引项 (，包括已加密格式的项目（包括由于其他原因导出选项) 而未编制索引的项目），则使用常规结果导出的部分索引项将在 Results.csv 报告中列出。 它们将不会在未索引索引items.csv列出。
  
### <a name="exporting-individual-messages-or-pst-files"></a>导出单个邮件或 PST 文件
  
- 如果邮件的文件路径名称超过 Windows 的最大字符限制，则文件路径名将被截断。 但原始文件路径名称将在清单和 ResultsLog 中列出。
  
- 如前所述，电子邮件搜索结果将导出到文件系统中的文件夹。 单个邮件的文件夹路径将复制用户邮箱中的文件夹路径。 例如，对于名为"ContosoCase101"的搜索，用户收件箱中的邮件将位于文件夹路径中  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` 。

- 如果您选择在一个 PST 文件中导出电子邮件，该文件包含单个文件夹中的所有邮件，"已删除邮件"文件夹和"搜索文件夹"文件夹将包含在 PST 文件夹的顶层。 这些文件夹为空。

- 如前所述，您必须将电子邮件搜索结果导出为单个邮件，以在导出受 RMS 保护的邮件时对其进行解密。 如果将电子邮件搜索结果导出为 PST 文件，加密的邮件将保持加密状态。
  
### <a name="exporting-results-from-more-than-100000-mailboxes"></a>从 100，000 多个邮箱导出结果

- 如前所述，您必须使用安全与合规& PowerShell 从 100，000 多个邮箱下载搜索结果。 可以在此部分中运行以下脚本来下载这些搜索结果。 使用此脚本假定你已导出搜索结果 (导出作业显示在内容搜索工具的"导出"选项卡上) 现在想要下载它们。

   ```powershell
   $export=Get-ComplianceSearchAction SEARCHNAME_Export -IncludeCredential;
   $exportUrl=   [System.Uri]::EscapeDataString(($export.Results.Split(";") | ?{$_ -like '*Container url*'} | %{$_.Split(":",2)} | select -last 1).Trim());
   $exportToken=($export.Results.Split(";") | ?{$_ -like '*SAS Token*'} | %{$_.Split(":",2)} | select -last 1).Trim();
   ."$env:ProgramFiles\Internet Explorer\IEXPLORE.EXE" "https://complianceclientsdf.blob.core.windows.net/v16/Microsoft.Office.Client.Discovery.UnifiedExportTool.application?name=$($export.Name)&source=$exportUrl&zip=allow&trace=1";
   $exportToken | clip;
   ```

  在脚本中，必须指定要导出结果的搜索的名称。 例如，对于名为的搜索， `SearchAllMailboxes` 将SEARCHNAME_Export替换为 `SearchAllMailboxes_Export` 。

  将搜索的名称添加到脚本后，可以复制脚本文本，然后将其粘贴到连接到安全与合规中心 PowerShell 的 Windows PowerShell 窗口中[&。](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 粘贴脚本后，电子数据展示导出工具 (与使用 UI 工具下载搜索结果时一样) ：

  ![电子数据展示导出工具](../media/eDiscoveryExportTool.png)

  在导出键框中单击，然后按以粘贴导出 (脚本将导出密钥复制到剪贴板 `CTRL + V`) 。 单击 **"** 浏览"以指定要下载文件的位置，然后开始下载。

  如前所述，建议您将搜索结果下载到本地磁盘驱动器，因为读取和写入 (磁盘活动) 。 不要将搜索结果下载到映射的网络驱动器或其他网络位置。

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>解密受 RMS 保护的电子邮件和加密的文件附件

导出内容 (任何受 RMS) 权限保护的电子邮件都会在导出时解密。 此外，使用 [Microsoft](encryption.md) 加密技术加密并附加到搜索结果中的电子邮件的任何文件在导出时也会解密。 默认情况下，为电子数据展示管理员角色组的成员启用此解密功能。 这是因为默认情况下，RMS 解密管理角色已分配给此角色组。 导出加密电子邮件和附件时，请记住以下事项：
  
- 如前所述，若要在导出受 RMS 保护的邮件时解密这些邮件，您必须将搜索结果导出为单个邮件。 如果将搜索结果导出到 PST 文件，则受 RMS 保护的邮件将保持加密状态。

- 解密的邮件在 **ResultsLog** 报告中进行标识。 此报告包含一个名为 **Decode Status** 的列，并且此列中的 **Decoded** 值标识解密的消息。

- 除了在导出搜索结果时解密文件附件之外，还可以在预览搜索结果时预览解密的文件。 导出后，只能查看受权限保护的电子邮件。

- 目前，导出搜索结果时解密功能不包括 SharePoint 和 OneDrive for Business 网站中的加密内容。 但是，即将推出对使用 Microsoft 加密技术加密并存储在 SharePoint Online 和 OneDrive for Business 中的文档的支持。

- 如果需要阻止某人解密 RMS 保护的邮件和加密的文件附件，您必须通过复制内置电子数据展示管理器角色组) 来创建自定义角色组 (，然后从自定义角色组中删除 RMS 解密管理角色。 然后将不希望解密邮件的人添加为自定义角色组的成员。
  
### <a name="filenames-of-exported-items"></a>导出项目的文件名
  
- 对于导出到本地计算机 (电子邮件和网站文档的完整路径名) ，操作系统会施加 260 个字符的限制。 导出项目的完整路径名称包括项目的原始位置和搜索结果下载到的本地计算机上的文件夹位置。 例如，如果指定将搜索结果下载到电子数据展示导出工具中，则下载的电子邮件项目的完整路径  `C:\Users\Admin\Desktop\SearchResults` 名为  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` 。

    如果超过 260 个字符的限制，则项目的完整路径名将被截断。

  - 如果完整路径名超过 260 个字符，将缩短文件名，以低于限制;请注意，截断的文件名 (文件扩展名) 不会少于 8 个字符。

  - 如果缩短文件名后完整路径名仍然太长，则项目会从当前位置移动到父文件夹。 如果路径名仍然太长，则重复此过程：缩短文件名，并在必要时再次移动到父文件夹。 此过程将重复，直到完整路径名在 260 个字符的限制下。

  - 如果截断的完整路径名已存在，则会在文件名末尾添加版本号;例如  `statusmessage(2).msg` ，。

    为了帮助缓解此问题，请考虑将搜索结果下载到路径名称短的位置;例如，将搜索结果下载到名为的文件夹时，向导出项目的路径名称添加的字符数少于将其下载到名为  `C:\Results`  `C:\Users\Admin\Desktop\Results` 文件夹的字符数。

- 导出网站文档时，还可以修改文档的原始文件名。 这尤其适用于从 SharePoint 或 OneDrive for Business 网站中删除并置于保留状态的文档。 在删除处于保留状态的网站上的文档后，已删除的文档将自动移动到网站 (的保留库，该库是在将网站置于保留状态时创建的) 。 将删除的文档移动到保留库时，随机生成的唯一 ID 将追加到文档的原始文件名中。 例如，如果文档的文件名是，并且该文档稍后被删除并移动到保留库，则移动到保留库的文档的文件名将修改为类似的内容  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 。 如果保留库中的文档与内容搜索的查询匹配，并且您导出了该搜索的结果，则导出的文件具有修改后的文件名;本示例中，导出文档的文件名为  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 。

    修改保留网站中的文档后 (并且网站中的文档库的版本控制已启用) ，则会自动在保留库中创建该文件的副本。 在这种情况下，随机生成的唯一 ID 也会追加到复制到保留库的文档的文件名中。

    将文档文件名移动或复制到保留库的原因是为了防止文件名冲突。 有关将网站和保留库置于保留状态详细信息，请参阅 [SharePoint Server 2016 中的](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)就地保留概述。

### <a name="miscellaneous"></a>其他
  
- 使用电子数据展示导出工具下载搜索结果时，可能会收到以下错误：这是暂时性错误，通常发生在 Azure 存储 `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 位置。 若要解决此问题，请 [重试下载](#step-2-download-the-search-results)搜索结果，这将重新启动电子数据展示导出工具。

- 所有搜索结果和导出报告包含在一个与内容搜索同名的文件夹中。 已导出的电子邮件位于名为 **Exchange** 的文件夹中。 文档位于名为 **SharePoint** 的文件夹中。

- 将文档导出到本地计算机时，将维护 SharePoint 和 OneDrive for Business 网站上文档的文件系统元数据。 这意味着当文档被导出时，其文档属性，如创建日期和上次修改日期不会被更改。

- 如果搜索结果包含与搜索查询匹配的 SharePoint 中的列表项，则除了与搜索查询匹配的项和列表中任何附件之外，还将导出列表中的所有行。 此行为的原因是为搜索结果中返回的列表项提供上下文。 另请注意，其他列表项和附件可能会导致导出项的计数不同于搜索结果的原始估计值。
