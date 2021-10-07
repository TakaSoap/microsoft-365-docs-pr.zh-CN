---
title: '在 Microsoft 隐私管理中管理主题权限 (预览) '
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Microsoft 隐私管理中的主题权限请求区域可帮助你查找个人数据，并协作查看内容和创建报告。
ms.openlocfilehash: deb5bc50aa047cd336684e586ee3bf86286417c1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207207"
---
# <a name="manage-subject-rights-requests-in-privacy-management-preview"></a>管理隐私管理中的主题权限请求 (预览) 

隐私管理提供了强大的主题权限请求功能，可帮助你处理寻求在组织中管理其个人数据的人的请求。 这些请求有时也称为数据主体请求 (DSR) 、数据主体访问 (DSAR) 或消费者权利请求。 隐私管理使负责履行主体权利请求的人员可以轻松识别数据主体，并找到 Exchange、SharePoint、OneDrive 和 Teams 中组织数据中的个人信息。

隐私管理功能独特，有助于在针对这些请求收集的数据中确定要审阅的项的优先级。 解决方案了解一些Microsoft 信息保护标签，这些标签指示可能属于机密的内容，可能需要进行特殊审查，并标记具有这些标签的项目。 有关敏感度标签详细信息，请参阅 [了解敏感度标签](sensitivity-labels.md)。 此外，隐私管理可以检测并标记包含多个人员的数据的项目，其中你可能需要在将内容提供给数据主体之前修订内容。

在收集和评估数据后，您可以选择要包括在报告和导出中的最相关的项目，并安全地与其他团队成员协作以完成请求。

## <a name="get-started-with-subject-rights-requests"></a>主题权限请求入门

隐私管理提供了一个中心中心，供隐私管理员处理组织收到的主体权限请求。

若要开始处理新的请求案例或处理正在进行中的请求，请访问主题 **权限请求主页** 。 它直观概述了团队在隐私管理中创建的情况、其状态 (active、closed 或 overdue) 以及请求类型，以及所有请求的可筛选列表。 此页面也是打开新请求的地方。

