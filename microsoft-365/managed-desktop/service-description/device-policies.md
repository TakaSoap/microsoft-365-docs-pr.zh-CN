---
title: 设备配置
description: 了解适用于 Microsoft 托管桌面设备的默认策略。
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a080c044939dfde223c231dfebdd248861d5f9f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278621"
---
# <a name="device-configuration"></a>设备配置


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

在预配新的 microsoft 托管桌面设备时, 请确保正确配置 (针对 Microsoft 托管桌面进行了优化) 已就绪。 这包括设置为加入过程的一部分的一组默认策略。 为避免冲突, 不应更改这些策略。 

设备将会收到签名映像, 然后在第一个用户登录时加入 Azure Active Directory 域。 设备将自动安装所需的策略和应用程序, 而无需任何 IT 干预。

## <a name="why-mdm-over-group-policy"></a>为什么 MDM over 组策略

使用移动设备管理 (MDM) 而不是组策略的原因有以下几个:

- 安全-MDM 策略在现代环境中更加安全。 组策略设计为最适用于本地标识, 而 MDM 设计为最佳使用云身份管理 (Azure Active Directory)。
- 可靠性-MDM 策略提供更可靠的策略部署。 另外, MDM 设置将覆盖组策略对象 (GPO) 策略。 从 Windows 10 版本1803开始, MDM 设置将优先于组策略值, 从而支持迁移到新式管理的客户。 
- 与 Microsoft 托管桌面远景保持一致-提供更全面的策略部署监控, 并支持基于组的方法逐步实施策略更改, 并在必要时能够暂停/恢复部署。

有关详细信息, 请参阅[移动设备管理](https://docs.microsoft.com/windows/client-management/mdm/)。 

## <a name="default-policies"></a>默认策略

此表突出显示在设备预配过程中应用于所有 Microsoft 托管桌面设备的默认策略。 所有检测到的 microsoft 托管桌面操作团队未批准的更改将还原为 microsoft 托管桌面管理的对象。

策略 | 说明
--- | ---
安全基准 | 针对所有 microsoft 托管桌面设备配置了适用于 MDM 的[microsoft 安全基准](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。 此基准是业界标准的配置。 它已公开发布、经过充分测试, 并已由 microsoft 安全专家进行了检查, 以保持 microsoft 托管桌面设备和应用在新式工作区中的安全。 <br><br>为了减轻不断演变的安全威胁的威胁, microsoft 安全基准将更新并部署到 microsoft 托管桌面设备 (每个 Windows 10 功能更新)。<br><br>有关详细信息, 请参阅[Windows 10 安全基准](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)。
Microsoft 托管桌面建议的安全模板 | 对安全基准的一组建议更改, 以优化用户体验。  这些更改记录在[安全附录](#security-addendum)中。 策略附录更新根据需要进行。  
设备合规性 | 默认情况下, 对所有 Microsoft 托管桌面设备配置这些策略。 如果不满足以下安全条件之一, 则会将设备报告为不合规:<br>-启用 BitLocker 设备加密以保护设备上的数据。 有关详细信息, 请参阅[Windows 10 中的 BitLocker 设备加密概述。](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-安全启动已启用并强制实施, 以在设备上验证固件映像, 然后才能执行。 有关详细信息, 请参阅[Secure boot and device encryption 概述。](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Microsoft 托管桌面设备需要密码才能登录。
更新部署 | 使用 Windows Update for Business (WUfB) 执行软件更新的逐步部署。 IT 管理员无法修改部署组策略的设置。 有关基于组的部署的详细信息, 请参阅[如何处理更新](../working-with-managed-desktop/updates.md)。
诊断数据 | 设备将设置为在已知商业版标识符下向 Microsoft 提供增强的诊断数据。 在 Microsoft 托管桌面中, IT 管理员不能更改这些设置。 对于一般数据保护条例 (GDPR) 区域中的客户, 最终用户可以减少提供的诊断数据的级别, 但会降低服务。 例如, Microsoft 托管桌面将无法收集必要的数据, 以对设置和策略进行迭代以最好地满足性能和安全性需求。 有关详细信息, 请参阅[在组织中配置 Windows 诊断数据。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>安全附录

 本节概述了将作为其他标准 Microsoft 托管桌面策略部署的策略。 标准策略在[默认策略](#default-policies)中列出。 此配置旨在提供金融服务和高度管控行业: 优化最安全的想法, 同时保持用户工作效率。

 ### <a name="additional-security-policies"></a>其他安全策略

 添加这些策略是为了提高高管控行业的安全性。 
 - **应用程序允许列表**: 组织必须信任应用程序才能在 Microsoft 托管桌面设备上运行。 这将提供锁定的环境。 需要载入的任何应用程序必须传递到 Microsoft 托管桌面操作团队。 有关详细信息, 请参阅[Windows Defender Device Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)。
 - **安全监视**: Microsoft 将使用[Windows Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)监视设备。 如果检测到威胁, Microsoft 将通知客户, 隔离设备, 并远程修正问题。 

