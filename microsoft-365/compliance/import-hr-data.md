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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 管理员可以设置数据连接器，以从组织的人力资源部门导入员工数据， (HR) 系统Microsoft 365。 这样，你可以将 HR 数据用于内部风险管理策略，以帮助你检测特定用户可能对组织造成内部威胁的活动。
ms.openlocfilehash: 0c3a6966155483ba374211b7db55675010b0c55f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151082"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>设置连接器以导入 HR 数据

您可以在 Microsoft 365 合规中心 中设置一个数据连接器，以导入与事件（如用户的决定或用户的工作级别变化）相关的人力资源 (HR) 数据。 然后，内部风险管理解决方案可以使用 HR[](insider-risk-management.md)数据生成风险指示器，以帮助你识别组织内部用户可能恶意活动或数据盗窃。

为内部风险管理策略可用于生成风险指标的 HR 数据设置连接器包括创建包含 HR 数据的 CSV 文件、在 Azure Active Directory 中创建用于身份验证的应用程序、在 Microsoft 365 合规中心 中创建 HR 数据连接器，然后按计划运行脚本 () 将 CSV 文件的 HR 数据导入 Microsoft 云，以便对内部风险管理解决方案可用。

## <a name="before-you-begin"></a>准备工作

- 确定哪些 HR 方案和数据要导入Microsoft 365。 这将帮助你确定需要创建的 CSV 文件和 HR 连接器的个数，以及如何生成和构建 CSV 文件。 导入的 HR 数据由要实施的内部风险管理策略确定。 有关详细信息，请参阅步骤 1。

- 确定如何检索或导出组织的 HR 系统 (并定期) 并将其添加到在步骤 1 创建的 CSV 文件中。 在步骤 4 中运行的脚本将 CSV 文件的 HR 数据上载到 Microsoft 云。

- 必须在步骤 3 中为在步骤 3 中创建 HR 连接器的用户分配邮箱导入导出Exchange Online。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到"邮箱管理"角色组Exchange Online。 也可以创建新的角色组，分配"邮箱导入导出"角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中管理角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 在步骤 4 中运行的示例脚本将你的 HR 数据上传到 Microsoft 云，以便内部风险管理解决方案可以使用该数据。 本示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。 示例脚本“原样”提供，不提供任何形式的保证。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>步骤 1：准备包含 HR 数据的 CSV 文件

第一步是创建一个 CSV 文件，其中包含连接器将导入Microsoft 365。 此数据将被内部风险解决方案用于生成潜在风险指标。 可以将以下 HR 方案的数据导入Microsoft 365：

- 员工满意度。 有关已离开组织的用户的信息。

- 作业级别更改。 有关用户的工作级别更改的信息，例如升级和降级。

- 性能评审。 有关用户性能的信息。

- 性能改进计划。 有关用户性能改进计划的信息。

要导入的 HR 数据类型取决于内部风险管理策略和要实施的相应策略模板。 下表显示了每个策略数据类型需要哪些 HR 策略：

|  策略模板 |  HR 数据类型 |
|:-----------------------------------------------|:---------------------------------------------------------------------|
| 离职用户窃取数据                   | 员工员工                                                 |
| 常规数据泄露                              | 不适用                                                        |
| 优先用户的数据泄露                    | 不适用                                                        |
| 心怀不满用户的数据泄露活动                 | 作业级别更改、绩效考核、绩效改进计划 |
| 违反常规安全策略              | 不适用                                                        |
| 离职用户的安全策略违规活动   | 员工员工                                                 |
| 优先用户的安全策略违规    | 不适用                                                        |
| 心怀不满员工的安全策略违规活动 | 作业级别更改、绩效考核、绩效改进计划 |
| 邮件中的冒犯性语言                     | 不适用                                                        |

