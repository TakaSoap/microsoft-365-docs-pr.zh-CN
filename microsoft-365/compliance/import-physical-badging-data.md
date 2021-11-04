---
title: 设置连接器以导入物理保护数据
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
description: 管理员可以设置数据连接器，以将数据从组织的物理密码系统导入Microsoft 365。 这允许你在内部风险管理策略中使用此数据，以帮助你检测特定用户对可能向组织指示可能的内部威胁的物理建筑物的访问。
ms.openlocfilehash: cb568836c0f763682cbad5524b41d19b034d02dc
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756159"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>设置连接器以在预览版中导入 () 

可以在 Microsoft 365 合规中心 中设置数据连接器以导入物理保护数据，例如员工的原始物理访问事件或由组织的密码系统生成的任何物理访问警报。 物理访问点的示例包括建筑物的入口或服务器会议室或数据中心的入口。 内部风险管理解决方案可以使用物理Microsoft 365，以帮助保护组织免受组织内部[](insider-risk-management.md)恶意活动或数据盗窃的攻击。

设置物理保护连接器包括以下任务：

- 在应用中Azure Active Directory (Azure AD) ，以访问接受包含物理保护数据的 JSON 有效负载的 API 终结点。

- 使用由物理保护数据连接器定义的架构创建 JSON 有效负载。

- 在服务器中创建物理Microsoft 365 合规中心。

- 运行脚本以将物理保护代码数据推送到 API 终结点。

- （可选）将脚本安排为自动运行以导入当前物理保护数据。

## <a name="before-you-set-up-the-connector"></a>设置连接器之前

- 必须在步骤 3 中为在步骤 3 中创建物理密码连接器的用户分配邮箱导入导出Exchange Online。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 可以将"邮箱导入导出"角色添加到组织中"组织管理"角色Exchange Online。 也可以创建新的角色组，分配"邮箱导入导出"角色，然后将相应的用户添加为成员。 有关详细信息，请参阅"管理角色[](/Exchange/permissions-exo/role-groups#create-role-groups)组中的角色组[](/Exchange/permissions-exo/role-groups#modify-role-groups)"一文的"创建角色组"或"修改角色Exchange Online"。

- 您需要确定如何每天从组织的物理密码系统 (检索或导出数据) 并创建步骤 2 中所述的 JSON 文件。 在步骤 4 中运行的脚本将 JSON 文件的数据推送到 API 终结点。

- 在步骤 4 中运行的示例脚本将 JSON 文件的物理保护数据推送到连接器 API，以便内部风险管理解决方案可以使用该数据。 本示例脚本在任何 Microsoft 标准支持计划或服务下都不受支持。 示例脚本“原样”提供，不提供任何形式的保证。 Microsoft 进一步拒绝所有默示保证，包括但不限于针对特定用途的适销性或适用性的任何默示保证。 由于示例脚本及文档的使用或性能所引起的全部风险均由你承担。 在任何情况下，对于由于使用或者无法使用示例脚本或文档所引起的任何损失（包括但不限于商业利润损失、业务中断、商业信息丢失或者其他经济损失），Microsoft、其作者或者参与创建、制作或交付脚本的任何人概不负责，即使 Microsoft 已被告知可能会出现此类损失。

- 此连接器可用于美国政府GCC中Microsoft 365环境中。 第三方应用程序和服务可能涉及在 Microsoft 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此 Microsoft 365 合规性和数据保护承诺未涵盖这些数据。 Microsoft 不表示使用此产品连接到第三方应用程序意味着这些第三方应用程序符合 FEDRAMP。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步骤 1：在 Azure Active Directory

第一步是在应用程序创建和注册Azure Active Directory (Azure AD) 。 该应用将对应于在步骤 3 中创建的物理保护连接器。 创建此应用将Azure AD验证包含物理保护数据的 JSON 有效负载的推送请求。 创建此应用程序Azure AD，请务必保存以下信息。 这些值将在稍后的步骤中使用。

- Azure AD应用程序 ID (也称为 *应用程序 ID* 或 *客户端 ID*) 

- Azure AD应用程序密码 (也称为 *客户端密码)*

- 租户 ID (*也称为目录 ID*) 

