---
title: Microsoft 托管桌面操作和监控
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 12/18/2018
ms.openlocfilehash: 66945d44df150b5be9af9a9dfe52daa4d7468298
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865573"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 托管桌面操作和监控

<!-- Operations and monitoring: -->


## <a name="change-management"></a>变更管理

一项服务，负责诸如硬件维护和安全的平衡中更新移到服务提供程序 (Microsoft) 而不是客户 （您）。但是，则仍需确保该第三方和自定义软件仍可正常运行时更新的推出。

对于内部部署的产品，您的组织假定所有负责管理更改。

### <a name="balance-of-responsibility"></a>责任的平衡

Responsibility | Microsoft 托管桌面服务 | Microsoft 365 客户端软件 | 本地客户端和服务器 | 第三方和自定义软件
----- | ----- | ----- | ----- | -----
提供新功能 | Microsoft | Microsoft | 两者 | 客户
测试新功能用于质量保证 |  Microsoft | Microsoft | 两者 | 客户
交流新功能 | 两者 | 两者 | 两者 | 客户
集成自定义软件 | 两者 | 两者 | 客户 | 客户
应用安全更新程序 | Microsoft | Microsoft | 客户 | 客户
维护系统软件 | Microsoft | Microsoft | 客户 | 客户
部署包 | Microsoft | Microsoft | 客户 | 客户


### <a name="change-process-overview"></a>更改过程概述

下面是如何更改过程共享 Microsoft 和客户之间的摘要。 



<table>
<tr><th></th><th><p>Microsoft 的角色：</p></th><th><p>客户的角色：</p></th></tr>
<tr><td>更改前</td><td><ul><li>设置服务更改的预期。</li><li>通知客户 5 天提前为需要管理员采取的操作的更改。</li><li>为紧急更改，应该应用之前通知缓解。</li></ul></td><td><ul><li>了解对更改和通信的预测。</li><li>阅读 Microsoft 托管桌面消息中心定期。</li><li>查看并升级内部更改管理过程。</li><li>了解，并检查遵守 Microsoft 托管桌面要求。 </li><li>确认并批准，在需要时。</li></ul></td></tr><tr><td>更改期间</td><td><ul><li>发布和部署 Windows 10 和 Office 365 客户端每月版安全和非安全更新。</li><li>监视数据信号和影响支持队列。</li></ul></td><td><ul><li>检查 Microsoft 托管桌面消息中心并查看任何其他信息。</li><li>   执行任何所需的操作，如果适用，并测试应用程序。</li><li>如果中断/修复方案有经验，创建一个支持请求。</li></ul></td></tr><tr><td>更改后</td><td><ul><li>收集客户反馈，以提高推出将来的更改。</li><li>监视数据信号和影响支持队列。</li></ul></td><td><ul><li>使用您的组织中的人员采用更改。</li><li>   查看获益的机会的更改，并应用管理过程。</li><li>提供一般的反馈信息和管理反馈工具在特定的反馈。</li><li>培训用户提供 Office 相关应用程序中使用 Windows 反馈集线器和笑脸按钮的特定于应用程序的反馈。</li></ul></td></tr>
<table> 






### <a name="change-types"></a>更改类型

有几种类型的定期上的服务所做的更改。通信通道的这些更改和客户负责操作而有所不同。

并非所有更改对用户有相同影响，或需要操作。一些计划和性质一些计划外 （非安全更新和安全更新不通常计划的）。根据更改的类型，通信通道可能会有所不同。下表列出了您可以预期 Microsoft 托管桌面服务的更改的类型。

|   | 功能 |   非安全更新 |  安全性
--- | --- | --- | ---
**更改类型** | -功能更新<br>-新功能或应用程序<br>-已弃用的功能 | 针对问题的客户端修补程序 | 安全修补程序
**事先通知** | 5 天通知需要操作的更改 |    否，这些元素包含月的版本中   | 否，这些元素包含月的版本中 
**信道** | -消息中心<br>电子邮件通知 | -消息中心<br>电子邮件通知 | -消息中心<br>电子邮件通知<br>安全公告或 CVE 
**需要租户管理操作** | 有时 |  很少 |    很少 
**操作的类型** | 更改设置 | 将更改传达给用户 | 更改管理员设置     
**需要测试** | 检查业务应用程序，包括远程访问服务 |  有时 - 针对流程或自定义项测试修补程序 |   很少 
**更改的示例** | -功能更新： IT 管理门户简化了支持票证提交和审查<br>-新功能或应用程序： Windows 10 功能更新的半年发布 | 基于客户报告的 bug 的修补程序 |  


