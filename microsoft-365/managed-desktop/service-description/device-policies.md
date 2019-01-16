---
title: 设备配置
description: 了解 Microsoft 托管桌面设备应用于的默认策略。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865846"
---
# <a name="device-configuration"></a>设备配置


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

正在设置新的 Microsoft 托管桌面设备时, 我们确保正确配置，针对 Microsoft 托管桌面中，优化是就地。这包括一组作为入职培训过程的一部分设置的默认策略。为了避免冲突，不应更改这些策略。 

设备将到达签名图像，然后加入的 Azure Active Directory 域的第一个用户登录时。设备将自动安装所需的策略和应用程序无需任何所需的 IT 干预。

## <a name="why-mdm-over-group-policy"></a>为什么 MDM 通过组策略

有几个原因而不是组策略使用移动设备管理 (MDM):

- 安全性-MDM 策略会更加安全现代世界。组策略旨在最适合于本地标识时 MDM 旨在最适合于云标识管理 (Azure Active Directory)。
- 可靠性-MDM 策略提供了更可靠的策略部署。此外，MDM 设置覆盖的组策略对象 (GPO) 策略。开头 Windows 10，版本 1803、 MDM 设置将它们优先于组策略值，其中将移至现代管理的客户提供支持。 
- 符合 Microsoft 托管桌面远景-提供更全面监控策略部署和支持通过功能要暂停 / 继续部署在必要时逐步推出策略更改基于组的方法。

有关详细信息，请参阅[Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/)。 

## <a name="default-policies"></a>默认策略

此表重点介绍设备设置过程中应用于所有 Microsoft 托管桌面设备的默认策略。所有检测到未批准由 Microsoft 托管桌面操作团队对由 Microsoft 托管桌面的对象的更改将被还原。

策略 | 说明
--- | ---
安全基准 | [Microsoft 安全基准](https://docs.microsoft.com/windows/device-security/windows-security-baselines)MDM 配置的所有 Microsoft 托管桌面设备。此比较基准的行业标准配置。它公开发布之后，还测试，并由 Microsoft 安全专家保留 Microsoft 托管桌面设备已审阅并在现代工作区安全应用程序。<br><br>以缓解威胁不断增加的安全威胁环境中，将更新的 Microsoft 安全基准并将其部署到每个 Windows 10 功能更新 Microsoft 托管桌面设备。<br><br>有关详细信息，请参阅[Windows 10 的安全基准](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)。
Microsoft 托管桌面推荐安全模板 | 一套安全基准对建议优化的用户体验的更改。 [安全附录](#security-addendum)中记录了这些更改。根据需要更新策略将 addendum 发生。  
设备合规性 | 默认情况下，所有 Microsoft 托管桌面设备配置这些策略。设备报告为非符合不满足以下安全条件之一时：<br>-BitLocker 设备加密启用，以免设备上的数据。有关详细信息，请参阅[概述的 BitLocker 设备加密 Windows 10 中。](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>安全启动启用并强制执行，以验证设备上的固件映像，可以执行之前。有关详细信息，请参阅[安全引导和设备加密概述。](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Microsoft 托管桌面设备需要登录的密码。
更新部署 | 用于 Windows Update for Business (WUfB) 执行逐步部署软件更新。IT 管理员不能修改部署组策略设置。基于组的部署的详细信息，请参阅[如何处理更新](../working-with-managed-desktop/updates.md)。
遥测 | 将设置设备的已知商业标识符下向 Microsoft 提供增强的诊断数据。作为 Microsoft 托管桌面的一部分，IT 管理员可以更改这些设置。客户通常数据保护法规 (GDPR) 区域，最终用户可以降低的诊断数据提供，但将服务中的减少。例如，Microsoft 托管桌面将无法收集上的设置和策略最佳提供性能和安全需求循环访问所必需的数据。有关详细信息，请参阅[组织中的配置 Windows 诊断数据。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>安全附录

 本节概述了将与标准 Microsoft 托管桌面策略为其他部署的策略。标准的策略列出了[默认策略](#default-policies)。此配置设计与金融服务和记住高度规范化行业： 为最安全的方案中，优化同时维护用户工作效率。

 ### <a name="additional-security-policies"></a>其他安全策略

 添加这些策略来提高安全性高度规范化行业。 
 - **应用程序允许列表**： 要在 Microsoft 托管桌面设备上运行的组织必须受信任应用程序。这可以锁定的环境。必须向 Microsoft 托管桌面操作团队传达需要 onboarded 任何应用程序。有关详细信息，请参阅[Windows Defender 设备 Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)。
 - **安全监控**： Microsoft 将监视使用[Windows Defender 高级威胁保护](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)设备。如果检测到威胁，Microsoft 将通知客户、 隔离该设备，以及远程纠正此问题。 