若要查看有关打开案例的详细信息，请选择列表中的任意请求，然后选择 **"转到请求详细信息"。** 有关详细信息，请参阅 [审阅并针对请求采取措施](#review-and-take-action-on-requests)。

若要打开新请求，请参阅 [创建请求](#create-a-request)。

## <a name="create-a-request"></a>创建请求

主题权限管理管理员可以使用隐私管理向导创建请求。 该向导将指导你完成查找有关数据主体的个人数据并满足其请求的过程。

四个主要步骤包括：

### <a name="identify-the-data-subject"></a>标识数据主体

提供提出请求的主题的名称，并指定他们与贵公司的关系。

### <a name="select-the-request-type"></a>选择请求类型

根据数据主体希望你使用其数据执行哪些操作，选择请求类型。 如果他们的请求与特定数据隐私法规相关，则还可以从提供的列表中选择请求以添加更多上下文。 将截止 (设置为) 将便于对接近或过期的请求进行排序，并及时解决它们。 请求类型包括：

- **Access：** 提供组织在 Microsoft 365 中存储的数据主体个人信息的摘要。
- **导出**：提供数据主体个人信息的摘要和导出，在查看过程中收集并添加注释。
- **用于跟进的带** 标记列表：生成可能需要在隐私管理之外执行其他操作的文件的摘要。 例如，如果需要根据数据主体的请求帮助删除数据主体的个人信息，则可能是一个示例方案。

### <a name="confirm-the-request-name"></a>确认请求名称

此步骤允许您确认此请求的名称，并添加可选说明作为参考。

### <a name="review-and-finish"></a>审阅并完成

在之前步骤中输入内容摘要。 在选择"创建请求"之前，可以 **编辑任何字段**。

在此级别，可以在创建请求后编辑某些属性，包括截止时间、请求名称和说明，但无法更改主题标识等关键属性。 若要编辑现有请求，请从"主题权限请求"页上的请求列表中找到它，并使用" **编辑请求详细信息"** 操作。

## <a name="review-and-take-action-on-requests"></a>查看请求并采取措施

打开请求后，隐私管理将开始搜索你的Microsoft 365数据以查找有关你的主题的数据。 To see the initial results， select that request in the list and choose **Go to request details**. 你可以在此处了解有关请求的属性、搜索结果和请求状态的信息。 此页面还将成为你工作并协作管理找到的文件、创建报告和导出以及完成请求的中心。

此页面上的磁贴包括：

- **详细信息**：有关请求的核心详细信息，包括截止时间、请求日期、说明和相关隐私法规。
- **进度**：指示已完成的步骤和任何尚未完成的任务的日程表。
- 有关当前进度阶段的统计数据。 此磁贴可能会显示数据估计摘要、搜索中发现的项目数及其在 Microsoft 365 中的位置或导出状态等信息。
- 要审阅的优先级项目：如果适用，这将显示隐私管理已检测到的重要项目的信息，包括已带有 Microsoft 敏感度标签的机密信息，或包含多个个人可能需要修订的数据的项目。 优先级项目可在通过筛选"优先级类型"列收集的数据下找到。

### <a name="monitor-progress-and-complete-requests"></a>监视进度和完成请求

主题权限请求在完成时经历多个阶段。 由于隐私管理执行数据评估，某些阶段会自动进行，其他阶段会在主体权限请求管理员和参与者完成基本步骤（如审阅、选择和修订文件）时推进。

由于请求可能需要随着时间的推移或由多个参与者处理，因此隐私管理会持续更新请求的状态，并指导下一步要采取哪些操作。 可以在主题权限请求的概述页面上查看这些更新。 进度阶段包括以下内容。

#### <a name="data-estimate"></a>数据估计

数据估计是数据评估的初始阶段。 创建请求后，隐私管理将确定组织数据中有多少项目包含与数据主体的潜在匹配项，并记录这些项目在Microsoft 365。 完成数据估计后，可以预览结果并查看原始搜索查询的详细信息。 如果要编辑搜索查询，请参阅查看和编辑搜索 [查询下的说明](#view-and-edit-search-queries)。 如果初始结果看起来满意，可以继续 **检索数据**。

- 从任何搜索中最多可以检索到 10，000 个单个项目。 与匹配项目关联的文件 (例如，电子邮件附件) 可能会计入你的总数。 如果搜索超过文件计数阈值，请尝试修改搜索以优化其范围。 有关详细信息 [，请参阅查看](#view-and-edit-search-queries) 和编辑搜索查询部分。 启动检索数据阶段后，将无法编辑搜索查询。

#### <a name="retrieve-data"></a>检索数据

此阶段指示隐私管理正在检索你的数据。 完成后，它将自动前进到 **查看数据**。

#### <a name="review-data"></a>查看数据

在此阶段，你的参与者应查看"收集的数据"选项卡下的结果。基本步骤包括：

- 选择是否在摘要和/或导出中包括标识的项目。 如果导出或报告中不需要报告匹配项，请选择"排除"选项。 如果内容显示为误报，可以选择"不匹配"以将文件从最终报告中排除，并标记项目为请求不应选取的内容。 若要设置项目的状态，请使用操作菜单 (名称旁边的) 省略号并选择所需的选项。 如果系统提示，请添加供内部参考的注释，以解释您的决定。 排除文件时需要注意。
- 使用 **"应用标记** "选项可帮助你识别需要关注的项目。 可用标记包括系统提供的选项，例如标记项目进行跟踪，并可能包含自定义标记，如设置。
- 使用 **注释** 对选定文件创建内联标记或修订。 例如，如果需要包含同时包含其他人个人信息的个人的文件，可以使用命令栏) 中"绘图"按钮下的"区域修订 ("来排除与提出请求的人不相关的所有信息。 编辑完成后，选择"包含"将修订后的文件添加到请求中。 请注意，批注会创建文件的副本，以便原始文件中的内容不会更改，并且将保留在原始位置。 副本存储在 Azure blob 中。
- To review notes on an item， select it and go to the File Notes tab.您还可以使用"添加文件注释"选项创建新注释。 若要在整体案例级别查看或添加备注，请转到上面的"备注"主选项卡并使用 **"添加案例注释"。** 这些备注对处理请求的用户可见，但将不会包含在最终报告中，或不会与数据主体共享。

在查看完所有项目并设置其状态后，选择"完成审阅"以打开一个飞入窗格，您可以在其中查看数据摘要并添加所有相关注释。 这些注释用于内部记录保留，不与数据主体共享。 再次选择"完成审阅"以继续下一阶段。 稍后将在"报告"选项卡下提供您的决策摘要。

#### <a name="generate-reports"></a>生成报告

此阶段指示正在生成报告。 完成后，可以在"报告"选项卡 **下找到** 它们。可以导出你在此处完成的文件，以传送给提出请求的数据主体。

#### <a name="close-the-request"></a>关闭请求

执行必要的操作来解决主题权限请求后，选择"**关闭请求"。** 这将创建最终报告，该报告将进行加密，并可在"报告"选项卡 **中提供** 。这可能需要一段时间，具体取决于请求中的文件数。

### <a name="view-and-edit-search-queries"></a>查看和编辑搜索查询

若要查看有关主题权限请求背后的数据搜索的详细信息，请选择"**查看搜索查询详细信息"。** 这将打开一个窗格，其中汇总了查询，并显示了有关所找到内容的进一步详细信息。

您可以选择在此处预览 **搜索结果** ，以查看将为此查询返回的内容类型。 如果您确定要更改此搜索的属性，并且尚未开始"检索数据"阶段，您可以使用"编辑 **搜索查询** "选项。 利用此向导，可以更改或添加数据主体标识、搜索筛选器和条件的属性，以及要查找数据 (包括 Exchange、SharePoint、OneDrive 和/或 Teams) 的位置。 使用这些选项可达到所需的特定程度。 在点击"保存"之前，你可以查看新查询的最终 **版本**。

编辑完搜索查询后，将运行新的搜索以替换以前的搜索结果。 这会将"进度"部分的状态重置为第一步"数据 **估计"。** 新搜索可能需要 60 分钟才能完成。 完成后，你将在请求的详细信息页面上看到更新后的结果。

## <a name="collaborate-on-requests-with-teams"></a>与用户协作处理Teams

隐私管理支持通过Microsoft Teams，以允许组共同处理主体权利请求。 创建新请求时，系统会自动创建Teams通道，并默认关联到您的请求。 你可以在这里讨论请求，并安全地共享输入和贡献，因为它接近完成。 若要加入对话，请打开你的请求并使用" **与协作者聊天"** 选项。 这将打开Microsoft Teams，将你放在主题权限请求的团队网站的常规频道中。

若要查看可以查看和为团队网站做贡献的活动协作者列表，在主题权限请求中打开" **协作者"** 选项卡。若要添加其他用户以协作处理此请求，请选择"添加协作者"选项。

若要更改创建主题权限请求时生成 Teams 网站的默认行为，请选择主题权限请求页面右上角的 **设置** 齿轮，然后选择"Teams 协作 **"以修改设置**。

您还可以使用主题权限请求中右上角的"共享"选项，通过 Teams 或电子邮件循环用户，或在隐私管理中将链接复制到页面。 通过 Teams 共享将允许你选择可供帐户使用的现有 Teams 网站，并选择该网站中的特定频道，将在该频道中发布指向此案例的链接以及你提供的任何消息。

## <a name="automate-subject-rights-request-tasks"></a>自动执行主题权限请求任务

Microsoft Power Automate 是一种工作流服务，可跨应用程序和服务自动执行操作。 启用隐私Power Automate流时，可以自动执行事例和用户的重要任务。 若要详细了解Power Automate，请访问其[文档网站](/power-automate/getting-started)。

具有包含Microsoft 365管理的客户无需其他许可证Power Automate，即可以使用建议的隐私管理Power Automate模板。 可以自定义这些模板以支持您的组织并涵盖核心隐私管理方案。 如果您选择在这些模板中Power Automate高级 Power Automate 功能、使用 Microsoft 365 合规性连接器创建自定义模板或使用 Power Automate 模板作为 Microsoft 365 中其他合规性区域，您可能需要更多 Power Automate 许可证。

隐私Power Automate包括以下模板：

- **Create record for privacy management case in ServiceNow**： This template is for organizations that want to use their ServiceNow solution to track subject rights request cases. 将要求您输入 ServiceNow 实例详细信息，包括用于连接到 ServiceNow 的帐户。 此帐户必须能够在 ServiceNow 中创建事件并填写事件详细信息。 连接到实例后，主题权限请求管理员可以在 ServiceNow 中为案例创建记录，并根据需要自定义模板将填充到选定字段中的内容。 有关连接器详细信息，请参阅 [ServiceNow 连接器参考页](/connectors/service-now/)。
- **创建日历提醒**：此模板用于为主题权限请求Outlook日历中的截止日期提醒。 该工具将基于请求的属性（如请求的名称及其截止日期）填充某些详细信息。 您可以添加描述性详细信息、指定收件人以及调整其他高级设置。

### <a name="create-a-new-power-automate-flow-from-a-template"></a>从模板Power Automate流

To begin， open the subject rights request you want to work with， select **Automate**， and then select **Manage Power Automate flows**. 这将打开"流"飞出窗格。 使用"新建"选项，然后从可用选项中选择想要使用的模板。 在此处，按照提示完成设置。

保存模板的实例后，必须从主题权限请求的详细信息页执行它，以便流实例具有正确的上下文和 ID。 打开请求，返回到"自动化 **"** 菜单，选择模板，然后选择"**运行流"。** 可以通过选择"查看流运行活动 **"来查看过去的活动**。

### <a name="share-a-power-automate-flow"></a>共享Power Automate流

通过共享Power Automate流，可以添加另一个所有者并允许他们编辑、更新和删除流。 所有所有者还可以访问运行历史记录并添加或删除其他所有者。 若要共享流，请打开要处理的主题权限请求，选择"自动执行"，然后选择"管理Power Automate **流"。**  从此窗格中，可以选择现有流，然后使用"共享"选项添加用户或组。

此窗格还为您提供了管理嵌入连接的选项，这些连接与在 Power Automate 流中使用的服务。 更改这些设置可能会影响执行流的能力。

### <a name="edit-or-delete-power-automate-flow"></a>编辑或删除Power Automate流

若要调整流的详细信息，Power Automate主题权限请求，选择"自动执行"，然后选择"管理Power Automate **流"。** 从此窗格中，可以选择一个现有流来查看详细信息。 在任何部分中使用"编辑"更改属性，然后保存。

若要完全删除流，请使用"删除 **"** 选项。 它将删除所有所有者的流，并卸载所有用户的流。 以前的流实例将继续运行以避免数据丢失。 您可以在删除完成之前确认您的选择。

## <a name="data-matching"></a>数据匹配

通过数据匹配，组织可以启用隐私管理解决方案，以根据提供的确切数据值标识数据主体。 这有助于提高为内部人员和与之交互的外部用户定位数据主体内容的准确性。 它还简化了创建主题权限请求期间手动提供字段的要求，并提供了主题权限请求中的上下文，以及展示具有最多数据主体内容的项的"概述"磁贴。 若要了解有关该视图的更多信息，请参阅 [查找和可视化数据](privacy-management-data-profile.md#items-with-the-most-data-subject-content)。

若要使用数据匹配功能，你需要是隐私管理角色组的成员。 Select the settings gear icon from the upper right of the main subject rights requests page and select **Data matching**. 在这里，你需要定义个人数据架构并提供个人数据上载，如下所示。 请注意，你可以添加项目，并且你可以删除通过 UI 添加的项目。 但是，此时无法从 UI 就地修改项。

### <a name="prepare-for-data-import"></a>准备数据导入

定义架构或上载数据之前，需要确定数据主体信息的来源。 必需的文件格式是.csv，应用程序（如应用程序）可以读取Microsoft Excel。 构造此导出，以便列标题显示在第一行中。 这些标头应包括个人数据架构的属性名称。 检查每个字段中数据的格式。 如果任何数据包含逗号，则使用双引号将这些值括起来，以确保不会将这些数据分入单独的字段中。

### <a name="define-the-personal-data-schema"></a>定义个人数据架构

个人数据架构将描述数据主体的属性。 Upload数据匹配设置区域的第一个选项卡上设置此架构。 所需文件包括 **个人数据架构** XML 文件和 **规则包** XML 文件。

#### <a name="personal-data-schema-xml"></a>个人数据架构 XML

个人数据架构文件是一个 XML 文件，它将定义期望的列名称。

- 将此 *架构文件* pdm.xml。
- 使用 Field Name 标记定义每个列名称，如下面的示例所示。
- 对要搜索的字段使用可搜索 = "true"，最多五个字段。 至少一个字段名称必须可搜索。 示例语法 `\<Field name="" searchable=""/>` ：。
- 个人数据架构具有 DataStore 标记部分。 必须将四个必填字段映射到字段名称：primaryKeyField、upnField、firstNameField、lastNameField。

例如，以下 XML 文件定义一个示例架构，其中五个字段指定为可搜索：PatientID、MRN、SSN、电话 和 DOB。 primaryKeyField 映射到 PatientID，upnField 映射到 MRN，firstNameField 映射到 FirstName，lastNameField 映射到 LastName。

可复制、修改和使用我们的示例。

 ```xml
<PdmSchema xmlns="http://schemas.microsoft.com/office/2020/pdm">
      <DataStore name="Patientrecords" description="Schema for patient records" version="1" primaryKeyField="PatientID" upnField="MRN" firstNameField="FirstName" lastNameField="LastName">
            <Field name="PatientID" searchable="true"/>
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</PdmSchema>
 ```

#### <a name="rule-package-xml"></a>规则包 XML

设置规则包时，请确保正确引用上面创建的个人数据架构文件：pdm.xml。 在下面的示例规则包 XML 中，需要自定义以下字段以创建数据匹配敏感类型：

- **RulePack id**  & **PrivacyMatch id：** 使用 New-GUID 生成 GUID。
- **数据存储**：此字段指定要使用的个人数据匹配查找数据存储。 提供已配置的个人数据架构的定义 DataStore 名称。
- **idMatch：** 此字段指向个人数据匹配的主元素。
  - **匹配**：指定要用于精确查找的字段。 提供个人数据架构中的可搜索字段名称。
  - **分类**：此字段指定触发个人数据匹配查找的敏感类型匹配。 可提供现有内建或自定义敏感信息类型的名称或 GUID。 为了避免导致性能问题，如果在个人数据匹配中将自定义敏感信息类型用作 Classification 元素，请不要使用与大部分内容类型匹配的自定义敏感信息类型 (如"任意数字"或"任何五个字母的单词") 。 我们建议添加支持关键字或在自定义分类敏感信息类型的定义中添加格式。
- **Match：** 此字段指向在 idMatch 邻近感应中发现的其他证据。
  - **匹配**：在个人数据架构中为 DataStore 提供任何字段名称。
- **资源**：此部分指定多个区域设置中敏感类型的名称和说明。
  - **idRef：** 提供 ExactMatch ID 的 GUID。
  - **名称&说明**：根据需要自定义。

在下面的规则包 XML 示例中，我们将引用上一pdm.xml创建个人数据架构 XML 的示例文件：

- **Datastore**：dataStore 名称引用我们之前创建的架构文件：dataStore = "PatientRecords"。
- **idMatch**：idMatch 值引用我们之前创建的 pdm.xml 文件中列出的可搜索字段：idMatch 匹配 = "SSN"。
  - **分类**：分类值引用现有或自定义敏感信息类型：classification = "SSN (美国社会保险) "。 （在此情况下，我们使用美国社会保障号的现有敏感信息类型。）

使用 Unicode 编码 (创建 XML 格式的规则) ，如以下示例代码所示。 您可以复制、修改和使用此示例。

 ```xml
<RulePackage xmlns="http://schemas.microsoft.com/office/2020/pdm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b21">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care PDM Rulepack</Name>
        <Description>This rule package contains the Personal Data Match sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <PrivacyMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB381" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="6">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </PrivacyMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB381">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">PDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
 ```

### <a name="upload-personal-data"></a>Upload个人数据
定义个人数据架构后，可以在数据匹配设置页的第二个选项卡上执行个人数据上载。 选择" **添加"** 时，选择第一步中定义的个人架构，然后上载包含个人数据的文件。

可以通过选择本地文件或向包含个人数据文件的现有位置提供 SAS MICROSOFT AZURE 存储上载此个人数据。
如果您准备一个文件作为此过程的第一步，且该文件符合创建的架构，您可以使用该文件进行上载。
