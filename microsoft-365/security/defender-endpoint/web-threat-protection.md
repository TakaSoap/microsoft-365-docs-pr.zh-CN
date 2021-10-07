---
title: 保护组织免受 Web 威胁
description: 了解 Microsoft Defender for Endpoint 中的 Web 保护及其如何保护你的组织。
keywords: Web 保护， Web 威胁防护， Web 浏览， 安全性， 网络钓鱼， 恶意软件， 攻击， 网站， 网络保护， 边缘， Internet Explorer， Chrome， Firefox， Web 浏览器
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 90775af14d78092159d2b92736abce56a961416e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159170"
---
# <a name="protect-your-organization-against-web-threats"></a>保护组织免受 Web 威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)。

Web 威胁防护是 [Defender](web-protection-overview.md) for Endpoint 中的 Web 保护的一部分。 它 [使用网络保护](network-protection.md) 保护你的设备免受 Web 威胁。 与 Chrome Microsoft Edge Firefox 等热门第三方浏览器集成后，Web 威胁防护无需 Web 代理即可阻止 Web 威胁，并可在设备离开或位于本地时保护设备。 Web 威胁防护会停止对钓鱼网站、恶意软件矢量、攻击网站、不受信任的或低信誉网站以及自定义指示器列表中阻止 [的网站的访问](manage-indicators.md)。

> [!NOTE]
> 设备可能需要一小时才能接收新的自定义指示器。

## <a name="prerequisites"></a>先决条件

Web 保护使用网络保护在 web 和第三Microsoft Edge Web 浏览器上提供 Web 浏览安全性。

若要在设备上打开网络保护，请运行：

- 编辑 Web 网络保护下的 Defender for Endpoint **&，** 以在部署或重新部署网络保护之前启用网络保护。 [了解如何查看和分配 Defender for Endpoint 安全基线](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- 使用 Intune 设备配置、SCCM、组策略或 MDM 解决方案打开网络保护。 [阅读有关启用网络保护的更多信息](enable-network-protection.md)

> [!NOTE]
> 如果将网络保护设置为"仅 **审核"，** 则阻止将不可用。 此外，你将能够仅检测并记录访问恶意和不需要的网站Microsoft Edge尝试。

## <a name="configure-web-threat-protection"></a>配置 Web 威胁防护

以下过程介绍如何使用管理中心Microsoft Endpoint Manager Web 威胁防护。

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，然后登录。
 
2. 选择 **"终结点安全** \> **攻击面减少"，** 然后选择 **"+ 创建策略"。**

3. 选择平台（如 Windows 10 **和更高版本**）选择 **Web 保护** 配置文件，然后选择"创建 **"。** 

4. 在"**基本信息"** 选项卡上，指定名称和说明，然后选择"下一步 **"。**

5. 在"**配置设置"** 选项卡上，展开 **"Web 保护"，** 指定设置，然后选择"下一步 **"。**

   - 将 **"启用网络保护****"设置为"已启用**"，以便启用 Web 保护。 或者，你可以将网络保护设置为 **审核模式** 以查看它在环境中如何工作。 在审核模式下，网络保护不会阻止用户访问网站或域，但会作为事件跟踪检测。 
   - 若要保护用户免受潜在网络钓鱼欺诈和恶意软件的攻击，请将其"要求 **SmartScreen Microsoft Edge 旧版** 为 **"是"。**
   - 若要防止用户绕过有关潜在恶意站点的警告，将阻止 **恶意站点访问** 设置为 **"是"。**
   - 若要防止用户绕过警告并下载未经验证的文件，请设置阻止 **未经验证的文件下载** tl **是**。 

6. 在"**范围标记**"选项卡上，如果组织正在使用范围标记，请选择 **"+ 选择范围标记**"，然后选择"下一步 **"。**  (如果您不使用范围标记，请选择"下一步".) 若要了解有关范围标记的信息，请参阅使用基于角色的访问控制[ (RBAC) 和](/mem/intune/fundamentals/scope-tags)适用于分布式 IT 的范围标记。 

7. 在"**分配**"选项卡上，指定要接收 Web 保护策略的用户和设备，然后选择"下一步 **"。**

8. 在"**查看 + 创建"** 选项卡上，查看策略设置，然后选择"创建 **"。**

## <a name="related-topics"></a>相关主题

- [Web 保护功能概述](web-protection-overview.md)
- [Web 威胁防护功能](web-threat-protection.md)
- [监视 web 安全性](web-protection-monitoring.md)
- [响应 web 威胁](web-protection-response.md)
- [网络保护](network-protection.md)
