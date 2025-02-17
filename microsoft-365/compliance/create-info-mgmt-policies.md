---
title: 创建和应用信息管理策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: 了解如何设置信息管理策略来控制信息的保留时间，并跟踪使用信息的人员。
ms.openlocfilehash: d62eea4c43e6c171bf8c640e341933e81a23e0d0
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64758962"
---
# <a name="create-and-apply-information-management-policies"></a>创建和应用信息管理策略

通过信息管理策略，组织可以控制保留内容的时间、审核用户对内容执行的操作以及向文档添加条形码或标签。 策略可帮助强制遵守法律和政府法规或内部业务流程。 作为管理员，可以设置策略来控制如何跟踪文档以及保留文档的时间。

可以在站点层次结构中的三个不同位置创建信息管理策略，从最宽到最窄：

- 创建一个策略，用于网站集中的多个内容类型。
- 为网站内容类型创建策略。
- 为列表或库创建策略。

有关详细信息，请参阅 [信息管理策略简介](intro-to-info-mgmt-policies.md)。

## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>为网站集中的多个内容类型创建策略
<a name="__toc261001590"> </a>

若要确保将信息策略应用于网站集中特定类型的所有文档，请考虑在网站集级别创建策略，然后将策略应用于内容类型。 这些策略称为网站集策略。

