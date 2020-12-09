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
description: 将搜索结果从 Microsoft 365 合规性中心中的内容搜索导出到本地计算机。 电子邮件结果将导出为 PST 文件。 SharePoint 和 OneDrive for business 网站中的内容将导出为本机 Office 文档。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a697f5cf81022bf8d8122d0dd57c07ba8a578f0a
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602049"
---
# <a name="export-content-search-results"></a>导出内容搜索结果

在成功运行内容搜索之后，您可以将搜索结果导出到本地计算机。 导出电子邮件结果时，会将其作为 PST 文件下载到您的计算机上。 当您从 SharePoint 和 OneDrive for business 网站导出内容时，会导出本机 Office 文档的副本。 导出的搜索结果中包含其他文档和报告。
  
导出内容搜索结果包括准备结果，然后将其下载到本地计算机。
  
## <a name="before-you-export-content-search-results"></a>导出内容搜索结果之前

- 若要导出搜索结果，您必须在安全 & 合规性中心中分配有导出管理角色。 此角色分配给内置电子数据展示管理员角色组。 它没有默认分配至组织管理角色组。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。

- 用于导出搜索结果的计算机必须满足以下系统要求：
  
  - 32位或64位版本的 Windows 7 及更高版本
  
  - Microsoft .NET Framework 4.7
  
- 您必须使用下列受支持的浏览器之一运行电子数据展示导出工具<sup>1</sup>：

  - Microsoft Edge <sup>2</sup>
  
    OR

  - Microsoft Internet Explorer 10 及更高版本
  
  > [!NOTE]
  > <sup>1</sup> Microsoft 不会为 ClickOnce 应用程序制造第三方扩展或加载项。 使用不受支持的浏览器导出搜索结果，但不支持第三方分机或加载项。<br/>
  > <sup>2</sup> 由于最近对 Microsoft Edge 进行了更改，因此 ClickOnce 支持在默认情况下不再启用。 有关在 Edge 中启用 ClickOnce 支持的说明，请参阅 [在 Microsoft Edge 中使用电子数据展示导出工具](configure-edge-to-export-search-results.md)。
  
