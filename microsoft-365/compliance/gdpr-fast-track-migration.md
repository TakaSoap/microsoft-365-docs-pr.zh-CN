---
title: GDPR
description: Microsoft 技术指南 - 用于提交删除请求的 FASTTRACK 迁移工具集
keywords: FastTrack 迁移, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 162a64535f82f24411121ed81e36078511eb8eba
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416908"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>用于提交删除请求的 FastTrack 迁移工具集

## <a name="toolset-purpose"></a>工具集用途

如果你是目前正在使用 FastTrack 迁移的客户，那么删除用户帐户将不会删除由 Microsoft FastTrack 团队保留的数据副本（该副本仅保留用于完成迁移）。在迁移过程中，如果你希望 Microsoft FastTrack 团队同时删除数据副本，请通过此工具集提交请求。在正常业务过程中，Microsoft FastTrack 将在迁移完成后立即删除所有数据副本。

### <a name="supported-platforms"></a>支持的平台
Microsoft 支持 Windows 平台和 PowerShell 控制台中此工具集的初始版本。此工具集支持以下已知平台：
 
***表 1 - 此工具集支持的平台***
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |**Windows 7**|**Windows 8**|**Windows 10**|**Windows Server 2012**|**Windows Server 2016**|
|PS 5.0|不<br/>支持|支持|支持|支持|支持|
|PS 5.1|不<br/>支持|支持|支持|支持|支持|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a>获取工具集

PowerShell 控制台应用程序上的 PowerShell 库中提供此工具集。若要查找和加载此 cmdlet 模块，首先在管理员模式下打开 PowerShell，以使其具有安装模块的相应权限。如果以前未使用过 PowerShell，请转到 Windows 任务栏，并在搜索框中键入“PowerShell”。右键单击并选择控制台应用，然后选择“以管理员身份运行”****，单击“是”**** 运行 Windows PowerShell。

![PowerShell - 以管理员身份运行](../media/fasttrack-powershell_image.png)

![PowerShell - 允许应用进行更改](../media/fasttrack-run-powershell_image.png)

打开控制台后，需要设置用于脚本执行的权限。键入以下命令以允许脚本运行：“Set-ExecutionPolicy - ExecutionPolicy: Bypass - Scope:Process”

系统将提示你确认此操作，因为管理员可以自行决定更改范围。

***设置执行策略***

![在 PowerShell 中设置执行策略更改](../media/powershell-set-execution-policy_image.png)

现在，已将控制台设置为允许脚本，运行下一个命令以安装模块：

>`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery `
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a>模块的先决条件
若要成功执行此模块，可能需要安装独立模块以供使用（如果尚未安装）。可能需要重启 PowerShell。  

为了提交 DSR，必须首先使用你的 Office 365 凭据登录：输入正确的凭据将验证你的全局管理员状态并收集租户信息。 

**登录-FastTrackAccount-ApiKey： \<API Key provided by FastTrack MVM\>**

成功登录后，将存储凭据和密钥，以供 FastTrack 模块在当前 PowerShell 会话的其余部分使用。

如果需要连接到云环境（而非商业环境），在以下其中一个有效环境中，需要向 *Login* 命令添加 *-Environment*：
- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**

若要提交 DSR 请求，请运行以下命令：Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com

成功后，cmdlet 将返回事务 ID 对象。请保留此事务 ID。


#### <a name="checking-the-status-of-a-request-transaction"></a>检查请求事务的状态

使用以前获取的事务 ID 运行以下函数：Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”

#### <a name="transaction-status-codes"></a>事务状态代码
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|**事务** |**状态**|
|**已创建** |已创建请求|
|**失败**|无法创建请求，请重新提交，或联系支持人员|
|**已完成**|请求已完成并已被清理|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a>了解更多
[Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview
)
