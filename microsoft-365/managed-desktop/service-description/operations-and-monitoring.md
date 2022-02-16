---
title: Microsoft 托管桌面操作和监视
description: Who对各种更改过程执行哪些操作
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 6b1771660cb25ccd9d23c97d1e3fcf6edd27feaa
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825212"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 托管桌面操作和监视

<!-- Operations and monitoring: -->

## <a name="change-management"></a>变更管理

在服务产品/服务中，硬件维护和安全更新的责任平衡将转移到服务提供商 (Microsoft) ，而不是 (客户) 。 但是，你仍然必须确保非 Microsoft 和自定义软件在推出更新时继续正常工作。

对于本地产品，组织承担管理更改的所有责任。

### <a name="balance-of-responsibility"></a>责任平衡

| 职责 | Microsoft 托管桌面服务 | Microsoft 365客户端软件 | 本地客户端和服务器 | 非 Microsoft 和自定义软件
| ----- | ----- | ----- | ----- | ----- |
| 提供新功能 | Microsoft | Microsoft | 两者都有 | 客户
| 测试新功能用于质量保证 |  Microsoft | Microsoft | 两者都有 | 客户
| 交流新功能 | 两者都有 | 两者都有 | 两者都有 | 客户
| 集成自定义软件 | 两者都有 | 两者都有 | 客户 | 客户
| 应用安全更新程序 | Microsoft | Microsoft | 客户 | 客户
| 维护系统软件 | Microsoft | Microsoft | 客户 | 客户
| 用于部署的程序包 | Microsoft | Microsoft | 客户 | 客户

### <a name="change-process-overview"></a>更改过程概述

下面汇总了如何在 Microsoft 与客户之间共享更改过程：

| 应用场景 | Microsoft 角色 | 客户角色 |
| ----- | ----- | ----- |
| 更改前 | <ul><li>设置服务更改的预期。</li><li>有关需要管理员操作的更改，请提前 5 天通知客户。</li><li>对于紧急更改，请在通知之前应用缓解。</li></ul> | <ul><li>了解对更改和通信的预测。</li><li>定期Microsoft 托管桌面邮件中心。</li><li>查看并升级内部更改管理过程。</li><li>了解并检查是否符合Microsoft 托管桌面要求。 </li><li>确认并批准（如果需要）。</li></ul>
| 更改期间 | <ul><li>发布和部署每月安全更新程序和非安全更新程序Windows 10 Office 365客户端。</li><li>监视数据信号和支持队列的影响。</li></ul> | <ul><li>检查Microsoft 托管桌面中心并查看任何其他信息。</li><li>执行任何所需操作（如果适用）并测试应用程序。</li><li>如果遇到中断/修复情况，请创建支持请求。</li></ul> |
| 更改后 | <ul><li>收集客户反馈，以改进未来更改的推出。</li><li>监视数据信号和支持队列的影响。</li></ul> | <ul><li>与组织人员合作以采用更改。</li><li>查看变更和采用管理流程，以获得提高效率的机会。</li><li>在管理员反馈工具中提供常规反馈和特定反馈。</li><li>培训用户使用应用中的"Windows 反馈中心和"Office反馈。</li></ul> |

### <a name="change-types"></a>更改类型

我们定期对服务进行几种类型的更改。 这些更改的信道以及你负责的操作各不相同。

并非所有更改对用户都具有相同的影响或需要操作。 一些是计划的，一些是计划外的。 例如，通常不计划非安全更新和安全更新。

根据更改的类型，信道可能会有所不同。 下表列出了您期望的 Microsoft 托管桌面 类型的更改。

|  | 功能 | 非安全更新 | 安全性 |
| ----- | ----- | ----- | ----- |
| **更改类型** | <ul><li>功能更新</li><li>新功能或应用程序</li><li>不推荐使用的功能</li></ul> | 针对问题的客户端修补程序 | 安全更新 |
**预先通知** | 有关需要操作的更改的 5 天通知 | 每月版本中不包含此类更改 | 每月版本中不包含任何更改 |
**信道** | <ul><li>消息中心</li><li>电子邮件警报</li></ul> | <ul><li>消息中心</li><li>电子邮件警报</li></ul> | <ul><li>消息中心</li><li>电子邮件警报</li></ul> |
**需要全局管理员操作** | 有时 | 很少 | 很少 |
**操作类型** | 更改设置 | 将更改传达给用户 | 更改管理员设置 |
**需要测试** | 检查包括远程访问服务在内的业务应用程序 | 有时;针对进程或自定义项测试修补程序 | 很少 |
**更改示例** | <ul><li>功能更新：IT 管理门户简化了支持票证提交和审阅</li><li>新功能或应用程序：Semi-Annual更新Windows 10发布</li></ul> | 基于客户报告的 bug 的修补程序 |

## <a name="standard-operating-procedures"></a>标准操作过程

The Microsoft 托管桌面 service is implemented and operated by Microsoft in your Microsoft cloud instance where you might conduct other administrative activities. Microsoft 仅负责Microsoft 托管桌面特定设置、配置和操作。

对于本地产品，贵组织承担管理设置、配置和操作活动的所有责任。