## <a name="standard-operating-procedures"></a>标准操作过程

Microsoft 托管桌面服务是实现，由 Microsoft 客户可以在其中执行其他管理活动 Microsoft 云实例中。全面负责特定于 Microsoft 托管桌面的安装、 配置和操作 Microsoft。 

对于内部部署产品，您的组织承担所有的管理设置和配置和操作活动的责任。

类别 |    Microsoft 将 | 客户将
--- | --- | ---
网络 （VPN 检查数据包来代理）  | 建议，并计划与客户业务用户的风险降至最低。 | 创建支持请求请求计划的配置更改，包括配置详细信息、 范围、 日程表和 microsoft 查看其他相关详细信息。<br>-仅应用更改后 Microsoft 托管桌面操作具有评估和建议。
服务帐户 |-实现、 安全地存储和管理的凭据。<br> -未经授权的访问或使用的这些凭据向安全操作团队进行通信。 | 创建支持请求请求计划的配置更改，包括配置详细信息、 范围、 日程表和 microsoft 查看其他相关详细信息。<br>-仅应用更改后 Microsoft 托管桌面操作具有评估和建议。<br>-不分配策略、 多重身份验证、 条件访问或应用程序部署到 Microsoft 托管桌面服务帐户。<br>-不重置密码或使用的凭据。<br>-如果可疑活动观察 Intune 或 Azure 与这些服务帐户相关的审核日志中，打开 Microsoft 托管桌面操作严重级别 C 支持请求。
设备组 | -实施和管理 Microsoft 托管桌面组内的设备的成员身份。<br>-使用 Microsoft 托管桌面组管理的工作分配和设备的配置和更新的版本。 | 创建支持请求请求计划的配置更改，包括配置详细信息、 范围、 日程表和 microsoft 查看其他相关详细信息。<br>-仅应用更改后 Microsoft 托管桌面操作具有评估和建议。<br>-不修改任何 Microsoft 托管桌面组的成员。<br>-仅使用组分配如 VPN、 Windows Hello 业务或电子邮件加密或企业 Wi-fi 配置文件配置服务的企业证书。<br>-共同管理所在、 部署 Configuration Manager 客户端时明确排除所有 Microsoft 托管桌面组。
Policies |  -实施和管理 Microsoft 托管桌面策略来管理配置状态服务内的设备。<br>-将更新部署到策略或窗口中，以增量方式使用设备组。<br> -明确排除设定的非 Microsoft 托管桌面组。 | 创建支持请求请求计划的配置更改，包括配置详细信息、 范围、 日程表和 microsoft 查看其他相关详细信息。<br>-仅应用更改后 Microsoft 托管桌面操作具有评估和建议。<br>-不能编辑或将 Microsoft 托管桌面策略分配到的设备或不受 Microsoft 托管桌面服务的用户。
Windows Defender 高级威胁防护 | 监视和调查 Microsoft 托管桌面服务的范围内的设备。 | 创建支持请求请求计划的配置更改，包括配置详细信息、 范围、 日程表和 microsoft 查看其他相关详细信息。<br>-仅应用更改后 Microsoft 托管桌面操作具有评估和建议
适用于企业的 Microsoft Store |  配置和维护 Microsoft 托管桌面服务的 Windows 自动执行某些操作配置文件。 | 创建支持请求请求计划的配置更改，包括配置详细信息、 范围、 日程表和 microsoft 查看其他相关详细信息。<br>-仅应用更改后 Microsoft 托管桌面操作具有评估和建议。<br>-不修改 Microsoft 托管桌面 Windows 自动执行某些操作配置文件进行配置或添加/删除已分配的设备。
证书 | | -创建支持请求 60 天之前证书过期、 请求计划的配置更改，包括配置详细信息、 范围、 日程表和 microsoft 查看其他相关详细信息。<br>-仅应用更改后 Microsoft 托管桌面操作具有评估和建议。<br>-更新配置证书配置文件、 VPN 配置文件和 Wi-fi 配置文件所需的所有证书。




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

时重置设备，您可以将其移交给另一个人在组织中。任何以前用户的数据或企业数据将在设备上。下一个用户将经过相同的以前的人员未与新的 Microsoft 托管桌面设备的过程。

BitLocker 是此过程中的数据安全性的关键组成部分。使用 Microsoft 托管桌面设备上的 BitLocker 加密的驱动器上的数据保持安全，即使出厂重置应用于该设备。不可用的设备的下一个用户的驱动器上的任何数据。有关详细信息，请参阅[BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。

有关详细信息，请参阅[执行出厂重置设备](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device)。 
