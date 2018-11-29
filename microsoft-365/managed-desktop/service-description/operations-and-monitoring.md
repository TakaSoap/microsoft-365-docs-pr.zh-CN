---
title: Microsoft 托管桌面操作和监控
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 00bdc95c191ce16be219cf0dc251f72eaf054e22
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865573"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 托管桌面操作和监控

<!-- Operations and monitoring: -->


## <a name="change-management"></a>变更管理

Microsoft 和客户将共享 Microsoft 托管桌面服务的变更管理。责任不同的联机服务与本地服务器或客户端。 

### <a name="change-process-overview"></a>更改过程概述

下面是如何更改过程共享 Microsoft 和客户之间的摘要。 



<table>
<tr><th></th><th><p>Microsoft 将：</p></th><th><p>客户将：</p></th></tr>
<tr><td>更改前</td><td><ul><li>通知客户 5 天提前为需要管理员采取的操作的更改。</li><li>为紧急更改，应该应用之前通知缓解。</li></ul></td><td><ul><li>阅读并理解通知电子邮件。</li><li>确认并批准，在需要时。</li></ul></td></tr><tr><td>更改期间</td><td><ul><li>部署 Windows 10 和 Office 的更改，根据需要释放安全和非安全更新。</li><li>监视遥测和支持对任何异常问题进行呈报。</li></ul></td><td><ul><li>管理内部更改管理流程。</li><li>如果需要，请创建一个支持请求。</li></ul></td></tr><tr><td>更改后</td><td><ul><li>收集客户反馈，以提高推出将来的更改。</li><li>监视遥测和支持对任何异常问题进行呈报。</li></ul></td><td><ul><li>阅读并理解通知电子邮件。</li><li>提供一般的反馈信息和管理反馈工具在特定的反馈。</li><li>培训用户提供 Office 相关应用程序中使用 Windows 反馈集线器和笑脸按钮的特定于应用程序的反馈。</li></ul></td></tr>
<table> 






### <a name="change-types"></a>更改类型

有几种类型的定期上的服务所做的更改。这些更改，并负责客户的操作的通信通道而有所不同。

预计以下类型的更改：

更改类型 | 通知 | 客户操作
--- | --- | ---
功能更新和新服务组件 | 电子邮件 | -传达给用户的更改<br><br> -操作所需由 Microsoft<br><br> 的必须在 48 小时内执行操作
安全更新，每月更新和比较基准设置 | 电子邮件、 安全公告或公共漏洞和披露 (CVE) 条目 | -每月将使用我们的[更新管理策略](updates.md)部署更新的安全。<br><br> -设置以缓解威胁将部署到整个组织，以保护组织。（这似乎不是客户操作）
高质量的更新，其中包括修补程序、 服务更新和非安全产生影响的基准策略 | 电子邮件 | 将建议在需要时。
紧急更新： 以缓解的服务、 配置或软件更新要求：<br><br> 关键的安全风险<br><br> -潜在数据丢失<br><br> 访问遥测数据的管理 Microsoft 托管桌面设备 | 将建议在需要时。

## <a name="standard-operating-procedures"></a>标准操作过程

此服务是实现，并在其中进行管理的其他活动您环境中由 Microsoft 操作。全面负责特定于 Microsoft 托管桌面的安装、 配置和操作 Microsoft。 

对于内部部署产品，您的组织承担所有负责管理操作和配置活动。

