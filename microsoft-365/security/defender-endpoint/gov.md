---
title: 适用于美国政府客户的 Microsoft Defender for Endpoint
description: 了解 Microsoft Defender for Endpoint for US Government 客户的要求和功能可用
keywords: government， gcc， high， requirements， capabilities， defender， defender atp， mdatp， endpoint， dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 089614fab57950af5f60181ce7ed2116046ad347
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379366"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>适用于美国政府客户的 Microsoft Defender for Endpoint

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

美国政府客户 Microsoft Defender for Endpoint 内置于 Azure 美国政府环境中，使用与 Azure 商业中的 Defender for Endpoint 相同的基础技术。

此产品适用于 GCC、GCC High 和 DoD 客户，并且基于与商业版本相同的预防、检测、调查和修正。 但是，此产品/服务的功能可用性存在一些差异。

> [!NOTE]
> 如果你是使用商业版 Defender for Endpoint 的 GCC 客户，请参阅公共文档页面。

## <a name="licensing-requirements"></a>许可要求
Microsoft Defender for Endpoint for US Government 客户需要以下 Microsoft 批量许可优惠之一：

### <a name="desktop-licensing"></a>桌面许可
GCC | GCC 高 | DoD
:---|:---|:---
Windows 10 企业版 E5 GCC | 适用于 GCC High 的 Windows 10 企业版 E5 | 适用于 DOD 的 Windows 10 企业版 E5
| | 适用于 GCC High 的 Microsoft 365 E5 | Microsoft 365 G5 for DOD
| | 适用于 GCC High 的 Microsoft 365 G5 安全性 | 适用于 DOD 的 Microsoft 365 G5 安全性
Microsoft Defender for Endpoint - GCC | Microsoft Defender for Endpoint for GCC High | Microsoft Defender for Endpoint for DOD

### <a name="server-licensing"></a>服务器许可
GCC | GCC 高 | DoD
:---|:---|:---
Microsoft Defender for Endpoint Server GCC | Microsoft Defender for Endpoint Server for GCC High | Microsoft Defender for Endpoint Server for DOD
Azure Defender for Servers | Azure Defender for Servers - 政府 | Azure Defender for Servers - 政府

<br />

## <a name="portal-urls"></a>门户 URL
以下是美国政府客户的 Microsoft Defender 终结点门户 URL：

客户类型 | 门户 URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC 高 | https://securitycenter.microsoft.us
DoD | https://securitycenter.microsoft.us

<br />

## <a name="endpoint-versions"></a>终结点版本

### <a name="standalone-os-versions"></a>独立操作系统版本
支持以下操作系统版本：

