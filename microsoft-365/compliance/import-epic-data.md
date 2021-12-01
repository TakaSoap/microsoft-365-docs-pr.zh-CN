---
title: 设置连接器以导入处理 EHR 数据
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
description: 管理员可以设置数据连接器，将 EHR 中的电子 (数据) 从组织的管理中心系统导入Microsoft 365。 这样，你可以将管理 EHR 数据用于内部风险管理策略，以帮助你检测员工对患者数据的未经授权的访问活动。
ms.openlocfilehash: 147519db433396376a406c5ce558fe4ad0f8428c
ms.sourcegitcommit: aacf895ba20ecec4312a447ff4432e257e41edee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2021
ms.locfileid: "61234539"
---
# <a name="set-up-a-connector-to-import-epic-ehr-audit-data-preview"></a>设置连接器以在预览版中导入 (EHR 审核) 

可以在 EHR Microsoft 365 合规中心设置数据连接器，以在组织的"电子医疗保健记录" (EHR) 中导入用户活动的审核记录。 来自你的处理 EHR 系统的审核记录包括有关访问患者健康记录的事件的记录。 内部风险管理解决方案可以使用安全 eHR 审核Microsoft 365，以帮助保护[](insider-risk-management.md)组织免受对患者信息的未经授权的访问。

设置一个 Connector 连接器包含以下任务：

- 在应用程序中创建Azure Active Directory (Azure AD) ，以访问 API 终结点，该终结点接受包含一个以制表符分隔的文本文件，其中包含一个"用户"EHR 审核记录。

- 创建包含连接器架构中定义的所有必填字段的文本文件。

- 在连接器中创建一个Microsoft 365 合规中心。

- 运行脚本将处理 EHR 审核记录推送到 API 终结点。

- （可选）将脚本安排为自动运行以导入审核记录。

## <a name="before-you-set-up-the-connector"></a>设置连接器之前

- 必须在步骤 3 中为在步骤 3 中创建连接器的用户分配邮箱导入导出Exchange Online。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到"管理"角色组Exchange Online。 也可以创建新的角色组，分配"邮箱导入导出"角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"在角色[](\Exchange\permissions-exo\role-groups#create-role-groups)组中管理角色组[](\Exchange\permissions-exo\role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 您需要确定如何每天从组织的 (EHR 系统检索或导出数据) 并创建步骤 2 中所述的文本文件。 在步骤 4 中运行的脚本将文本文件中的数据推送到 API 终结点。

- 在步骤 4 中运行的示例脚本将"一般 EHR 审核记录"从文本文件推送到连接器 API，以便内部风险管理解决方案可以使用它。 本示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。 示例脚本“原样”提供，不提供任何形式的保证。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤 1：在 Azure Active Directory

第一步是在应用程序创建和注册Azure Active Directory (Azure AD) 。 该应用将对应于你在步骤 3 创建的"放大"连接器。 创建此应用Azure AD验证包含一些用户 EHR 审核记录的文本文件的推送请求。 创建此应用程序Azure AD，请务必保存以下信息。 这些值将在稍后的步骤中使用。

- Azure AD ID (也称为 *应用程序 ID* 或 *客户端 ID*) 

- Azure AD应用程序密码 (也称为 *客户端密码*) 

- 租户 ID (*也称为目录 ID*) 

有关在应用程序中创建应用的分步Azure AD，请参阅使用 Microsoft 标识平台[注册应用程序](\azure\active-directory\develop\quickstart-register-app)。

## <a name="step-2-prepare-a-text-file-with-epic-ehr-audit-records"></a>步骤 2：使用管理 EHR 审核记录准备文本文件

下一步是创建一个文本文件，其中包含有关员工在组织的管理 EHR 系统中访问患者健康记录的信息。 如前所述，你需要确定如何从你的"百年计划"EHR 系统生成此文本文件。 The Connector workflow requires a text file with tab-separated values to map that data in the text file with required connector schema. 支持的文件格式是管道或制表符分隔.txt文件。

> [!NOTE]
> 包含审核数据的文本文件的最大大小为 3 GB。 最大行数为 500 万。 此外，请务必仅包含来自医疗保健 EHR 系统的相关审核数据。