类别 |    操作
--- | ---
服务帐户 |  Microsoft 将：<br><br> -实现、 安全地存储和管理的凭据<br><br> -通信未经授权的访问或使用的这些凭据向安全操作团队<br><br><br><br>客户将：<br><br> -打开信息性的支持要求与 Microsoft 托管桌面操作规划的可能影响帐户更改时<br><br> -不分配策略、 多重身份验证、 条件访问或应用程序部署 Microsoft 托管桌面服务帐户<br><br> -不重置密码或使用的凭据<br><br> -如果可疑活动观察 Intune 或 Azure 与这些服务帐户相关的审核日志中打开严重级别 C 支持请求 Microsoft 托管桌面操作
设备组 | Microsoft 将：<br><br> -实施和管理 Microsoft 托管桌面组内的设备的成员身份<br><br> -使用 Microsoft 托管桌面组来管理的工作分配和设备的配置和更新的版本<br><br><br><br>客户将：<br><br> -打开信息性的支持要求与 Microsoft 托管桌面操作规划的可能影响组更改时<br><br> -不修改任何 Microsoft 托管桌面组的成员身份<br><br> -仅使用组分配如 VPN、 Windows Hello 业务或电子邮件加密或企业 Wi-fi 配置文件配置服务的企业证书<br><br> -共同管理所在、 部署 Configuration Manager 客户端时明确排除所有 Microsoft 托管桌面组
Policies |  Microsoft 将：<br><br> -实施和管理 Microsoft 托管桌面策略来管理服务中的设备的配置状态<br><br> -将更新部署到策略或 Windows，以增量方式使用设备组<br><br> -明确排除设定的非 Microsoft 托管桌面组<br><br><br><br>客户将：<br><br> -信息性支持票证，从而使用 Microsoft 托管桌面操作时打开规划的可能影响的设备所需的配置状态更改<br><br> -不能编辑或将 Microsoft 托管桌面策略分配到的设备或不受 Microsoft 托管桌面服务的用户
Windows Defender 高级威胁防护 | Microsoft 将：<br><br> -监视和调查 Microsoft 托管桌面服务的范围内的设备<br><br><br><br>客户将：<br><br> -信息性支持票证，从而使用 Microsoft 托管桌面操作时打开规划的可能影响 Microsoft 托管桌面安全操作中心监控或调查功能更改
适用于企业的 Microsoft Store |  Microsoft 将：<br><br> -配置和维护 Microsoft 托管桌面服务的 Windows 自动执行某些操作配置文件<br><br><br><br>客户将：<br><br> -信息性支持票证，从而使用 Microsoft 托管桌面操作时打开规划打开可能会影响到存储访问或修改 Microsoft 托管桌面 Windows 自动执行某些操作配置文件更改<br><br> -不修改 Microsoft 托管桌面 Windows 自动执行某些操作配置文件进行配置或添加/删除已分配的设备
证书 |  客户将：<br><br> -打开信息性支持票证，从而使用 Microsoft 托管桌面操作 60 天之前任何证书过期<br><br> -更新配置需要的所有证书： 证书配置文件、 VPN 配置文件和 Wi-fi 配置文件



## <a name="device-wipe-with-factory-reset"></a>出厂重置设备擦除

托管桌面运营团队可以执行出厂重置最先所需要的 Microsoft 托管桌面托管设备上。如果您需要向不同的员工，授予设备或员工离开公司，这是非常有用。 

有几项要求：

- 客户的租户管理员必须提交服务请求
- 我们需要的设备的计算机名称
- 用户帐户必须是在我们先将重置的 Azure AD

托管的桌面运营团队将：

- 查找 Intune 中的设备名称
- 发送到设备出厂重置的命令

>[!NOTE]
>出厂重置之前的 Azure AD 中删除的用户帐户。如果用户不在 Azure AD，Intune 无法发送到设备出厂重置的命令。 

设备将启动到 OOBE，并将再次应用所有预安装的应用程序和设置。设备的用户需要提供再次信息的初始设置。 

时重置设备，您可以将其移交给另一个人在组织中。任何前用户数据或企业数据将在设备上。下一个用户将经过相同的以前的人员未与新的 Microsoft 托管桌面设备的过程。

BitLocker 是此过程中的数据安全性的关键组成部分。使用 Microsoft 托管桌面设备上的 BitLocker 加密的驱动器上的数据保持安全，即使出厂重置应用于该设备。不可用的设备的下一个用户的驱动器上的任何数据。有关详细信息，请参阅[BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。

有关详细信息，请参阅[执行出厂重置设备](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device)。 