有关在应用程序中创建应用的分步Azure AD，请参阅使用 Microsoft 标识平台 注册[应用程序](/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>步骤 2：准备包含物理保护数据的 JSON 文件

下一步是创建一个 JSON 文件，其中包含有关员工物理访问数据的信息。 如开始之前部分所述，你需要确定如何从组织的物理保护系统生成此 JSON 文件。

JSON 文件必须符合连接器所需的架构定义。 以下是 JSON 文件所需的架构属性的说明：

|属性|说明|数据类型|
|---|---|---|
|UserID|员工可以在系统中具有多个数字标识。 输入需要使源Azure AD ID 已解析。|UPN 或电子邮件地址|
|AssetId|物理资产或物理访问点的参考 ID。|字母数字字符串|
|AssetName|物理资产或物理访问点的友好名称。|字母数字字符串|
|EventTime|访问时间戳。|日期和时间（UTC 格式）|
|AccessStatus|或 `Success` 的值 `Failed`|String|
|||

下面是符合所需架构的 JSON 文件示例：

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

还可以在步骤 3 中创建物理保护连接器时，从向导下载 JSON 文件的以下架构定义。

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

## <a name="step-3-create-the-physical-badging-connector"></a>步骤 3：创建物理保护连接器

下一步是在服务器中创建一个Microsoft 365 合规中心。 在步骤 4 中运行脚本后，将在步骤 3 中创建的 JSON 文件进行处理并推送到在步骤 1 中配置的 API 终结点。 在此步骤中，请确保复制创建连接器时生成的 JobId。 运行脚本时，将使用 JobId。

1. 转到"Microsoft 365 合规中心"，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**数据连接器"。**</a>

2. 在"**数据连接器"页上** 的"**物理保护"下，** 单击"查看 **"。**

3. 在"**物理保护"页上**，单击"**添加连接器"。**

4. 在"**身份验证凭据"** 页上，执行以下操作，然后单击"下一步 **"：**

   1. 键入或粘贴Azure AD 1 中创建的 Azure 应用的应用程序 ID。

   2. 下载示例架构，以参考创建 JSON 文件。

   3. 键入物理保护连接器的唯一名称。

5. 在" **审阅** "页上，查看设置，然后单击" **完成** "以创建连接器。

6. 将显示一个状态页，确认连接器已创建。 此页面还包含作业 ID。 可以从此页面或连接器的飞出页复制作业 ID。 运行脚本时需要此作业 ID。

   状态页还包含指向脚本的链接。 请参阅此脚本，了解如何将 JSON 文件张贴到 API 终结点。

7. 单击“**完成**”。

   新连接器显示在"连接器"选项卡 **上的** 列表中。

8. 单击刚创建的物理保护符连接器以显示该飞出页，其中包含有关该连接器的属性和其他信息。

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>步骤 4：运行脚本以 POST 包含物理保护数据的 JSON 文件

设置物理保护连接器的下一步是运行一个脚本，该脚本将在步骤 2) 中创建的 JSON 文件 (中将物理保护数据推送到在步骤 1 中创建的 API 终结点。 我们提供示例脚本供你参考，你可以选择使用它，也可以创建自己的脚本将 JSON 文件张贴到 API 终结点。

运行脚本后，包含物理保护数据的 JSON 文件将推送到 Microsoft 365 组织，内部风险管理解决方案可在该组织中访问该文件。 我们建议你每天发布物理保护数据。 为此，可以自动执行每天从物理保护系统生成 JSON 文件的过程，然后计划脚本以推送数据。

> [!NOTE]
> API 可以处理的 JSON 文件中的最大记录数为 50，000 条记录。

1. 转到[此GitHub网站](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1)以访问示例脚本。

2. 单击" **原始** "按钮以在文本视图中显示脚本

3. 复制示例脚本中所有的行，然后将它们保存到文本文件中。

4. 如有必要，修改组织的示例脚本。

5. 使用文件名后缀将文本文件另存为Windows PowerShell脚本.ps1;例如，PhysicalBadging.ps1。

6. 在本地计算机上打开命令提示符，然后转到保存脚本的目录。

7. 运行以下命令，将 JSON 文件的物理保护数据推送到 Microsoft 云;例如：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   下表介绍了要用于此脚本的参数及其所需值。 在之前步骤中获取的信息用于这些参数的值中。

   |参数|说明|
   |---|---|
   |tenantId|这是在步骤 1 Microsoft 365获得的组织 ID。 还可以在管理中心的"概述"边栏选项卡上获取Azure AD的 tenantId。 这用于标识您的组织。|
   |appId|这是Azure AD步骤 1 中创建的应用的应用程序Azure AD ID。 当脚本尝试Azure AD组织时，此参数Microsoft 365进行身份验证。|
   |appSecret|这是Azure AD步骤 1 中创建的应用的Azure AD密码。 这还用于身份验证。|
   |jobId|这是在步骤 3 中创建的物理保护连接器的作业 ID。 这用于将推送到 Microsoft 云的物理保护数据与物理保护连接器关联。|
   |JsonFilePath|这是本地计算机的文件路径 (您用于为步骤 2 中创建的 JSON 文件运行脚本) 的文件路径。 此文件必须遵循步骤 3 中所述的示例架构。|
   |||

   下面是将实际值用于每个参数的物理保护连接器脚本的语法示例：

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   如果上传成功，脚本将显示Upload **成功** 消息。

   如果你有多个 JSON 文件，必须运行每个文件的脚本。

> [!NOTE]
> 还可以选择通过运行前一个脚本的方法，将物理保护数据推送到 API 终结点。 例如，下面是使用 Postman 将数据推送到 API 终结点的示例。

## <a name="step-5-monitor-the-physical-badging-connector"></a>步骤 5：监视物理保护连接器

创建物理保护连接器并推送物理保护数据后，可以查看该连接器，并上传Microsoft 365 合规中心。 如果安排脚本定期自动运行，还可以在上次运行脚本后查看当前状态。

1. 转到"Microsoft 365 合规中心"，然后选择"<a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**数据连接器"。**</a>

2. 单击 **"连接器"** 选项卡，然后选择物理保护符连接器以显示飞出页。 此页面包含有关连接器的属性和信息。

   ![物理保护连接器的状态飞出页。](..\media\PhysicalBadgingStatusFlyout.png)

3. 在 **"上次导入**"下， **单击"下载** 日志"链接 (或) 连接器的状态日志。 此日志包含有关脚本每次运行以及将数据从 CSV 文件上载到 Microsoft 云时的信息。

   ![物理保护连接器日志文件 JSON 文件中上传的行数。](..\media\PhysicalBadgingConnectorLogFile.png)

   **RecordsSaved** 字段指示 CSV 文件中上载的行数。 例如，如果 CSV 文件包含四行，则 **RecordsSaved** 字段的值为 4（如果脚本成功上载 CSV 文件的所有行）。

如果尚未在步骤 4 中运行脚本，则"上次导入"下将显示用于下载脚本 **的链接**。 可以下载脚本，然后按照步骤 4 中的步骤运行它。

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a> (可选) 步骤 6：计划脚本自动运行

若要确保组织的最新物理保护数据可用于内部风险管理解决方案等工具，建议安排脚本定期自动运行，如每天运行一次。 这还要求你将物理保护数据更新为类似 (（如果不是同一) 计划）上的 JSON 文件，以便其中包含有关离开组织的员工的最新信息。 目标是上载最新的物理保护数据，以便物理保护连接器能够将其提供给内部风险管理解决方案。

You can user the Task Scheduler app in Windows to automatically run the script every day.

1. 在本地计算机上，单击 **"Windows"** 按钮，然后键入 **"任务计划程序"。**

2. 单击任务 **计划程序** 应用以打开它。

3. 在"**操作"部分**，单击"**创建任务"。**

4. 在" **常规"** 选项卡上，键入计划任务的描述性名称;例如，物理 **保护连接器脚本**。 还可以添加可选说明。

5. 在 **"安全选项**"下，执行以下操作：

   1. 确定是仅在您登录到计算机时运行脚本，还是在您登录时运行该脚本。

   2. 确保选中 **了"使用最高权限** 运行"复选框。

6. 选择 **"触发器"** 选项卡，单击 **"新建**"，然后执行以下操作：

   1. 在 **设置"** 下，选择"**每天**"选项，然后选择首次运行脚本的日期和时间。 脚本将每天在同一指定时间运行。

   2. 在 **"高级设置**"下，确保 **选中"已启用** "复选框。

   3. 单击“确定”。

7. 选择" **操作"** 选项卡，单击 **"新建**"，然后执行以下操作：

   ![操作设置，用于为物理保护连接器脚本创建新的计划任务。](..\media\SchedulePhysicalBadgingScript1.png)

   1. 在 **"操作** "下拉列表中，确保已 **选择"启动程序** "。

   2. 在"**程序/脚本**"框中，单击"浏览"，然后转到以下位置并选择它，以便路径显示在框中：C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe。

   3. 在" **添加 (可选) "** 框中，粘贴在步骤 4 中运行相同的脚本命令。 例如， .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. 在 **" (可选**) "框中，粘贴在步骤 4 中运行脚本的文件夹位置。 例如，C：\Users\contosoadmin\Desktop\Scripts。

   5. 单击 **"** 确定"保存新操作的设置。

8. 在" **创建任务"** 窗口中，单击" **确定** "保存计划任务。 系统可能会提示您输入用户帐户凭据。

   新任务将显示在任务计划程序库中。

   ![新任务将显示在任务计划程序库中。](..\media\SchedulePhysicalBadgingScript2.png)

显示脚本上次运行的时间和计划运行的下一次。 可以双击任务进行编辑。

还可以验证脚本上次在合规中心中相应物理保护连接器的飞出页面上运行的时间。
