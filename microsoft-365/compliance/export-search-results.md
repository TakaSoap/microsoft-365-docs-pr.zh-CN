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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 将搜索内容搜索中的搜索结果导出Microsoft 365 合规中心本地计算机。 电子邮件结果导出为 PST 文件。 来自SharePoint和OneDrive for Business网站的内容作为本机文档Office导出。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f4a140b933aabbdcf06c9f3c9ab0cbf40d2b05e7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170676"
---
# <a name="export-content-search-results"></a>导出内容搜索结果

成功运行内容搜索后，可以将搜索结果导出到本地计算机。 导出电子邮件结果时，它们作为 PST 文件下载到计算机。 当您从网站和SharePoint网站OneDrive for Business内容时，将导出本机Office文档的副本。 导出的搜索结果中包含其他文档和报告。
  
导出内容搜索结果涉及准备结果，然后将结果下载到本地计算机。 导出搜索结果的这些步骤也适用于导出与核心电子数据展示事例关联的搜索结果。
  
## <a name="before-you-export-search-results"></a>导出搜索结果之前

- 若要导出搜索结果，您必须在"网站"中分配"导出"Microsoft 365 合规中心。 此角色分配给内置电子数据展示管理员角色组。 它没有默认分配至组织管理角色组。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。

- 用于导出搜索结果的计算机必须满足以下系统要求：
  
  - 最新版 Windows (32 位或 64 位) 
  
  - Microsoft .NET Framework 4.7 或更高版本
  
- 您必须使用 Microsoft Edge<sup>1</sup>运行电子数据展示导出工具。 使用 Internet Explorer 11 导出搜索结果不再受<sup>支持 2。</sup>
  
  > [!NOTE]
  > <sup>1</sup>由于最近对 Microsoft Edge 所做的更改，ClickOnce不再启用默认支持。 有关在 Edge 中ClickOnce支持的说明，请参阅使用 Edge 中的电子[数据展示导出Microsoft Edge。](configure-edge-to-export-search-results.md) 此外，Microsoft 不会为应用程序制作第三方扩展ClickOnce加载项。 不支持使用不支持的浏览器和第三方扩展或加载项导出搜索结果。
  >
  > <sup>2</sup>从 2021 年 8 月开始，Microsoft 365 应用和服务将不再支持 Internet Explorer 11 (IE11) 并且用户可能体验降级或无法连接到这些应用和服务。 这些应用和服务将在过去的几周和几个月内逐步淘汰，以确保顺利结束支持。 每个应用和服务都按独立计划逐步淘汰。 有关详细信息，请参阅此 [博客文章](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666)。

- 在步骤 2 中用于下载搜索结果电子数据展示导出工具不支持 (脚本或运行 cmdlet 来自动) 。 强烈建议不要自动执行步骤 1 中的准备过程或步骤 2 中的下载过程。 如果自动执行上述任一过程，Microsoft 支持人员将不会在遇到问题时提供帮助。