有关内部风险管理的策略模板详细信息，请参阅 [预览体验成员风险管理策略](insider-risk-management-policies.md#policy-templates)。

对于每个 HR 方案，你需要在一个或多个 CSV 文件中提供相应的 HR 数据。 本节稍后将讨论用于内部风险管理实施的 CSV 文件数。

创建包含所需 HR 数据的 CSV 文件后，请存储在步骤 4 中运行脚本的本地计算机上。 还应实施更新策略，以确保 CSV 文件始终包含最新信息，以便无论运行脚本，最新 HR 数据都将上载到 Microsoft 云，并且可供内部风险管理解决方案访问。

> [!IMPORTANT]
> 以下各节中介绍的列名称不是必需参数，而只是示例。 可以在 CSV 文件中使用任意列名称。 但是，在 CSV 文件中使用的列名称必须映射到数据类型步骤 3 中的 HR 连接器时，该列名必须映射到该位置。 另请注意，以下各节中的示例 CSV 文件显示在记事本视图中。 在文件视图中查看和编辑 CSV 文件Microsoft Excel。

以下各节介绍每个 HR 方案所需的 CSV 数据。

### <a name="csv-file-for-employee-resignation-data"></a>员工调查数据的 CSV 文件

以下是员工数据 CSV 文件的示例。

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

下表介绍了 CSV 文件的每一列，用于员工数据。

|  列   |   说明 |
|:------------|:----------------|
|**EmailAddress**| 指定已终止 (UPN) 的电子邮件地址。|
| **为系统** | 指定在组织中正式终止用户的雇佣关系的日期。 例如，这可能是用户通知你离开组织的日期。 此日期可能不同于人员最后一天的工作日期。 使用以下日期格式 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ：，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **LastWorkingDate** | 指定终止的用户的最后一天工作。 使用以下日期格式 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ：，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
|||

### <a name="csv-file-for-job-level-changes-data"></a>用于作业级别的 CSV 文件更改数据

下面是用于作业级别更改数据的 CSV 文件的示例。

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

下表介绍了 CSV 文件每一列的作业级别更改数据。

|  列 | 说明 |
|:--------- |:------------- |
| **EmailAddress**  | 指定用户的电子邮件地址 (UPN) 。|
| **EffectiveDate** | 指定正式更改用户的工作级别的日期。 使用以下日期格式 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ：，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **备注**| 指定评估程序提供的有关作业级别更改的备注。 可以输入 200 个字符的限制。 此参数是可选的。 你不必在 CSV 文件中添加它。|
| **OldLevel**| 指定更改用户的工作级别之前。 这是自由文本参数，可以包含组织的分层分类。 此参数是可选的。 你不必在 CSV 文件中添加它。|
| **NewLevel**| 指定更改后的用户的作业级别。 这是自由文本参数，可以包含组织的分层分类。 此参数是可选的。 你不必在 CSV 文件中添加它。|
|||

### <a name="csv-file-for-performance-review-data"></a>性能评审数据的 CSV 文件

下面是性能数据的 CSV 文件示例。

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

下表介绍了 CSV 文件的每一列，用于查看性能评审数据。

|  列 | 说明 |
|:----------|:--------------|
| **EmailAddress**  | 指定用户的电子邮件地址 (UPN) 。|
| **EffectiveDate** | 指定正式通知用户其绩效考核结果的日期。 这可以是绩效考核周期结束的日期。 使用以下日期格式 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` ：，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **备注**| 指定评估程序为执行绩效考核而提供给用户的任何备注。 这是一个限制为 200 个字符的文本参数。 此参数是可选的。 你不必在 CSV 文件中添加它。|
| **评级**| 指定为绩效考核提供的分级。 这是一个文本参数，可以包含组织用于识别评估的任何自由格式文本。 例如，"3 满足预期"或"2 低于平均值"。 这是一个文本参数，限制为 25 个字符。 此参数是可选的。 你不必在 CSV 文件中添加它。|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>性能改进计划数据的 CSV 文件

下面是性能改进计划数据数据的 CSV 文件示例。

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

下表介绍了 CSV 文件的每一列，用于查看性能评审数据。

|  列 |  说明 |
|:----------|:---------------|
| **EmailAddress**  | 指定用户的电子邮件地址 (UPN) 。|
| **EffectiveDate** | 指定正式通知用户其性能改进计划的日期。 必须使用以下日期格式：，即 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
| **备注**| 指定评估者提供的有关性能改进计划的任何备注。 这是一个限制为 200 个字符的文本参数。 这是一个可选参数。 你不必在 CSV 文件中添加它。 |
| **评级**| 指定与绩效考核相关的任何评分或其他信息。 性能改进计划。 这是一个文本参数，可以包含组织用于识别评估的任何自由格式文本。 例如，"3 满足预期"或"2 低于平均值"。 这是一个限制为 25 个字符的文本参数。 这是一个可选参数。 你不必在 CSV 文件中添加它。|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>确定要用于 HR 数据的 CSV 文件个

在步骤 3 中，可以选择为每个 HR 数据类型创建单独的连接器，也可以选择针对所有数据类型创建单个连接器。 你可以为一个 HR 方案使用包含数据的单独 CSV 文件 (如前面章节中所述的 CSV 文件) 。 或者，您可以使用单个 CSV 文件，其中包含两个或多个 HR 方案的数据。 下面是一些指南，可帮助你确定要用于 HR 数据的 CSV 文件个个。

- 如果要实现的内部风险管理策略需要多个 HR 数据类型，请考虑使用包含所有所需数据类型的单个 CSV 文件。

- 生成或收集 HR 数据的方法可以确定 CSV 文件的数量。 例如，如果用于配置 HR 连接器的不同类型的 HR 数据位于您组织的单个 HR 系统中，则您可能能够将数据导出到单个 CSV 文件。 但是，如果数据分布在不同的 HR 系统中，则将数据导出到不同的 CSV 文件可能更容易。 例如，员工审核数据可能位于与作业级别或绩效考核数据不同的 HR 系统中。 在这种情况下，可以更轻松地拥有单独的 CSV 文件，而不必手动将数据合并到单个 CSV 文件中。 因此，如何检索或导出 HR 系统中的数据可能会确定您需要的 CSV 文件数。

- 一般而言，您需要创建的 HR 连接器的数量由 CSV 文件的数据类型决定。 例如，如果 CSV 文件包含支持内部风险管理实施所需的全部数据类型，则只需一个 HR 连接器。 但是，如果你有两个单独的 CSV 文件，每个文件都包含一数据类型，则你必须创建两个 HR 连接器。 例外情况是，如果将 **HRScenario** 列添加到 CSV 文件 (请参阅下一部分) ，您可以配置可以处理不同 CSV 文件的单个 HR 连接器。

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>为多个 HR 数据类型配置单个 CSV 文件

可以将多个 HR 数据类型添加到单个 CSV 文件。 如果您要实现的内部风险管理解决方案需要多个 HR 数据类型，或者数据类型位于您组织的单个 HR 系统中，这将非常有用。 CSV 文件越少，创建和管理的 HR 连接器就越少。

以下是配置包含多个数据类型的 CSV 文件的要求：

- 如果在每个列和标题行 (列名称) ，必须数据类型和可选列。 如果数据类型列不对应，可以将该值留空。

- 若要将 CSV 文件与多种类型的 HR 数据一同使用，HR 连接器需要知道 CSV 文件中哪些行包含哪种类型的 HR 数据。 这是通过将其他 **HRScenario** 列添加到 CSV 文件来完成的。 此列中的值标识每行中的 HR 数据类型。 例如，对应于四个 HR 方案的值可以是"业务级别更改"、"绩效考核"和" \` \` \` \` \` \` \` 绩效改善计划 \` "。

- 如果你有多个包含 HRScenario** 列的 CSV 文件，请确保每个文件使用相同的列名和标识特定 HR 方案的相同值。

以下示例显示包含 **HRScenario** 列的 CSV 文件。 HRScenario 列中的值标识对应行中的数据类型。

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
> 可以使用标识 HR 数据类型 列的任何名称，因为当您在步骤 3 中设置连接器时，您可以将 CSV 文件中该列的名称映射为标识 HR 数据类型 的列。 在设置连接器时，还将映射用于 数据类型 列的值。

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>将 HRScenario 列添加到包含单个文件的 CSV 数据类型

根据组织的 HR 系统和您将 HR 数据导出到 CSV 文件，您可能必须创建多个 CSV 文件，其中包含一个 HR 数据类型。 在这种情况下，您仍可以创建单个 HR 连接器以从不同的 CSV 文件导入数据。 为此，只需将 HRScenario 列添加到 CSV 文件并指定 HR 数据类型。 然后您可以运行每个 CSV 文件的脚本，但对连接器使用相同的作业 ID。 请参阅[步骤 4。](#step-4-run-the-sample-script-to-upload-your-hr-data)

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步骤 2：在 Azure Active Directory

下一步是在 Azure AD Azure Active Directory (创建和注册) 。 该应用将对应于你在步骤 3 创建的 HR 连接器。 创建此应用将允许 Azure AD 在 HR 连接器运行时进行身份验证，并尝试访问你的组织。 此应用还将用于对在步骤 4 中运行的脚本进行身份验证，以将 HR 数据上传到 Microsoft 云。 创建此 Azure AD 应用期间，请务必保存以下信息。 这些值将在步骤 3 和步骤 4 中使用。

- Azure AD 应用程序 ID (也称为 *应用 ID* 或 *客户端 ID*) 

- Azure AD 应用程序密码 (也称为 *客户端密码*) 

- 租户 ID (*也称为目录 ID*) 

有关在 Azure AD 中创建应用的分步说明，请参阅使用 Microsoft 标识平台[注册应用程序](/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-3-create-the-hr-connector"></a>步骤 3：创建 HR 连接器

下一步是在企业内部创建 HR Microsoft 365 合规中心。 在步骤 4 中运行脚本后，您创建的 HR 连接器将从 CSV 文件将 HR 数据导入Microsoft 365组织。 创建连接器之前，请确保您具有 HR 方案的列表以及每个方案对应的 CSV 列名称。 配置连接器时，您必须将每个方案所需的数据映射到 CSV 文件中的实际列名称。 或者，您可以在配置连接器时上载示例 CSV 文件，向导将帮助您将列的名称映射到所需的数据类型。

完成此步骤后，请确保复制创建连接器时生成的作业 ID。 运行脚本时，将使用作业 ID。

1. 转到 ， [https://compliance.microsoft.com](https://compliance.microsoft.com/) 然后单击左侧 **导航中的** "数据连接器"。

2. 在"**数据连接器"页上** 的 **"HR"下**，单击"查看 **"。**

3. 在 **"HR 自定义"** 页上，单击"**添加连接器"。**

4. 在"**设置连接"** 页上，执行以下操作，然后单击"下一步 **"：**

   1. 键入或粘贴你在步骤 2 中创建的 Azure 应用的 Azure AD 应用程序 ID。

   1. 键入 HR 连接器的名称。

5. 在"HR 方案"页上，选择要导入其数据的一个或多个 HR 方案，然后单击"下一步 **"。**

6. 在文件映射方法页上，选择下列选项之一，然后单击下一 **步**。

   - **Upload示例文件**。 如果选择此选项，请单击"Upload **文件**"以上载在步骤 1 中准备的 CSV 文件。 此选项允许您从下拉列表中快速选择 CSV 文件的列名称，以将其映射到您之前选择的 HR 方案的数据类型。

   或

   - **手动提供映射详细信息**。 如果选择此选项，您必须在 CSV 文件中键入列的名称，以将它们映射到之前选择的 HR 方案的数据类型。

7. 在"文件映射详细信息"页上，执行下列操作之一，具体取决于是上传了示例 CSV 文件，还是为单个 HR 方案或多个方案配置了连接器。 如果上载了示例文件，则不必键入列名称。 从下拉列表中选取它们。

    - 如果在上一步中选择了单个 HR 方案，请在每个相应的框中键入列标题 *名称 (也称为* "参数) "（来自在步骤 1 中创建的 CSV 文件）。 您键入的列名称不区分大小写，但如果 CSV 文件的列名称包含空格，请务必包含空格。 如前所述，您在这些框中键入的名称必须与 CSV 文件中的参数名称相匹配。 例如，以下屏幕截图显示了步骤 1 中显示的员工福利 HR 方案的示例 CSV 文件的参数名称。

    - 如果在以上步骤中选择了多个数据类型，则需要输入标识符列名称，以标识 CSV 数据类型 HR 数据。 输入标识符列名称后，键入标识此 HR 数据类型 的值，并键入 CSV 文件 (s) 中所选数据类型的列标题名称，这些类型在步骤 1 中针对每个选定 数据类型 的每个相应框中创建。 如前所述，在这些框中键入的名称必须与 CSV 文件的列名称相匹配。

8. 在" **审阅** "页上，查看设置，然后单击" **完成** "以创建连接器。

   将显示一个状态页，确认连接器已创建。 此页面包含两个重要内容，您需要完成下一步以运行示例脚本来上载 HR 数据。

   ![查看包含作业 ID 的页面，并链接到 github，获取示例脚本。](../media/HRConnector_Confirmation.png)

   1. **作业 ID。** 您需要此作业 ID，以在下一步中运行脚本。 可以从此页面或连接器飞出页复制它。

   2. **指向示例脚本的链接。** 单击 **"此处**"链接可转到GitHub网站以访问示例脚本 (该链接将打开一个新窗口) 。 保持此窗口为打开状态，以便你可以复制步骤 4 中的脚本。 或者，您可以为目标添加书签或复制 URL，以便可以在运行脚本时再次访问它。 连接器飞出页面上也提供此链接。

9. 单击“完成”。

   新连接器显示在"连接器"选项卡 **上的** 列表中。

10. 单击刚创建的 HR 连接器以显示该飞出页，其中包含有关连接器的属性和其他信息。

   ![新 HR 连接器的"飞出"页面。](../media/HRConnectorWizard7.png)

如果你尚未这样做，你可以复制 **Azure 应用 ID** 和连接器作业 **ID 的值**。 下一步中，将需要使用这些脚本来运行脚本。 您还可以从飞出页面下载脚本 (下一步中的链接进行下载。) 

还可以单击" **编辑"** 更改在"文件映射"页上定义的 Azure 应用 ID 或列 **标题** 名称。

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>步骤 4：运行示例脚本以上载 HR 数据

设置 HR 连接器的最后一步是运行示例脚本，该脚本将在你在步骤 1) 中创建的 CSV 文件 (中的 HR 数据上载到 Microsoft 云。 具体而言，脚本将数据上载到 HR 连接器。 运行脚本后，在步骤 3 中创建的 HR 连接器将 HR 数据导入 Microsoft 365 组织，其他合规性工具（如预览体验成员风险管理解决方案）可以访问该组织。 运行脚本后，请考虑安排一项任务，每天自动运行一次，以便将最新的员工离职数据上传到 Microsoft 云。 请参阅 [计划脚本自动运行](#optional-step-6-schedule-the-script-to-run-automatically)。

1. 转到上一步中打开的窗口，通过示例脚本GitHub网站。 或者，打开已添加书签的网站或使用您复制的 URL。 也可以在此处访问 [脚本](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1)。

2. 单击" **原始** "按钮以在文本视图中显示脚本。

3. 复制示例脚本中所有的行，然后将它们保存到文本文件中。

4. 如有必要，修改组织的示例脚本。

5. 使用 文件名后缀 将文本文件另存为Windows PowerShell脚本文件 `.ps1` ;例如， `HRConnector.ps1` 。 或者，您也可以将 GitHub文件名用于 脚本，即 `upload_termination_records.ps1` 。

6. 在本地计算机上打开命令提示符，然后转到保存脚本的目录。

7. 运行以下命令，将 CSV 文件的 HR 数据上载到 Microsoft 云;例如：

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   下表介绍了要用于此脚本的参数及其所需值。 在之前步骤中获取的信息将使用这些参数的值。

   | 参数 | 说明 |
   |:-----|:-----|:-----|
   |`tenantId`|这是在步骤 2 Microsoft 365获得的组织 ID。 还可以在 Azure AD 管理中心的"概述"边栏选项卡上获取组织的租户 ID。 这用于标识您的组织。|
   |`appId` |这是你在步骤 2 中的 Azure AD 中创建的应用的 Azure AD 应用程序 ID。 当脚本尝试访问你的组织时，Azure AD 会Microsoft 365身份验证。 | 
   |`appSecret`|这是你在步骤 2 的 Azure AD 中创建的应用的 Azure AD 应用程序密码。 这还用于身份验证。|
   |`jobId`|这是在步骤 3 中创建的 HR 连接器的作业 ID。 这用于将上载到 Microsoft 云的 HR 数据与 HR 连接器关联。|
   |`csvFilePath`|这是 CSV 文件的文件路径， (步骤 1 中创建的脚本) 存储在同一系统中。 尝试避免文件路径中的空格;否则请使用单引号。|
   |||

   下面是使用每个参数的实际值的 HR 连接器脚本的语法示例：

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   如果上传成功，脚本将显示Upload **成功** 消息。

   > [!NOTE]
   > 如果由于执行策略而运行上一个命令时遇到问题，[](/powershell/module/microsoft.powershell.core/about/about_execution_policies)请参阅关于执行策略和[Set-ExecutionPolicy，](/powershell/module/microsoft.powershell.security/set-executionpolicy)了解设置执行策略的指南。

## <a name="step-5-monitor-the-hr-connector"></a>步骤 5：监视 HR 连接器

创建 HR 连接器并运行脚本以上传 HR 数据后，可以查看该连接器，并上传Microsoft 365 合规中心。 如果安排脚本定期自动运行，还可以在上次运行脚本后查看当前状态。

1. 转到左侧 [https://compliance.microsoft.com](https://compliance.microsoft.com) 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击 **"连接器"** 选项卡，然后选择 HR 连接器以显示飞出页面。 此页面包含有关连接器的属性和信息。

   ![包含属性和状态的 HR 连接器飞出页。](../media/HRConnectorFlyout1.png)

3. 在 **"进度****"下，** 单击"下载日志"链接 (或) 连接器的状态日志。 此日志包含有关脚本每次运行以及将数据从 CSV 文件上载到 Microsoft 云时的信息。 

   ![HR 连接器日志文件 CSV 文件中上传的行数。](../media/HRConnectorLogFile.png)

   `RecordsSaved`字段指示 CSV 文件中已上载的行数。 例如，如果 CSV 文件包含四行，则字段的值为 4（如果脚本成功上传 CSV 文件的所有 `RecordsSaved` 行）。

如果尚未在步骤 4 中运行脚本，则"上次导入"下将显示用于下载脚本 **的链接**。 可以下载脚本，然后按照步骤运行脚本。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (可选) 步骤 6：将脚本安排为自动运行

若要确保组织的最新 HR 数据可供内部风险管理解决方案等工具使用，建议安排脚本定期自动运行，如每天运行一次。 这还要求你在类似的 (（如果不是同一) 计划）上更新 CSV 文件的 HR 数据，以便其中包含有关离开组织的员工的最新信息。 目标是上载最新的 HR 数据，以便 HR 连接器能够将其提供给内部风险管理解决方案。

You can user the Task Scheduler app in Windows to automatically run the script every day.

1. 在本地计算机上，单击 **"Windows"** 按钮，然后键入 **"任务计划程序"。**

2. 单击任务 **计划程序** 应用以打开它。

3. 在"**操作"部分**，单击"**创建任务"。**

4. 在" **常规"** 选项卡上，键入计划任务的描述性名称;例如 **，HR 连接器脚本**。 还可以添加可选说明。

5. 在 **"安全选项**"下，执行以下操作：

   1. 确定是仅在您登录到计算机时运行脚本，还是在您登录时运行该脚本。

   1. 确保选中 **了"使用最高权限** 运行"复选框。

6. 选择 **"触发器"** 选项卡，单击 **"新建**"，然后执行以下操作：

   1. 在 **设置"** 下，选择"**每天**"选项，然后选择首次运行脚本的日期和时间。 脚本将每天在同一指定时间运行。

   1. 在 **"高级设置**"下，确保 **选中"已启用** "复选框。

   1. 单击“确定”。

7. 选择" **操作"** 选项卡，单击 **"新建**"，然后执行以下操作：

   ![为 HR 连接器脚本创建新的计划任务的操作设置。](../media/HRConnectorScheduleTask1.png)

   1. 在 **"操作** "下拉列表中，确保已 **选择"启动程序** "。

   1. 在"**程序/脚本**"框中，单击"浏览"，然后转到以下位置并选择它，以便路径显示在框中 `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` ：。

   1. 在" **添加 (可选) "** 框中，粘贴在步骤 4 中运行相同的脚本命令。 例如，`.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. 在 **" (可选**) "框中，粘贴在步骤 4 中运行脚本的文件夹位置。 例如，`C:\Users\contosoadmin\Desktop\Scripts`。

   1. 单击 **"** 确定"保存新操作的设置。

8. 在" **创建任务"** 窗口中，单击" **确定** "保存计划任务。 系统可能会提示你输入用户帐户凭据。

   新任务将显示在任务计划程序库中。

   ![新任务将显示在任务计划程序库中。](../media/HRConnectorTaskSchedulerLibrary.png)

   显示脚本上次运行的时间和计划运行的下一次。 可以双击任务进行编辑。

   还可以验证脚本上次在合规中心中相应 HR 连接器的飞出页面上运行的时间。

## <a name="existing-hr-connectors"></a>现有 HR 连接器

2020 年 7 月 20 日，我们发布了 HR 连接器支持的其他方案。 这些是本文前面介绍的 HR 方案。 在此日期之前创建的任何 HR 连接器都仅支持员工参与方案。 如果你在 2020 年 7 月 20 日之前创建了 HR 连接器，我们已经将其迁移，以便它可以继续将 HR 数据迁移到 Microsoft 云。 不必执行任何工作来维护此功能。 您可以一直使用该连接器，而不会中断任何操作。

如果要实现其他 HR 方案，请创建新的 HR 连接器，并针对已发布的其他 HR 方案配置它。 你还需要创建一个或多个包含数据的新 CSV 文件以支持其他 HR 方案。 创建新的 HR 连接器后，使用新连接器的作业 ID 和 CSV 文件 (运行脚本) 其他 HR 方案的数据。