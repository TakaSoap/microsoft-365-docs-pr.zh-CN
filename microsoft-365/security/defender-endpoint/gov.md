---
title: 面向美国政府客户的Microsoft Defender for Endpoint
description: 了解 Microsoft Defender for Endpoint for US Government 客户的要求和功能可用
keywords: government， gcc， high， requirements， capabilities， defender， Microsoft Defender for Endpoint， endpoint， dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 846a1007a63164807b3667cb7c06fe5ea260a10a
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370712"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>面向美国政府客户的Microsoft Defender for Endpoint

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

美国政府客户 Microsoft Defender for Endpoint 内置于 Azure 美国政府环境中，使用与 Azure 商业中的 Defender for Endpoint 相同的基础技术。

此产品/服务GCC、GCC高和 DoD 客户，并且基于与商业版本相同的预防、检测、调查和修正。 但是，此产品/服务的功能可用性存在一些差异。

> [!NOTE]
> 如果你是使用商业GCC Defender for Endpoint 的客户，请参阅公共文档页面。

## <a name="licensing-requirements"></a>许可要求

Microsoft Defender for Endpoint for US Government 客户需要以下 Microsoft 批量许可优惠之一：

### <a name="desktop-licensing"></a>桌面许可

<br />

****

|GCC|GCC 高|DoD|
|---|---|---|
|Microsoft 365 GCC G5|Microsoft 365 E5高GCC|Microsoft 365 G5 for DOD|
|Microsoft 365 G5 安全GCC|Microsoft 365高GCC G5 安全性|Microsoft 365 DOD 的 G5 安全性|
|Microsoft Defender for Endpoint - GCC|Microsoft Defender for Endpoint for GCC High|Microsoft Defender for Endpoint for DOD|
|Windows 10 企业版 E5 GCC|Windows 10 企业版 E5 for GCC High|Windows 10 企业版 E5 for DOD|
|

### <a name="server-licensing"></a>服务器许可

<br />

****

|GCC|GCC 高|DoD|
|---|---|---|
|Microsoft Defender for Endpoint Server GCC|Microsoft Defender for Endpoint Server for GCC High|Microsoft Defender for Endpoint Server for DOD|
|Microsoft Defender for servers|Microsoft Defender for servers - 政府|Microsoft Defender for servers - 政府|
|

## <a name="portal-urls"></a>门户 URL

以下是美国政府客户的 Microsoft Defender 终结点门户 URL：

<br />

****

|客户类型|门户 URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC 高|<https://securitycenter.microsoft.us>|
|DoD|<https://securitycenter.microsoft.us>|
|
> [!NOTE]
> 如果你是客户GCC从 Microsoft Defender for Endpoint 商业移动到 GCC，请使用 访问 Microsoft Defender for https://transition.security.microsoft.com Endpoint 商业数据。

## <a name="endpoint-versions"></a>终结点版本

### <a name="standalone-os-versions"></a>独立操作系统版本

支持以下操作系统版本：

<br />

****

OS 版本|GCC|GCC 高|DoD
:---|:---:|:---:|:---:
Windows 11|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 21H1 及以上版本|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 20H2 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10 2004 版本 2004 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 1909 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10 1903 版本 1903 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10 版本 1809 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 1803 ([KB4598245](https://support.microsoft.com/help/4598245) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10，版本 1709|![否。](images/svg/check-no.svg) <br /> 注意：将不受支持|![是 ](images/svg/check-yes.svg) ，包含 [KB4499147](https://support.microsoft.com/help/4499147) <sup>1</sup> <br /> 注意： [已弃用，](/lifecycle/announcements/revised-end-of-service-windows-10-1709)请升级|![否](images/svg/check-no.svg) <br /> 注意：将不受支持
Windows 10版本 1703 及更早版本|![否。](images/svg/check-no.svg) <br /> 注意：将不受支持|![否](images/svg/check-no.svg) <br /> 注意：将不受支持|![否](images/svg/check-no.svg) <br /> 注意：将不受支持
Windows Server 2022|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2019 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2016 (新式) <sup>2</sup>|![是。](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版
Windows Server 2012 R2 (Modern) <sup>2</sup>|![是。](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版
Windows Server 2016 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2012 R2 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 (旧版) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 8.1 企业版 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 8 专业版 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 7 SP1 Pro (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Linux|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
macOS|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Android|![否。](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中
iOS|![否。](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中
|

> [!NOTE]
> <sup>1</sup> 必须在设备载入之前部署修补程序，才能将适用于终结点的 Defender 配置为正确的环境。
>
> <sup>2</sup>了解适用于[Windows 2016 和 2012 R2](configure-server-endpoints.md#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)的统一新式解决方案。 如果之前已使用 MMA 载入服务器，请按照服务器迁移中提供的指南[](server-migration.md)迁移到新解决方案。
>
> <sup>3</sup>使用[Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)如果使用安装向导，或者使用命令行或脚本，则需要选择"Azure 云"下的"Azure[](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)美国政府版"，将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为[](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)1。 [](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) <br /> 支持的最低 MMA 版本为 2020 年 3 月 20 (10.20.18029) 。

### <a name="os-versions-when-using-microsoft-defender-for-servers"></a>将 Microsoft Defender 用于服务器时的操作系统版本

将 Microsoft Defender 用于服务器时，支持 [以下操作系统版本](/azure/security-center/security-center-wdatp)：

<br />

****

OS 版本|GCC|GCC 高|DoD
:---|:---:|:---:|:---:
Windows Server 2022|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2019|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2016|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2012 R2|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
|

## <a name="required-connectivity-settings"></a>所需的连接设置

如果代理或防火墙在默认情况下阻止所有通信，并且只允许特定域通过，请将可下载工作表中列出的域添加到允许的域列表中。

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 验证没有拒绝访问这些 URL 的防火墙或网络筛选规则，或专门为它们创建允许规则。 

域列表的电子表格|说明
:-----|:-----
![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图。](images/mdatp-urls.png)|服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

有关详细信息，请参阅配置 [设备代理和 Internet 连接设置](configure-proxy-internet.md)。

> [!NOTE]
> 电子表格还包含商业 URL，请务必查看"US Gov"选项卡。
>
> 筛选时，在地理位置列下查找标记为"US Gov"的记录和您的特定云。

## <a name="api"></a>API

你需要使用以下 URI，而不是我们的 [API](apis-intro.md)文档中列出的公共 URI：

<br />

****

|终结点类型|GCC|GCC高& DoD|
|---|---|---|
|登录|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Defender for Endpoint API|`https://api-gcc.securitycenter.microsoft.us`|`https://api-gov.securitycenter.microsoft.us`|
|SIEM|`https://wdatp-alertexporter-us.gcc.securitycenter.windows.us`|`https://wdatp-alertexporter-us.securitycenter.windows.us`|
|

## <a name="feature-parity-with-commercial"></a>功能与商业奇偶校验

适用于美国政府客户的 Defender for Endpoint 与商业产品/服务没有完全同等价值。 尽管我们的目标是向美国政府客户提供所有商业特性和功能，但我们要重点说明一些功能。

这些就是已知差距：

<br />

****

|功能名称|GCC|GCC 高|DoD|
|---|:---:|:---:|:---:|
|网络评估|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|
|网络发现|![是](images/svg/check-yes.svg)|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|
|报告：攻击面减少、设备控制、设备运行状况、防火墙|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|
|Web 内容筛选|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|![否](images/svg/check-no.svg) 开发中|
|集成：Microsoft Power Automate & Azure 逻辑应用|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|
