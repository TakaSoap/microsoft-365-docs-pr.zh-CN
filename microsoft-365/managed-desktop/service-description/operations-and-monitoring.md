---
title: Microsoft 托管桌面操作和监视
description: 谁对各种更改过程执行哪些操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5d7c6a7b836d0044ba9cde188170dd51f117dd2b
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840369"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 托管桌面操作和监视

<!-- Operations and monitoring: -->


## <a name="change-management"></a>变更管理

在服务产品中，硬件维护和安全更新程序等的责任平衡会转为服务提供商 (Microsoft) 而不是客户（您）。 但是，你仍然需要确保非 Microsoft 和自定义软件在推出更新时继续正常工作。

对于本地产品，您的组织承担管理更改的所有责任。

### <a name="balance-of-responsibility"></a>责任平衡

Responsibility | Microsoft 托管桌面服务 | Microsoft 365 客户端软件 | 本地客户端和服务器 | 非 Microsoft 和自定义软件
----- | ----- | ----- | ----- | -----
提供新功能 | Microsoft | Microsoft | 两者都有 | 客户
测试新功能用于质量保证 |  Microsoft | Microsoft | 两者都有 | 客户
交流新功能 | 两者都有 | 两者都有 | 两者都有 | 客户
集成自定义软件 | 两者都有 | 两者都有 | 客户 | 客户
应用安全更新程序 | Microsoft | Microsoft | 客户 | 客户
维护系统软件 | Microsoft | Microsoft | 客户 | 客户
用于部署的程序包 | Microsoft | Microsoft | 客户 | 客户


### <a name="change-process-overview"></a>更改过程概述

下面汇总了如何在 Microsoft 与客户之间共享更改过程： 



<table>
<tr><th></th><th><p>Microsoft 的角色：</p></th><th><p>客户角色：</p></th></tr>
<tr><td>更改前</td><td><ul><li>设置服务更改的预期。</li><li>有关需要管理员操作的更改，请提前 5 天通知客户。</li><li>对于紧急更改，请在通知之前应用缓解。</li></ul></td><td><ul><li>了解对更改和通信的预测。</li><li>定期阅读 Microsoft 托管桌面消息中心。</li><li>查看并升级内部更改管理过程。</li><li>了解并检查 Microsoft 托管桌面要求的合规性。 </li><li>确认并批准（如果需要）。</li></ul></td></tr><tr><td>更改期间</td><td><ul><li>发布和部署 Windows 10 和 Office 365 客户端的每月安全更新和非安全更新。</li><li>监视数据信号和支持队列以产生影响。</li></ul></td><td><ul><li>检查 Microsoft 托管桌面消息中心并查看任何其他信息。</li><li>   执行所需的任何操作（如果适用）并测试应用程序。</li><li>如果遇到中断/修复方案，请创建支持请求。</li></ul></td></tr><tr><td>更改后</td><td><ul><li>收集客户反馈，以改进未来更改的推出。</li><li>监视数据信号和支持队列以产生影响。</li></ul></td><td><ul><li>与组织人员合作以采用更改。</li><li>   查看变更和采用管理流程，以获得提高效率的机会。</li><li>在管理员反馈工具中提供常规反馈和特定反馈。</li><li>培训用户使用 Windows 反馈中心和 Office 应用中的"笑"按钮提供特定于应用的反馈。</li></ul></td></tr>
<table> 






### <a name="change-types"></a>更改类型

我们定期对服务进行几种类型的更改。 这些更改的通信通道以及您负责的操作各不相同。

并不是所有的更改都会对您的用户产生相同的影响，或需要采取操作。 一些已计划，一些计划外 (非安全更新，而安全更新通常不会) 。 根据更改类型，信道可能会有所不同。 下表列出了 Microsoft 托管桌面服务预期更改的类型。

|   | 功能 |   非安全更新 |  安全性
--- | --- | --- | ---
**更改类型** | - 功能更新<br>- 新功能或应用程序<br>- 已弃用的功能 | 针对问题的客户端修补程序 | 安全更新
**预先通知** | 需要采取措施的更改通知五天 | 否，此类更改包含在每月版本中    | 否，更改包含在每月版本中 
**信道** | - 消息中心<br>- 电子邮件警报 | - 消息中心<br>- 电子邮件警报 | - 消息中心<br>- 电子邮件警报
**需要全局管理员操作** | 有时 |  很少 |    很少 
**操作类型** | 更改设置 | 将更改传达给用户 | 更改管理员设置     
**需要测试** | 检查业务应用程序，包括远程访问服务 |  有时 - 针对流程或自定义项测试修补程序 |   很少 
**更改示例** | - 功能更新：IT 管理门户简化了支持票证提交和审阅<br>- 新功能或应用程序：Semi-Annual Windows 10 功能更新的发布 | 基于客户报告的 bug 的修补程序 |  


## <a name="standard-operating-procedures"></a>标准操作过程

Microsoft 托管桌面服务由 Microsoft 在 Microsoft 云实例中实施和运行，您可以在其中执行其他管理活动。 Microsoft 仅负责 Microsoft 托管桌面特定的设置、配置和操作。 

对于本地产品，您的组织承担管理设置、配置和操作活动的所有责任。

