---
title: 设置连接器以将 HR 数据导入美国政府云
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
ms.custom: admindeeplinkCOMPLIANCE
ROBOTS: NOINDEX, NOFOLLOW
description: 美国政府云中的管理员可以设置数据连接器，以从组织的人力资源部门导入员工数据， (HR) 系统导入Microsoft 365。 这样，你可以将 HR 数据用于内部风险管理策略，以帮助你检测特定用户可能对组织造成内部威胁的活动。
ms.openlocfilehash: abfe43d1f0b61952c2dbc0f603250723965953a1
ms.sourcegitcommit: 99067d5eb1fa7b094e7cdb1f7be65acaaa235a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2022
ms.locfileid: "62271858"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>设置连接器以导入美国政府中的 HR 数据

您可以在企业设置数据连接器Microsoft 365 合规中心将人力资源 () 到美国政府组织。 与 HR 相关的数据包括员工提交其期限的日期和员工最后一天的日期。 然后，此 HR 数据Microsoft 信息保护解决方案（如内部风险管理解决方案）用于帮助保护组织[](insider-risk-management.md)免受组织内部恶意活动或数据盗窃的攻击。 设置 HR 连接器包括：在 Azure Active Directory 中创建用于连接器身份验证的应用，创建包含 HR 数据的 CSV 映射文件，在合规中心创建数据连接器，然后按计划运行脚本 () 该脚本将 CSV 文件的 HR 数据导入到 Microsoft 云。 然后，内部风险管理工具使用数据连接器访问导入到美国政府组织的MICROSOFT 365 HR 数据。

## <a name="before-you-begin"></a>准备工作

