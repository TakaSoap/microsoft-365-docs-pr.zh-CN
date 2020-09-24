---
title: 设备配置
description: 了解适用于 Microsoft 托管桌面设备的默认策略。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a76bae70adeb07d9ea0574a25bac14f89a0a790d
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262213"
---
# <a name="device-configuration"></a>设备配置


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

在设置新的 Microsoft 托管桌面设备时，我们确保其具有针对 Microsoft 托管桌面的正确配置优化。 这包括设置为加入过程的一部分的一组默认策略。 只要可能，就会使用移动设备管理 (MDM) 提供这些策略。 有关详细信息，请参阅 [移动设备管理](https://docs.microsoft.com/windows/client-management/mdm/)。 

>[!NOTE]
>若要避免冲突，请不要更改这些策略。

设备将会收到签名图像，然后在第一个用户登录时加入 Azure Active Directory 域。 设备将自动安装所需的策略和应用程序，而无需任何其他 IT 人员干预。

## <a name="default-policies"></a>默认策略

此表突出显示在设备预配过程中应用于所有 Microsoft 托管桌面设备的默认策略。 所有检测到的 Microsoft 托管桌面操作团队未批准的更改将还原为 Microsoft 托管桌面管理的对象。

Policy | Description
--- | ---
安全基准 | 针对所有 Microsoft 托管桌面设备配置了适用于 MDM 的[microsoft 安全基准](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。 此基准是业界标准的配置。 它已公开发布、经过充分测试，并已由 Microsoft 安全专家进行了检查，以保持 Microsoft 托管桌面设备和应用在新式工作区中的安全。 <br><br>为了缓解不断发展的安全威胁中的威胁，Microsoft 安全基准将更新并部署到 Microsoft 托管桌面设备（每个 Windows 10 功能更新）。<br><br>有关详细信息，请参阅 [Windows 安全基准](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)。
Microsoft 托管桌面建议的安全模板 | 对安全基准的一组建议更改，以优化用户体验。  这些更改记录在 [安全附录](#security-addendum)中。 策略附录更新根据需要进行。  
更新部署 | 使用 Windows Update for Business 执行软件更新的逐步部署。 IT 管理员无法修改部署组策略的设置。 有关基于组的部署的详细信息，请参阅 [如何在 Microsoft 托管桌面中处理更新](updates.md)。
按流量计费的连接 | 默认情况下，通过按流量计费的连接 (（如 LTE 网络) ）进行更新，尽管每个用户都可以在 **设置 > 更新 > 高级选项**中单独打开此功能。 如果您希望允许所有用户通过按流量计费的连接启用更新，请 [提交更改请求](../working-with-managed-desktop/admin-support.md)，这将为所有设备启用此设置。
| 设备合规性 | 这些策略是针对所有 Microsoft 托管桌面设备进行配置的。 当设备从我们所需的安全配置中 drifts 时，该设备将报告为不合规。

## <a name="windows-diagnostic-data"></a>Windows 诊断数据

 设备将设置为在已知商业版标识符下向 Microsoft 提供增强的诊断数据。 在 Microsoft 托管桌面中，IT 管理员不能更改这些设置。 对于常规数据保护法规中的客户 (GDPR) 地区，用户可以减少提供的诊断数据的级别，但会降低服务。 例如，Microsoft 托管桌面将无法收集必要的数据，以对设置和策略进行迭代以最好地满足性能和安全性需求。 有关详细信息，请参阅 [在组织中配置 Windows 诊断数据。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>安全附录

 本节概述除了 [默认策略](#default-policies)中列出的标准 Microsoft 托管桌面策略之外，将部署的策略。 此配置旨在满足金融服务和高度管控行业的需求，并在保持用户工作效率的同时优化最高安全性。

 ### <a name="additional-security-policies"></a>其他安全策略

 添加这些策略是为了提高高度管控行业的安全性。 
 - **安全监视**： microsoft 将使用 [Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)监视设备。 如果检测到威胁，Microsoft 将通知客户，隔离设备，并远程纠正问题。 
 - **Disable Powershell v2**： Microsoft 在8月2017的 powershell 中删除了 powershell v2。 此功能已在所有 Microsoft 托管桌面设备上禁用。 有关此更改的详细信息，请参阅 [Windows PowerShell 2.0 弃用](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。