类别 |    Microsoft 将 | 客户将
--- | --- | ---
网络 (代理、数据包检查、VPN)   | 为客户提供建议和规划，以最大限度地降低业务用户的风险。 | - 创建支持请求，请求有关计划配置更改的信息，包括配置详细信息、范围、时间线和其他相关详细信息，供 Microsoft 查看。<br>- 仅在 Microsoft 托管桌面操作进行评估和建议后应用更改。
服务帐户 |- 实现、安全存储和管理凭据。<br> - 向安全运营团队传达未经授权访问或使用这些凭据。 | - 创建支持请求，请求有关计划配置更改的信息，包括配置详细信息、范围、时间线和其他相关详细信息，供 Microsoft 查看。<br>- 仅在 Microsoft 托管桌面操作进行评估和建议后应用更改。<br>- 不向 Microsoft 托管桌面服务帐户分配策略、多重身份验证、条件访问或应用程序部署。<br>- 不重置密码或使用凭据。<br>- 如果 Intune 或 Azure 审核日志中发现与这些服务帐户相关的可疑活动，请打开对 Microsoft 托管桌面运营的 Sev C 支持请求。
设备组 | - 实现和管理 Microsoft 托管桌面组内的设备成员身份。<br>- 使用 Microsoft 托管桌面组管理配置和更新设备的分配和发布。 | - 创建支持请求，请求有关计划配置更改的信息，包括配置详细信息、范围、时间线和其他相关详细信息，供 Microsoft 查看。<br>- 仅在 Microsoft 托管桌面操作进行评估和建议后应用更改。<br>- 不修改任何 Microsoft 托管桌面组的成员身份。<br>- 仅使用这些组为服务（如 VPN、Windows Hello 企业或电子邮件加密）或公司Wi-Fi配置文件配置。<br>- 如果存在共同管理，则部署 Configuration Manager 客户端时显式排除所有 Microsoft 托管桌面组。
策略 |  - 实现和管理 Microsoft 托管桌面策略，这些策略控制服务内设备的配置状态。<br>- 使用设备组以增量方式将更新部署到策略或 Windows。<br> - 明确排除非 Microsoft 托管桌面组。 | - 创建支持请求，请求有关计划配置更改的信息，包括配置详细信息、范围、时间线和其他相关详细信息，供 Microsoft 查看。<br>- 仅在 Microsoft 托管桌面操作进行评估和建议后应用更改。<br>- 不编辑 Microsoft 托管桌面策略或将 Microsoft 托管桌面策略分配给未由 Microsoft 托管桌面服务管理的设备或用户。
Microsoft Defender for Endpoint | 监视和调查 Microsoft 托管桌面服务范围内的设备。 | - 创建支持请求，请求有关计划配置更改的信息，包括配置详细信息、范围、时间线和其他相关详细信息，供 Microsoft 查看。<br>- 仅在 Microsoft 托管桌面操作进行评估并建议后应用更改
适用于企业的 Microsoft Store |  配置和维护 Microsoft 托管桌面服务的 Windows Autopilot 配置文件。 | - 创建支持请求，请求有关计划配置更改的信息，包括配置详细信息、范围、时间线和其他相关详细信息，供 Microsoft 查看。<br>- 仅在 Microsoft 托管桌面操作进行评估和建议后应用更改。<br>- 不修改 Microsoft 托管桌面 Windows Autopilot 配置文件的配置，或添加/删除分配的设备。
证书 | | - 在证书过期前 60 天创建支持请求，请求有关计划配置更改的信息，包括配置详细信息、范围、时间线和其他相关详细信息，供 Microsoft 查看。<br>- 仅在 Microsoft 托管桌面操作进行评估和建议后应用更改。<br>- 更新配置证书配置文件、VPN 配置文件和证书配置文件所需的Wi-Fi证书。




## <a name="device-wipe-with-factory-reset"></a>恢复出厂设置的设备擦除

如果需要，Microsoft 托管桌面操作团队可以执行在服务中注册的设备出厂重置。 如果需要将设备授予其他员工，或者员工离开公司，重置会很有帮助。 

有一些要求：

- 全局管理员必须提交服务请求。
- 在请求中包括设备的计算机名称。
- 重置设备之前，用户帐户必须在 Azure AD 中。

托管桌面操作团队将执行以下操作：

- 在 Intune 中查找设备名称
- 将恢复出厂设置命令发送到设备

>[!NOTE]
>在重置设备之前，请勿从 Azure AD 中删除用户帐户。 如果用户不在 Azure AD 中，Intune 无法将恢复出厂设置命令发送到设备。 

设备将启动到"开箱即用体验"，并且所有预安装的应用程序和设置将再次应用。 设备的用户需要再次提供初始设置信息。 

重置设备后，你可以将设备授予组织中的其他人。 以前用户的数据或企业数据都不在设备上。 下一位用户将执行与上一个人使用新的 Microsoft 托管桌面设备相同的过程。

BitLocker 是此过程中数据安全性的一个关键组件。 借助 Microsoft 托管桌面设备的 BitLocker 加密，即使设备已恢复出厂设置，驱动器上的数据仍保持安全。 驱动器上的任何数据将不能供设备的下一位用户使用。 有关详细信息，请参阅 [BitLocker 概述](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。

有关详细信息，请参阅"出厂[重置设备"。](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device) 