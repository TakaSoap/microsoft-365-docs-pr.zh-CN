---
title: Microsoft 托管桌面操作和监视
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9f0d1889e625ceba52f3e91ee950041f82e9750e
ms.sourcegitcommit: 4612c270867c148818eaa4008f45ca793f5d2a2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074764"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 托管桌面操作和监视

<!-- Operations and monitoring: -->


## <a name="change-management"></a>变更管理

在服务产品中，硬件维护和安全更新程序等的责任平衡会转为服务提供商 (Microsoft) 而不是客户（您）。 但是，当滚动更新时，您仍需要确保第三方和自定义软件继续按预期方式工作。

对于本地产品，组织应承担管理更改的所有责任。

### <a name="balance-of-responsibility"></a>责任余额

Responsibility | Microsoft 托管桌面服务 | Microsoft 365 客户端软件 | 本地客户端和服务器 | 第三方和自定义软件
----- | ----- | ----- | ----- | -----
提供新功能 | Microsoft | Microsoft | 两者都有 | 客户
测试新功能用于质量保证 |  Microsoft | Microsoft | 两者都有 | 客户
交流新功能 | 两者都有 | 两者都有 | 两者都有 | 客户
集成自定义软件 | 两者都有 | 两者都有 | 客户 | 客户
应用安全更新程序 | Microsoft | Microsoft | 客户 | 客户
维护系统软件 | Microsoft | Microsoft | 客户 | 客户
用于部署的包 | Microsoft | Microsoft | 客户 | 客户


### <a name="change-process-overview"></a>更改过程概述

下面概述了如何在 Microsoft 和客户之间共享更改过程。 



<table>
<tr><th></th><th><p>Microsoft 的角色：</p></th><th><p>客户的角色：</p></th></tr>
<tr><td>更改前</td><td><ul><li>设置服务更改的预期。</li><li>在需要管理员操作的更改时提前5天通知客户。</li><li>对于紧急更改，请在发出通知之前应用缓解措施。</li></ul></td><td><ul><li>了解对更改和通信的预测。</li><li>定期阅读 Microsoft 托管桌面邮件中心。</li><li>查看并升级内部更改管理过程。</li><li>了解并检查是否符合 Microsoft 托管桌面要求。 </li><li>必要时，确认和批准。</li></ul></td></tr><tr><td>更改期间</td><td><ul><li>为 Windows 10 和 Office 365 客户端发布和部署每月安全更新和非安全更新。</li><li>监视数据信号并支持队列的影响。</li></ul></td><td><ul><li>检查 Microsoft 托管桌面消息中心并查看任何其他信息。</li><li>   执行所需的任何操作（如果适用），并测试应用程序。</li><li>如果遇到中断/修复方案，请创建支持请求。</li></ul></td></tr><tr><td>更改后</td><td><ul><li>收集客户反馈以改进未来更改的推出。</li><li>监视数据信号并支持队列的影响。</li></ul></td><td><ul><li>与组织中的人员合作以采用更改。</li><li>   查看更改和采用管理流程，以提高提高效率的机会。</li><li>在管理员反馈工具中提供常规反馈和特定反馈。</li><li>使用 Windows 反馈中心和 Office 应用中的笑脸按钮培训用户，以提供特定于应用的反馈。</li></ul></td></tr>
<table> 






### <a name="change-types"></a>更改类型

将定期对服务进行多种类型的更改。 这些更改的通信通道和客户负责的操作会有所不同。

并不是所有的更改都会对您的用户产生相同的影响，或需要采取操作。 有些人按照自己的性质规划和一些计划外（非安全更新和安全更新通常不规划）。 根据更改的类型，通信通道可能会有所不同。 下表列出了 Microsoft 托管桌面服务可预期的更改类型。

|   | 功能 |   非安全更新 |  安全性
--- | --- | --- | ---
**更改类型** | -功能更新<br>-新功能或应用程序<br>-弃用的功能 | 针对问题的客户端修补程序 | 安全修补程序
**预先通知** | 5天通知需要操作的更改 |    否，这些都包含在每月发布中   | 否，这些都包含在每月发布中 
**信道** | -消息中心<br>-电子邮件通知 | -消息中心<br>-电子邮件通知 | -消息中心<br>-电子邮件通知
**需要租户管理操作** | 有时 |  很少 |    很少 
**操作类型** | 更改设置 | 将更改传达给用户 | 更改管理员设置     
**需要测试** | 检查业务应用程序，包括远程访问服务 |  有时 - 针对流程或自定义项测试修补程序 |   很少 
**更改示例** | -功能更新： IT 管理员门户简化了支持票证提交和审核<br>-新功能或应用程序： Windows 10 功能更新的半年发布 | 基于客户报告的 bug 的修补程序 |  


## <a name="standard-operating-procedures"></a>标准操作过程

Microsoft 托管桌面服务由 Microsoft 在你可以执行其他管理活动的 Microsoft 云实例中实施和运行。 Microsoft 独自负责 Microsoft 托管的特定于桌面的安装、配置和操作。 

对于本地产品，贵组织承担管理设置、配置和操作活动的所有责任。

