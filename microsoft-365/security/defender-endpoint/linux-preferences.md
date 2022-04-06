---
title: 在 Linux 上设置Microsoft Defender for Endpoint首选项
ms.reviewer: ''
description: 介绍如何在企业中配置 Linux 上的Microsoft Defender for Endpoint。
keywords: microsoft， defender， Microsoft Defender for Endpoint， linux， 安装， 部署， 卸载， 木偶， ansible， linux， redhat， ubuntu， debian， sles， suse， centos
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
ms.openlocfilehash: 1a579944fa0f7578fa2afcf66472cebbb6f07037
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663767"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上设置Microsoft Defender for Endpoint首选项

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

> [!IMPORTANT]
> 本主题包含有关如何在企业环境中为 Linux 上的 Defender for Endpoint 设置首选项的说明。 如果有兴趣从命令行在设备上配置产品，请参阅 [资源](linux-resources.md#configure-from-the-command-line)。

在企业环境中，Linux 上的 Defender for Endpoint 可以通过配置文件进行管理。 此配置文件是从所选管理工具部署的。 企业管理的首选项优先于在设备本地设置的首选项。 换句话说，企业中的用户无法更改通过此配置文件设置的首选项。

本文介绍此配置文件的结构 (包括可用于开始) 的建议配置文件以及有关如何部署配置文件的说明。

## <a name="configuration-profile-structure"></a>配置文件结构

配置文件是一个 .json 文件，由键 (标识的条目组成，该项表示首选项) 的名称，后跟一个值，该值取决于首选项的性质。 值可能很简单，例如数字值或复杂值，例如嵌套首选项列表。

通常情况下，你将使用配置管理工具推送位于该位置```/etc/opt/microsoft/mdatp/managed/```的名称```mdatp_managed.json```的文件。

配置文件的顶层包括产品范围的首选项和产品子区域的条目，这些项在下一部分中进行了更详细的说明。

### <a name="antivirus-engine-preferences"></a>防病毒引擎首选项

配置文件的 *防病毒Engine* 部分用于管理产品的防病毒组件的首选项。

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

- 实时 (`real_time`) ：在启用) 访问文件时 (扫描文件的实时保护。
- 按需 (`on_demand`) ：仅按需扫描文件。 在此示例中：
  - 实时保护已关闭。
- 被动 (`passive`) ：在被动模式下运行防病毒引擎。 在此示例中：
  - 实时保护已关闭。
  - 按需扫描已启用。
  - 自动威胁修正已关闭。
  - 安全智能更新已启用。

<br>

****

|说明|值|
|---|---|
|**注册表项**|enforcementLevel|
|**数据类型**|String|
|**可能的值**|real_time (默认)  <p> on_demand <p> 被动|
|**Comments**|在 Defender for Endpoint 版本 101.10.72 或更高版本中可用。|
|


#### <a name="enabledisable-behavior-monitoring"></a>启用/禁用行为监视 

确定是否在设备上启用行为监视和阻止功能。 为了提高安全保护的有效性，建议保持启用此功能。

<br>

****

|说明|值|
|---|---|
|**注册表项**|behaviorMonitoring|
|**数据类型**|String|
|**可能的值**|已禁用 (默认)  <p> 已启用 (默认) |
|**Comments**|在 Defender for Endpoint 版本 101.45.00 或更高版本中可用。|
  
#### <a name="run-a-scan-after-definitions-are-updated"></a>更新定义后运行扫描

指定在设备上下载新的安全智能更新后是否启动进程扫描。 启用此设置将触发对设备正在运行的进程的防病毒扫描。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanAfterDefinitionUpdate|
|**数据类型**|Boolean|
|**可能的值**|true (默认)  <p> false|
|**Comments**|在 Defender for Endpoint 版本 101.45.00 或更高版本中可用。|
|

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>仅扫描存档 (按需防病毒扫描) 

指定是否在按需防病毒扫描期间扫描存档。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanArchives|
|**数据类型**|Boolean|
|**可能的值**|true (默认)  <p> false|
|**Comments**|Microsoft Defender for Endpoint版本 101.45.00 或更高版本中提供。|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>按需扫描的并行度

指定按需扫描的并行度。 这与用于执行扫描并影响 CPU 使用情况的线程数以及按需扫描的持续时间相对应。

<br>

****

|说明|值|
|---|---|
|**注册表项**|maximumOnDemandScanThreads|
|**数据类型**|整数|
|**可能的值**|2 (默认) 。 允许的值为介于 1 和 64 之间的整数。|
|**Comments**|Microsoft Defender for Endpoint版本 101.45.00 或更高版本中提供。|
|||
  

#### <a name="exclusion-merge-policy"></a>排除合并策略

指定排除项的合并策略。 它可以是管理员定义的排除项和用户定义的排除项的组合， () `merge` 或仅管理员定义的排除项 () `admin_only` 。 此设置可用于限制本地用户定义自己的排除项。

<br>

****

|说明|值|
|---|---|
|**注册表项**|exclusionsMergePolicy|
|**数据类型**|String|
|**可能的值**|合并 (默认)  <p> admin_only|
|**Comments**|在 Defender for Endpoint 版本 100.83.73 或更高版本中可用。|
|

#### <a name="scan-exclusions"></a>扫描排除项

已从扫描中排除的实体。 排除项可以由完整路径、扩展名或文件名指定。
 (排除项指定为项数组，管理员可以根据任何顺序指定任意数量的元素。) 

<br>

****

|说明|值|
|---|---|
|**注册表项**|排除|
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

用于通过完整文件路径从扫描中排除内容。

<br>

****

|说明|值|
|---|---|
|**注册表项**|路径|
|**数据类型**|String|
|**可能的值**|有效路径|
|**Comments**|仅当 *排除$type* 时才适用 *。*|
|

##### <a name="path-type-file--directory"></a>路径类型 (文件/目录) 

指示 *路径* 属性是否引用文件或目录。

<br>

****

|说明|值|
|---|---|
|**注册表项**|isDirectory|
|**数据类型**|Boolean|
|**可能的值**|false（默认值） <p> true|
|**Comments**|仅当 *排除$type* 时才适用 *。*|
|

##### <a name="file-extension-excluded-from-the-scan"></a>从扫描中排除的文件扩展名

用于按文件扩展名从扫描中排除内容。

<br>

****

|说明|值|
|---|---|
|**注册表项**|扩展|
|**数据类型**|String|
|**可能的值**|有效文件扩展名|
|**Comments**|仅当 *排除$type* 时才适用 *FileExtension*|
|

##### <a name="process-excluded-from-the-scan"></a>从扫描中排除的过程*

指定从扫描中排除所有文件活动的过程。 该进程可以通过其名称 (指定， `cat` 例如，) 或完整路径 (，例如 `/bin/cat`) 。

<br>

****

|说明|值|
|---|---|
|**注册表项**|name|
|**数据类型**|String|
|**可能的值**|任何字符串|
|**Comments**|仅当 *排除$type* 时才适用 *FileName*|
|

#### <a name="allowed-threats"></a>允许的威胁

 (由其名称标识的威胁列表) ，这些威胁不会被产品阻止，而是允许运行。

<br>

****

|说明|值|
|---|---|
|**注册表项**|allowedThreats|
|**数据类型**|字符串数组|
|

#### <a name="disallowed-threat-actions"></a>不允许的威胁操作

限制检测到威胁时设备的本地用户可以执行的操作。 此列表中包含的操作不会显示在用户界面中。

<br>

****

|说明|值|
|---|---|
|**注册表项**|disallowedThreatActions|
|**数据类型**|字符串数组|
|**可能的值**|允许 (限制用户允许威胁)  <p> 还原 (限制用户从隔离) 还原威胁|
|**Comments**|在 Defender for Endpoint 版本 100.83.73 或更高版本中可用。|
|

#### <a name="threat-type-settings"></a>威胁类型设置

防病毒引擎中的 *threatTypeSettings* 首选项用于控制某些威胁类型的处理方式。

<br>

****

|说明|值|
|---|---|
|**注册表项**|threatTypeSettings|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

##### <a name="threat-type"></a>威胁类型

为其配置行为的威胁类型。

<br>

****

|说明|值|
|---|---|
|**注册表项**|注册表项|
|**数据类型**|String|
|**可能的值**|potentially_unwanted_application <p> archive_bomb|
|

##### <a name="action-to-take"></a>要采取的措施

遇到上一部分中指定类型的威胁时要执行的操作。 可以是：

- **审核**：设备不受此类威胁的保护，但会记录有关威胁的条目。
- **阻止**：设备受到此类威胁的保护，并在安全控制台中通知你。
- **关闭**：设备不受此类威胁的保护，且未记录任何内容。

<br>

****

|说明|值|
|---|---|
|**注册表项**|值|
|**数据类型**|String|
|**可能的值**|审核 (默认)  <p> 块 <p> 关|
|

#### <a name="threat-type-settings-merge-policy"></a>威胁类型设置合并策略

指定威胁类型设置的合并策略。 这可以是管理员定义设置和用户定义设置的组合， () `merge` 或仅管理员定义的设置 () `admin_only` 。 此设置可用于限制本地用户为不同威胁类型定义自己的设置。

<br>

****

|说明|值|
|---|---|
|**注册表项**|threatTypeSettingsMergePolicy|
|**数据类型**|String|
|**可能的值**|合并 (默认)  <p> admin_only|
|**Comments**|在 Defender for Endpoint 版本 100.83.73 或更高版本中可用。|
|

#### <a name="antivirus-scan-history-retention-in-days"></a>防病毒扫描历史记录保留期 (天) 

指定在设备上的扫描历史记录中保留结果的天数。 旧扫描结果将从历史记录中删除。 从磁盘中删除的旧隔离文件。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanResultsRetentionDays|
|**数据类型**|String|
|**可能的值**|90 (默认) 。 允许的值为 1 天到 180 天。|
|**Comments**|在 Defender for Endpoint 版本 101.04.76 或更高版本中可用。|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>防病毒扫描历史记录中的最大项数

指定要保留在扫描历史记录中的最大条目数。 条目包括过去执行的所有按需扫描和所有防病毒检测。

<br>

****

|说明|值|
|---|---|
|**注册表项**|scanHistoryMaximumItems|
|**数据类型**|String|
|**可能的值**|10000 (默认) 。 允许的值从 5000 项到 15000 项不等。|
|**Comments**|在 Defender for Endpoint 版本 101.04.76 或更高版本中可用。|
|

### <a name="cloud-delivered-protection-preferences"></a>云提供的保护首选项

配置文件中的 *cloudService* 条目用于配置产品的云驱动保护功能。

<br>

****

|说明|值|
|---|---|
|**注册表项**|cloudService|
|**数据类型**|字典 (嵌套首选项) |
|**Comments**|有关字典内容的说明，请参阅以下部分。|
|

#### <a name="enable--disable-cloud-delivered-protection"></a>启用/禁用云提供的保护

确定是否在设备上启用云传递的保护。 为了提高服务的安全性，我们建议保持启用此功能。

<br>

****

|说明|值|
|---|---|
|**注册表项**|enabled|
|**数据类型**|Boolean|
|**可能的值**|true (默认)  <p> false|
|

#### <a name="diagnostic-collection-level"></a>诊断集合级别

诊断数据用于保护 Defender for Endpoint 的安全和最新、检测、诊断和修复问题，并改进产品。 此设置确定产品发送到 Microsoft 的诊断级别。

<br>

****

|说明|值|
|---|---|
|**注册表项**|diagnosticLevel|
|**数据类型**|String|
|**可能的值**|可选 (默认)  <p> 必需|
|

#### <a name="enable--disable-automatic-sample-submissions"></a>启用/禁用自动示例提交

确定是否将可能包含威胁) 的可疑示例 (发送到 Microsoft。 控制示例提交有三个级别：

- **无**：没有向 Microsoft 提交任何可疑示例。
- **保险箱**：仅自动提交不包含个人身份信息 (PII) 的可疑示例。 这是此设置的默认值。
- **全部**：所有可疑示例都提交给 Microsoft。

<br>

****

|说明|值|
|---|---|
|**注册表项**|automaticSampleSubmissionConsent|
|**数据类型**|String|
|**可能的值**|无 <p> 安全 (默认)  <p> 所有|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>启用/禁用自动安全智能更新

确定是否自动安装安全智能更新：

<br>

****

|说明|值|
|---|---|
|**注册表项**|automaticDefinitionUpdateEnabled|
|**数据类型**|Boolean|
|**可能的值**|true (默认)  <p> false|
|

## <a name="recommended-configuration-profile"></a>建议的配置文件

若要开始，我们建议企业使用以下配置文件来利用 Defender for Endpoint 提供的所有保护功能。

以下配置文件将：

- 启用实时保护 (RTP) 
- 指定如何处理以下威胁类型：
  - **可能不需要的应用程序 (PUA)** 被阻止
  - 将高压缩率 () 存 **档炸弹** 审核到产品日志
- 启用自动安全智能更新
- 启用云保护
- 在级别启用自动示例提交`safe`
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

以下配置文件包含本文档中所述的所有设置的条目，可用于更高级的方案，你希望对产品进行更多控制。

### <a name="full-profile"></a>完整配置文件

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

首次运行 `mdatp health` 命令时，标记和组 ID 的值将为空。 若要向 `mdatp_managed.json` 文件添加标记或组 ID，请执行以下步骤：
  
  1. 从路径 `/etc/opt/microsoft/mdatp/managed/mdatp_managed.json`打开配置文件。
  2. 下到该块所在的 `cloudService` 文件底部。
  3. 添加所需的标记或组 ID，如以下示例所示，位于右大括号 `cloudService`的末尾。

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
  > 不要忘记在块末尾 `cloudService` 的右大括号后添加逗号。 此外，请确保在添加标记或组 ID 块后有两个右大括号 (请参阅上面的示例) 。 目前，标记的唯一支持密钥名称是 `GROUP`。 
  
## <a name="configuration-profile-validation"></a>配置文件验证

配置文件必须是有效的 JSON 格式的文件。 有许多工具可用于验证这一点。 例如，如果已 `python` 在设备上安装：

```bash
python -m json.tool mdatp_managed.json
```

如果 JSON 格式正确，上述命令会将其输出回终端，并返回其退出代码 `0`。 否则，将显示描述该问题的错误，并且该命令返回的退出代码 `1`。

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>验证mdatp_managed.json 文件是否按预期工作

若要验证 /etc/opt/microsoft/mdatp/managed/mdatp_managed.json 是否正常工作，应会看到以下设置旁边的"[托管]"：

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> 若要使 mdatp_managed.json 生效，无需重启 `mdatp` deamon。

## <a name="configuration-profile-deployment"></a>配置文件部署

为企业生成配置文件后，可以通过企业使用的管理工具部署配置文件。 Linux 上的 Defender for Endpoint 从 */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* 文件中读取托管配置。
