---
title: 为基于精确数据匹配的敏感信息类型哈希并上传敏感信息源表
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 哈希并上载敏感信息源表，以准确匹配敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e8726b17a3f87d61c8d63be7137ec8e465a5cd9a
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568469"
---
# <a name="hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types"></a>为基于精确数据匹配的敏感信息类型哈希并上传敏感信息源表

本文演示如何对敏感信息源表进行哈希处理和上载。

## <a name="hash-and-upload-the-sensitive-information-source-table"></a>哈希和上载敏感信息源表

在此阶段中，您将：

1. 设置自定义安全组和用户帐户
2. 设置 EDM Upload代理工具
3. 使用 EDM Upload代理工具对包含一个 salt 值的敏感信息源表进行哈希处理，然后上载它。

可使用一台计算机完成哈希创建和上传，也可以将哈希创建步骤与上传步骤分离，以实现更高的安全性。

如果想要在一台计算机上创建哈希并上传，则需要在可直接连接到 Microsoft 365 租户的计算机上执行此操作。 这需要您的清除文本敏感信息源表文件位于该计算机上进行哈希处理。

如果您不想在直接访问计算机上公开您的清除文本敏感信息源表文件，可以在位于安全位置的计算机上进行哈希操作，然后将哈希文件和 salt 文件复制到可以直接连接到 Microsoft 365 租户进行上载的计算机上。 在单独的哈希和上载方案中，需要两台计算机上的 EDMUploadAgent。