下表列出了启用内部风险管理方案所需的字段。 这些字段的子集是必需的。 这些字段用星号* (突出显示) 。 如果文本文件中缺少任何必需字段，将不会验证该文件，并且不会导入该文件的数据。

|字段|类别|
|:----|:----------|
| ACCESS_LOG。*<br/> ACCESS_TIME ACCESS_LOG_METRIC。METRIC_NAME*<br/>ACCESS_LOG。WORKSTATION_ID<br/>ZC \_ \_ 指标 GROUP.NAME<br/>ZC \_ ACCESS \_ ACTION.NAME |这些字段用于标识您的"管理中心"EHR 系统中的访问活动事件。|
| PATIENT。PAT_MRN_ID<br/>PATIENT。PAT_FIRST_NAME* <br/>PATIENT。PAT_MIDDLE_NAME <br/>PATIENT。PAT_LAST_NAME* <br/>PATIENT。ADD_LINE_1* <br/>PATIENT。ADD_LINE_2  <br/>PATIENT。CITY* <br/>PATIENT.ZIP*  <br/>ZC_STATE.NAME <br/>ZC_COUNTRY.NAME <br/>CLARITY_DEP。DEPARTMENT_NAME              | 这些字段用于标识患者配置文件信息。|
| ZC_BTG_REASON.NAME*<br/> PAT_BTG_AUDIT。BTG_EXPLANATION | 这些字段用于标识对受限记录的访问。|
| EMP。SYSTEM_LOGIN*<br/>CLARITY_EMP。USER_ID <br/> employee_last_name<sup>1</sup> <br/> employee_first_name<sup>1</sup>                | 这些字段用于标识确定对"家庭/邻接/员工"记录的访问权限所需的地址和名称匹配的员工个人资料信息。 |
|||

> [!NOTE]
> 确保仅从"百度"导出相关的日志指标。 
> <sup>1</sup>默认情况下，此字段在"百分百"中不可用。 您需要配置导出以确保文本文件包含此字段。

## <a name="step-3-create-the-epic-connector"></a>步骤 3：创建连接器

下一步是在应用程序创建一个 Microsoft 365 合规中心。 在步骤 4 中运行脚本后，将处理在步骤 2 中创建的文本文件，并推送到在步骤 1 中设置的 API 终结点。 在此步骤中，请确保复制创建连接器时生成的 JobId。 运行脚本时，将使用 JobId。

1. 转到 ， <https://compliance.microsoft.com> 然后单击左侧 **导航中的** "数据连接器"。

2. 在"**数据连接器"页上** 的"**连接器**"下，单击"查看 **"。**

3. 在 **"连接器"页上**，单击"**添加连接器"。**

4. 在"**设置连接"** 页上，执行以下操作，然后单击"下一步 **"：**

    1. 键入或粘贴Azure AD 2 中创建的 Azure 应用的应用程序 ID。

    2. 键入"百年"连接器的名称。

5. 在" **审阅** "页上，查看设置，然后单击" **完成** "以创建连接器。

   将显示一个状态页，确认连接器已创建。 此页面包含两个重要内容，您需要完成下一步以运行示例脚本来上载您的处理 EHR 审核记录数据。

    查看包含作业 ID 的页面和指向 github 的链接，获取示例脚本

    1. **作业 ID。** 您需要此作业 ID，以在下一步中运行脚本。 可以从此页面或连接器飞出页复制它。

    2. **参考架构。** 请参阅架构，了解连接器接受来自您的为时系统哪些字段。 这将帮助你创建一个包含所有必需的"完成时间"数据库字段的文件。

    3. **指向示例脚本的链接。** 单击 **"此处**"链接可转到GitHub网站以访问示例脚本 (该链接将打开一个新窗口) 。 保持此窗口为打开状态，以便你可以复制步骤 4 中的脚本。 或者，您可以为目标添加书签或复制 URL，以便可以在运行脚本时再次访问它。 连接器飞出页面上也提供此链接。

6. 单击“**完成**”。

   新连接器显示在"连接器"选项卡 **上的** 列表中。