- 建议将搜索结果下载到本地计算机。 但是，若要避免公司的防火墙或代理基础结构在下载搜索结果时导致出现问题，您可能需要考虑将搜索结果下载到网络外部的虚拟桌面。 这可能会降低在导出大量文件时在 Azure 数据连接中发生的超时。 有关虚拟桌面的详细信息，请参阅 [Windows 虚拟桌面](https://azure.microsoft.com/services/virtual-desktop)。 

- 若要在下载搜索结果时提高性能，请考虑将返回大型结果集的搜索划分为较小的搜索。 例如，您可以在搜索查询中使用日期范围来返回可以更快下载的较小结果集。
  
- 当您导出搜索结果时，数据暂时存储在 Microsoft 云中的 Microsoft 提供的 Azure 存储位置中，然后将其下载到本地计算机。 确保您的组织可以连接到 Azure 中的终结点，即 **\* blob.core.windows.net** (通配符代表导出) 的唯一标识符。 搜索结果数据在创建后的两周内从 Azure 存储位置中删除。 
  
- 如果您的组织使用代理服务器与 Internet 通信，则需要在用于导出搜索结果的计算机上定义代理服务器设置，以便您的代理服务器可以对导出工具进行身份验证)  (。 为此，请在与您的 Windows 版本相匹配的位置打开  *machine.config*  文件。 
  
  - **32 位：**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64 位：**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    将以下行添加到 "  *machine.config*  " 文件中的 "  `<configuration>` 和" 标记之间  `</configuration>` 。 请务必将和替换为  `ProxyServer`  `Port` 你的组织的正确值; 例如，  `proxy01.contoso.com:80` 。 
  
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

第一步是要准备用于导出的搜索结果。 当你准备结果时，会将其上载到 Microsoft 云中的 Microsoft 提供的 Azure 存储位置。 邮箱和网站中的内容将以每小时 2 GB 的最大速度上载。
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
  
2. 使用工作或学校帐户进行登录。
  
3. 在安全性 & 合规性中心的左侧窗格中，单击 " **搜索** \> **内容搜索**"。
  
4. 在 " **内容搜索** " 页上，选择 "搜索"。 
  
5. 在详细信息窗格中的“将结果导出到计算机”下，单击“开始导出”。
  
    > [!NOTE]
    > 如果搜索结果超过 7 天，将提示你更新搜索结果。如果发生这种情况，取消导出，单击选定搜索的详细信息窗格中的“更新搜索结果”，然后在结果更新后再次启动导出。  
  
6. 在 " **导出搜索结果** " 页上的 " **输出选项**" 下，选择下列选项之一：
  
    - 除其他原因之外的所有项（不包括不可识别格式的项）均已加密或未编制索引
  
    - 所有项目（包括不可识别格式的项目）均已加密，或未针对其他原因进行索引
  
    - 仅有无法识别的格式的项目被加密，或没有为其他原因编制索引
  
    请参阅 [详细信息](#more-information) 部分，了解有关如何导出部分索引项的说明。 有关部分索引项的详细信息，请参阅 [内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)。
  
7. 在 "将 **Exchange 内容导出为**" 下，选择下列选项之一：
  
    - **每个邮箱一个 PST 文件：** 为包含搜索结果的每个用户邮箱导出一个 PST 文件。 来自用户存档邮箱的任何结果都包含在同一个 PST 文件中。 此选项将从源邮箱中重现邮箱文件夹结构。
  
    - **一个包含所有邮件的 PST 文件：** 从包含在搜索中的所有源邮箱中的搜索结果中 (名为) 的 *Exchange .pst* 文件中导出一个 PST 文件。 此选项将为每个邮件重现邮箱文件夹结构。
  
    - **一个 PST 文件，其中包含单个文件夹中的所有邮件：** 将搜索结果导出到单个 PST 文件中，其中所有邮件都位于单个顶级文件夹中。 使用此选项，审阅者可以按时间顺序查看项目 (项目按发送日期进行排序) 无需为每个项目导航原始邮箱文件夹结构。
  
    - **单个邮件：** 将搜索结果导出为单个电子邮件（使用 .msg 格式）。 如果选择此选项，则会将电子邮件搜索结果导出到文件系统中的文件夹。 单个邮件的文件夹路径与您将结果导出到 PST 文件时所使用的相同。
  
      > [!IMPORTANT]
      > 若要在导出受 RMS 保护的邮件时对其进行解密，必须将电子邮件搜索结果导出为单个邮件。 如果将搜索结果导出为 PST 文件，则加密邮件将保持加密。 有关详细信息，请参阅本文中的 [解密受 RMS 保护的电子邮件和加密文件附件](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments) 。
  
8. 单击 " **启用重复数据** 删除" 复选框以排除重复的邮件。 仅当搜索的内容源包括 Exchange 邮箱或公用文件夹时，才会出现此选项。 
  
    如果选择此选项，则即使在搜索的邮箱中找到同一邮件的多个副本，也只导出邮件的一个副本。  ( # A0) 的导出结果报告将包含一个重复邮件的每个副本的行，以便您可以识别包含重复邮件副本) 的邮箱 (或公用文件夹。 有关重复数据删除和标识重复项目的详细信息，请参阅 [电子数据展示搜索结果中的重复数据](de-duplication-in-ediscovery-search-results.md)消除。
  
9. 单击 " **包括 sharepoint 文档的版本** " 复选框以导出 sharepoint 文档的所有版本。 仅当搜索的内容源包括 SharePoint 或 OneDrive for Business 网站时，才会出现此选项。 
  
10. 单击 " **在压缩 (压缩) 文件夹中导出文件** " 复选框，将搜索结果导出到压缩文件夹。 仅当选择将 Exchange 项目导出为单个邮件以及搜索结果包括 SharePoint 或 OneDrive 文档时，此选项才可用。 此选项主要用于在导出项目时，在 Windows 文件路径名中解决260字符的限制。 请参阅 " [详细信息](#more-information) " 部分中的 "导出项目的文件名"。 
  
11. 单击“开始导出”。 搜索结果已准备好下载，这意味着正在将其上载到 Microsoft 云中的 Azure 存储位置。 这可能需要几分钟。

有关下载导出的搜索结果的说明，请参阅下一节。
  
## <a name="step-2-download-the-search-results"></a>第 2 步：下载搜索结果

下一步是将搜索结果从 Azure 存储位置下载到本地计算机。
  
1. 在 " **内容搜索** " 页上，单击 " **导出** " 选项卡。 
  
   您可能需要单击 " **刷新** " 以更新导出作业的列表，以便显示您创建的导出作业。 导出作业与对应的搜索具有相同的名称，并将 **_Export** 追加到搜索名称。
  
2. 选择您在步骤1中创建的导出作业。

3. 在 " **导出项**" 下的弹出页面上，单击 " **复制到剪贴板**"。 您可以使用步骤6中的此键下载搜索结果。
  
4. 单击“下载结果”。

5. 如果系统提示您安装 **电子数据展示导出工具**，请单击 " **安装**"。

6. 在 " **电子数据展示导出工具**" 中，执行以下操作：

   ![电子数据展示导出工具](../media/eDiscoveryExportTool.png)

   1. 将您在步骤3中复制的导出密钥粘贴在相应的框中。
  
   2. 单击“**浏览**”指定要下载搜索结果文件的位置。
  
      > [!NOTE]
      > 由于大量磁盘活动 (读取和写入) ，因此应将搜索结果下载到本地磁盘驱动器;不要将其下载到映射的网络驱动器或其他网络位置。 
  
6. 单击“启动”将搜索结果下载到计算机。
  
    **电子数据展示工具** 显示有关导出过程的状态信息，包括要下载的剩余项的估计数量（和大小）。 导出过程完成后，可以在文件的下载位置访问这些文件。

## <a name="more-information"></a>详细信息

以下是有关导出搜索结果的详细信息。
  
[导出限制](#export-limits)
  
[导出报告](#export-reports)
  
[导出部分索引的项目](#exporting-partially-indexed-items)

[导出单个邮件或 PST 文件](#exporting-individual-messages-or-pst-files)
  
[从100000个以上的邮箱导出结果](#exporting-results-from-more-than-100000-mailboxes)

[解密受 RMS 保护的电子邮件和加密文件附件](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[导出项目的文件名](#filenames-of-exported-items)  
  
[其他](#miscellaneous)
  
### <a name="export-limits"></a>导出限制
  
- 从安全性 & 合规性中心导出搜索结果的限制如下：

  - 您可以从单个内容搜索中导出最多 2 TB 的数据。 如果搜索结果大于 2 TB，请考虑使用日期范围或其他类型的筛选器来减小搜索结果的总大小。
  
  - 您的组织可以在一天内导出最多 2 TB 的数据。
  
  - 在你的组织中最多可以同时运行 10 个导出。

  - 单个用户最多可以同时运行三个导出。
  
  - 您可以使用 Office 365 安全性 & 合规性中心或 Microsoft 365 合规性中心中的电子数据展示导出工具，从最多100000个邮箱中下载搜索结果。 若要从100000个以上的邮箱下载搜索结果，您必须使用 Security & 合规性中心 PowerShell。 有关说明，请参阅 [导出超过100000个邮箱的结果](#exporting-results-from-more-than-100000-mailboxes)。

  > [!NOTE]
  > 仅导出内容搜索中的报告也会对同时运行的导出数以及单个用户可以运行的导出数进行计数。
  
- 如前所述，邮箱和网站中的搜索结果将上载到 Microsoft 提供的 Azure 存储位置 (如 [步骤1：为导出) 准备搜索结果](#step-1-prepare-search-results-for-export) 中所述，最大速率为每小时 2 GB。
  
- 默认情况下，可以导出的 PST 文件的最大大小为 10 GB。 这意味着，如果用户邮箱中的搜索结果大于 10 GB，则邮箱的搜索结果将在两个 (或更多) 单独的 PST 文件中导出。 如果选择在单个 PST 文件中导出所有搜索结果，则在搜索结果的总大小大于 10 GB 时，PST 文件将 spilt 到其他 PST 文件中。 如果要更改此默认大小，可以在用于导出搜索结果的计算机上编辑 Windows 注册表。 请参阅 [在导出电子数据展示搜索结果时更改 PST 文件的大小](change-the-size-of-pst-files-when-exporting-results.md)。
  
    此外，特定邮箱中的搜索结果不会在多个 PST 文件中划分，除非单个邮箱中的内容大于 10 GB。 如果您选择将搜索结果导出到一个包含单个文件夹中的所有邮件的一个 PST 文件中，并且搜索结果大于 10 GB，则这些项目仍按时间顺序进行组织，因此这些项目将根据发送日期 spilt 到其他 PST 文件中。
  
### <a name="export-reports"></a>导出报告
  
- 当您导出搜索结果时，除了搜索结果之外，还包含以下报告。
  
  - **导出摘要** 包含导出摘要的 Excel 文档。 这包括一些信息，如搜索的内容源的数量、搜索结果的估计和下载大小以及导出的估计和下载项目数。
  
  - **清单** 以 XML 格式)  (的清单文件，其中包含搜索结果中包含的每个项目的相关信息。
  
  - **结果** 包含作为搜索结果下载的每个项目的相关信息的 Excel 文档。 对于电子邮件，结果日志包含有关每封邮件的信息，其中包括：
  
    - 邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。
  
    - 发送或接收邮件的日期。

    - 邮件的主题行。

    - 邮件的发件人和收件人。

    - 如果在导出搜索结果时启用了重复数据删除选项，则该邮件是否为重复的邮件。 重复邮件的 " **重复项** " 列中有一个将邮件标识为重复的值。 " **复制到项** " 列中的值包含导出的邮件的项目标识。 有关详细信息，请参阅 [电子数据展示搜索结果中的重复数据消除](de-duplication-in-ediscovery-search-results.md)。

      对于 SharePoint 和 OneDrive for business 网站中的文档，结果日志包含有关每个文档的信息，包括：

      - 文档的 URL。

      - 文档所在的网站集的 URL 。

      - 上次修改文档的日期。

      - 文档的名称（位于结果日志中的主题列）。

  - 未 **编制索引的项目** 一个 Excel 文档，其中包含搜索结果中将包含的任何部分已编制索引的项目的相关信息。 如果在生成搜索结果报告时未包含部分索引项目，则仍将下载此报告，但会将其保留为空。

  - **错误和警告** 包含导出过程中遇到的文件的错误和警告。 有关特定于每个单独的错误或警告的信息，请参阅 "错误详细信息" 列。

  - **跳过的项目** 当您从 SharePoint 和 OneDrive for business 网站导出搜索结果时，导出通常会在 # A0)  ( 包含跳过的项目报告。 此报告中引用的项目通常是不会下载的项目，如文件夹或文档集。 不能导出这些类型的项目是设计的。 对于跳过的其他项目，跳过的项目报告中的 "错误类型" 和 "错误详细信息" 字段将显示跳过项目的原因并在其他搜索结果中下载。

  - **跟踪日志** 包含有关导出过程的详细日志记录信息，并且有助于在导出过程中发现问题。
  
    > [!NOTE]
    > 您可以只导出这些文档，而无需导出实际的搜索结果。 请参阅 [导出内容搜索报告](export-a-content-search-report.md)。 
  
### <a name="exporting-partially-indexed-items"></a>导出部分索引的项目
  
- 如果要从内容搜索中导出邮箱项目，而该搜索将返回搜索结果中的所有邮箱项目 (因为在搜索查询中包含的关键字不) ，则不会将部分索引项目复制到包含未编制索引的项目的 PST 文件中。 这是因为所有项目（包括任何部分索引的项目）都会自动包括在常规搜索结果中。 这意味着部分索引项目将包含在 PST 文件 (或单个邮件中，) 包含其他已编制索引的项目。

    如果同时导出已编制索引和部分索引的项目，或者如果只从返回所有项目的内容搜索中导出已编制索引的项目，则会下载相同数量的项目。 即使在安全 & 合规性中心的搜索统计信息中显示的内容搜索 (的估计搜索结果也会发生，) 仍将包含对部分索引项目的数量的单独估计。 例如，假设搜索条件包括搜索查询中的所有项目 (没有关键字) 显示已找到1000个项目，并且也找到了200个部分索引的项目。 在这种情况下，1000项目包含部分索引的项目，因为搜索将返回所有项目。 换言之，搜索返回的项目总数为1000个，而不是1200个项目 (您可能会看到) 。 如果您导出此搜索的结果并选择导出已编制索引和部分索引的项目 (或仅导出部分索引项目) ，则将下载1000个项目。 同样，这是因为在使用空白搜索查询返回所有项目时，部分索引项目包含在常规 (索引) 结果中。 在此示例中，如果您选择仅导出部分索引项，则只会下载200未编制索引的项。

    另请注意，在上一示例中 (导出已编制索引和部分索引的项目，或者仅导出索引项) 时，导出的搜索结果中包含的 **导出摘要** 报告将列出1000项目估计项目和1000下载项目，原因与前面所述的相同。 

- 如果要从中导出结果的搜索是对组织中的特定内容位置或所有内容位置的搜索，则仅导出内容位置中包含与搜索条件匹配的项目的部分项目。 换言之，如果在邮箱或网站中找不到任何搜索结果，则不会导出该邮箱或网站中的任何部分索引项目。 这样做的原因是，从组织中的很多位置导出部分索引项目可能会增加导出错误的可能性，并增加导出和下载搜索结果所需的时间。

    若要从搜索的所有内容位置中导出部分索引的项目，请将搜索配置为返回所有项目 (，方法是删除搜索查询中的所有关键字) ，然后在导出搜索结果时仅导出部分索引项。

    ![使用第三个导出选项仅导出未编制索引的项目](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- 从 SharePoint 或 OneDrive for Business 网站导出搜索结果时，导出未编制索引的项目的功能还取决于您选择的导出选项以及所搜索的网站是否包含与搜索条件匹配的索引项。 例如，如果您搜索特定的 SharePoint 或 OneDrive for Business 网站，并且未找到任何搜索结果，则如果选择 "第二个导出" 选项以导出已编制索引和未编制索引的项目，则不会导出这些网站中未索引的项目。 如果网站中的某个索引项与搜索条件匹配，则在导出索引项目和未编制索引的项目时，将导出该网站中的所有未编制索引的项目。 下图介绍了基于网站是否包含与搜索条件匹配的索引项的导出选项。

    ![根据网站是否包含与搜索条件匹配的索引项，选择 "导出" 选项](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    1. 仅导出与搜索条件匹配的索引项。 不会导出任何部分索引的项目。

    2. 如果网站中没有索引项与搜索条件相匹配，则不会导出来自该相同网站的部分索引项。 如果在搜索结果中返回网站中的索引项，则导出来自该网站的部分索引项。 换言之，仅导出包含与搜索条件匹配的项目的网站中部分索引的项目。

    3. 将导出搜索中所有网站的部分已编制索引的项目，而不管网站是否包含与搜索条件匹配的项目。

    如果选择导出部分索引项目，部分索引的邮箱项目将导出到单独的 PST 文件中，而不考虑您在 "将 **Exchange 内容导出为**" 下选择的选项。

- 如果在搜索结果中返回部分索引项 (由于部分索引项的其他属性与搜索条件相匹配) ，则将使用常规搜索结果导出部分索引的项。 因此，如果选择通过选择 " **所有项目" （包括格式不可识别的项目）、"已加密" 或 "未按其他) 原因编制** 索引" (导出已编制索引的项目和部分索引的项目，则 Results.csv 报告中将列出以常规结果导出的部分索引项目。 它们不会列在未编制索引的 items.csv 报告中。
  
### <a name="exporting-individual-messages-or-pst-files"></a>导出单个邮件或 PST 文件
  
- 如果邮件的文件路径名称超过了 Windows 的最大字符数限制，文件路径名称将被截断。 但原始文件路径名称将在清单和 ResultsLog 中列出。
  
- 如前所述，电子邮件搜索结果导出到文件系统中的文件夹。 每个邮件的文件夹路径将复制用户邮箱中的文件夹路径。 例如，在用户收件箱中名为 "ContosoCase101" 的搜索邮件位于文件夹路径中  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` 。

- 如果选择在一个 PST 文件中导出电子邮件，其中包含单个文件夹中的所有邮件，则 " **已删除邮件** " 文件夹和 " **搜索文件夹** " 文件夹将包含在 pst 文件夹的顶层。 这些文件夹是空的。

- 如前所述，您必须将电子邮件搜索结果导出为单个邮件，以便在导出受 RMS 保护的邮件时对其进行解密。 如果将电子邮件搜索结果导出为 PST 文件，则加密邮件将保持加密。
  
### <a name="exporting-results-from-more-than-100000-mailboxes"></a>从100000个以上的邮箱导出结果

- 如前所述，必须使用 Security & 合规性中心 PowerShell 下载100000多个邮箱中的搜索结果。 您可以在此部分中运行以下脚本以下载这些搜索结果。 使用此脚本假设您已经导出了搜索结果 ("导出" 作业将显示在 "内容搜索" 工具的 " **导出** " 选项卡上) 并且现在想要下载它们。

   ```powershell
   $export=Get-ComplianceSearchAction SEARCHNAME_Export -IncludeCredential;
   $exportUrl=   [System.Uri]::EscapeDataString(($export.Results.Split(";") | ?{$_ -like '*Container url*'} | %{$_.Split(":",2)} | select -last 1).Trim());
   $exportToken=($export.Results.Split(";") | ?{$_ -like '*SAS Token*'} | %{$_.Split(":",2)} | select -last 1).Trim();
   ."$env:ProgramFiles\Internet Explorer\IEXPLORE.EXE" "https://complianceclientsdf.blob.core.windows.net/v16/Microsoft.Office.Client.Discovery.UnifiedExportTool.application?name=$($export.Name)&source=$exportUrl&zip=allow&trace=1";
   $exportToken | clip;
   ```

  在脚本中，必须指定要导出其结果的搜索的名称。 例如，对于名为的搜索，将 `SearchAllMailboxes` SEARCHNAME_Export 替换为 `SearchAllMailboxes_Export` 。

  将搜索的名称添加到脚本后，可以复制脚本文本，然后将其粘贴到 [已连接到安全 & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)的 Windows PowerShell 窗口中。 在粘贴脚本之后，将显示电子数据展示导出工具 (如下所示：当您使用 UI) 下载搜索结果时：

  ![电子数据展示导出工具](../media/eDiscoveryExportTool.png)

  在 "导出密钥" 框中单击，然后按 `CTRL + V` "粘贴导出密钥" (脚本将导出密钥复制到 "剪贴板") 。 单击 " **浏览** " 以指定要在其中下载文件的位置，然后开始下载。

  如前所述，我们建议您将搜索结果下载到本地磁盘驱动器，因为大量磁盘活动 (读写) 。 不将搜索结果下载到映射的网络驱动器或其他网络位置。

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>解密受 RMS 保护的电子邮件和加密文件附件

在导出内容搜索的结果中包含的任何受权限保护 (受 RMS 保护的) 电子邮件都将被解密。 此外，使用 [Microsoft 加密技术](encryption.md) 加密的任何文件和附加到搜索结果中包含的电子邮件的任何文件在导出时也会被解密。 默认情况下，将为电子数据展示管理器角色组的成员启用此解密功能。 这是因为默认情况下会将 RMS 解密管理角色分配给此角色组。 在导出加密的电子邮件和附件时，请记住以下几点：
  
- 如前所述，若要在导出受 RMS 保护的邮件时对其进行解密，您必须将搜索结果导出为单个邮件。 如果将搜索结果导出到 PST 文件，受 RMS 保护的邮件将保持加密状态。

- 解密的邮件在 **ResultsLog** 报告中进行标识。 此报告包含一个名为 " **解码状态**" 的列，此列中的 " **解码** " 值标识已解密的邮件。

- 除了在导出搜索结果时对文件附件进行解密之外，还可以在预览搜索结果时预览解密的文件。 导出受权限保护的电子邮件后，才能查看该邮件。

- 目前，导出搜索结果时的解密功能不包括 SharePoint 和 OneDrive for business 网站中的加密内容。 但是，对使用 Microsoft 加密技术加密的文档，以及存储在 SharePoint Online 和 OneDrive for business 中的文档即将提供支持。

- 如果需要阻止某人解密受 RMS 保护的邮件和加密文件附件，则必须通过复制内置的电子数据展示管理器角色组来创建自定义角色组，) 然后从自定义角色组中删除 RMS 解密管理角色 (。 然后，将您不想将邮件解密的人员添加为自定义角色组的成员。
  
### <a name="filenames-of-exported-items"></a>导出项目的文件名
  
- 操作系统 (设定了260字符的限制) 用于电子邮件和导出到本地计算机的网站文档的完整路径名称。 导出项目的完整路径名称包括项目的原始位置和本地计算机上将搜索结果下载到的文件夹位置。 例如，如果您指定将搜索结果下载到  `C:\Users\Admin\Desktop\SearchResults` 电子数据展示导出工具中，则下载的电子邮件项目的完整路径名将为  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` 。

    如果超过260字符的限制，将截断项目的完整路径名称。

  - 如果完整路径名的长度超过260个字符，则文件名将被缩短，以达到限制。请注意，截断的文件名 (不包括文件扩展名) 不会少于8个字符。

  - 如果缩短文件名后完整路径名仍然过长，则项目将从当前位置移至父文件夹。 如果路径名仍然太长，则重复该过程：缩短文件名，并在需要时再次移到父文件夹。 将重复此过程，直到完整路径名低于260个字符的限制。

  - 如果已存在截断的完整路径名称，则会将版本号添加到文件名的末尾;例如，  `statusmessage(2).msg` 。

    若要帮助缓解此问题，请考虑将搜索结果下载到具有短路径名称的位置;例如，将搜索结果下载到名为的文件夹中时，  `C:\Results` 会向导出项的路径名称添加更少的字符，而不是将其下载到名为的文件夹中  `C:\Users\Admin\Desktop\Results` 。

- 导出网站文档时，也可能会修改文档的原始文件名。 对于已从 SharePoint 或 OneDrive for business 网站中删除的文档已被置于保留状态，这一点尤其适用。 删除处于保留状态的网站上的文档后，已删除的文档将自动移至网站的保留保留库，该网站是在网站置于保留状态时创建的 () 。 将已删除的文档移到保留保留库时，将在文档的原始文件名后追加随机生成的唯一 ID。 例如，如果某个文档的文件名为  `FY2017Budget.xlsx` ，并且随后删除该文档并移到保留保留库中，则移动到保留保留库的文档的文件名将修改为类似的内容  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 。 如果保留保留库中的文档与内容搜索的查询相匹配，并且您导出该搜索的结果，则导出的文件具有修改后的文件名;在此示例中，导出的文档的文件名为  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 。

    如果修改了处于保留状态的网站上的文档 (并且已在网站上) 启用了文档库的版本控制，则会在 "保留保留" 库中自动创建该文件的副本。 在这种情况下，随机生成的唯一 ID 也会追加到复制到保留保留库的文档的文件名。

    移动或复制到保留保留库的文档文件名的原因是，避免文件名发生冲突。 有关在网站和保留保留库中放置保留的详细信息，请参阅 [SharePoint Server 2016 中的就地保留概述](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)。

### <a name="miscellaneous"></a>其他
  
- 使用电子数据展示导出工具下载搜索结果时，可能会收到以下错误： `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 这是暂时性错误，通常发生在 Azure 存储位置中。 若要解决此问题，请重试 [下载搜索结果](#step-2-download-the-search-results)，这将重新启动电子数据展示导出工具。

- 所有搜索结果和导出报告包含在一个与内容搜索同名的文件夹中。 已导出的电子邮件位于名为 **Exchange** 的文件夹中。 文档位于名为 **SharePoint** 的文件夹中。

- 将文档导出到本地计算机时，SharePoint 和 OneDrive for Business 网站上的文档的文件系统元数据将保留。 这意味着当文档被导出时，其文档属性，如创建日期和上次修改日期不会被更改。

- 如果搜索结果包含与搜索查询匹配的 SharePoint 中的列表项，则除了与搜索查询匹配的项以及列表中的任何附件之外，还将导出列表中的所有行。 此行为的原因是为搜索结果中返回的列表项提供上下文。 另请注意，其他列表项和附件可能会导致导出项目的计数与搜索结果的原始估计值不同。
