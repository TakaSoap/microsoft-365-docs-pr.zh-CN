---
title: 面向美国政府客户的Microsoft Defender for Endpoint
description: 了解美国政府客户的Microsoft Defender for Endpoint要求和可用功能
keywords: 政府， gcc， 高， 要求， 功能， defender， Microsoft Defender for Endpoint， 终结点， dod
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
ms.openlocfilehash: ea689ca87d5d72204ba5621a59ca4fe43047ef52
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783218"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>面向美国政府客户的Microsoft Defender for Endpoint

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

对于在 Azure 美国政府环境中构建的美国政府客户，Microsoft Defender for Endpoint使用与 Azure 商业版中的 Defender for Endpoint 相同的基础技术。

此产品/服务适用于 GCC、GCC High 和 DoD 客户，并基于与商业版本相同的预防、检测、调查和修正。 但是，此产品/服务的功能可用性存在一些差异。

> [!NOTE]
> 如果你是使用商业版 Defender for Endpoint 的GCC客户，请参阅公共文档页。

## <a name="licensing-requirements"></a>许可要求

对于美国政府客户，Microsoft Defender for Endpoint需要以下 Microsoft 批量许可产品/服务之一：

### <a name="desktop-licensing"></a>桌面许可

<br />

****

|GCC|GCC 高|DoD|
|---|---|---|
|Microsoft 365 GCC G5|高GCC Microsoft 365 E5|Microsoft 365 G5 for DOD|
|Microsoft 365 G5 安全GCC|Microsoft 365 G5 安全性GCC高|Microsoft 365 G5 安全性 DOD|
|Microsoft Defender for Endpoint - GCC|高GCC Microsoft Defender for Endpoint|DOD 的Microsoft Defender for Endpoint|
|Windows 10 企业版 E5 GCC|Windows 10 企业版 E5 for GCC High|Windows 10 企业版 E5 for DOD|
|

### <a name="server-licensing"></a>服务器许可

<br />

****

|GCC|GCC 高|DoD|
|---|---|---|
|Microsoft Defender for Endpoint服务器GCC|Microsoft Defender for Endpoint Server for GCC High|Microsoft Defender for Endpoint服务器 for DOD|
|适用于服务器的 Microsoft Defender|适用于服务器的 Microsoft Defender - 政府版|适用于服务器的 Microsoft Defender - 政府版|
|

## <a name="portal-urls"></a>门户 URL

以下是美国政府客户的Microsoft Defender for Endpoint门户 URL：

<br />

****

|客户类型|门户 URL|
|---|---|
|GCC|<https://security.microsoft.com>|
|GCC 高|<https://security.microsoft.us>|
|DoD|<https://security.microsoft.us>|
|
> [!NOTE]
> 如果你是GCC客户，并且在从Microsoft Defender for Endpoint商业数据迁移到GCC的过程中，请使用https://transition.security.microsoft.com它来访问Microsoft Defender for Endpoint商业数据。

## <a name="endpoint-versions"></a>终结点版本

### <a name="standalone-os-versions"></a>独立 OS 版本

支持以下 OS 版本：

<br />

****

