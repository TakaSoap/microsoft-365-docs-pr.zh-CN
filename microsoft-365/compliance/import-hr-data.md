---
title: 设置连接器以导入 HR 数据
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理员可以设置数据连接器，将员工数据从其组织的人力资源 (HR) 系统导入 Microsoft 365。 这使您可以使用内幕风险管理策略中的 HR 数据来帮助您检测可能对组织造成内部威胁的特定用户执行的活动。
ms.openlocfilehash: 49589d2e5a6a716a2e224aa28b73bd14f9048d0b
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255765"
---
# <a name="set-up-a-connector-to-import-hr-data-preview"></a>设置连接器以将 HR 数据导入 (预览) 

您可以在 Microsoft 365 合规性中心中设置数据连接器，以导入人力资源 (HR) 与事件相关的数据，如用户的辞职或用户的工作级别中的更改。 此 HR 数据可由 [内幕风险管理解决方案](insider-risk-management.md) 使用，以生成风险指标，可帮助您标识组织内部用户可能存在的恶意活动或数据被窃。

为内幕风险管理策略可用于生成风险指标的 HR 数据设置连接器包括创建包含 HR 数据的 CSV 文件，在 Azure Active Directory 中创建一个用于身份验证的应用程序，在 Microsoft 365 合规性中心中创建一个 HR 数据连接器，然后以 ingests 的方式运行一个脚本 (，以将 CSV 文件中的 HR 数据到 Microsoft 云，从而使其可用于内部人员风险管理) 解决方案。

## <a name="before-you-begin"></a>准备工作

- 确定要导入到 Microsoft 365 的 HR 方案和数据。 这将帮助您确定需要创建多少个 CSV 文件和 HR 连接器，以及如何生成和构造 CSV 文件。 您导入的 HR 数据由要实施的内幕风险管理策略确定。 有关详细信息，请参阅步骤1。

- 确定如何从组织的 HR 系统 (和定期) 中检索或导出数据，并将其添加到您在步骤1中创建的 CSV 文件。 您在步骤4中运行的脚本会将 CSV 文件中的 HR 数据上传到 Microsoft 云。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的数据。 若要同意此请求，请转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能在步骤3中成功创建 HR 连接器。

- 必须在 Exchange Online 中为在步骤3中创建 HR 连接器的用户分配邮箱导入导出角色。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建新的角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

- 您在步骤4中运行的示例脚本会将 HR 数据上传到 Microsoft 云，以供内幕风险管理解决方案使用。 在任何 Microsoft standard 支持计划或服务下，不支持此示例脚本。 示例脚本按原样提供，而不提供任何种类的担保。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 因使用或性能示例脚本和文档而导致的全部风险都将保留给您。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>步骤1：使用 HR 数据准备 CSV 文件

第一步是创建一个 CSV 文件，其中包含连接器将导入到 Microsoft 365 的 HR 数据。 内幕风险解决方案将使用此数据生成潜在风险指标。 可将以下 HR 方案的数据导入到 Microsoft 365：

- 员工辞职。 有关已离开组织的用户的信息。

- 作业级更改。 有关用户的作业级更改的信息，例如促销和降级。

- 性能检查。 有关用户性能的信息。

- 性能改进计划。 有关用户的性能改进计划的信息。

要导入的 HR 数据的类型取决于要实现的内幕风险管理策略和相应的策略模板。 下表显示了每个策略模板所需的 HR 数据类型：

| **策略模板**| **HR 数据类型**|
|:-----------------------------------------------|:---------------------------------------------------------------------|
| 通过去声用户窃取数据                   | 员工 resignations                                                 |
| 常规数据泄露                              | 不适用                                                        |
| 按优先级用户的数据泄露                    | 不适用                                                        |
| 因不满用户而进行的数据泄露                 | 作业级更改、性能评审、性能改进计划 |
| 一般安全策略冲突              | 不适用                                                        |
| 通过去声用户违反安全策略   | 员工 resignations                                                 |
| 优先级用户违反安全策略    | 不适用                                                        |
| 因不满用户而违反安全策略 | 作业级更改、性能评审、性能改进计划 |
| 电子邮件中的冒犯性语言                     | 不适用                                                        |

