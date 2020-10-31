---
title: 设置连接器以导入物理徽章数据
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
description: 管理员可以将数据连接器设置为将数据从其组织的物理徽章系统导入到 Microsoft 365。 这使您可以在内部风险管理策略中使用此数据，以帮助您检测特定用户对您的物理建筑物的访问，这些建筑物可能表明您的组织可能存在内部威胁。
ms.openlocfilehash: 71f43d8e6abd53454b6c81d811d0dca2e8b08388
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816645"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>设置连接器以导入物理徽章数据 (预览) 

您可以在 Microsoft 365 合规性中心中设置数据连接器，以导入物理徽章数据，如员工的原始物理访问事件或由组织的徽章系统生成的任何物理访问告警。 物理访问点的示例是建筑物的入口或服务器机房或数据中心的入口。 物理徽章数据可由 Microsoft 365 [内幕风险管理解决方案](insider-risk-management.md) 使用，以帮助您的组织防止恶意活动或组织内的数据被盗。

设置物理徽章连接器包含以下任务：

- 在 Azure Active Directory 中创建应用程序 (Azure AD) 访问接受包含物理徽章数据的 JSON 有效负载的 API 终结点。

- 使用物理徽章数据连接器定义的架构创建 JSON 有效负载。

- 在 Microsoft 365 合规性中心创建物理徽章数据连接器。

- 运行脚本以将物理徽章数据推送到 API 终结点。

- （可选）安排脚本自动运行以导入当前物理徽章数据。

## <a name="before-you-set-up-the-connector"></a>设置连接器之前