> [!IMPORTANT]
> 如果使用精确数据匹配架构和敏感信息类型向导创建架构文件，则必须下载此过程的架构（如果尚未下载）。 请参阅 [以 XML 格式导出 EDM 架构文件](sit-get-started-exact-data-match-create-schema.md#export-of-the-edm-schema-file-in-xml-format)。

> [!NOTE]
> 如果你的组织为租户级别的Microsoft 365[](customer-key-overview.md)密钥，精确数据匹配将自动使用其加密功能。 这仅适用于商业云中 E5 许可的租户。

### <a name="best-practices"></a>最佳做法

分离哈希处理和上载敏感数据的过程，以便更轻松地隔离过程中的任何问题。

进入生产后，在大多数情况下，请保持两个步骤分开。 在隔离计算机上执行哈希过程，然后将文件上载到面向 Internet 的计算机，这可确保在计算机中永远不会有由于连接到 Internet 而可能受到威胁的纯文本格式的实际数据。

### <a name="ensure-your-sensitive-data-table-doesnt-have-formatting-issues"></a>确保敏感数据表没有格式设置问题。

在哈希和上载敏感数据之前，执行搜索以验证是否存在可能导致内容分析问题的特殊字符。
您可以使用带以下语法的 EDM 上载代理验证该表的格式是否适合用于 EDM：

```powershell
EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]
```

如果工具指示列数不匹配，则可能是表中值中出现逗号或引号字符，而这些值与列分隔符混淆。 除非它们围绕整个值，否则单引号和双引号可能导致工具对单个列的起始或结束位置进行错误识别。

**如果在完整值周围找到单引号或双引号字符**：可以保留它们。

如果在值内找到单引号字符或逗号：例如，用户名 Tom O'则，或以撇号字符开头的市/县的-Citynhage，则需要修改用于生成敏感信息表的数据导出过程，以使用双引号将此类列括起来。

**如果在值** 内找到双引号字符，则最好对表使用以 Tab 分隔的格式，这种格式对此类问题不太敏感。

### <a name="prerequisites"></a>先决条件

- 向 **EDM\_DataUploaders** 安全组中添加一个 Microsoft 365 工作或学校帐户
- Windows 10 .NET Windows Server 2016 4.6.2 的虚拟机或计算机 <!--4.7.2 un comment this around 9/29-->用于运行 EDMUploadAgent
- 用于上传的计算机上应含有以下内容的目录：
  - [EDM Upload 代理](#links-to-edm-upload-agent-by-subscription-type)
  - 您的敏感项目文件.csv.tsv 或管道传输 (|) 格式， **PatientRecords.csv** 示例中的示例
  - 此过程中创建的输出哈希和 salt 文件
  - 来自 **edm .xml** 文件的数据存储名称，在本示例中为 `PatientRecords`

#### <a name="set-up-the-security-group-and-user-account"></a>设置安全组和用户帐户

1. 作为全局管理员，使用相应的 [订阅链接](sit-get-started-exact-data-match-based-sits-overview.md#portal-links-for-your-subscription)转到管理中心并 [创建安全组](/office365/admin/email/create-edit-or-delete-a-security-group)，名为 **EDM\_DataUploaders**。

2. 将一个或多个用户添加到 **EDM\_DataUploaders** 安全组。 （这些用户将管理敏感信息的数据库。）

### <a name="hash-and-upload-from-one-computer"></a>从一台计算机上创建哈希并上传

此计算机必须对你的 Microsoft 365 租户拥有直接访问权限。

> [!NOTE]
> 在开始此过程之前，请确保你是 **EDM\_DataUploaders** 安全组的成员。

> [!TIP]
>（可选）您可以针对敏感信息源表文件运行验证，以在上载之前通过运行：
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> 有关支持的所有参数EdmUploadAgent.exe运行
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>按订阅类型链接到 EDM 上传代理

- [商用 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 商业客户应使用此文件
- [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 这是专为高安全性政府云订阅者提供的
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 这是专为美国国防部云客户提供的

1. 创建 EDMUploadAgent 要使用的工作目录。 例如，**C:\EDM\Data**。 将 **PatientRecords .csv** 文件放入该目录中。

2. 下载并将适合你的订阅的 [EDM 上传代理](#links-to-edm-upload-agent-by-subscription-type)安装到步骤 1 创建的目录中。

   > [!NOTE]
   > 上述链接中的 EDMUploadAgent 已更新，可自动将随机混淆值添加到哈希数据。 或者，你可以提供自己的随机混淆值。 使用此版本后，你将不能使用 EDMUploadAgent 的先前版本。
   >
   > 每天只能使用 EDMUploadAgent 上传数据到任何给定的数据存储空间两次。

3. 授权 EDM Upload代理，以管理员角色打开命令提示符窗口，切换到 **C：\EDM\Data** 目录，然后运行以下命令：

   `EdmUploadAgent.exe /Authorize`

   > [!IMPORTANT]
   > 必须从安装 **EdmUploadAgent** 的文件夹运行它，并指示数据文件的完整路径。

4. 使用添加到 EDM_DataUploaders 安全组的 Microsoft 365 工作或学校帐户登录。 将从用户帐户提取你的租户信息以建立连接。

   可选：如果使用精确数据匹配架构和敏感信息类型向导创建架构，则必须下载它以用于此过程（如果尚未下载）。 在命令提示符窗口中运行此命令：

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. 若要为敏感数据创建哈希并上传，请在命令提示符窗口中运行以下命令：

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"] /AllowedBadLinesPercentage [value]
   ```

   > [!NOTE]
   > 敏感数据文件的默认格式是逗号分隔的值。 可以通过使用 /ColumnSeparator 参数指示"{Tab}"选项来指定以制表符分隔的文件，或者通过指示"|"选项来指定管道分隔的文件。
   >
   > 例如：`EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5`

   如果您的敏感信息表包含一些格式不正确的值，但您希望在忽略无效行的同时导入剩余数据，可以在命令中使用 */AllowedBadLinesPercentage* 参数。 上面的示例指定 5% 阈值。 这意味着，即使多达 5% 的行无效，该工具也将哈希并上载敏感信息表。

   此命令将自动将随机生成的 salt 值添加到哈希中，以增强安全性。 或者，如果你想要使用自己的随机混淆值，请将 **/Salt \<saltvalue\>** 值添加到命令中。 该值的长度必须为 64 个字符，并且只能包含 a-z 的字符和 0-9 的数字。

6. 运行以下命令，检查“上传”状态：

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   例如：`EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords`

   在 **ProcessingInProgress** 中查找状态。 每隔几分钟再次检查，直到状态更改为“**已完成**”。 在状态为已完成后，即可使用 EDM 数据。 根据您的敏感信息源表文件的大小，这可能需要几分钟到几个小时。

> [!TIP]
> 如果要在上载的敏感数据可供使用后收到通知，请按照创建准确数据匹配活动的通知 [中的过程操作](sit-edm-notifications-activities.md#create-notifications-for-exact-data-match-activities)。

### <a name="separate-hash-and-upload"></a>将哈希与上传分开操作

在处于安全环境中的计算机上执行哈希。 必须在两台计算机上安装 **EDMUploadAgent** 。

可选：如果使用精确数据匹配架构和敏感信息类型向导创建架构，并且尚未下载架构，在命令提示符窗口中运行以下命令以下载 XML 格式的文件：

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. 在安全环境中的计算机上，在命令提示符窗口中运行以下命令：

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /AllowedBadLinesPercentage [value]
   ```

   例如：

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5
   ```

   > [!NOTE]
   > 敏感数据文件的默认格式是逗号分隔的值。 可以通过使用 /ColumnSeparator 参数指示"{Tab}"选项来指定以制表符分隔的文件，或者通过指示"|"选项来指定管道分隔的文件。

   如果没有指定“**/Salt \<saltvalue\>**”选项，这将会输出具有以下扩展名的哈希文件和随机混淆值文件：

   - .EdmHash
   - .EdmSalt

2. 以安全的方式将这些文件复制到计算机，以将敏感信息源表文件 (PatientRecords) 租户。

3. 授权 EDM Upload代理，以管理员角色打开命令提示符窗口，切换到 **C：\EDM\Data** 目录，然后运行以下命令：

   ```dos
   EdmUploadAgent.exe /Authorize
   ```

   > [!IMPORTANT]
   > 必须从安装 **EdmUploadAgent** 的文件夹运行它，并指示数据文件的完整路径。

4. 使用添加到 EDM_DataUploaders 安全组的 Microsoft 365 工作或学校帐户登录。 将从用户帐户提取你的租户信息以建立连接。

5. 若要上传哈希数据，请在 Windows 命令提示符中运行以下命令：

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\ /ColumnSeparator ["{Tab}"|"|"]
   ```

   例如：

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\**PatientRecords.EdmHash**
   ```

6. 若要验证是否已上传敏感数据，请在“命令提示符”窗口中运行以下命令：

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```

   你将看到数据存储区列表以及上次更新时间。

7. 如果要查看所有数据上载到特定存储，在 Windows 命令提示符中运行以下命令，以查看所有数据存储的列表以及更新时间：

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```

## <a name="next-step"></a>后续步骤

- [创建基于精确数据匹配的敏感信息类型/规则包](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package)