类别 |    Microsoft 将 | 客户将
--- | --- | ---
网络（代理、数据包检查、VPN）  | 建议并与客户进行规划，以最大限度地降低企业用户的风险。 | -创建针对计划配置更改请求信息的支持请求，包括配置详细信息、范围、时间线以及 Microsoft 评审的其他相关详细信息。<br>-仅在 Microsoft 托管桌面操作经过评估和建议后才应用更改。
服务帐户 |-实施、安全地存储和管理凭据。<br> -对安全操作团队进行未经授权的访问或使用这些凭据。 | -创建针对计划配置更改请求信息的支持请求，包括配置详细信息、范围、时间线以及 Microsoft 评审的其他相关详细信息。<br>-仅在 Microsoft 托管桌面操作经过评估和建议后才应用更改。<br>-不向 Microsoft 托管桌面服务帐户分配策略、多重身份验证、条件访问或应用程序部署。<br>-不重置密码或使用凭据。<br>-如果在 Intune 或 Azure 审核日志中观察到与这些服务帐户相关的可疑活动，请打开严重级别 C 支持对 Microsoft 托管桌面操作的请求。
设备组 | -在 Microsoft 托管桌面组中实施和管理设备的成员身份。<br>-使用 Microsoft 托管桌面组来管理对设备的配置和更新的分配和发布。 | -创建针对计划配置更改请求信息的支持请求，包括配置详细信息、范围、时间线以及 Microsoft 评审的其他相关详细信息。<br>-仅在 Microsoft 托管桌面操作经过评估和建议后才应用更改。<br>-不修改任何 Microsoft 托管桌面组的成员身份。<br>-仅使用组为服务（如 VPN、Windows Hello 企业版或电子邮件加密）或公司 Wi-fi 配置文件配置分配企业证书。<br>-存在共同管理，请在部署 Configuration Manager 客户端时显式排除所有 Microsoft 托管桌面组。
策略 |  -实施和管理 Microsoft 托管桌面策略，以控制服务中设备的配置状态。<br>-将更新部署到策略或 Windows，以增量方式使用设备组。<br> -显式排除针对非 Microsoft 托管桌面组的目标。 | -创建针对计划配置更改请求信息的支持请求，包括配置详细信息、范围、时间线以及 Microsoft 评审的其他相关详细信息。<br>-仅在 Microsoft 托管桌面操作经过评估和建议后才应用更改。<br>-不编辑 microsoft 托管桌面服务不管理的设备或用户的 Microsoft 托管桌面策略或将其分配给这些策略。
Microsoft Defender 高级威胁防护   | 监视和调查 Microsoft 托管桌面服务范围内的设备。 | -创建针对计划配置更改请求信息的支持请求，包括配置详细信息、范围、时间线以及 Microsoft 评审的其他相关详细信息。<br>-仅在 Microsoft 托管桌面操作经过评估和建议后才应用更改
适用于企业的 Microsoft Store |  为 Microsoft 托管桌面服务配置和维护 Windows Autopilot 配置文件。 | -创建针对计划配置更改请求信息的支持请求，包括配置详细信息、范围、时间线以及 Microsoft 评审的其他相关详细信息。<br>-仅在 Microsoft 托管桌面操作经过评估和建议后才应用更改。<br>-不修改 Microsoft 托管桌面 Windows Autopilot 配置文件或添加/删除分配的设备的配置。
证书 | | -在证书即将过期之前的60天内创建支持请求，并请求有关计划配置更改的信息，包括有关 Microsoft 审查的配置详细信息、范围、时间线和其他相关详细信息。<br>-仅在 Microsoft 托管桌面操作经过评估和建议后才应用更改。<br>-更新配置证书配置文件、VPN 配置文件和 Wlan 配置文件所需的所有证书。




## <a name="device-wipe-with-factory-reset"></a>具有恢复出厂设置的设备擦除

Microsoft 托管桌面操作团队可在需要时执行在服务中注册的设备的出厂重置。 如果需要将设备提供给不同的员工，或者员工离开了你的公司，这将非常有用。 

有几个要求：

- 客户的租户管理员必须提交服务请求
- 我们需要设备的计算机名称
- 在重置之前，用户帐户必须在 Azure AD 中

托管桌面操作团队将：

- 在 Intune 中查找设备名称
- 将出厂重置命令发送到设备

>[!NOTE]
>在恢复出厂设置之前，请勿从 Azure AD 中删除用户帐户。 如果用户不在 Azure AD 中，Intune 将无法将出厂重置命令发送到设备。 

设备将引导进入 OOBE，并将再次应用所有预安装的应用程序和设置。 设备用户需要提供初始设置信息。 

重置设备后，可以将其提供给组织中的其他人。 以前的用户数据或企业数据将不在设备上。 下一个用户将完成与上一个用户使用新的 Microsoft 托管桌面设备所做的相同的过程。

BitLocker 是此过程中数据安全的关键组成部分。 在 Microsoft 托管桌面设备上使用 BitLocker 加密时，即使在将出厂重置应用于设备之后，驱动器上的数据仍然是安全的。 驱动器上的所有数据将对该设备的下一个用户不可用。 有关详细信息，请参阅[BitLocker 概述](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。

有关详细信息，请参阅[Factory reset a device](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device)。 