1. 在网站集主页\>**设置**![SharePoint标题栏上的 2016 设置按钮。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \>“**网站设置**”。

    在SharePoint组连接的站点中，单击 **设置**，单击 **“网站内容**”，然后单击 **“网站设置**”。

2. 在“网站设置”页上，在 **“网站集管理** \> **内容类型策略模板**”下。

   ![网站设置页上的内容类型策略模板链接。](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. 在“**策略”** 页\>“创建”

4. 输入策略的名称和说明，然后编写一个简短的策略语句，向用户解释策略的用处。

5. 请参阅下一部分，了解如何为网站内容类型创建策略，了解如何设置要与策略关联的功能。

6. 选择“**确定**”。

## <a name="create-a-policy-for-a-site-content-type"></a>为网站内容类型创建策略
<a name="__create_a_policy"> </a>

将信息管理策略添加到内容类型可以轻松地将策略功能与多个列表或库相关联。 可以选择将现有信息管理策略添加到内容类型，或创建特定于单个内容类型的唯一策略。

 还可以将信息管理策略添加到特定于列表的内容类型。 这会影响仅将策略应用到使用内容类型的列表中的项。

1. 在网站集主页\>**设置**![SharePoint标题栏上的 2016 设置按钮。](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \>“**网站设置**”。

    在SharePoint组连接的站点中，单击 **设置**，单击 **“网站内容**”，然后单击 **“网站设置**”。

2. 在“网站设置”页上，**在“Web 设计器库** \> **”网站内容类型** 下。

   ![网站设置页上的网站内容类型链接。](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)

3. 在“网站内容类型设置”页上，选择要向其添加策略的内容类型。

4. 在“网站内容类型”页 **上的设置** \> **信息管理策略设置** 下。

5. 在“编辑策略”页上，输入策略的名称和说明，然后编写一个简短的说明，向用户说明策略的用量。

6. 在下一部分中，选择要添加到信息管理策略的各个策略功能。

   ![内容策略的类型。](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)

7. 若要为受此策略约束的文档和项目指定保留期，请选择 **“启用保留**”，然后指定保留期和项目过期时要执行的操作。

   指定保留期：

   1. 选择 **为记录添加保留阶段**。

   2. 选择保留期选项以指定文档或项目何时设置为过期。 请按照以下步骤之一操作：
      - 若要根据日期属性设置过期日期，请在 **“事件** \> **此阶段”下基于该项的日期属性**，然后选择文档或项目操作 (例如，创建或修改) 以及此操作后的时间增量 (例如，希望项目过期的天数、月数或年数) 。
      - 若要使用自定义保留公式来确定过期，请选择 **此服务器上安装的自定义保留公式设置**。

        > [!NOTE]
        > 仅当管理员已设置自定义公式时，此选项才可用。

   3. 只有在为已具有与其关联的工作流的列表、库或内容类型定义策略时，“ **启动工作流** ”选项才可用。 然后，你将可以选择要从中选择的工作流。

   4. 在 **“重复”** 部分中，选择 **“重复此阶段的操作...**”，然后输入希望该操作重复执行的频率。

      > [!NOTE]
      >  仅当所选操作可以重复时，此选项才可用。 例如，不能为“ **永久删除**”操作设置重复周期。

   5. 选择“**确定**”。

8. 若要为受此策略约束的文档和项目启用审核，请选择 **“启用审核**”，然后指定要审核的事件。

   若要启用审核，请执行以下操作：

   1. 在 **“审核** ”下的“编辑策略”页上，选择 **“启用审核**”，然后选中要保留审核线索的事件旁边的复选框。

   2. 若要提示用户将这些条形码插入文档，请选择 **提示用户在保存或打印之前插入条形码**。

   3. 选择 **“确定** ”以将审核功能应用于策略。

   审核策略功能使组织能够创建和分析文档的审核线索，并列出任务列表、问题列表、讨论组和日历等项。 此策略功能可提供用于记录事件的审核日志，例如内容被查看、编辑或删除的时间。

   在作为信息管理策略的一部分启用审核时，管理员可以在基于Microsoft Excel和汇总当前使用情况的策略使用情况报告中查看审核数据。 管理员可以使用这些报告来确定信息在组织内的使用率。 这些报告还可以帮助组织验证和记录其法规合规性，或调查潜在问题。

   审核日志可记录以下信息：事件名称、事件的日期和时间以及执行操作的用户的系统名称。

9. 当条形码作为策略的一部分启用时，它们将添加到文档属性中，并显示在应用条形码的文档的标题区域中。 与标签一样，也可以手动从文档中删除条形码。 您可以指定在打印或保存项目时是否应提示用户包含条形码，或者是否应在 2010 Office发布程序中使用 **“插入**”选项卡手动插入条形码。

   若要启用条形码，请执行以下操作：

   1. 在 **“条形码**”下的 **“编辑** 策略”页上，选择 **“启用条形码**”。

   2. 若要提示用户将这些条形码插入文档，请选择 **提示用户在保存或打印之前插入条形码**。

   3. 选择 **“确定** ”以将条形码功能应用于策略。

   条形码策略生成代码 39 标准条形码。 每个条形码图像都包含表示条形码值的条形码符号下方的文本。 这样，即使扫描硬件不可用，也可使用条形码数据。 用户可以在搜索框中手动键入条形码编号，以在网站上找到该项目。  <br/> |

10. 若要要求受此策略约束的文档具有标签，请选择 **“启用标签**”，然后为标签指定所需的设置。

    若要启用标签，请执行以下操作：

    1. 若要要求用户向文档添加标签，请选择 **提示用户在保存或打印之前插入标签**。

       > [!NOTE]
       > 如果您希望标签为可选的，请不要选中此复选框。 

    2. 若要锁定标签，使其在插入后无法更改，请在 **添加标签后选择“阻止对标签的更改**”。

       此设置可防止标签文本在标签插入到客户端应用程序（如 Word、Excel 或 PowerPoint）中的项中后进行更新。 如果您想要在更新该文档或项的属性时更新标签，请不要选中此复选框。

    3. 在“标签”格式框中，输入要显示标签的文本。 标签最多可以包含 10 个列引用，每个引用最多可包含 255 个字符。 若要为标签创建格式，请执行以下步骤：
       - 键入要在标签中包含的列的名称，其顺序是希望它们显示的顺序。 将列名括在卷曲括号 ({}) 中，如“编辑策略”页上的示例所示。
       - 键入单词以标识括号外的列，如“编辑策略”页上的示例所示。

    4. 若要添加换行符，请输入要在其中显示换行符的 **\n** 。

    5. 选择所需的字体大小和样式，并指定是要将标签放置在文档的左侧、中间还是右侧。

       选择可以在用户计算机上使用的字体和样式。 字体的大小将影响可以在标签上显示的文本的多少。

    6. 输入标签的高度和宽度。 标签高度介于 0.25 英寸到 20 英寸之间，标签宽度介于 0.25 英寸到 20 英寸之间。 标签文本始终在标签图像内垂直居中。

    7. 选择 **“刷新** ”以预览标签内容。

11. 选择“**确定**”。

## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>为列表、库或文件夹创建策略（基于位置的保留策略）
<a name="__create_a_policy"> </a>

可以定义仅适用于特定列表、库或文件夹的保留策略。 但是，如果以这种方式创建保留策略，则不能在其他列表、库、文件夹或网站上重复使用此策略，并且不能将网站集策略应用到基于位置的策略。

如果要将单个保留策略应用于单个位置中的所有类型的内容，则很可能希望使用基于位置的保留。 在大多数其他情况下，需要验证是否为所有内容类型指定了保留策略。

每个子文件夹继承其父级的保留策略，除非你选择中断继承并在子级别定义新的保留策略。

如果要定义除保留到列表或库以外的信息管理策略，则需要为与该列表或库关联的每个列表内容类型定义信息管理策略。

如果在任何时候决定从列表或库的内容类型切换到基于位置的策略，则仅保留策略将用作基于位置的策略。 所有其他管理策略 (审核、条形码和条形码) 将从关联的内容类型继承。

可以通过停用基于库和文件夹的保留功能，为网站集禁用基于位置的策略。 这使网站集管理员能够确保其内容类型策略不会被列表管理员的位置策略覆盖。

至少需要管理列表权限才能更改列表或库的信息管理策略设置。

1. 导航到要为其指定信息管理策略的列表或库。

2. 在功能区上，选择“**库** 或 **列表”** 选项卡\>**库设置** 或 **列表设置**。

   在“SharePoint联机”中，单击 **设置**，然后单击 **“列表设置**”或“**库设置**”。

3. 在 **权限和管理**\>**信息管理策略设置下**。

   ![文档库的设置页上的信息管理策略链接。](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. 在“信息管理策略设置页上，确保列表或库的保留源设置为”库“和”文件夹”。

   如果 **内容类型** 显示为源，请单击 **“更改源**”，然后单击“ **库”和“文件夹**”。 系统会提醒你，内容类型保留策略将被忽略。 选择“**确定**”。

5. 在“编辑策略”页上， **在“基于库的保留计划”** 下，输入要创建的策略的简要说明。

6. 选择 **“添加保留阶段...”**

   请注意，在“记录”下，可以选择通过选择“为记录定义不同的保留阶段”选项来定义不同的记录保留策略。

7. 在“阶段属性”对话框中，选择一个保留期选项，以指定文档或项目何时设置为过期。 执行下列操作之一：

   - 若要根据日期属性设置过期日期，请在 **“事件** \> **此阶段”下基于该项的日期属性**，然后选择文档或项目操作 (例如，创建或修改) 以及此操作后的时间增量 (例如，希望项目过期的天数、月数或年数) 。

   - 若要使用自定义保留公式来确定过期，请选择 **此服务器上安装的自定义保留公式设置**。

     > [!NOTE]
     >  仅当管理员已设置自定义公式时，此选项才可用。

   - 在 **“操作**”下，指定要在文档或项目过期时发生的情况。 若要使特定操作发生在文档或项目 (（如删除) ）中，请从列表中选择一个操作。

8. 只有在为已具有与其关联的工作流的列表、库或内容类型定义策略时，“ **启动工作流** ”选项才可用。 然后，你将可以选择要从中选择的工作流。

9. 在 **“重复”** 下，选择 **“重复此阶段”操作...**

   > [!NOTE]
   >  仅当所选操作可以重复时，此选项才可用。 例如，不能为“ **永久删除**”操作设置重复周期。

10. 选择“**确定**”。

## <a name="apply-a-site-collection-policy-to-a-content-type"></a>将网站集策略应用于内容类型
<a name="__apply_a_site"> </a>

如果已为网站创建信息管理策略作为网站集策略，则可以将其中一个策略应用于内容类型。 通过执行此操作，可以将相同的策略应用于不共享相同父内容类型的网站集中的多个内容类型。

 如果要将策略应用于网站集中的多个内容类型，并且配置了托管元数据服务，则可以使用内容类型发布将信息管理策略发布到多个网站集。 有关详细信息，请参阅“ [跨网站集应用策略](#apply-a-policy-across-site-collections) ”部分。

1. 导航到包含要向其应用策略的内容类型的列表或库。

2. 在功能区上，选择“**库** 或 **列表”** 选项卡\>**库设置** 或 **列表设置**。

   在“SharePoint联机”中，单击 **设置**，然后单击 **“列表设置**”或“**库设置**”。

3. 在 **权限和管理** \> **信息管理策略设置下**。

   ![文档库的设置页上的信息管理策略链接。](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)

4. 验证策略源是否设置为 **内容类型**，并在 **“内容类型策略** ”下选择要将策略应用到的内容类型。

5. 在 **“指定策略** \> **”下，使用网站集策略**，然后从列表中选择要应用的策略。

   > [!NOTE]
   >  如果“ **使用网站集策略** ”选项不可用，则尚未为网站集定义任何网站集策略。

6. 选择“**确定**”。

   如果你使用的列表或库支持管理多个内容类型，则在 **“内容类型** ”下，可以选择要为其指定信息管理策略的内容类型。 这会直接转到上面的步骤 5。

## <a name="apply-a-policy-across-site-collections"></a>跨网站集应用策略
<a name="__toc260646789"> </a>

使用托管元数据服务应用程序设置内容类型发布，在网站集之间共享内容类型。 内容类型发布可帮助你在整个网站中一致地管理内容和元数据，因为可以集中创建和更新内容类型，并且更新可以发布到多个订阅网站集或 Web 应用程序。

## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>从现有策略创建模板以跨网站集使用
<a name="__toc262125409"> </a>

可以定义信息管理策略，然后从中创建一个模板，以便在多个网站集中根据需要使用。 如果想要备份信息策略，也可以使用此方法，也可以将其用作使用内容类型发布跨网站集应用一个策略的替代方法。 通过从一个网站集导出策略，然后将其导入到保存的位置或其他网站集，创建策略的模板或备份。

> [!IMPORTANT]
> 如果使用导出/导入功能来创建一组策略模板，请记住策略.xml文件中存在唯一标识符。 因此，在不更改此唯一标识符的情况下，无法多次将该策略导入网站。

### <a name="export-a-policy"></a>导出策略
<a name="__toc260646790"> </a>

1. 在网站集主页上，选择 **取代网站设置的设置**![Small设置齿轮。](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\>**网站设置**。

   在SharePoint组连接的站点中，单击 **设置**，单击 **“网站内容**”，然后单击 **“网站设置**”。

2. 在“网站设置”页上，在 **“网站集管理** \> **内容类型策略模板**”下。

   ![网站设置页上的内容类型策略模板链接。](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)

3. 选择要将滚动导\>出 **到底部**\>导出的策略。

4. 在保存或打开文件的提示处，选择 **“保存**”，然后选择要将文件保存到的位置。 请务必选择可用于导入策略的网站集的位置。

5. 显示“下载完成”对话框时，选择 **“关闭**”。

### <a name="import-a-policy-to-a-different-site-collection"></a>将策略导入到其他网站集
<a name="__toc260646791"> </a>

通过导入信息管理策略，可以将其应用于任何给定网站集中网站或列表级别的多个内容类型。 这样做的好处有两个：无需对每个内容类型重新定义和应用策略，只需在一个位置对策略进行更改即可更轻松地管理策略修改。

1. 在要应用策略的网站集的主页上，选择 **取代网站设置的设置**![设置齿轮。](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png)\>**网站设置**。

   在SharePoint组连接的站点中，单击 **设置**，单击 **“网站内容**”，然后单击 **“网站设置**”。

2. 在“网站设置”页上，在 **“网站集管理** \> **内容类型策略模板**”下。

3. 在“策略”页\>“**导**\>入 **浏览**”中，查找策略的 XML 文件。

4. 选择保存策略的 XML 文件\>**“打开**”。

5. 在“导入网站集策略”页 \>“ **导** 入”中，将策略添加到网站集。

现在可以将导入的策略应用于网站或列表级别的一个或多个内容类型。

通过信息管理策略，组织可以控制保留内容的时间、审核用户对内容执行的操作以及向文档添加条形码或标签。 策略可帮助强制遵守法律和政府法规或内部业务流程。 作为管理员，可以设置策略来控制如何跟踪文档以及保留文档的时间。

可以在站点层次结构中的三个不同位置创建信息管理策略，从最宽到最窄：

- 创建一个策略，用于网站集中的多个内容类型。
- 为网站内容类型创建策略。
- 为列表或库创建策略。

有关详细信息，请参阅 [信息管理策略简介](intro-to-info-mgmt-policies.md)。