有关内幕风险管理的策略模板的详细信息，请参阅 [内幕风险管理策略](insider-risk-management-policies.md#policy-templates)。

对于每个 HR 方案，您需要在一个或多个 CSV 文件中提供相应的 HR 数据。 要用于内幕风险管理实施的 CSV 文件的数量将在本节的后面部分中进行讨论。

创建具有所需 HR 数据的 CSV 文件后，将其存储在您在步骤4中运行脚本的本地计算机上。 您还应实现更新策略，以确保 CSV 文件始终包含最新的信息，以便您运行脚本时，最新的 HR 数据将上传到 Microsoft 云中，并可供内幕风险管理解决方案访问。

> [!IMPORTANT]
> 以下各节中介绍的列名称不是必需参数，只是示例。 您可以在 CSV 文件中使用任何列名称。 但是，当您在步骤3中创建 HR 连接器时，您在 CSV 文件中使用的列名称 *必须* 映射到数据类型。 另请注意，以下部分中的示例 CSV 文件将显示在记事本视图中。 在 Microsoft Excel 中查看和编辑 CSV 文件要容易得多。

以下各节介绍了每个 HR 方案所需的 CSV 数据。

### <a name="csv-file-for-employee-resignation-data"></a>用于员工辞职数据的 CSV 文件

下面是一个用于员工辞职数据的 CSV 文件的示例。

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

下表介绍了 CSV 文件中的每个用于员工辞职数据的列。

| **列**  |  **说明**|
|:------------|:----------------|
|**EmailAddress**| 指定终止的用户 (UPN) 的电子邮件地址。|
| **ResignationDate** | 指定在您的组织中正式终止用户雇用的日期。 例如，这可能是用户在离开你的组织时给出通知的日期。 此日期可能与人员的最后一天的工作日期不同。 必须使用以下日期格式：，即 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **LastWorkingDate** | 指定终止的用户的最后一天的工作。 必须使用以下日期格式：，即 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
|||

### <a name="csv-file-for-job-level-changes-data"></a>作业级更改数据的 CSV 文件

下面的示例展示了作业级更改数据的 CSV 文件。

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

下表介绍了 CSV 文件中的每个作业级别更改数据的列。

| **列**|**说明**|
|:--------- |:------------- |
| **EmailAddress**  | 指定用户的电子邮件地址 (UPN) 。|
| **EffectiveDate** | 指定用户的作业级别的正式更改日期。 必须使用以下日期格式：，即 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **备注**| 指定评估程序已提供有关作业级别更改的备注。 这是一个长度限制为200个字符的文本参数。 这是一个可选参数。 您无需将其包含在 CSV 文件中。|
| **OldLevel**| 指定用户在更改之前的作业级别。 这是一个自由文本参数，可以包含您的组织的层次分类。 这是一个可选参数。 您无需将其包含在 CSV 文件中。|
| **NewLevel**| 指定用户的作业级别更改后的级别。 这是一个自由文本参数，可以包含您的组织的层次分类。 这是一个可选参数。 您无需将其包含在 CSV 文件中。|
|||

### <a name="csv-file-for-performance-review-data"></a>用于性能检查数据的 CSV 文件

下面的示例展示了用于性能数据的 CSV 文件。

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

下表介绍了 CSV 文件中的每一列的性能检查数据。

| **列**|**说明**|
|:----------|:--------------|
| **EmailAddress**  | 指定用户的电子邮件地址 (UPN) 。|
| **EffectiveDate** | 指定用户在其性能评审的结果中获得官方通知的日期。 这可以是绩效考核周期结束的日期。 必须使用以下日期格式：，即 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **备注**| 指定评估程序为用户提供的用于性能评审的任何备注。 这是一个长度限制为200个字符的文本参数。 这是一个可选参数。 您无需将其包含在 CSV 文件中。|
| **Rating**| 指定为执行性能评审而提供的分级。 这是一个文本参数，可包含贵组织用于识别评估的任意自由格式文本。 例如，"3 达到预期" 或 "低于平均值 2"。 这是一个文本参数，最大限制为25个字符。 这是一个可选参数。 您无需将其包含在 CSV 文件中。|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>用于性能改进计划数据的 CSV 文件

下面的示例展示了性能改进计划数据的数据的 CSV 文件。

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

下表介绍了 CSV 文件中的每一列的性能检查数据。

| **列**| **说明**|
|:----------|:---------------|
| **EmailAddress**  | 指定用户的电子邮件地址 (UPN) 。|
| **EffectiveDate** | 指定用户获得其绩效改善计划的正式通知的日期。 必须使用以下日期格式：，即 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **备注**| 指定评估程序已提供有关性能改进计划的任何备注。 这是一个长度限制为200个字符的文本参数。 这是一个可选参数。 您无需将其包含在 CSV 文件中。 |
| **Rating**| 指定任何级别或与性能评审相关的其他信息。 性能改进计划。 这是一个文本参数，可以包含贵组织用于识别评估的任意自由格式文本。 例如，"3 达到预期" 或 "低于平均值 2"。 这是一个长度限制为25个字符的 text 参数。 这是一个可选参数。 您无需将其包含在 CSV 文件中。|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>确定要用于 HR 数据的 CSV 文件的数量

在步骤3中，可以选择为每个 HR 数据类型创建单独的连接器，也可以选择为所有数据类型创建单个连接器。 您可以使用包含一个 HR 方案的数据的单独 CSV 文件 (如前面各节中所述的 CSV 文件的示例) 。 或者，您可以使用包含两个或更多个 HR 方案的数据的单个 CSV 文件。 下面的准则可帮助您确定要用于 HR 数据的 CSV 文件的数量。

- 如果要实现的内幕风险管理策略需要多个 HR 数据类型，请考虑使用包含所有所需数据类型的单个 CSV 文件。

- 生成或收集 HR 数据的方法可能会决定 CSV 文件的数量。 例如，如果用于配置 HR 连接器的不同类型的 HR 数据位于组织中的单个 HR 系统中，则可以将该数据导出到单个 CSV 文件中。 但是，如果数据分布在不同的 HR 系统中，则将数据导出到不同的 CSV 文件可能会更容易。 例如，员工辞职数据所在的 HR 系统可能与作业级或绩效考核数据不同。 在这种情况下，可能更易于使用单独的 CSV 文件，而无需将数据手动组合到单个 CSV 文件中。 因此，从 HR 系统检索或导出数据的方式可能决定了所需的 CSV 文件的数量。

- 通常情况下，您需要创建的 HR 连接器的数量由 CSV 文件中的数据类型决定。 例如，如果 CSV 文件包含支持您的内幕风险管理实施所需的所有数据类型，则只需要一个 HR 连接器。 但是，如果您有两个单独的 CSV 文件，每个文件都包含一个数据类型，那么您必须创建两个 HR 连接器。 例外情况是，如果向 CSV 文件添加 **HRScenario** 列 (请参阅下一节) ，可以配置单个 HR 连接器来处理不同的 CSV 文件。

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>为多个 HR 数据类型配置单个 CSV 文件

您可以向单个 CSV 文件中添加多个 HR 数据类型。 如果要实现的内幕风险管理解决方案需要多个 HR 数据类型，或者如果数据类型位于组织中的单个 HR 系统中，这将非常有用。 使用较少的 CSV 文件，您可以创建和管理更少的 HR 连接器。

以下是使用多个数据类型配置 CSV 文件的要求：

- 如果对标题行中的每个数据类型和相应的列名称使用) 它们，则必须在 (和可选的列中添加所需的列。 如果数据类型与列不对应，则可以将该值保留为空。

- 若要将 CSV 文件与多种类型的 HR 数据结合使用，HR 连接器需要知道 CSV 文件中的哪些行包含 HR 数据类型。 这是通过向 CSV 文件添加其他 **HRScenario** 列来实现的。 此列中的值标识每行中 HR 数据的类型。 例如，与四个 HR 方案对应的值可能会 \` 让步 \` 、 \` 作业级别更改 \` 、 \` 性能评审 \` 和 \` 性能改进计划 \` 。

- 如果有多个包含 HRScenario * * 列的 CSV 文件，请确保每个文件使用相同的列名称和标识特定 HR 方案的相同值。

下面的示例演示包含 **HRScenario** 列的 CSV 文件。 "HRScenario" 列中的值标识相应行中的数据类型。

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> 您可以对标识 HR 数据类型的列使用任意名称，因为您会将 CSV 文件中的列名称映射为在步骤3中设置连接器时标识 HR 数据类型的列。 您还将映射在设置连接器时用于 "数据类型" 列的值。

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>将 "HRScenario" 列添加到包含单个数据类型的 CSV 文件中

根据组织的 HR 系统以及将 HR 数据导出到 CSV 文件的方式，您可能必须创建多个包含单个 HR 数据类型的 CSV 文件。 在这种情况下，仍可以创建单个 HR 连接器以从不同的 CSV 文件中导入数据。 若要执行此操作，您只需向 CSV 文件中添加一个 HRScenario 列并指定 HR 数据类型。 然后，您可以运行每个 CSV 文件的脚本，但对连接器使用相同的作业 ID。 请参阅 [步骤 4](#step-4-run-the-sample-script-to-upload-your-hr-data)。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步骤2：在 Azure Active Directory 中创建应用程序

下一步是在 Azure Active Directory (AAD) 中创建和注册新应用程序。 应用将与您在步骤3中创建的 HR 连接器相对应。 创建此应用程序将允许 AAD 在运行 HR 连接器时对其进行身份验证，并尝试访问你的组织。 此应用程序还将用于对您在步骤4中运行的脚本进行身份验证，以将 HR 数据上传到 Microsoft 云。 在创建此 AAD 应用过程中，请务必保存以下信息。 这些值将在步骤3和步骤4中使用。

- AAD 应用程序 ID (也称为 " *应用程序* id" 或 " *客户端 id* ") 

- AAD 应用程序机密 (也称为 *客户端密码*) 

- 租户 Id (也称为 *目录 Id*) 

有关在 AAD 中创建应用程序的分步说明，请参阅 [向 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-3-create-the-hr-connector"></a>步骤3：创建 HR 连接器

下一步是在 Microsoft 365 合规性中心中创建 HR 连接器。 在步骤4中运行脚本后，您创建的 HR 连接器会将 HR 数据从 CSV 文件中接收到 Microsoft 365 组织。 创建连接器之前，请确保有一个 HR 方案列表以及每个方案的相应 CSV 列名称。 配置连接器时，您必须将每个方案所需的数据映射到 CSV 文件中的实际列名称。 或者，可以在配置连接器时上载一个示例 CSV 文件，向导将帮助您将列的名称映射到所需的数据类型。

完成此步骤后，请务必复制创建连接器时生成的作业 ID。 运行脚本时，将使用作业 ID。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击左侧导航中的 " **数据连接器** "。

2. 在 " **数据连接器" (预览) ** 在 **HR**下的页面上，单击 " **查看**"。

3. 在 **HR 自定义** 页面上，单击 " **添加连接器**"。

4. 在 " **设置连接"** 页面上，执行以下操作，然后单击 " **下一步**"：

   a. 为您在步骤2中创建的 Azure 应用程序键入或粘贴 AAD 应用程序 ID。

   b. 键入 HR 连接器的名称。

5. 在 "HR 方案" 页上，选择要为其导入数据的一个或多个 HR 方案，然后单击 " **下一步**"。

6. 在 "文件映射方法" 页上，选择下列选项之一，然后单击 " **下一步**"。

   - **上载示例文件**。 如果选择此选项，请单击 " **上载示例文件** " 以上传您在步骤1中准备的 CSV 文件。 使用此选项，可以从下拉列表中快速选择 CSV 文件中的列名称，以便将其映射到之前选择的 HR 方案的数据类型。

   OR

   - **手动提供映射详细信息**。 如果选择此选项，则必须键入 CSV 文件中列的名称，以便将其映射到之前选择的 HR 方案的数据类型。

7. 在 "文件映射详细信息" 页上，执行下列操作之一，具体取决于是否上载了示例 CSV 文件，以及是为单个 HR 方案还是针对多个方案配置连接器。 如果上载了示例文件，则不必键入列名称。 您可以从下拉列表中选择它们。

    - 如果在上一步中选择了单个 HR 方案，则在每个相应框中的步骤1中创建的 CSV 文件中，键入列标题名称 (也称为 *参数*) 。 键入的列名称不区分大小写，但如果 CSV 文件中的列名称包含空格，则应确保包含空格。 如前面所述，在这些框中键入的名称必须与 CSV 文件中的参数名称相匹配。 例如，下面的屏幕截图显示了第1步中显示的员工辞职 HR 方案的示例 CSV 文件中的参数名称。

    - 如果在上述步骤中选择了 "多个数据类型"，则需要输入将在 CSV 文件中标识 HR 数据类型的标识符列名称。 在输入标识符列名称后，键入标识此 HR 数据类型的值，然后在每个所选数据类型对应的每个框中为您在步骤1中创建的 CSV 文件 (s) 中键入所选数据类型的列标题名称。 如前所述，在这些框中键入的名称必须与 CSV 文件中的列名称相匹配。

8. 在 " **检查** " 页上，查看您的设置，然后单击 " **完成** " 以创建连接器。

   将显示 "状态" 页，确认已创建连接器。 此页面包含完成下一步以运行示例脚本以上载 HR 数据所需的两个重要事项。

   ![查看包含作业 ID 的页面并链接到 github 以获取示例脚本](../media/HRConnector_Confirmation.png)

   a. **作业 ID。** 在下一步中，你将需要此作业 ID 来运行脚本。 您可以从此页面或从 "连接线" 飞出页面复制它。

   b. **指向示例脚本的链接。** 单击 **此处** 链接转到 GitHub 站点以访问示例脚本 (链接将) 中打开新的窗口。 保持此窗口处于打开状态，以便您可以在第4步中复制脚本。 或者，也可以将目标做成书签或复制 URL，以便在运行脚本时可以再次访问它。 此链接在 "连接线" 弹出页面上也可用。

9. 单击“**完成**”。

   新的连接器将显示在 " **连接器** " 选项卡上的列表中。

10. 单击刚创建的 HR 连接器以显示弹出页面，其中包含有关连接器的属性和其他信息。

   ![新 HR 连接器的飞出页面](../media/HRConnectorWizard7.png)

如果还未执行此操作，则可以复制 **Azure 应用 id** 和 **连接器作业 ID**的值。 在下一步中，你将需要这些脚本来运行脚本。 您还可以从弹出页面下载脚本， (或在下一步中使用链接下载。 ) 

您还可以单击 " **编辑** " 更改在 " **文件映射** " 页上定义的 Azure 应用 ID 或列标题名称。

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>步骤4：运行示例脚本以上传 HR 数据

设置 HR 连接器的最后一步是运行一个示例脚本，该脚本将把在第1步中创建的 CSV 文件 (中创建的 HR 数据上载到 Microsoft 云) 。 具体来说，该脚本会将数据上载到 HR 连接器。 运行该脚本后，您在步骤3中创建的 HR 连接器会将 HR 数据导入到 Microsoft 365 组织中，以供其他合规性工具（如内幕风险管理解决方案）进行访问。 运行脚本后，请考虑计划任务每天定期自动运行，以便将最新的员工终止数据上载到 Microsoft 云。 请参阅 [安排脚本自动运行](#optional-step-6-schedule-the-script-to-run-automatically)。

1. 转到您在上一步中打开的窗口以使用示例脚本访问 GitHub 网站。 或者，也可以打开已加书签的网站或使用您复制的 URL。

2. 单击 " **原始** " 按钮以在文本视图中显示脚本。

3. 复制示例脚本中的所有行，然后将它们保存到一个文本文件中。

4. 如有必要，请修改组织的示例脚本。

5. 将文本文件另存为 Windows PowerShell 脚本文件，方法是使用文件名后缀 `.ps1` ; 例如， `HRConnector.ps1` 。

6. 在本地计算机上打开命令提示符，并转到保存该脚本的目录。

7. 运行以下命令，将 CSV 文件中的 HR 数据上传到 Microsoft 云;例如：

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   下表介绍了要与此脚本一起使用的参数及其必需的值。 您在前面步骤中获取的信息用于这些参数的值。

   |**参数**|**说明**
   |:-----|:-----|:-----|
   |`tenantId`|这是您在步骤2中获取的 Microsoft 365 组织的 Id。 您还可以在 Azure AD 管理中心的 **概述** 边栏中获取组织的租户 Id。 这用于标识你的组织。|
   |`appId` |这是您在第2步中的 Azure AD 中创建的应用程序的 AAD 应用程序 Id。 当脚本尝试访问 Microsoft 365 组织时，Azure AD 使用此方法进行身份验证。 | 
   |`appSecret`|这是在步骤2中的 Azure AD 中创建的应用程序的 AAD 应用程序密码。 这也用于身份验证。|
   |`jobId`|这是您在步骤3中创建的 HR 连接器的作业 ID。 这用于将上载到 Microsoft 云的 HR 数据与 HR 连接器相关联。|
   |`csvFilePath`|这是 CSV 文件 (与您在步骤1中创建的脚本) 存储在同一系统上的文件路径。 请尝试避免在文件路径中包含空格;否则，请使用单引号。|
   |||

   下面的示例展示了使用每个参数的实际值的 HR 连接器脚本的语法：

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   如果上载成功，则脚本将显示 **上传成功** 消息。
   
   > [!NOTE]
   > 如果由于 excution 策略而运行上一个命令时遇到问题，请参阅 [关于执行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) 和 [ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) ，以获取有关设置执行策略的指南。 

## <a name="step-5-monitor-the-hr-connector"></a>步骤5：监视 HR 连接器

创建 HR 连接器并运行脚本以上载您的 HR 数据后，您可以在 Microsoft 365 合规性中心查看连接器和上传状态。 如果将脚本安排为定期自动运行，还可以在上次脚本运行之后查看当前状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并单击左侧导航中的 " **数据连接器** "。

2. 单击 " **连接器** " 选项卡，然后选择 HR 连接器以显示弹出页面，其中包含有关连接器的属性和信息。

   ![带有属性和状态的 HR 连接器浮出控件页](../media/HRConnectorFlyout1.png)

3. 在 " **进度**" 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。 此日志包含有关每次脚本运行的信息，并将数据从 CSV 文件上载到 Microsoft 云。 

   ![HR 连接器日志文件显示从 CSV 文件上载的编号行数](../media/HRConnectorLogFile.png)

   该 `RecordsSaved` 字段指示上传的 CSV 文件中的行数。 例如，如果 CSV 文件包含四行，则字段的值 `RecordsSaved` 为4，如果脚本成功上传了 CSV 文件中的所有行。

如果您没有在步骤4中运行该脚本，则在 " **上次导入**" 下将显示下载该脚本的链接。 您可以下载脚本，然后按照步骤运行脚本。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (可选) 步骤6：安排脚本自动运行

若要确保组织中的最新 HR 数据对类似于内幕风险管理解决方案的工具可用，我们建议您安排脚本定期（例如一天一次）自动运行。 这还要求在类似 (上更新 CSV 文件中的 HR 数据（如果不是相同的) 计划），以便它包含有关离开组织的员工的最新信息。 目标是上载最新的 HR 数据，以便 HR 连接器可以将其提供给内幕风险管理解决方案。

您可以在 Windows 中将 "任务计划程序" 应用程序用户每天自动运行该脚本。

1. 在本地计算机上，单击 Windows " **开始** " 按钮，然后键入 " **任务计划程序**"。

2. 单击 " **任务计划** 程序" 应用将其打开。

3. 在 " **操作** " 部分，单击 " **创建任务**"。

4. 在 " **常规** " 选项卡上，为计划的任务键入一个描述性名称;例如， **HR 连接器脚本**。 您还可以添加可选的说明。

5. 在 " **安全选项**" 下，执行下列操作：

   a. 确定是仅在登录到计算机时运行脚本，还是在登录时运行脚本。

   b. 确保选中 " **以最高特权运行** " 复选框。

6. 选择 " **触发器** " 选项卡，单击 " **新建**"，然后执行以下操作：

   a. 在 " **设置**" 下，选择 " **每日** " 选项，然后选择第一次运行脚本的日期和时间。 脚本每天都在指定的时间。

   b. 在 " **高级设置**" 下，确保选中 " **启用** " 复选框。

   c. 单击“确定”****。

7. 选择 " **操作** " 选项卡，单击 " **新建**"，然后执行以下操作：

   ![为 HR 连接器脚本创建新的计划任务的操作设置](../media/HRConnectorScheduleTask1.png)

   a. 在 " **操作** " 下拉列表中，确保选择 " **启动程序** "。

   b. 在 " **程序/脚本** " 框中，单击 " **浏览**"，然后转到以下位置并选择它，以使路径显示在框中： `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` 。

   c. 在 " **添加参数" (可选) ** 框中，粘贴您在步骤4中运行的相同脚本命令。 例如，`.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. 在 " **开始 (可选) ** " 框中，粘贴您在步骤4中运行的脚本的文件夹位置。 例如，`C:\Users\contosoadmin\Desktop\Scripts`。

   e. 单击 **"确定"** 保存新操作的设置。

8. 在 " **创建任务** " 窗口中，单击 **"确定"** 以保存计划的任务。 系统可能会提示您输入您的用户帐户凭据。

   新任务将显示在 "任务计划程序库" 中。

   ![新任务将显示在任务计划程序库中](../media/HRConnectorTaskSchedulerLibrary.png)

   最后一次运行脚本并显示下一次计划运行时。 您可以双击该任务以对其进行编辑。

   您还可以验证在符合性中心中对应 HR 连接器的飞出页面上，脚本的上次运行时间。

## <a name="existing-hr-connectors"></a>现有 HR 连接器

在2020年7月20日，我们发布了 HR 连接器支持的其他方案。 这些是上文中所述的 HR 方案。 在此日期之前创建的任何 HR 连接器都仅支持员工辞职方案。 如果在2020年7月20日之前创建了 HR 连接器，我们已将其迁移，以便继续将 HR 数据迁移到 Microsoft 云。 您无需执行任何操作即可维护此功能。 您可以继续使用连接器，而无需任何中断。

如果要实现其他 HR 方案，请创建一个新的 HR 连接器并为其配置已发布的其他 HR 方案。 您还需要创建一个或多个包含数据的新 CSV 文件，以支持其他 HR 方案。 在创建新的 HR 连接器之后，使用新的连接器和 CSV 文件的作业 ID 运行该脚本， (s) 包含其他 HR 方案的数据。