操作系统版本 | GCC | GCC 高 | DoD
:---|:---|:---|:---
Windows 10 版本 20H2 ([KB4586853](https://support.microsoft.com/help/4586853))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 10 版本 2004 ([KB4586853](https://support.microsoft.com/help/4586853))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 10 版本 1909 ([KB4586819](https://support.microsoft.com/help/4586819))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 10 版本 1903 ([KB4586819](https://support.microsoft.com/help/4586819))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 10 版本 1809 ([KB4586839](https://support.microsoft.com/help/4586839))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 10 版本 1803 ([KB4598245](https://support.microsoft.com/help/4598245))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 10 版本 1709 | ![否](images/svg/check-no.svg)<br />注意：将不受支持 | ![是 ](images/svg/check-yes.svg) ，包含 [KB4499147](https://support.microsoft.com/help/4499147)<br />注意： [已弃用，](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)请升级 | ![否](images/svg/check-no.svg)<br />注意：将不受支持
Windows 10 版本 1703 和更早版本 | ![否](images/svg/check-no.svg)<br />注意：将不受支持 | ![否](images/svg/check-no.svg)<br />注意：将不受支持 | ![否](images/svg/check-no.svg)<br />注意：将不受支持
Windows Server 2019 ([KB4586839](https://support.microsoft.com/help/4586839))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows Server 2016 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 8.1 企业版 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 8 专业版 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 7 SP1 企业版 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 7 SP1 专业版 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Linux | ![是](images/svg/check-yes.svg) 预览版<br />请参阅下面的注释 | ![是](images/svg/check-yes.svg) 预览版<br />请参阅下面的注释 | ![是](images/svg/check-yes.svg) 预览版<br />请参阅下面的注释
macOS | ![是](images/svg/check-yes.svg) 预览版<br />请参阅下面的注释 | ![是](images/svg/check-yes.svg) 预览版<br />请参阅下面的注释 | ![是](images/svg/check-yes.svg) 预览版<br />请参阅下面的注释
Android | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
iOS | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作

> [!NOTE]
> 如果指定了修补程序，则必须在设备载入之前部署该修补程序，才能将适用于终结点的 Defender 配置为正确的环境。

> [!NOTE]
> 尝试使用 Microsoft 监视代理载入低于 Windows 10 或 Windows Server 2019 [的 Windows 设备](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)？ 如果使用安装向导，或者使用命令行或脚本-将"OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE"参数设置为 1，则需要在"Azure 云[](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line)"下选择"Azure 美国政府"。 [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard) [](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)

> [!NOTE]
> 需要 Linux 版本 101.25.72 及以上版本，macOS 需要版本 101.25.69 及以上版本。 当我们预览时，这些版本仅在"预览体验成员 - 快"频道中可用。 有关 [说明，](linux-install-manually.md#configure-the-linux-software-repository) 请参阅配置 Linux 软件存储库或 ([macOS) ](mac-updates.md#set-the-channel-name) 频道名称。

### <a name="os-versions-when-using-azure-defender-for-servers"></a>使用 Azure Defender for Servers 时的操作系统版本
使用 Azure Defender for Servers 时支持以下 [操作系统版本](https://docs.microsoft.com/azure/security-center/security-center-wdatp)：

操作系统版本 | GCC | GCC 高 | DoD
:---|:---|:---|:---
Windows Server 2016 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows Server 2012 R2 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows Server 2008 R2 SP1 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)

<br />

## <a name="required-connectivity-settings"></a>所需的连接设置
如果代理或防火墙在默认情况下阻止所有通信，并且只允许特定域通过，请将可下载工作表中列出的域添加到允许的域列表中。

以下可下载的电子表格列出了网络必须能够连接到的服务及其关联 URL。 验证没有拒绝访问这些 URL 的防火墙或网络筛选规则，或专门为它们创建允许规则。

域列表电子表格 | 说明
:-----|:-----
![适用于终结点 URL 电子表格的 Microsoft Defender 缩略图](images/mdatp-urls.png)<br/> | 服务位置、地理位置和操作系统的特定 DNS 记录的电子表格。 <br /><br />[在此处下载电子表格。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

有关详细信息，请参阅配置 [设备代理和 Internet 连接设置](configure-proxy-internet.md)。

> [!NOTE]
> 电子表格还包含商业 URL，请务必检查"US Gov"选项卡。
> 
> 筛选时，在地理位置列下查找标记为"US Gov"的记录和您的特定云。

### <a name="service-backend-ip-ranges"></a>服务后端 IP 范围

如果网络设备不支持基于 DNS 的规则，请改为使用 IP 范围。

适用于美国政府客户的 Defender for Endpoint 内置于 Azure 美国政府环境中，部署在以下地区：

- AzureCloud.usgovtexas
- AzureCloud.usgovvirginia

可以在 Azure IP 范围和服务标记 - 美国政府云 中查找 Azure IP [范围](https://www.microsoft.com/download/details.aspx?id=57063)。

> [!NOTE]
> 作为基于云的解决方案，IP 地址范围可能会更改。 建议移动到基于 DNS 的规则。

<br />

## <a name="api"></a>API
你需要使用以下 URI，而不是我们的 [API](apis-intro.md)文档中列出的公共 URI：

终结点类型 | GCC | GCC High & DoD
:---|:---|:---
登录 | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
Defender for Endpoint API | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br />

## <a name="feature-parity-with-commercial"></a>功能与商业奇偶校验
适用于美国政府客户的 Defender for Endpoint 与商业产品/服务没有完全同等价值。 尽管我们的目标是向美国政府客户提供所有商业特性和功能，但我们要重点说明一些功能。

这些是截至 2021 年 3 月已知差距：

功能名称 | GCC | GCC 高 | DoD
:---|:---|:---|:---
自动调查和修正：实时响应 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
自动调查和修正：Office 365 警报响应 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
电子邮件通知 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
评估实验室 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
管理和 API：设备运行状况和合规性报告 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
管理和 API：和第三方产品集成 | ![否](images/svg/check-no.svg) 即将推出 | ![否](images/svg/check-no.svg) 即将推出 | ![否](images/svg/check-no.svg) 即将推出
管理和 API：流式处理 API | ![是](images/svg/check-yes.svg) | ![否](images/svg/check-no.svg) 开发中 | ![否](images/svg/check-no.svg) 开发中
管理和 API：威胁防护报告 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
威胁&漏洞管理 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
威胁分析 | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Web 内容筛选 | ![否](images/svg/check-no.svg) 开发中 | ![否](images/svg/check-no.svg) 开发中 | ![否](images/svg/check-no.svg) 开发中
集成：Azure Sentinel | ![是](images/svg/check-yes.svg) | ![否](images/svg/check-no.svg) 开发中 | ![否](images/svg/check-no.svg) 开发中
集成：Microsoft Cloud App Security | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
集成：Microsoft 合规性管理器 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
集成：Microsoft Defender for Identity | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
集成：Microsoft Defender for Office 365 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
集成：Microsoft Endpoint DLP | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
集成：Microsoft Intune | ![是](images/svg/check-yes.svg) | ![否](images/svg/check-no.svg) 开发中 | ![否](images/svg/check-no.svg) 开发中
集成：Microsoft Power Automate & Azure 逻辑应用 | ![是](images/svg/check-yes.svg) | ![否](images/svg/check-no.svg) 开发中 | ![否](images/svg/check-no.svg) 开发中
集成：Skype for Business/Teams | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Microsoft 威胁专家 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作 | ![否](images/svg/check-no.svg) 工程积压工作
