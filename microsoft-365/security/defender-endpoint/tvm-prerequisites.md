---
title: 权限&的先决条件 - 危险和漏洞管理
description: 在开始使用危险和漏洞管理，请确保您具有相关的配置和权限。
keywords: 威胁& 漏洞管理权限先决条件、危险和漏洞管理权限先决条件、适用于 Endpoint TVM 的 Microsoft Defender 权限先决条件漏洞管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c3bb52686c43afca710dbe8842463c493a15e140
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206729"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>权限&的先决条件 - 危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

确保你的设备：

- 已载入到 Microsoft Defender for Endpoint

- 运行 [支持的操作系统和平台](tvm-supported-os.md)

- 在网络中安装并部署以下强制更新，以提高漏洞评估检测速率：

  > 发布 | 安全更新 KB 编号和链接
  > :---|:---
  > Windows 10版本 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) [和 KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
  > Windows 10版本 1803 | [KB4493464](https://support.microsoft.com/help/4493464) [和 KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
  > Windows 10版本 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
  > Windows 10版本 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- 已[载入Microsoft Intune Microsoft Endpoint Configuration Manager](/mem/intune/fundamentals/what-is-intune)以帮助修正由[](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)危险和漏洞管理 发现的威胁。 如果你使用的是 Configuration Manager，请更新控制台到最新版本。

  > [!NOTE]
  > 如果启用了 Intune 连接，则创建修正请求时可以选择创建 Intune 安全任务。 如果未设置连接，则不显示此选项。

- 具有至少一个可在设备页面中查看的安全建议

- 已标记或标记为共同管理

## <a name="relevant-permission-options"></a>相关权限选项

1. 使用分配Microsoft 365 Defender全局管理员角色的帐户登录门户。
2. 在导航窗格中，选择"设置 >**终结点>角色"。**

有关详细信息，请参阅为基于角色 [的访问控制创建和管理角色](user-roles.md)。

### <a name="view-data"></a>查看数据

- **安全操作** - 在门户中查看所有安全操作数据
- **威胁漏洞管理**- 危险和漏洞管理门户中查看数据

### <a name="active-remediation-actions"></a>可用修正操作

- **安全操作** - 执行响应操作、批准或消除挂起的修正操作、管理自动化和指示器的允许/阻止列表
- **威胁和漏洞管理 - 异常处理**- 创建新的异常和管理活动异常
- **威胁和漏洞管理 - 修正处理**- 提交新的修正请求、创建票证和管理现有修正活动

有关详细信息，请参阅 [RBAC 权限选项](user-roles.md#permission-options)

## <a name="related-articles"></a>相关文章

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [支持的操作系统和平台](tvm-supported-os.md)
- [分配设备值](tvm-assign-device-value.md)
- [威胁和漏洞管理仪表板](tvm-dashboard-insights.md)

