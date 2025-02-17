---
title: 在 Linux 上设置Microsoft Defender for Endpoint首选项
ms.reviewer: ''
description: 介绍如何在企业Microsoft Defender for Endpoint Linux 上配置部署。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 安装， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 19e107e500f3c90f00edb81d67e0da05b5e579d4
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634176"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上设置Microsoft Defender for Endpoint首选项

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

> [!IMPORTANT]
> 本主题包含有关如何在企业环境中为 Linux 上的 Defender for Endpoint 设置首选项的说明。 如果你有兴趣从命令行在设备上配置产品，请参阅 [资源](linux-resources.md#configure-from-the-command-line)。

在企业环境中，Linux 上的 Defender for Endpoint 可通过配置文件进行管理。 此配置文件从你选择的管理工具部署。 企业管理的首选项优先于在设备上本地设置的首选项。 换句话说，企业中的用户不能更改通过此配置文件设置的首选项。

本文介绍此配置文件 (包括可用于开始使用配置文件的建议) 以及如何部署配置文件的说明。

## <a name="configuration-profile-structure"></a>配置文件结构

配置文件是一个 .json 文件，它由键 (标识的条目表示首选项) 的名称，后跟一个值，具体取决于首选项的性质。 值可以是简单的（如数字值）或复杂值（如嵌套的首选项列表）。

通常，你将使用配置 ```mdatp_managed.json``` 管理工具在 位置推送名称为 的文件 ```/etc/opt/microsoft/mdatp/managed/```。

配置文件的顶层包括产品范围的首选项和产品子区域条目，下一节将对此进行详细介绍。

### <a name="antivirus-engine-preferences"></a>防病毒引擎首选项

配置文件 *的 antivirusEngine* 部分用于管理产品的防病毒组件的首选项。

<br>

****

|说明|值|
|---|---|
|**注册表项**|antivirusEngine|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

#### <a name="enforcement-level-for-antivirus-engine"></a>防病毒引擎的强制级别

指定防病毒引擎的强制首选项。 设置强制级别有三个值：

- 实时 (`real_time`) ：实时保护 (启用时扫描) 文件。
- 按需 (`on_demand`) ：仅按需扫描文件。 在此：
  - 实时保护已关闭。
- 被动 (`passive`) ：在被动模式下运行防病毒引擎。 在此：
  - 实时保护已关闭。
  - 按需扫描已打开。
  - 自动威胁修正已关闭。
  - 安全智能更新已打开。

<br>

****

|说明|值|
|---|---|
|**注册表项**|enforcementLevel|
|**数据类型**|String|
|**可能的值**|real_time (默认)  <p> on_demand <p> 被动|
|**Comments**|适用于终结点版本 101.10.72 或更高版本的 Defender 中可用。|
|


#### <a name="enabledisable-behavior-monitoring"></a>启用/禁用行为监视 

确定是否在设备上启用行为监视和阻止功能。 若要提高安全保护的有效性，我们建议保持启用此功能。

<br>

****

|说明|值|
|---|---|
|**注册表项**|behaviorMonitoring|
|**数据类型**|String|
|**可能的值**|已禁用 (默认)  <p> 已启用 (默认) |
|**Comments**|适用于终结点版本 101.45.00 或更高版本的 Defender 中可用。|
  
#### <a name="run-a-scan-after-definitions-are-updated"></a>更新定义后运行扫描

指定是否在设备上下载新的安全智能更新后启动进程扫描。 启用此设置将在设备的运行进程上触发防病毒扫描。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanAfterDefinitionUpdate|
|**数据类型**|Boolean|
|**可能的值**|true (默认值)  <p> false|
|**Comments**|适用于终结点版本 101.45.00 或更高版本的 Defender 中可用。|
|

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>扫描存档 (按需防病毒扫描仅扫描) 

指定在按需防病毒扫描过程中是否扫描存档。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanArchives|
|**数据类型**|Boolean|
|**可能的值**|true (默认值)  <p> false|
|**Comments**|可用于 Microsoft Defender for Endpoint 101.45.00 或更高版本。|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>按需扫描的并行度

指定按需扫描的并行度。 这与用于执行扫描并影响 CPU 使用率的线程数以及按需扫描的持续时间相对应。

<br>

****

|说明|值|
|---|---|
|**注册表项**|maximumOnDemandScanThreads|
|**数据类型**|整数|
|**可能的值**|2 (默认值) 。 允许的值是介于 1 和 64 之间的整数。|
|**Comments**|可用于 Microsoft Defender for Endpoint 101.45.00 或更高版本。|
|||
  

#### <a name="exclusion-merge-policy"></a>排除合并策略

指定排除项的合并策略。 它可以是管理员定义的排除项 `merge` `admin_only` 和用户定义的排除项 () 管理员定义的排除项 () 。 此设置可用于限制本地用户定义自己的排除项。

<br>

****

|说明|值|
|---|---|
|**注册表项**|exclusionsMergePolicy|
|**数据类型**|String|
|**可能的值**|合并 (默认)  <p> admin_only|
|**Comments**|适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。|
|

#### <a name="scan-exclusions"></a>扫描排除项

从扫描中排除的实体。 排除项可以通过完整路径、扩展名或文件名指定。
 (排除项指定为项目数组，则管理员可以按任意顺序指定所需数量的元素。) 

<br>

****

|说明|值|
|---|---|
|**注册表项**|排除项|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

##### <a name="type-of-exclusion"></a>排除类型

指定从扫描中排除的内容的类型。

<br>

****

|说明|值|
|---|---|
|**注册表项**|$type|
|**数据类型**|String|
|**可能的值**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|

##### <a name="path-to-excluded-content"></a>排除内容的路径

用于按完整文件路径从扫描中排除内容。

<br>

****

|说明|值|
|---|---|
|**注册表项**|路径|
|**数据类型**|String|
|**可能的值**|有效路径|
|**Comments**|仅在 *排除$type**时适用*|
|

##### <a name="path-type-file--directory"></a>文件 (目录的路径) 

指示 *path 属性* 是否引用文件或目录。

<br>

****

|说明|值|
|---|---|
|**注册表项**|isDirectory|
|**数据类型**|Boolean|
|**可能的值**|false（默认值） <p> true|
|**Comments**|仅在 *排除$type**时适用*|
|

##### <a name="file-extension-excluded-from-the-scan"></a>从扫描中排除的文件扩展名

用于按文件扩展名从扫描中排除内容。

<br>

****

|说明|值|
|---|---|
|**注册表项**|extension|
|**数据类型**|String|
|**可能的值**|有效的文件扩展名|
|**Comments**|仅在 *排除$type* *FileExtension 时适用*|
|

##### <a name="process-excluded-from-the-scan"></a>从扫描中排除的进程*

指定从扫描中排除所有文件活动的进程。 可以通过进程的名称或名称指定 (例如 `cat` ，) 或完整 (例如， `/bin/cat`) 。

<br>

****

|说明|值|
|---|---|
|**注册表项**|name|
|**数据类型**|String|
|**可能的值**|任何字符串|
|**Comments**|仅在排除 *$type* *FileName 时适用*|
|

#### <a name="allowed-threats"></a>允许的威胁

威胁列表 (名称) 产品未阻止但允许运行的威胁列表。

<br>

****

|说明|值|
|---|---|
|**注册表项**|allowedThreats|
|**数据类型**|字符串数组|
|

#### <a name="disallowed-threat-actions"></a>不允许的威胁操作

限制设备的本地用户在检测到威胁时可采取的操作。 此列表中包含的操作不会显示在用户界面中。

<br>

****

|说明|值|
|---|---|
|**注册表项**|disallowedThreatActions|
|**数据类型**|字符串数组|
|**可能的值**|允许 (限制用户允许威胁)  <p> restore (限制用户从隔离网站还原) |
|**Comments**|适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。|
|

#### <a name="threat-type-settings"></a>威胁类型设置

防病毒 *引擎中的 threatTypeSettings* 首选项用于控制产品如何处理某些威胁类型。

<br>

****

|说明|值|
|---|---|
|**注册表项**|threatTypeSettings|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

##### <a name="threat-type"></a>威胁类型

配置其行为的威胁类型。

<br>

****

|说明|值|
|---|---|
|**注册表项**|注册表项|
|**数据类型**|String|
|**可能的值**|potentially_unwanted_application <p> archive_bomb|
|

##### <a name="action-to-take"></a>要采取的措施

遇到上一节中指定的类型的威胁时要采取的操作。 可以是：

- **审核**：设备不受此类型威胁的保护，但会记录关于威胁的条目。
- **阻止**：设备受到此类型威胁的保护，并且你将在安全控制台中收到通知。
- **关闭**：设备不受此类威胁的保护，并且不会记录任何内容。

<br>

****

|说明|值|
|---|---|
|**注册表项**|值|
|**数据类型**|String|
|**可能的值**|审核 (默认)  <p> block <p> 关|
|

#### <a name="threat-type-settings-merge-policy"></a>威胁类型设置合并策略

指定威胁类型设置的合并策略。 它可以是管理员定义的 `merge` `admin_only` 设置和用户定义的设置 () 管理员定义的设置 () 。 此设置可用于限制本地用户为不同的威胁类型定义自己的设置。

<br>

****

|说明|值|
|---|---|
|**注册表项**|threatTypeSettingsMergePolicy|
|**数据类型**|String|
|**可能的值**|合并 (默认)  <p> admin_only|
|**Comments**|适用于终结点版本 100.83.73 或更高版本的 Defender 中可用。|
|

#### <a name="antivirus-scan-history-retention-in-days"></a>防病毒扫描历史记录保留 (天数) 

指定结果在设备的扫描历史记录中保留的天数。 旧扫描结果将从历史记录中删除。 也从磁盘中删除的旧隔离文件。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanResultsRetentionDays|
|**数据类型**|String|
|**可能的值**|90 (默认值) 。 允许的值从 1 天到 180 天。|
|**Comments**|适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>防病毒扫描历史记录中的最大项目数

指定在扫描历史记录中保留的最大条目数。 条目包括过去执行的所有按需扫描以及所有防病毒检测。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanHistoryMaximumItems|
|**数据类型**|String|
|**可能的值**|10000 (默认值) 。 允许的值从 5000 个项目到 15000 个项目。|
|**Comments**|适用于终结点版本 101.04.76 或更高版本的 Defender 中可用。|
|

### <a name="cloud-delivered-protection-preferences"></a>云提供的保护首选项

配置文件 *中的 cloudService* 条目用于配置产品的云驱动保护功能。

<br>

****

|说明|值|
|---|---|
|**注册表项**|cloudService|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

#### <a name="enable--disable-cloud-delivered-protection"></a>启用/禁用云提供的保护

确定是否在设备上启用云保护。 若要提高服务的安全性，我们建议保持启用此功能。

<br>

****

|说明|值|
|---|---|
|**注册表项**|enabled|
|**数据类型**|Boolean|
|**可能的值**|true (默认值)  <p> false|
|

#### <a name="diagnostic-collection-level"></a>诊断集合级别

诊断数据用于使 Defender for Endpoint 保持安全和最新，检测、诊断和修复问题，并改进产品。 此设置确定产品发送给 Microsoft 的诊断级别。

<br>

****

|说明|值|
|---|---|
|**注册表项**|diagnosticLevel|
|**数据类型**|String|
|**可能的值**|可选 (默认)  <p> 必需|
|

#### <a name="enable--disable-automatic-sample-submissions"></a>启用/禁用自动示例提交

确定是否将 (可能包含威胁的可疑) 发送给 Microsoft。 有三个级别用于控制示例提交：

- **无**：不会向 Microsoft 提交任何可疑示例。
- **保险箱**：仅自动提交不包含个人身份信息或个人身份 (的) 样本。 这是此设置的默认值。
- **全部**：所有可疑示例都提交到 Microsoft。

<br>

****

|说明|值|
|---|---|
|**注册表项**|automaticSampleSubmissionConsent|
|**数据类型**|String|
|**可能的值**|无 <p> 安全 (默认)  <p> all|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>启用/禁用自动安全智能更新

确定是否自动安装安全智能更新：

<br>

****

|说明|值|
|---|---|
|**注册表项**|automaticDefinitionUpdateEnabled|
|**数据类型**|Boolean|
|**可能的值**|true (默认值)  <p> false|
|

## <a name="recommended-configuration-profile"></a>建议的配置文件

若要开始，我们建议你的企业采用以下配置文件，以利用 Defender for Endpoint 提供的所有保护功能。

以下配置文件将：

- 启用实时保护 (RTP) 
- 指定如何处理以下威胁类型：
  - **阻止 PUA (可能不需要)** 的应用程序
  - **存档 (** 高压缩率的文件) 审核到产品日志
- 启用自动安全智能更新
- 启用云保护
- 启用级别的自动示例 `safe` 提交
- 启用行为监视

### <a name="sample-profile"></a>示例配置文件

```JSON
{
   "antivirusEngine":{
      "behaviorMonitoring":"enabled",
      "enforcementLevel":"real_time",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy": "<EXAMPLE DO NOT USE> http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>完整配置文件示例

以下配置文件包含本文档中所述的所有设置的条目，可用于更高级的方案，您希望对产品进行更多控制。

### <a name="full-profile"></a>完整个人资料

```JSON
{
   "antivirusEngine":{
      "behaviorMonitoring":"enabled",
      "enforcementLevel":"real_time",
      "scanAfterDefinitionUpdate":true,
      "scanArchives":true,
      "maximumOnDemandScanThreads":2,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "<EXAMPLE DO NOT USE>EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "<EXAMPLE DO NOT USE> http://proxy.server:port/"
   }
}
```

## <a name="add-tag-or-group-id-to-the-configuration-profile"></a>将标记或组 ID 添加到配置文件

首次运行 `mdatp health` 命令时，标记和组 ID 的值将为空。 若要将标记或组 ID 添加到文件 `mdatp_managed.json` ，请按照以下步骤操作：
  
  1. 从路径 中打开配置文件 `/etc/opt/microsoft/mdatp/managed/mdatp_managed.json`。
  2. 转到阻止所在的文件 `cloudService` 底部。
  3. 添加所需的标记或组 ID，如以下示例所示，位于 右大括号的 末尾 `cloudService`。

  ```JSON
    },
    "cloudService": {
      "enabled": true,
      "diagnosticLevel": "optional",
      "automaticSampleSubmissionConsent": "safe",
      "automaticDefinitionUpdateEnabled": true,
      "proxy": "http://proxy.server:port/"
  },
  "edr": {
    "groupIds":"GroupIdExample",
    "tags": [
              {
              "key": "GROUP",
              "value": "Tag"
              }
            ]
        }
  }
  ```

  > [!NOTE]
  > 不要忘记在块末尾的右大括号后面 `cloudService` 添加逗号。 此外，请确保添加 Tag 或组 ID 块后有两个右大括号 (请参阅上面的示例) 。 目前，标记唯一支持的键名称是 `GROUP`。 
  
## <a name="configuration-profile-validation"></a>配置文件验证

配置文件必须是有效的 JSON 格式文件。 有许多工具可用于验证这一点。 例如，如果你已安装 `python` 在设备上：

```bash
python -m json.tool mdatp_managed.json
```

如果 JSON 格式良好，则上述命令会输出回终端，并返回 的退出代码 `0`。 否则，将显示描述该问题的错误，并且该命令将返回 的退出代码 `1`。

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>验证 mdatp_managed.json 文件是否正常工作

若要验证 /etc/opt/microsoft/mdatp/managed/mdatp_managed.json 是否正常工作，应在这些设置旁边看到"[托管]"：

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> 若要使 mdatp_managed.json 生效，无需 `mdatp` 重新启动 deamon。

## <a name="configuration-profile-deployment"></a>配置文件部署

为企业生成配置文件后，可以通过企业使用的管理工具进行部署。 Linux 上的 Defender for Endpoint 从 */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* 文件读取托管配置。