| 类别 | Microsoft 将 | 客户将 |
| ----- | ----- | ----- |
| 网络 (代理、数据包检查、VPN)  | 为客户提供建议和计划，以最大限度地降低业务用户的风险。 | <ul><li>创建支持请求，请求有关计划配置更改的信息。 包括 Microsoft 查看的配置详细信息、范围、日程表和其他相关详细信息。</li><li>仅在操作已评估和Microsoft 托管桌面后应用更改。</li></ul> |
服务帐户 | <ul><li>实现、安全存储和管理凭据。</li><li>将未经授权访问或使用这些凭据告知安全运营团队。</li></ul> | <ul><li>创建支持请求，请求有关计划配置更改的信息。 包括配置详细信息、范围、日程表和其他相关详细信息，供 Microsoft 查看。</li><li>仅在操作已评估和Microsoft 托管桌面后应用更改。</li><li>不向服务帐户分配策略、多重身份验证、条件访问或Microsoft 托管桌面部署。</li><li>不要重置密码或使用凭据。</li><li>如果 Intune 或 Azure 审核日志中发现与这些服务帐户Microsoft 托管桌面可疑活动，请打开 Sev C 支持请求以执行安全操作。</li></ul>
| 设备组 | <li> 实现和分配组内设备Microsoft 托管桌面成员身份。</li><li>使用Microsoft 托管桌面组管理配置和更新的分配和发布。</li></ul> | <ul><li>创建支持请求，请求有关计划配置更改的信息。 包括配置详细信息、范围、日程表和其他相关详细信息，供 Microsoft 查看。</li><li>仅在操作已评估和Microsoft 托管桌面后应用更改。</li><li>仅按照将设备分配给Microsoft 托管桌面组中所述的步骤将设备[分配给任何组](../working-with-managed-desktop/assign-deployment-group.md)。</li><li>仅使用这些组为 VPN、Windows Hello或电子邮件加密或公司 wifi 配置文件配置等服务分配公司证书。</li><li>如果存在共同管理，则部署 Configuration Manager Microsoft 托管桌面明确排除所有组。</li></ul>
| 策略 | <ul><li>实现和管理Microsoft 托管桌面服务中的设备配置状态的策略。</li><li> 使用设备组以增量Windows策略或策略部署更新。</li><li>明确排除非目标Microsoft 托管桌面组。</li></ul> | <ul><li>创建支持请求，请求有关计划配置更改的信息。 包括配置详细信息、范围、日程表和其他相关详细信息，供 Microsoft 查看。</li><li>仅在操作已评估和Microsoft 托管桌面后应用更改。</li><li>不编辑或Microsoft 托管桌面策略分配给非由 Microsoft 托管桌面 服务管理的设备或用户。
Microsoft 365 Defender终结点。</li></ul> | 监视和调查服务范围内的Microsoft 托管桌面。 | <ul><li>创建支持请求，请求有关计划配置更改的信息。 包括配置详细信息、范围、日程表和其他相关详细信息，供 Microsoft 查看。</li><li>仅在操作已评估和Microsoft 托管桌面后应用更改。</li></ul>
| 适用于企业的 Microsoft Store | 配置和维护 Windows 服务的 Autopilot Microsoft 托管桌面配置文件。 | <ul><li>创建支持请求，请求有关计划配置更改的信息。 包括配置详细信息、范围、日程表和其他相关详细信息，供 Microsoft 查看。</li><li>仅在操作已评估和Microsoft 托管桌面后应用更改。</li><li>不修改 Autopilot 配置文件Microsoft 托管桌面 Windows添加/删除分配的设备的配置。</li></ul>
| 证书 | | <ul><li>在证书到期前 60 天创建支持请求，请求有关计划配置更改的信息。 包括配置详细信息、范围、日程表和其他相关详细信息，供 Microsoft 查看。</li><li>仅在操作已评估和Microsoft 托管桌面后应用更改。</li><li>更新配置证书配置文件、VPN 配置文件和证书配置文件所需的Wi-Fi证书。</li></ul>|

## <a name="device-wipe-with-factory-reset"></a>通过恢复出厂设置的设备擦除

Microsoft 托管桌面团队可以执行恢复服务中注册的设备出厂重置（如果需要）。 如果需要将设备授予其他员工，或者员工离开公司，重置会很有帮助。

有一些要求：

- 全局管理员必须提交支持请求。
- 在请求中包括设备的计算机名称。
- 重置设备之前，用户帐户Azure AD帐户。

托管桌面操作团队将：

- 在 Intune 中查找设备名称。
- 将恢复出厂设置命令发送到设备。

> [!NOTE]
> 在重置设备之前，不要Azure AD用户帐户。 如果用户不在设备Azure AD，Intune 无法将恢复出厂设置命令发送到设备。

设备将启动到"开箱即用"体验，并且所有预安装的应用程序和设置将再次应用。 设备用户需要再次提供初始设置信息。

重置设备后，你可以将设备授予你组织的不同人员。 以前用户的数据或企业数据都不在设备上。 下一个用户将经历上一个人使用新设备Microsoft 托管桌面过程。

BitLocker 是此过程中数据安全性的一个关键组件。 在设备上使用 BitLocker Microsoft 托管桌面，即使设备已恢复出厂设置，驱动器上的数据仍保持安全。 驱动器上的任何数据将不能供设备的下一位用户使用。 有关详细信息，请参阅 [BitLocker 概述](/windows/security/information-protection/bitlocker/bitlocker-overview)。

有关详细信息，请参阅恢复 [设备出厂设置](/intune/remote-actions/devices-wipe#factory-reset-a-device)。