7. 单击刚创建的"连接器"以显示包含有关连接器的属性和其他信息的飞出页。

如果你尚未这样做，你可以复制 **Azure 应用 ID** 和连接器作业 **ID 的值**。 下一步中，将需要使用这些脚本来运行脚本。 您还可以从飞出页面下载脚本 (下一步中的链接下载脚本。) 

还可以单击" **编辑"** 更改在"文件映射"页上定义的 Azure 应用 ID 或列 **标题** 名称。

## <a name="step-4-run-the-sample-script-to-upload-your-epic-ehr-audit-records"></a>步骤 4：运行示例脚本以上载您的处理 EHR 审核记录

设置云解决方案连接器的最后一步是运行示例脚本，该脚本将在你在步骤 1) 中创建的文本文件 (中上载"完成 EHR"审核记录数据，并将其上载到 Microsoft 云。 具体而言，脚本将数据上载到 Connector 连接器。 运行脚本后，在步骤 3 中创建的部署连接器将"完成 EHR 审核记录"数据导入 Microsoft 365 组织，其他合规性工具（如预览体验成员风险管理解决方案）可以访问该数据。 运行脚本后，请考虑安排每天自动运行该脚本的任务，以便将最新的员工离职数据上传到 Microsoft 云。 请参阅 [ (可选) 步骤 6：将脚本安排为自动运行](#optional-step-6-schedule-the-script-to-run-automatically)。

> [!NOTE]
> 如前所述，包含审核数据的文本文件的最大大小为 3 GB。 最大行数为 500 万。 在此步骤中运行的脚本将大约需要 30 至 40 分钟从大型文本文件导入审核数据。 此外，该脚本还将大型文本文件划分为包含 10 万行的较小块，然后按顺序导入这些块。

1. 转到上一步中打开的窗口，通过示例脚本GitHub网站。 或者，打开已添加书签的网站或使用您复制的 URL。

2. 单击" **原始** "按钮以在文本视图中显示脚本。

3. 复制示例脚本中所有行，然后将它们保存到文本文件。

4. 如有必要，修改组织的示例脚本。

5. 使用 文件名后缀 将文本文件另存为Windows PowerShell脚本文件 `.ps1` ;例如， `EpicConnector.ps1` 。

6. 在本地计算机上打开命令提示符，然后转到保存脚本的目录。

7. 运行以下命令，将文本文件中的管理审核数据上载到 Microsoft 云;例如：

   ```powershell
   .\EpicConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -filePath '<filePath>'
   ```

下表介绍了要用于此脚本的参数及其所需值。 在之前步骤中获取的信息将使用这些参数的值。

|参数  |说明|
|:----------|:----------|
|tenantId|这是在步骤 1 Microsoft 365获取的组织的 ID。 还可以在管理中心的"概述"边栏选项卡上获取Azure AD ID。 这用于标识您的组织。|
|appId|这是Azure AD步骤 1 中创建的应用的应用程序Azure AD ID。 当脚本尝试Azure AD组织时，此参数用于Microsoft 365身份验证。|
|appSecret|这是Azure AD步骤 1 中创建的应用的Azure AD密码。 这还用于身份验证。|
|jobId|这是在步骤 3 中创建的"放大"连接器的作业 ID。 这用于将上载到 Microsoft 云的"完成"EHR 审核记录与"云解决方案提供商"连接器关联。|
|filePath|这是文本文件的文件路径， (步骤 2 中创建的脚本) 存储在同一系统中。 尝试避免文件路径中的空格;否则请使用单引号。|
|||

下面是使用每个参数的实际值的 Connector 脚本的语法示例：

```powershell
.\EpicConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -filePath 'C:\Users\contosoadmin\Desktop\Data\epic_audit_records.txt'
```

如果上传成功，脚本将显示Upload **成功** 消息。

> [!NOTE]
> 如果由于执行策略而运行上一个命令时遇到问题，[](\powershell\module\microsoft.powershell.core\about\about_execution_policies)请参阅关于执行策略和[Set-ExecutionPolicy，](\powershell\module\microsoft.powershell.security\set-executionpolicy)了解设置执行策略的指南。

## <a name="step-5-monitor-the-epic-connector"></a>步骤 5：监视连接器

创建连接器并推送 EHR 审核记录后，可以查看连接器，并上传Microsoft 365 合规中心。 如果安排脚本定期自动运行，还可以在上次运行脚本后查看当前状态。

1. 转到左侧 <https://compliance.microsoft.com> 导航 **导航中的"数据** 连接器"，然后单击" 数据连接器"。

2. 单击" **连接器"** 选项卡，然后选择"连接器"以显示飞出页面。 此页面包含有关连接器的属性和信息。

3. 在 **"上次导入**"下，单击"下载日志"链接 (或) 连接器的状态日志。 此日志包含有关脚本每次运行以及将数据从文本文件上载到 Microsoft 云时的信息。

    连接器日志文件显示已上载的文本文件中的行数

    `RecordsSaved`该字段指示已上载的文本文件中的行数。 例如，如果文本文件包含四行，则字段的值为 4（如果脚本已成功上载文本文件中所有 `RecordsSaved` 行）。

如果尚未在步骤 4 中运行脚本，则"上次导入"下将显示用于下载脚本 **的链接**。 可以下载脚本，然后按照步骤运行脚本。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (可选) 步骤 6：将脚本安排为自动运行

若要确保来自 Your Insider EHR 系统的最新审核记录可供内部风险管理解决方案等工具使用，建议安排脚本每天自动运行。 这还要求你在类似的 (（如果不是同一) 计划）上更新同一文本文件中的"Patient"审核记录数据，以便其中包含员工有关患者记录访问活动的最新信息。 目标是上载最新的审核记录，以便"确定"连接器可用于内部风险管理解决方案。 

You can user the Task Scheduler app in Windows to automatically run the script every day.

1. 在本地计算机上，单击 **"Windows"** 按钮，然后键入 **"任务计划程序"。**

2. 单击任务 **计划程序** 应用以打开它。

3. 在"**操作"部分**，单击"**创建任务"。**

4. 在" **常规"** 选项卡上，键入计划任务的描述性名称;例如 **，Connector 连接器脚本**。 还可以添加可选说明。

5. 在 **"安全选项**"下，执行以下操作：

    1. 确定是仅在您登录到计算机时运行脚本，还是在您登录时运行该脚本。

    2. 确保选中 **了"使用最高权限** 运行"复选框。

6. 选择 **"触发器"** 选项卡，单击 **"新建**"，然后执行以下操作：

    1. 在 **设置"** 下，选择"**每天**"选项，然后选择首次运行脚本的日期和时间。 脚本将每天在同一指定时间运行。

    2. 在 **"高级设置**"下，确保 **选中"已启用** "复选框。

    3. 单击“确定”。

7. 选择" **操作"** 选项卡，单击 **"新建**"，然后执行以下操作：

   ![为连接器脚本创建新的计划任务的操作设置。](../media/EpicConnectorScheduleTask1.png)

    1. 在 **"操作** "下拉列表中，确保已 **选择"启动程序** "。

    2. 在"**程序/脚本**"框中，单击"浏览"，然后转到以下位置并选择它，以便路径显示在框中：C:.0.exe。

    3. 在" **添加 (可选) "** 框中，粘贴在步骤 4 中运行相同的脚本命令。 例如，`.\EpicConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -filePath "C:\Epic\audit\records.txt"`

    4. 在 **" (可选**) "框中，粘贴在步骤 4 中运行脚本的文件夹位置。 例如，C：\的\Audit\audit。

    5. 单击 **"** 确定"保存新操作的设置。

8. 在" **创建任务"** 窗口中，单击" **确定** "保存计划任务。 系统可能会提示您输入用户帐户凭据。

   新任务将显示在任务计划程序库中。

   ![医疗保健连接器脚本的新任务显示在任务计划程序库中。](../media/EpicConnectorTaskSchedulerLibrary.png)

   显示脚本上次运行的时间和计划运行的下一次。 可以双击任务进行编辑。

   还可以验证脚本上次在合规中心中相应"空心连接器"的"飞出"页面上运行的时间。
