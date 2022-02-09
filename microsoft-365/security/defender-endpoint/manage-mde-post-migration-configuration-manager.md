---
title: 使用 Configuration Manager 管理 Microsoft Defender for Endpoint
description: 了解如何使用 Configuration Manager 管理 Microsoft Defender for Endpoint
keywords: 迁移后， 管理， 操作， 维护， 利用率， Configuration Manager， Microsoft Defender for Endpoint， edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 11/29/2021
ms.reviewer: chventou
ms.openlocfilehash: 40bac47a4c22e3a8706ed4b38b479fff5d500410
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62465224"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>使用 Configuration Manager 管理 Microsoft Defender for Endpoint

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。


我们建议使用 [Microsoft Endpoint Manager](/mem)，其中包括Microsoft Intune[ (](/mem/intune/fundamentals/what-is-intune) Intune) 和 [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) 管理组织对也称为终结点 (的设备的威胁防护) 。

- [详细了解Endpoint Manager](/mem/endpoint-manager-overview)
- [使用 Configuration Manager 和 Intune 在 Windows 10 和 Windows 11 设备上共同管理 Microsoft Defender for Endpoint](manage-mde-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>使用 Configuration Manager 配置 Microsoft Defender for Endpoint

<br/><br/>

|任务|了解详细信息的资源|
|---|---|
|**安装 Configuration Manager** 控制台（如果尚未安装） <br/><br/> *如果你还没有配置管理器控制台，请使用这些资源获取位并安装它。*|[获取安装媒体](/mem/configmgr/core/servers/deploy/install/get-install-media) <br/><br/> [安装 Configuration Manager 控制台](/mem/configmgr/core/servers/deploy/install/install-consoles)|
|**使用 Configuration Manager 将设备载入** 到 Microsoft Defender for Endpoint <br/><br/> *如果你的设备已 (或) 尚未载入到 Microsoft Defender for Endpoint，可以使用 Configuration Manager 完成这一操作。*|[使用 Configuration Manager 载入到 Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)|
|**管理客户端计算机和 Windows** 终结点的反恶意软件策略 (防火墙)  <br/><br/> *配置终结点保护功能，包括适用于终结点的 Microsoft Defender、Exploit Protection、应用程序控制、反恶意软件、防火墙设置等。*|[Configuration Manager：Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)|
|**选择在组织设备上更新** 反恶意软件更新的方法 <br/><br/> *使用Endpoint Protection管理器中，你可以选择多种方法使反恶意软件定义在组织设备上保持最新。*|[配置终结点保护的定义更新](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/> [使用 Configuration Manager 提供定义更新](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr)|
|**启用网络** 保护以帮助防止员工使用 Internet 上恶意内容的应用 <br/><br/> *我们建议在 [测试环境中首先](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 使用审核模式进行网络保护，以查看在推出之前哪些应用将被阻止。*|[使用 Configuration Manager 打开网络保护](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)|
|**配置受控文件夹访问权限** 以防范勒索软件 <br/><br/> *受控文件夹访问权限也称为反反somware保护。*|[终结点保护：受控文件夹访问权限](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/> [在 Microsoft Endpoint Configuration Manage 中启用受控文件夹访问权限](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager)|

## <a name="configure-your-microsoft-365-defender-portal"></a>配置Microsoft 365 Defender门户

如果尚未配置，请配置 Microsoft 365 Defender 门户以查看警报、配置威胁防护功能，并查看有关组织整体安全状况的详细信息。 See While the attack was detected and stopped， alerts， such as a "initial access alert，" was triggered and appeared in the [Microsoft 365 Defender portal](/microsoft-365/security/defender/microsoft-365-defender). 还可以配置最终用户是否可以在网站门户中查看这些功能Microsoft 365 Defender功能。

- [概述Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [终结点保护：Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>后续步骤

- [获取威胁和漏洞管理的概述](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [访问 Microsoft 365 Defender门户安全操作仪表板](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
- [使用 Intune 管理 Microsoft Defender for Endpoint](manage-mde-post-migration-intune.md)