- 您的组织必须同意允许 Office 365 导入服务访问组织中的数据。 若要同意此请求，请转到 [此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全局管理员的凭据登录，然后接受该请求。 您必须完成此步骤，然后才能在步骤3中成功创建物理徽章连接器。

- 在第3步中创建物理徽章连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者，您可以创建新的角色组，分配邮箱导入导出角色，然后将相应的用户添加为成员。 有关详细信息，请参阅文章 "管理 Exchange Online 中的角色组" 中的 " [创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) " 或 " [修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) " 部分。

- 您需要确定如何检索或导出组织的物理徽章系统 (中的数据，) 并创建步骤2中所述的 JSON 文件。 您在步骤4中运行的脚本会将 JSON 文件中的数据推送到 API 终结点。

- 您在步骤4中运行的示例脚本将物理徽章数据从 JSON 文件推送到连接器 API，以便内部风险管理解决方案可以使用该数据。 在任何 Microsoft standard 支持计划或服务下，不支持此示例脚本。 示例脚本按原样提供，而不提供任何种类的担保。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 因使用或性能示例脚本和文档而导致的全部风险都将保留给您。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤1：在 Azure Active Directory 中创建应用程序

第一步是在 Azure Active Directory (Azure AD) 中创建和注册新应用程序。 应用将与您在步骤3中创建的物理徽章连接器相对应。 创建此应用程序将允许 Azure AD 对包含物理徽章数据的 JSON 有效负载的推送请求进行身份验证。 在创建此 Azure AD 应用过程中，请务必保存以下信息。 这些值将在后续步骤中使用。

- Azure AD 应用程序 ID (也称为 " *应用程序 id* " 或 " *客户端 id* ") 

- Azure AD 应用程序机密 (也称为 *客户端密码* ) 

- 租户 Id (也称为 *目录 Id* ) 

有关在 Azure AD 中创建应用程序的分步说明，请参阅 [使用 Microsoft identity Platform 注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>步骤2：使用物理徽章数据准备 JSON 文件

下一步是创建一个 JSON 文件，其中包含有关员工的物理访问数据的信息。 如 "开始之前" 一节中所述，您需要确定如何从组织的物理徽章系统生成此 JSON 文件。

JSON 文件必须符合连接器所需的架构定义。 以下是 JSON 文件所需的架构属性的说明：

| 属性 | 说明 | 数据类型 |
|:-----------|:--------------|:------------|
|UserID|一个员工可以在系统中具有多个数字标识。 输入需要有源系统已解析的 Azure AD ID。 |UPN 或电子邮件地址|
|AssetId|物理资产或物理访问点的参考 ID。| 字母数字字符串|
|AssetName|物理资产或物理访问点的友好名称。|字母数字字符串|
|EventTime|访问的时间戳。|以 UTC 格式表示的日期和时间|
|AccessStatus|值 `Success` 或 `Failed`| String|
|||

下面的示例展示了符合所需架构的 JSON 文件：

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",        
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",        
        "AccessStatus":"Success",
    }
]
```
当您在步骤3中创建物理徽章连接器时，您还可以从向导下载以下用于 JSON 文件的架构定义。

```text
{
    "title" : "Physical Badging Signals",
    "description" : "Access signals from physical badging systems",
    "DataType" : {
        "description" : "Identify what is the data type for input signal",
        "type" : "string",
    },
    "type" : "object",
    "properties": {
        "UserId" : {
            "description" : "Unique identifier AAD Id resolved by the source system",
            "type" : "string",
        },
        "AssetId": {
            "description" : "Unique ID of the physical asset/access point",
            "type" : "string",
        },
        "AssetName": {
            "description" : "friendly name of the physical asset/access point",
            "type" : "string",
        },
        "EventTime" : {
            "description" : "timestamp of access",
            "type" : "string",
        },
        "AccessStatus" : {
            "description" : "what was the status of access attempt - Success/Failed",
            "type" : "string",
        },
    }
    "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>步骤3：创建物理徽章连接器

下一步是在 Microsoft 365 合规性中心中创建物理徽章连接器。 在第4步中运行脚本之后，将处理您在步骤3中创建的 JSON 文件并将其推送到您在步骤1中配置的 API 终结点。 在此步骤中，请务必复制创建连接器时生成的 JobId。 运行该脚本时，您将使用 JobId。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然后单击左侧导航中的 " **数据连接器** "。

2. 在 " **物理徽章** " 下的 " **数据连接器** " 页上，单击 " **查看** "。

3. 在 " **物理徽章** " 页上，单击 " **添加连接器** "。

4. 在 " **身份验证凭据** " 页上，执行以下操作，然后单击 " **下一步** "：
  
   1. 键入或粘贴您在步骤1中创建的 Azure 应用程序的 Azure AD 应用程序 ID。
  
   2. 下载引用的示例架构以创建 JSON 文件。
  
   3. 为物理徽章连接器键入一个唯一的名称。

5. 在 " **检查** " 页上，查看您的设置，然后单击 " **完成** " 以创建连接器。

6. 将显示 "状态" 页，确认已创建连接器。 此页面还包含作业 ID。 您可以从此页面或连接线的飞出页面复制作业 ID。 运行脚本时需要此作业 ID。

   "状态" 页还包含指向脚本的链接。 请参阅此脚本，了解如何将 JSON 文件发布到 API 终结点。

7. 单击“ **完成** ”。

   新的连接器将显示在 " **连接器** " 选项卡上的列表中。

8. 单击刚创建的物理徽章连接器以显示弹出页面，其中包含有关连接器的属性和其他信息。

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>步骤4：运行脚本以发布包含物理徽章数据的 JSON 文件

设置物理徽章连接器的下一步是运行一个脚本，该脚本将在第) 2 步中创建的 JSON 文件 (中创建的徽章数据推送到您在步骤1中创建的 API 终结点。 我们提供了一个用于参考的示例脚本，您可以选择使用它或创建自己的脚本将 JSON 文件发布到 API 终结点。

运行该脚本后，包含物理徽章数据的 JSON 文件将被推送到 Microsoft 365 组织中，该文件可由内幕风险管理解决方案访问。 我们建议您每天发布物理徽章数据。 为此，可以自动执行从物理徽章系统每天生成 JSON 文件的过程，然后安排脚本来推送数据。

> [!NOTE]
> 可由 API 处理的 JSON 文件中的最大记录数为50000记录。

1. 请转到 [此 GitHub 网站](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) 以访问示例脚本。

2. 单击 " **原始** " 按钮以在文本视图中显示脚本

3. 复制示例脚本中的所有行，然后将它们保存到一个文本文件中。

4. 如有必要，请修改组织的示例脚本。

5. 使用文件名后缀（. ps1）将文本文件另存为 Windows PowerShell 脚本文件;例如，PhysicalBadging.ps1。

6. 在本地计算机上打开命令提示符，并转到保存该脚本的目录。

7. 运行以下命令以将 JSON 文件中的物理徽章数据推送到 Microsoft 云;例如：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   下表介绍了要与此脚本一起使用的参数及其必需的值。 您在前面步骤中获取的信息用于这些参数的值。

   | 参数 | 说明 |
   |:-------------|:--------------|
   |tenantId | 这是您在步骤1中获取的 Microsoft 365 组织的 Id。 您还可以在 Azure AD 管理中心的 **概述** 边栏上获取您的组织的 tenantId。 这用于标识你的组织。 |
   |appId | 这是您在第1步中的 Azure AD 中创建的应用程序的 Azure AD 应用程序 Id。 当脚本尝试访问 Microsoft 365 组织时，Azure AD 使用此方法进行身份验证。                    |
   |appSecret | 这是您在第1步中的 Azure AD 中创建的应用程序的 Azure AD 应用程序密码。 这也用于身份验证。                                                        |
   |jobId | 这是您在步骤3中创建的物理徽章连接器的作业 Id。 这用于将通过物理徽章连接器推送到 Microsoft 云的物理徽章数据相关联。              |
   |JsonFilePath | 这是本地计算机上的文件路径 (您要用来运行您在步骤2中创建的 JSON 文件的脚本) 。 此文件必须遵循步骤3中所述的示例架构。|
   |||

   下面的示例展示了使用每个参数的实际值的物理徽章连接器脚本的语法：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   如果上载成功，则脚本将显示 **上传成功** 消息。

   如果有多个 JSON 文件，则必须为每个文件运行脚本。

> [!NOTE]
> 您还可以选择将物理徽章数据推送到 API 终结点，而不是运行上一个脚本的方法。 例如，下面的示例展示了如何使用 Postman 将数据推送到 API 终结点。

## <a name="step-5-monitor-the-physical-badging-connector"></a>步骤5：监视物理徽章连接器

在创建物理徽章连接器并推送物理徽章数据之后，您可以在 Microsoft 365 合规性中心中查看连接器和上传状态。 如果将脚本安排为定期自动运行，还可以在上次脚本运行之后查看当前状态。

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 并单击左侧导航中的 " **数据连接器** "。

2. 单击 " **连接器** " 选项卡，然后选择物理徽章连接器以显示弹出页面。 此页面包含有关连接器的属性和信息。

   ![物理徽章连接器的状态弹出页面](..\media\PhysicalBadgingStatusFlyout.png)

3. 在 " **上次导入** " 下，单击 " **下载日志** " 链接以打开 " (" 或 "保存") 连接器的状态日志。 此日志包含有关每次脚本运行的信息，并将数据从 CSV 文件上载到 Microsoft 云。

   ![物理徽章连接器日志文件显示上载的 JSON 文件中的编号行](..\media\PhysicalBadgingConnectorLogFile.png)

   **RecordsSaved** 字段指示上传的 CSV 文件中的行数。 例如，如果 CSV 文件包含四行，则 **RecordsSaved** 字段的值为4，如果脚本成功上传了 CSV 文件中的所有行。