- 我们建议将搜索结果下载到本地计算机。 若要消除公司防火墙或代理基础结构在下载搜索结果时导致问题，可以考虑将搜索结果下载到网络外部的虚拟桌面。 这可以减少导出大量文件时 Azure 数据连接中发生的超时。 有关虚拟桌面的信息，请参阅虚拟Windows[桌面](https://azure.microsoft.com/services/virtual-desktop)。

- 若要在下载搜索结果时提高性能，请考虑将返回大量结果的搜索划分为较小的搜索。 例如，您可以使用搜索查询中的日期范围返回一组较小的结果，可以更快地下载结果。
  
- 导出搜索结果时，数据会临时存储在 Microsoft 提供的Azure 存储 Microsoft 云中的位置，然后再下载到本地计算机。 请确保你的组织可以连接到 Azure 中的终结点，即 **\* .blob.core.windows.net** (通配符表示导出服务的唯一) 。 搜索结果数据在创建后的两Azure 存储从搜索位置删除。 
  
- 如果您的组织使用代理服务器与 Internet 进行通信，则需要在用于导出搜索结果 (的计算机上定义代理服务器设置，以便您的代理服务器) 可以验证导出工具。 为此，请打开 *machine.config* 版本匹配的位置中的文件Windows。 
  
  - **32 位：** `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64 位：** `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    将以下行添加到  *machine.config*  和 标记之间的  `<configuration>` 某  `</configuration>` 位置。 请务必将 和 替换为组织的正确  `ProxyServer`  `Port` 值;例如， `proxy01.contoso.com:80` 。 
  
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

- 如果搜索结果超过 7 天并且您提交导出作业，则会显示一条错误消息，提示您重新运行搜索以更新搜索结果。 如果发生这种情况，请取消导出，重新运行搜索，然后再次开始导出。

## <a name="step-1-prepare-search-results-for-export"></a>第 1 步：准备要导出的搜索结果

第一步是要准备用于导出的搜索结果。 当你准备结果时，它们上传到 Microsoft 提供的Azure 存储 Microsoft 云中的位置。 邮箱和网站中的内容以每小时 2 GB 的最大速率上载。
  
1. 在Microsoft 365 合规中心中，选择要导出结果的内容搜索。
  
2. 在弹出 **页** 底部的"操作"菜单上，单击"**导出结果"。**

   !["操作"菜单中的"导出结果"选项。](../media/ActionMenuExportResults.png)

   将显示 **"导出结果** "飞出页。 可用于导出内容的导出选项取决于搜索结果位于邮箱或网站中还是两者的组合。

3. 在 **"输出选项**"下，选择下列选项之一：
  
   ![导出输出选项。](../media/ExportOutputOptions.png)

    - **所有项目（不包括无法识别** 的格式的项目）都经过加密，或者出于其他原因未编制索引。 此选项仅导出索引项。
  
    - **所有项目（包括无法识别的格式** 的项目）都经过加密，或者出于其他原因未编制索引。 此选项导出已编制索引和未编制索引的项目。
  
    - **只有具有无法识别的格式**、已加密或出于其他原因未编制索引的项。 此选项仅导出未索引的项目。

      请参阅 [详细信息部分](#more-information) ，了解有关如何导出部分索引项的说明。 有关部分索引项的信息，请参阅内容搜索 [中的部分索引项](partially-indexed-items-in-content-search.md)。

4. 在 **"Exchange内容导出为"下**，选择下列选项之一：
  
   ![Exchange选项。](../media/ExchangeExportOptions.png)

    - **每个邮箱一个 PST 文件**：为包含搜索结果的每个用户邮箱导出一个 PST 文件。 来自用户存档邮箱的任何结果都包含在同一 PST 文件中。 此选项从源邮箱重现邮箱文件夹结构。
  
    - **一个包含** 所有邮件的 PST 文件：导出一个名为 *Exchange (.pst*) 的 PST 文件，其中包含搜索中包含的所有源邮箱的搜索结果。 此选项可重现每封邮件的邮箱文件夹结构。
  
    - **一个 PST 文件，其中包含** 单个文件夹中的所有邮件：将搜索结果导出到单个 PST 文件，其中所有邮件均位于单个顶级文件夹中。 此选项允许审阅者按时间顺序审阅项目 (按发送日期) 而无需导航每个项目的原始邮箱文件夹结构。
  
    - **单个邮件**：使用 .msg 格式将搜索结果导出为单个电子邮件。 如果选择此选项，电子邮件搜索结果将导出到文件系统中的文件夹。 单个邮件的文件夹路径与将结果导出到 PST 文件时所使用的文件夹路径相同。
  
5. 配置以下附加选项：

   ![配置其他导出选项。](../media/OtherExportOptions.png)

   1. 选中"**为内容Exchange重复数据删除"复选框** 以排除重复邮件。
  
      如果选择此选项，即使在搜索的邮箱中发现了同一邮件的多个副本，也只会导出邮件的一个副本。 导出结果报告 (该文件名为 Results.csv) ，它将包含重复邮件每个副本的行，以便您可以标识包含重复邮件副本的邮箱 (或公用文件夹) 。 有关重复数据删除以及如何标识重复项的信息，请参阅电子数据展示搜索结果中 [的重复数据删除](de-duplication-in-ediscovery-search-results.md)。
  
   2. 选中 **"包括文件SharePoint复选框** 导出文档的所有SharePoint版本。 此选项仅在搜索的内容源包括网站或网站SharePoint OneDrive for Business显示。
  
   3. Select the **Export files in a compressed (zipped) folder.仅包含单个邮件SharePoint文档** 复选框，以将搜索结果导出到压缩文件夹。 此选项仅在选择将项目导出为Exchange以及搜索结果包含单个邮件或文档SharePoint时OneDrive显示。 此选项主要用于在导出项目时处理文件路径Windows 260 个字符的限制。 请参阅详细信息部分中的"导出项目的 [文件名](#more-information) "。
   > [!IMPORTANT]
   > 将文件导出到压缩 (压缩) 将增加导出时间。
  
6. 单击 **"导出** "开始导出过程。 搜索结果准备下载，这意味着它们从原始内容位置收集，然后上传到 Microsoft 云中的Azure 存储位置。 这可能需要几分钟。

有关下载导出的搜索结果的说明，请参阅下一部分。
  
## <a name="step-2-download-the-search-results"></a>第 2 步：下载搜索结果

下一步是将搜索结果从本地Azure 存储下载到本地计算机。
  
1. 在页面 **的"** 内容搜索"Microsoft 365 合规中心，选择"导出 **"** 选项卡
  
   您可能必须 **单击"刷新** "来更新导出作业的列表，以便它显示您创建的导出作业。 导出作业与相应的搜索具有相同的名称，_Export附加到搜索名称。
  
2. 选择在步骤 1 中创建的导出作业。

3. 在"导出密钥"下的飞出 **页面上，** 单击 **"复制到剪贴板"。** 在步骤 6 中使用此密钥下载搜索结果。
  
   > [!IMPORTANT]
   > 因为任何人都可以安装和启用电子数据展示导出工具，然后使用该密钥来下载搜索结果，所以一定要采取预防措施来保护此密钥，就像保护你的密码或其他与安全相关的信息。 

4. 在飞出页面顶部，单击"**下载结果"。**

5. 如果系统提示安装电子 **数据展示导出工具，请单击**"安装 **"。**

6. 在 **电子数据展示导出工具中**，执行以下操作：

   ![电子数据展示导出工具。](../media/eDiscoveryExportTool.png)

   1. 将步骤 3 中复制的导出密钥粘贴到相应的框中。
  
   2. 单击“**浏览**”指定要下载搜索结果文件的位置。
  
      > [!IMPORTANT]
      >  由于下载期间网络活动较高，应仅将搜索结果下载到本地计算机上内部驱动器上的位置。 为了获得最佳下载体验，请遵循以下指南： <br/>
      >- 不要将搜索结果下载到 UNC 路径、映射的网络驱动器、外部 USB 驱动器或已同步OneDrive for Business帐户。<br/>
      >- 对将搜索结果下载到的文件夹禁用防病毒扫描。<br/>
      >- 将搜索结果下载到并发下载作业的不同文件夹。

7. 单击“启动”将搜索结果下载到计算机。
  
    **电子数据展示工具** 显示有关导出过程的状态信息，包括要下载的剩余项的估计数量（和大小）。 导出过程完成后，你可以在文件下载的位置访问它们。

## <a name="more-information"></a>更多信息

以下是有关导出搜索结果的信息。
  
[导出限制](#export-limits)
  
[导出报告](#export-reports)
  
[导出部分索引项](#exporting-partially-indexed-items)

[导出单个邮件或 PST 文件](#exporting-individual-messages-or-pst-files)

[解密受 RMS 保护的电子邮件和加密的文件附件](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[导出项的文件名](#filenames-of-exported-items)  
  
[其他](#miscellaneous)
  
### <a name="export-limits"></a>导出限制

有关导出内容搜索结果时的限制的信息，请参阅内容搜索限制中的"导出 [限制"部分](limits-for-content-search.md#export-limits)。

### <a name="export-reports"></a>导出报告
  
- 导出搜索结果时，除搜索结果外，还包括以下报告。
  
  - **导出摘要** 包含Excel摘要的一个文档。 其中包括搜索的内容源数量、搜索结果的估计和下载大小以及导出的预计和下载的项目数等信息。
  
  - **清单** 清单文件 (XML 格式) ，其中包含有关搜索结果中包括的每个项目的信息。
  
  - **结果** 一Excel文档，其中包含有关作为搜索结果下载的每个项目的信息。 对于电子邮件，结果日志包含有关每封邮件的信息，包括：
  
    - 邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。
  
    - 发送或接收邮件的日期。

    - 邮件的主题行。

    - 邮件的发件人和收件人。

    - 如果在导出搜索结果时启用了"重复数据删除"选项，则邮件是否是重复邮件。 重复邮件在"复制到项目" **列中有** 一个值，该值将邮件标识为重复邮件。 "复制到 **项目"** 列中的值包含已导出的邮件的项目标识。 有关详细信息，请参阅电子[数据展示搜索结果中的重复数据展示。](de-duplication-in-ediscovery-search-results.md)

      对于来自SharePoint和OneDrive for Business的文档，结果日志包含有关每个文档的信息，包括：

      - 文档的 URL。

      - 文档所在的网站集的 URL 。

      - 上次修改文档的日期。

      - 文档的名称（位于结果日志中的主题列）。

  - **未索引项目** 一Excel文档，其中包含有关搜索结果中将包含的任何部分索引项的信息。 如果在生成搜索结果报告时未包含部分索引项，此报告仍将下载，但将为空。

  - **错误和警告** 包含导出过程中遇到的文件的错误和警告。 有关特定于每个错误或警告的信息，请参阅错误详细信息列。

  - **跳过的项目** 从网站和网站SharePoint搜索结果OneDrive for Business导出时，导出通常包括跳过的项目 (SkippedItems.csv) 。 此报告中引用的项目通常是不会下载的项目，例如文件夹或文档集。 不导出这些类型的项目是设计使的。 对于跳过的其他项目，跳过的项目报告中的"错误类型"和"错误详细信息"字段会显示跳过项目且未与其他搜索结果一起下载的原因。

  - **Trace.log** 包含有关导出过程的详细日志记录信息，有助于在导出过程中发现问题。 如果向 Microsoft 支持人员打开与导出搜索结果相关的问题的票证，系统可能会要求您提供此跟踪日志。
  
    > [!NOTE]
    > 您可以只导出这些文档，而无需导出实际搜索结果。 请参阅 [导出内容搜索报告](export-a-content-search-report.md)。
  
### <a name="exporting-partially-indexed-items"></a>导出部分索引项
  
- 如果要从返回搜索结果 (中所有邮箱项目的内容搜索中导出邮箱项目，因为搜索查询) 中不包含任何关键字，部分索引项目不会复制到包含未编制索引的项目的 PST 文件中。 这是因为所有项目（包括任何部分索引的项目）都会自动包含在常规搜索结果中。 这意味着部分索引项目将包含在 PST 文件中 (或作为单个邮件) 包含其他已编制索引的项目。

    如果同时导出索引项和部分索引项，或者只从返回所有项的内容搜索中导出索引项，则下载的项目数相同。 即使显示在 Microsoft 365 合规中心) 中的搜索统计信息中的内容搜索 (估计的搜索结果仍将包含部分索引项数的单独估计值，也会发生这种情况。 例如，假设包含搜索查询) 中未包含关键字的所有项目 (搜索的估计值显示找到了 1，000 个项目，并且还找到了 200 个部分索引项。 在这种情况下，1，000 个项目包括部分索引项，因为搜索将返回所有项目。 换句话说，搜索总共返回了 1，000 个项目，而不是您 (1，200 个项目) 。 如果导出此搜索的结果并选择导出索引项和部分索引项 (或仅导出部分索引项) ，将下载 1，000 个项目。 同样，这是因为当您使用空白搜索查询返回所有项目时，常规 (索引) 包含部分索引项。 在同一示例中，如果选择仅导出部分索引项，则仅下载 200 个未编制索引的项目。

    另请注意，在上一示例 (中，导出索引项和部分索引项或仅导出索引项) 时，导出搜索结果中包含的"导出摘要"报告将列出 1，000 个项目估计项目和 1，000 个已下载项目，原因与前面所述相同。 

- 如果要导出结果的搜索是组织中特定内容位置或所有内容位置的搜索，则仅导出包含与搜索条件匹配的项的内容位置的部分项目。 换句话说，如果在邮箱或网站中未找到搜索结果，则不导出该邮箱或网站中任何部分索引的项目。 这样做的原因是，从组织中很多位置导出部分索引项可能会增加导出错误的可能性，并增加导出和下载搜索结果所花的时间。

    若要从搜索的所有内容位置导出部分索引项，请通过从搜索查询) 中删除任何关键字，将搜索配置为返回所有项目 (，然后在导出搜索结果时仅导出部分索引项。

    ![使用第三个导出选项仅导出未索引的项目。](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- 从 SharePoint 或 OneDrive for Business 网站导出搜索结果时，导出未编制索引的项目的能力还取决于您选择的导出选项，以及搜索的网站是否包含与搜索条件匹配的索引项。 例如，如果您搜索特定 SharePoint 或 OneDrive for Business 网站，但没有找到搜索结果，那么如果您选择第二个导出选项来导出已编制索引的项目和未编制索引的项目，则不导出这些网站的未编制索引的项目。 如果网站中的索引项与搜索条件匹配，则导出已编制索引的项目和未编制索引的项目时，将导出该网站的所有未编制索引的项目。 下图介绍基于网站是否包含与搜索条件匹配的索引项的导出选项。

    ![根据网站是否包含与搜索条件匹配的索引项，选择导出选项。](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    a. 只导出与搜索条件匹配的索引项。 不导出部分索引项。

    b. 如果网站中的索引项与搜索条件不匹配，则不导出同一网站中的部分索引项。 如果搜索结果中返回了网站的索引项，则导出该网站中的部分索引项。 换句话说，仅导出网站中包含与搜索条件匹配的项目的部分索引项。

    c. 将导出搜索中所有网站的所有部分索引项，无论网站是否包含与搜索条件匹配的项目。

    如果您选择导出部分索引项目，部分索引的邮箱项目将导出到单独的 PST 文件中，而不管在"将内容导出为"下选择的选项Exchange **导出**。

- 如果在搜索结果中返回部分索引项 (因为部分索引项的其他属性与搜索条件) 匹配，那么这些部分索引项会与常规搜索结果一起导出。 因此，如果您选择通过选择"所有项目"（包括具有无法识别的格式、已加密或由于其他原因未编制索引的导出选项) ）导出已编制索引的项目和部分索引项 (，则随常规结果导出的部分索引项将列在 Results.csv 报告中。 它们不会列在未索引索引items.csv报告中。
  
### <a name="exporting-individual-messages-or-pst-files"></a>导出单个邮件或 PST 文件
  
- 如果邮件的文件路径名超过邮件的最大字符Windows，则文件路径名将被截断。 但原始文件路径名称将在清单和结果日志中列出。
  
- 如前所述，电子邮件搜索结果将导出到文件系统中的文件夹。 单个邮件的文件夹路径将复制用户邮箱中的文件夹路径。 例如，对于名为"ContosoCase101"的搜索，用户收件箱中的邮件将位于文件夹路径 中  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` 。

- 如果您选择将电子邮件导出到一个 PST 文件中，其中包含单个文件夹中的所有邮件，则"已删除邮件"文件夹和"搜索文件夹"文件夹将包含在 PST 文件夹的顶层中。 这些文件夹为空。

- 如前所述，必须将电子邮件搜索结果导出为单个邮件，以在导出受 RMS 保护的邮件时对其进行解密。 如果将电子邮件搜索结果导出为 PST 文件，加密邮件将保持加密状态。
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>解密受 RMS 保护的电子邮件和加密的文件附件

导出内容 (结果) 受 RMS 保护的任何受 RMS 保护的电子邮件都将被解密。 此外，任何使用 [Microsoft](encryption.md) 加密技术加密并附加到包含在搜索结果中的电子邮件的文件在导出时也会解密。 默认情况下，为电子数据展示管理员角色组的成员启用此解密功能。 这是因为默认情况下，RMS 解密管理角色已分配给此角色组。 导出加密电子邮件和附件时，请记住以下事项：
  
- 如前所述，若要在导出受 RMS 保护的邮件时解密这些邮件，您必须将搜索结果导出为单个邮件。 如果将搜索结果导出到 PST 文件，受 RMS 保护的邮件将保持加密状态。

- 解密的邮件在 **ResultsLog** 报告中进行标识。 此报告包含一个名为 **Decode Status** 的列，并且此列中的 **Decoded** 值标识已解密的消息。

- 除了在导出搜索结果时解密文件附件之外，还可以在预览搜索结果时预览解密的文件。 导出后，只能查看受权限保护的电子邮件。

- 目前，导出搜索结果时解密功能不包括来自网站和网站SharePoint OneDrive for Business内容。 但是，即将推出对使用 Microsoft 加密技术加密并存储在 SharePoint Online 和 OneDrive for Business 中的文档的支持。

- 如果需要阻止某人解密受 RMS 保护的邮件和加密的文件附件，您必须通过复制内置电子数据展示管理器角色组) 创建自定义角色组 (，然后从自定义角色组中删除 RMS 解密管理角色。 然后将不希望解密邮件的人添加为自定义角色组的成员。
  
### <a name="filenames-of-exported-items"></a>导出项的文件名
  
- 操作系统 (对导出到本地计算机的电子邮件和网站文档的完整路径) 具有 260 个字符的限制。 导出项目的完整路径名称包括项目的原始位置和搜索结果下载到的本地计算机上的文件夹位置。 例如，如果指定将搜索结果下载到电子数据展示导出工具中，则下载的电子邮件项的完整路径名  `C:\Users\Admin\Desktop\SearchResults` 为  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` 。

- 如果超过 260 个字符的限制，则项目的完整路径名将截断，依据如下：

  - 如果完整路径名超过 260 个字符，则文件名将缩短，以低于限制;请注意，截断的文件名 (不包括文件扩展名) 不会少于 8 个字符。

  - 如果缩短文件名后完整路径名仍然太长，则项目会从当前位置移动到父文件夹。 如果 pathname 仍然过长，则重复此过程：缩短文件名，如有必要，请再次移动到父文件夹。 重复此过程，直到完整路径名在 260 个字符的限制下。

  - 如果截断的完整路径名已存在，版本号将添加到文件名的末尾;例如， `statusmessage(2).msg` 。

    为了帮助缓解此问题，请考虑将搜索结果下载到路径名称短的位置;例如，将搜索结果下载到名为 的文件夹时，导出项目的路径名称中的字符数将少于将其下载到名为  `C:\Results` 的文件夹的字符  `C:\Users\Admin\Desktop\Results` 数。

- 导出网站文档时，也可能修改文档的原始文件名。 对于从已置于保留状态SharePoint OneDrive for Business或网站中删除的文档，尤其会发生此情况。 删除处于保留状态的网站上的文档后，已删除的文档将自动移动到网站 (在网站处于保留状态时创建的保留库) 。 当删除的文档移动到保留库时，随机生成的唯一 ID 将追加到文档的原始文件名中。 例如，如果文档的文件名是 ，并且该文档稍后被删除并移动到保留库，则移动到保留库的文档的文件名将修改为类似 的内容  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 。 如果保留库中的文档与内容搜索的查询匹配，并且您导出了该搜索的结果，则导出的文件具有修改后的文件名;本示例中，导出文档的文件名为  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 。

    修改保留网站中的文档后 (且网站中的文档库的版本控制已启用) 时，将自动在保留库中创建文件副本。 在这种情况下，还会将随机生成的唯一 ID 附加到复制到保留库的文档的文件名中。

    将文档文件名移动或复制到保留库的原因是为了防止文件名冲突。 有关将网站和保留库置于保留状态详细信息，请参阅[overview of in-place hold in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)。

### <a name="miscellaneous"></a>其他
  
- 使用电子数据展示导出工具下载搜索结果时，您可能会收到以下错误：这是暂时性错误，通常发生在 Azure 存储 `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 位置。 若要解决此问题，请 [重试下载搜索结果](#step-2-download-the-search-results)，这将重新启动电子数据展示导出工具。

- 所有搜索结果和导出报告都包含在与内容搜索同名的文件夹中。 已导出的电子邮件位于名为 **Exchange** 的文件夹中。 文档位于名为 **SharePoint** 的文件夹中。

- 将文档导出到本地计算机SharePoint OneDrive for Business将维护文档和网站中文档的文件系统元数据。 这意味着当文档被导出时，其文档属性，如创建日期和上次修改日期不会被更改。

- 如果您的搜索结果包含来自 SharePoint 且与搜索查询匹配的列表项，则除了与搜索查询匹配的项目以及列表中任何附件之外，还将导出列表中的所有行。 此行为的原因是为搜索结果中返回的列表项提供上下文。 其他列表项和附件可能会导致导出的项目数不同于搜索结果的原始估计值。