OS 版本|GCC|GCC 高|DoD
:---|:---:|:---:|:---:
Windows 11|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 21H1 及更高版本|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 20H2 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 2004 ([KB4586853](https://support.microsoft.com/help/4586853) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 1909 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 1903 ([KB4586819](https://support.microsoft.com/help/4586819) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10 版本 1809 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 1803 ([KB4598245](https://support.microsoft.com/help/4598245) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 10版本 1709|![不是。](images/svg/check-no.svg) <br /> 注意：不支持|![是](images/svg/check-yes.svg)[，KB4499147](https://support.microsoft.com/help/4499147) <sup>1</sup> <br /> 注意： [已弃用](/lifecycle/announcements/revised-end-of-service-windows-10-1709)，请升级|![否](images/svg/check-no.svg) <br /> 注意：不支持
Windows 10版本 1703 及更早版本|![不是。](images/svg/check-no.svg) <br /> 注意：不支持|![否](images/svg/check-no.svg) <br /> 注意：不支持|![否](images/svg/check-no.svg) <br /> 注意：不支持
Windows Server 2022|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows服务器 2019 ([KB4586839](https://support.microsoft.com/help/4586839) <sup>1</sup>) |![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2016 (新式) <sup>2</sup>|![是。](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版
Windows Server 2012 R2 (现代) <sup>2</sup>|![是。](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版
Windows Server 2016 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2012 R2 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 (旧版) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 8.1 企业版 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 8 专业版 (旧) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 7 SP1 Enterprise (旧版) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Windows 7 SP1 Pro (旧版) <sup>3</sup>|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Linux|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
macOS|![是。](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)
Android|![是。](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版
iOS|![是。](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版|![是](images/svg/check-yes.svg) <br /> 公共预览版
|

> [!NOTE]
> <sup>1</sup> 必须先在设备加入之前部署修补程序，才能将 Defender for Endpoint 配置为正确的环境。
>
> <sup>2</sup> 了解[适用于 Windows 2016 和 2012 R2 的统一新式解决方案](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)。 如果以前已使用 MMA 载入服务器，请按照 [服务器迁移](server-migration.md) 中提供的指导迁移到新解决方案。
>
> <sup>3</sup> 使用[Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma)时，如果使用[设置向导](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)，或者使用[命令行](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)或[脚本](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)，则需要在“Azure 云”下选择“Azure 美国政府”，或者将“OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE”参数设置为 1。 <br /> MMA 支持的最低版本为 10.20.18029 (2020 年 3 月) 。

### <a name="os-versions-when-using-microsoft-defender-for-servers"></a>使用适用于服务器的 Microsoft Defender 时的 OS 版本

使用 [适用于服务器的 Microsoft Defender](/azure/security-center/security-center-wdatp) 时，支持以下 OS 版本：

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

以下可下载电子表格列出了网络必须能够连接到的服务及其关联 URL。 验证没有防火墙或网络筛选规则会拒绝对这些 URL 的访问，或专门为这些 URL 创建 *允许* 规则。

|域列表的电子表格| 说明|
|---|---|
|商业客户Microsoft Defender for Endpoint URL 列表| 针对商业客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender for Endpoint Gov/GCC/DoD 的 URL 列表 | 适用于 Gov/GCC/DoD 客户的服务位置、地理位置和 OS 的特定 DNS 记录的电子表格。 <p> [在此处下载电子表格。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

有关详细信息，请参阅 [配置设备代理和 Internet 连接设置](configure-proxy-internet.md)。

> [!NOTE]
> 电子表格中还包含商业 URL，请确保检查“US Gov”选项卡。
>
> 筛选时，在地理列下查找标记为“US Gov”的记录和特定云。

## <a name="api"></a>API

需要使用以下 URI，而不是 [API 文档](apis-intro.md)中列出的公共 URI：

<br />

****

|终结点类型|GCC|GCC高& DoD|
|---|---|---|
|登录|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Defender for Endpoint API|`https://api-gcc.securitycenter.microsoft.us`|`https://api-gov.securitycenter.microsoft.us`|
|SIEM|`https://wdatp-alertexporter-us.gcc.securitycenter.windows.us`|`https://wdatp-alertexporter-us.securitycenter.windows.us`|
|

## <a name="feature-parity-with-commercial"></a>与商业功能奇偶校验

适用于美国政府客户的 Defender for Endpoint 与商业产品/服务没有完全奇偶校验。 虽然我们的目标是向美国政府客户提供所有商业功能和功能，但我们还希望重点介绍一些尚不可用的功能。

这些是已知的差距：

<br />

****

|功能名称|GCC|GCC 高|DoD|
|---|:---:|:---:|:---:|
|网络评估|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|
|网络发现|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|
|报告：设备控制、设备运行状况、防火墙|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|
|Web 内容筛选|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|
  

以下是 [Android & iOS) 上的移动威胁防御 (Microsoft Defender for Endpoint](mtd.md)的功能和已知差距：

<br />

****

|功能名称|GCC|GCC 高|DoD|
|---|:---:|:---:|:---:|
|Web 保护 (防钓鱼和自定义指标) |![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|
|恶意软件保护 (仅限 Android 的) |![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|
|仅限 iOS 的越狱检测 () |![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|
|条件访问/条件启动|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|
|对 MAM 的支持|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|
|隐私控制|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|![是](images/svg/check-yes.svg)|
| (TVM) 的威胁和漏洞管理|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|
|Web 内容筛选|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|![否](images/svg/check-no.svg) 在开发中|
  

