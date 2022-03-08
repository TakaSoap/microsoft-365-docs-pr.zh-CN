---
title: 设备配置
description: 了解应用于设备Microsoft 托管桌面策略。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 19acff97a1541dcf6151b531696cf373e604371f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327849"
---
# <a name="device-configuration"></a>设备配置

<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

在设置Microsoft 托管桌面设备时，我们会确保配置已Microsoft 托管桌面。

配置包括一组在载入过程中设置的默认策略。 只要有可能，这些策略 (MDM) 移动设备管理。 有关详细信息，请参阅 [移动设备管理](/windows/client-management/mdm/)。

>[!NOTE]
>为避免冲突，请勿更改这些策略。

设备将到达签名图像，然后在第一Azure Active Directory登录时加入域。 设备将自动安装所需的策略和应用程序，无需 IT 人员的任何干预。

## <a name="default-policies"></a>默认策略

此表突出显示了在设备预配期间应用于Microsoft 托管桌面设备的默认策略。 将还原对未由运营Microsoft 托管桌面批准且由Microsoft 托管桌面对象的所有检测到的更改。

| 策略 | 说明
| ----- | ----- |
| 安全基线 | [针对所有](/windows/device-security/windows-security-baselines)移动设备配置了用于移动设备管理的 Microsoft Microsoft 托管桌面基线。 此基线是行业标准配置。 它公开发布、经过测试，并经过 Microsoft 安全专家审查，Microsoft 托管桌面现代工作场所中确保设备和应用安全。 <br><br>为了在不断演变的安全威胁形势中缓解威胁，Microsoft 安全基线将进行更新，并随着每个 Microsoft 托管桌面 功能更新部署到Windows 10设备。<br><br>有关详细信息，请参阅Windows[基线](/windows/security/threat-protection/windows-security-baselines)。
| Microsoft 托管桌面建议的安全模板 | 此模板是一组对安全基线的建议更改，可优化用户体验。 这些更改记录在安全附录 [中](#security-addendum)。 根据需要更新策略附录。  
| 更新部署 | 使用 Windows Update for Business 执行软件更新的逐步部署。 IT 管理员无法修改部署组策略的设置。 有关基于组部署的信息，请参阅如何在部署[中处理Microsoft 托管桌面](updates.md)。
| 按流量计费的连接 | 默认情况下，通过按流量计费的连接（ (LTE 网络) 将关闭。 但是，每个用户都可以导航到"更新"和"设置""高级"**选项来单独打开此设置**。 <br><br>如果要允许所有用户通过按流量计费的连接启用更新，请提交更改请求[](../working-with-managed-desktop/admin-support.md)，这将针对所有设备启用此设置。
| 设备合规性 | 这些策略针对所有设备Microsoft 托管桌面配置。 当设备偏离所需安全配置时，该设备被报告为不符合要求。

## <a name="windows-diagnostic-data"></a>Windows 诊断数据

 设备将设置为根据已知的商业标识符向 Microsoft 提供增强的诊断数据。 作为Microsoft 托管桌面的一部分，IT 管理员不能更改这些设置。

对于使用 GDPR 区域 (数据保护条例) ，用户可以降低提供的诊断数据级别，但服务将会减少。 例如，Microsoft 托管桌面无法收集在设置和策略上进行访问以最好地满足性能和安全需求所需的数据。 有关详细信息，请参阅在[Windows配置诊断数据。](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>安全附录

 本节概述了除了默认策略中列出的标准策略外，还将部署Microsoft 托管桌面[策略](#default-policies)。 此配置在设计时牢记金融服务和高度管控行业，并针对最高安全性进行了优化，同时保持用户工作效率。

### <a name="additional-security-policies"></a>其他安全策略

 添加了这些策略以提高高度管控行业的安全性：

| 策略 | 说明 |
| ----- | ----- |
|安全监视 | Microsoft 将监视使用 [Microsoft Defender for Endpoint 的设备](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。 如果检测到威胁，Microsoft 将通知客户、隔离设备并远程纠正问题。 |
 | 禁用 PowerShell V2 | Microsoft 在 2017 年 8 月删除了 PowerShell V2。<br><br>此功能已在所有设备上Microsoft 托管桌面禁用。 有关此更改详细信息，请参阅 Windows PowerShell [2.0 弃用](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。 |