如果您没有在步骤4中运行该脚本，则在 " **上次导入** " 下将显示下载该脚本的链接。 您可以下载该脚本，然后按照步骤4中的步骤运行它。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (可选) 步骤6：安排脚本自动运行

若要确保组织中的最新物理徽章数据对类似于内幕风险管理解决方案的工具可用，建议您安排脚本定期（例如一天一次）自动运行。 这还要求在类似 (上将物理徽章数据更新为 JSON 文件（如果不是同一个) 计划），以便它包含有关离开组织的员工的最新信息。 目标是上载最新的物理徽章数据，以便物理徽章连接器可以将其提供给内部风险管理解决方案。

您可以在 Windows 中将 "任务计划程序" 应用程序用户每天自动运行该脚本。

1. 在本地计算机上，单击 Windows " **开始** " 按钮，然后键入 " **任务计划程序** "。

2. 单击 " **任务计划** 程序" 应用将其打开。

3. 在 " **操作** " 部分，单击 " **创建任务** "。

4. 在 " **常规** " 选项卡上，为计划的任务键入一个描述性名称;例如， **物理徽章连接器脚本** 。 您还可以添加可选的说明。

5. 在 " **安全选项** " 下，执行下列操作：

   1. 确定是仅在登录到计算机时运行脚本，还是在登录时运行脚本。

   2. 确保选中 " **以最高特权运行** " 复选框。

6. 选择 " **触发器** " 选项卡，单击 " **新建** "，然后执行以下操作：

   1. 在 " **设置** " 下，选择 " **每日** " 选项，然后选择第一次运行脚本的日期和时间。 脚本每天都在指定的时间。

   2. 在 " **高级设置** " 下，确保选中 " **启用** " 复选框。

   3. 单击“确定”  。

7. 选择 " **操作** " 选项卡，单击 " **新建** "，然后执行以下操作：

   ![为物理徽章连接器脚本创建新的计划任务的操作设置](..\media\SchedulePhysicalBadgingScript1.png)

   1. 在 " **操作** " 下拉列表中，确保选择 " **启动程序** "。

   2. 在 " **程序/脚本** " 框中，单击 " **浏览** "，然后转到以下位置并将其选中，以便在框中显示路径： C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe。

   3. 在 " **添加参数" (可选)** 框中，粘贴您在步骤4中运行的相同脚本命令。 例如，.\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9"-appId "c12823b7-b55a-4989-faba-02de41bb97c3"-appSecret "MNubVGbcQDkGCnn"-jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458"-jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. 在 " **开始 (可选)** " 框中，粘贴您在步骤4中运行的脚本的文件夹位置。 例如，C:\Users\contosoadmin\Desktop\Scripts。

   5. 单击 **"确定"** 保存新操作的设置。

8. 在 " **创建任务** " 窗口中，单击 **"确定"** 以保存计划的任务。 系统可能会提示您输入您的用户帐户凭据。

   新任务将显示在 "任务计划程序库" 中。

   ![新任务将显示在任务计划程序库中](..\media\SchedulePhysicalBadgingScript2.png)

最后一次运行脚本并显示下一次计划运行时。 您可以双击该任务以对其进行编辑。

您还可以验证符合性中心中对应物理徽章连接器的飞出页面上的上次脚本运行时间。