- 必须在步骤 3 中为在步骤 3 中创建 HR 连接器的用户分配邮箱导入导出Exchange Online。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建新的角色组，分配"邮箱导入导出"角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[组中的角色组](/Exchange/permissions-exo/role-groups#create-role-groups)"[](/Exchange/permissions-exo/role-groups#modify-role-groups)一文的"创建角色组"或"修改角色Exchange Online"。

- 你需要确定如何定期从组织的 HR 系统 (检索或导出数据) 并将其添加到步骤 2 中介绍的 CSV 文件。 在步骤 4 中运行的脚本将在 CSV 文件中将 HR 数据上载到 Microsoft 云。

- 在步骤 4 中运行的示例脚本将 HR 数据上载到 Microsoft 云，以便其他 Microsoft 工具（如内部风险管理解决方案）可以使用这些数据。 本示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。 示例脚本“原样”提供，不提供任何形式的保证。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤 1：在 Azure Active Directory

第一步是在应用程序创建和注册Azure Active Directory (Azure AD) 。 该应用将对应于你在步骤 3 创建的 HR 连接器。 创建此应用程序将使Azure AD在 HR 连接器运行时和尝试访问组织时进行身份验证。 此应用还将用于对在步骤 4 中运行的脚本进行身份验证，以将 HR 数据上传到 Microsoft 云。 创建此应用程序Azure AD，请务必保存以下信息。 这些值将在稍后的步骤中使用。

- Azure AD ID (也称为 *应用 ID* 或 *客户端 ID)*

- Azure AD应用程序密码 (也称为 *客户端密码*) 

- 租户 ID (*也称为目录 ID*) 

有关在应用程序中创建应用的分步Azure AD，请参阅使用 Microsoft 标识平台 注册[应用程序](/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>步骤 2：准备包含 HR 数据的 CSV 文件

下一步是创建一个 CSV 文件，其中包含有关已离开组织的员工的信息。 如开始之前部分所述，你需要确定如何从组织的 HR 系统生成此 CSV 文件。 以下示例显示在记事 (打开的已完成 CSV 文件) 其中包含三个必需参数 (列) 。 在文件编辑中编辑 CSV 文件Microsoft Excel。

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

CSV 文件的第一行（即标题行）列出了所需的列名称。 每个列标题中使用的名称由您决定 (示例中的名称是建议) 。 但是，在步骤 3 中创建 HR 连接器时，必须指定 CSV 文件中使用的相同列名称。 列名称中不要包含空格。

下表介绍了 CSV 文件的每一列：

| 列名称 | 说明 |
|:-----|:-----|
| **EmailAddress** <br/> |指定已终止员工的电子邮件地址。|
| **TerminationDate** <br/> |指定在组织中正式终止其雇佣关系的日期。 例如，这可能是员工通知你离开组织的日期。 此日期可能不同于人员最后一天的工作日期。 使用以下日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
|**LastWorkingDate**|指定离职员工的最后一天工作。 使用以下日期格式： `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`，即 [ISO 8601 日期和时间格式](https://www.iso.org/iso-8601-date-and-time-format.html)。|
|||

创建包含所需 HR 数据的 CSV 文件后，请与步骤 4 中运行的脚本存储在同一系统中。 请务必实现更新策略，以便 CSV 文件始终包含最新信息。 这样做可确保无论运行脚本如何，最新的员工离职数据都会上传到 Microsoft 云。

## <a name="step-3-create-the-hr-connector"></a>步骤 3：创建 HR 连接器

下一步是在企业内部创建 HR Microsoft 365 合规中心。 在步骤 4 中运行脚本后，您创建的 HR 连接器将从 CSV 文件将 HR 数据导入Microsoft 365组织。 在此步骤中，请确保复制创建连接器时生成的作业 ID。 运行脚本时，将使用作业 ID。

1. 转到"Microsoft 365 合规中心"，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**数据连接器"** 页</a>。

2. 在" **数据连接器"页上** 的 **"HR"下**，单击" **查看"**。

3. 在" **HR"** 页上，单击" **添加连接器"**。

4. 在" **身份验证凭据"** 页上，执行以下操作，然后单击"下一步 **"**：

   1. 键入或粘贴Azure AD 1 中创建的 Azure 应用的应用程序 ID。

   1. 键入 HR 连接器的名称。

5. 在"**文件映射**"页上，键入三列标题的名称 (在每个相应的框中键入在步骤 2 中创建的 CSV 文件) 也称为 *参数) 。* 名称不区分大小写。 如前所述，在这些框中键入的名称必须与 CSV 文件中的参数名称相匹配。 例如，以下屏幕截图显示了步骤 2 中显示的示例 CSV 文件中的示例的参数名称。

   ![列标题名称与 CSV 文件中的名称匹配。](../media/HRConnectorWizard3.png)

6. 在" **审阅** "页上，查看设置，然后单击" **完成** "以创建连接器。

   将显示一个状态页，确认连接器已创建。 此页面包含两个重要内容，您需要完成下一步以运行示例脚本来上载 HR 数据。

   ![查看包含作业 ID 的页面，并链接到 github，获取示例脚本。](../media/HRConnector_Confirmation.png)

   1. **作业 ID。** 您需要此作业 ID，以在下一步中运行脚本。 可以从此页面或连接器飞出页复制它。
   
   1. **指向示例脚本的链接。** 单击 **"此处**"链接可转到GitHub网站以访问示例脚本 (该链接将打开一个新窗口) 。 保持此窗口为打开状态，以便你可以复制步骤 4 中的脚本。 或者，您可以为目标添加书签或复制 URL，以便可以在步骤 4 中再次访问它。 连接器飞出页面上也提供此链接。

7. 单击“**完成**”。

   新连接器显示在"连接器"选项卡 **上的** 列表中。 

8. 单击刚创建的 HR 连接器以显示该飞出页，其中包含有关连接器的属性和其他信息。

   ![新 HR 连接器的"飞出"页面。](../media/HRConnectorWizard7.png)

   如果尚未复制，可以复制 **Azure 应用 ID** 和连接器作业 **ID 的值**。 下一步中，将需要使用这些脚本来运行脚本。 您还可以从飞出页面下载脚本 (下一步中的链接下载脚本。) 

   还可以单击" **编辑"** 更改在"文件映射"页上定义的 Azure 应用 ID 或列 **标题** 名称。

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>步骤 4：运行示例脚本以上载 HR 数据

设置 HR 连接器的最后一步是运行示例脚本，该脚本将在 CSV 文件 (（在步骤 2) 中创建）中将 HR 数据上载到 Microsoft 云。 具体而言，脚本将数据上载到 HR 连接器。 运行脚本后，在步骤 3 中创建的 HR 连接器将 HR 数据导入 Microsoft 365 组织，其他合规性工具（如预览体验成员风险管理解决方案）可以访问此组织。 运行脚本后，请考虑安排每天自动运行该脚本的任务，以便将最新的员工离职数据上传到 Microsoft 云。 请参阅 [计划脚本自动运行](#optional-step-6-schedule-the-script-to-run-automatically)。

1. 转到上一步中打开的窗口，通过示例脚本GitHub网站。 或者，打开已添加书签的网站或使用您复制的 URL。

2. 单击" **原始** "按钮以在文本视图中显示脚本。

3. 复制示例脚本中所有行，然后将它们保存到文本文件。

4. 如有必要，修改组织的示例脚本。

5. 使用 文件名后缀 将文本文件另存为`.ps1`Windows PowerShell脚本文件;例如， `HRConnector.ps1`。

6. 在本地计算机上打开命令提示符，然后转到保存脚本的目录。

7. 运行以下命令，将 CSV 文件的 HR 数据上载到 Microsoft 云;例如：

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   下表介绍了要用于此脚本的参数及其所需值。 在之前步骤中获取的信息将使用这些参数的值。

   | 参数 | 说明 |
   |:-----|:-----|:-----|
   |`tenantId`|在步骤 1 Microsoft 365获得的组织 ID。 还可以在管理中心的"概述"边栏选项卡上获取Azure AD ID。 这用于标识您的组织。|
   |`appId` |步骤 1 Azure AD中创建的应用的应用程序Azure AD ID。 当脚本尝试Azure AD组织时，此参数Microsoft 365进行身份验证。 |
   |`appSecret`|在Azure AD步骤 1 中创建的应用的Azure AD密码。 这还用于身份验证。|
   |`jobId`|在步骤 3 中创建的 HR 连接器的作业 ID。 这用于将上载到 Microsoft 云的 HR 数据与 HR 连接器关联。|
   |`csvFilePath`|CSV 文件的文件路径 (步骤 2 中创建的脚本) 存储在同一系统中。 尝试避免文件路径中的空格;否则请使用单引号。|
   |||
   
   下面是使用每个参数的实际值的 HR 连接器脚本的语法示例：

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   如果上传成功，脚本将显示Upload **成功** 消息。

   > [!NOTE]
   > 如果由于执行策略而运行上一个命令时遇到问题，[](/powershell/module/microsoft.powershell.core/about/about_execution_policies)请参阅关于执行策略和 [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)，了解设置执行策略的指南。

## <a name="step-5-monitor-the-hr-connector"></a>步骤 5：监视 HR 连接器

创建 HR 连接器并运行脚本以上传 HR 数据后，可以查看该连接器，并上传Microsoft 365 合规中心。 如果安排脚本定期自动运行，还可以在上次运行脚本后查看当前状态。

1. 转到"Microsoft 365 合规中心"，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**数据连接器"**</a>。

2. 单击 **"连接器"** 选项卡，然后选择 HR 连接器以显示飞出页面。 此页面包含有关连接器的属性和信息。

   ![包含属性和状态的 HR 连接器飞出页。](../media/HRConnectorFlyout1.png)

3. 在 **"进度****"下，** 单击"下载日志"链接 (或) 连接器的状态日志。 此日志包含有关脚本每次运行以及将数据从 CSV 文件上载到 Microsoft 云时的信息。 

   ![HR 连接器日志文件 CSV 文件中上传的行数。](../media/HRConnectorLogFile.png)

   字段 `RecordsSaved` 指示 CSV 文件中已上载的行数。 例如，如果 CSV 文件 `RecordsSaved` 包含四行，则字段的值为 4（如果脚本成功上传 CSV 文件的所有行）。

如果尚未在步骤 4 中运行脚本，则"上次导入"下将显示用于下载脚本 **的链接**。 可以下载脚本，然后按照步骤 4 中的步骤运行它。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (可选) 步骤 6：计划脚本自动运行

若要确保组织的最新 HR 数据可用于内部风险管理解决方案等工具，建议安排脚本定期自动运行，如每天运行一次。 这还要求你在类似的 (（如果不是同一) 计划）上更新 CSV 文件的 HR 数据，以便其中包含有关离开组织的员工的最新信息。 目标是上载最新的 HR 数据，以便 HR 连接器能够将其提供给内部风险管理解决方案。

可以使用任务计划程序应用Windows每天自动运行脚本。

1. 在本地计算机上，单击"Windows **"** 按钮，然后键入 **"任务计划程序"**。

2. 单击任务 **计划程序** 应用以打开它。

3. 在" **操作"** 部分，单击" **创建任务"**。

4. 在" **常规"** 选项卡上，键入计划任务的描述性名称;例如， **HR 连接器脚本**。 还可以添加可选说明。

5. 在 **"安全选项**"下，执行以下操作：

   1. 确定是仅在您登录到计算机时运行脚本，还是在您登录时运行该脚本。
   
   1. 确保选中 **了"使用最高权限** 运行"复选框。

6. 选择 **"触发器"** 选项卡，单击 **"新建**"，然后执行以下操作：

   1. 在 **设置**"下，选择"每天"选项，然后选择首次运行脚本的日期和时间。 脚本将每天在指定的同一时间运行。
   
   1. 在 **"高级设置**"下，确保 **选中"已启用** "复选框。
   
   1. 单击“确定”。

7. 选择" **操作"** 选项卡，单击 **"新建**"，然后执行以下操作：

   ![为 HR 连接器脚本创建新的计划任务的操作设置。](../media/HRConnectorScheduleTask1.png)

   1. 在 **"操作** "下拉列表中，确保已 **选择"启动程序** "。

   1. 在"**程序/脚本**"框中，单击"浏览"，然后转到以下位置并选择它，以便路径显示在框中：`C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`。

   1. 在" **添加 (可选)** "框中，粘贴在步骤 4 中运行相同的脚本命令。 例如，`.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. 在" **(可选**) "框中，粘贴在步骤 4 中运行脚本的文件夹位置。 例如，`C:\Users\contosoadmin\Desktop\Scripts`。

   1. 单击 **"** 确定"保存新操作的设置。

8. 在" **创建任务"** 窗口中，单击" **确定** "保存计划任务。 系统可能会提示您输入用户帐户凭据。

   新任务将显示在任务计划程序库中。

   ![新任务将显示在任务计划程序库中。](../media/HRConnectorTaskSchedulerLibrary.png)

   显示脚本上次运行的时间和计划运行的下一次。 可以双击任务进行编辑。

   还可以验证脚本上次在合规中心中相应 HR 连接器的飞出页面上运行的时间。