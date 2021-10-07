---
title: 创建 IP 和 URL/域指示器
ms.reviewer: ''
description: 为定义实体的检测、防护和排除的 IP 和 URL/域创建指示器。
keywords: ip， url， 域， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0aaeb4a290c43b8fc725fe806014acfe61a939e8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150016"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>创建 IP 和 URL/域指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)。

Defender for Endpoint 可以阻止 Microsoft 视为恶意 IP/URL、通过适用于 Microsoft 浏览器的 Windows Defender SmartScreen，以及针对非 Microsoft 浏览器或在浏览器外进行调用的网络保护。

针对这一点的威胁情报数据集已由 Microsoft 管理。

通过创建 IP 和 URL 或域的指示器，你现在可以基于自己的威胁情报允许或阻止 IP、URL 或域。 如果用户打开有风险的应用，也可以提示他们。 提示不会阻止他们使用应用，但你可以提供一条自定义消息和指向描述应用相应使用情况的公司页面的链接。 用户仍可以绕过警告，并如果需要继续使用该应用。


如果你认为某些组的风险大于或低于其他组，可以通过设置页面或计算机组来这样做。

> [!NOTE]
> 不支持Inter-Domain IP 地址 (CIDR) 表示法进行无类别路由。

## <a name="before-you-begin"></a>准备工作
在创建 IPS、URL 或域的指示器之前，了解以下先决条件非常重要：

- URL/IP 允许和阻止依赖于 Defender for Endpoint 组件网络保护在阻止模式下启用。 有关网络保护和配置说明详细信息，请参阅启用 [网络保护](enable-network-protection.md)。
- 反恶意软件客户端版本必须为 4.18.1906.x 或更高版本。
- 在 Windows 10 版本 1709 或更高版本或 Windows 11 上支持。
- 确保自定义 **网络指示器在** 终结点Microsoft 365 Defender > 设置 >高级>**启用**。 有关详细信息，请参阅高级 [功能](advanced-features.md)。
- 有关 iOS 上的指示器支持，请参阅 [配置自定义指示器](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)。

> [!IMPORTANT]
> 只能将外部 IP 添加到指示器列表。 无法为内部 IP 创建指示器。
> 对于 Web 保护方案，我们建议使用 Web 保护中的内置Microsoft Edge。 Microsoft Edge网络保护[来](network-protection.md)检查网络流量并允许阻止 TCP、HTTP 和 HTTPS (TLS) 。
> 如果存在冲突的 URL 指示器策略，则应用较长的路径。 例如，URL 指示器策略 `https:\\support.microsoft.com/office` 优先于 URL 指示器策略 `https:\\support.microsoft.com` 。

> [!NOTE]
> 对于所有其他进程，Web 保护方案利用网络保护进行检查和强制执行：
>
> - 所有三种协议均支持 IP
> - 没有 CIDR 块或 IP 范围 (仅支持单个 IP 地址) 
> - 只有在第一 (浏览器、边缘) ，才能阻止加密的 URL (Internet Explorer完整路径) 
> - 加密的 URL (FQDN) 可以在第一方浏览器或边缘 (Internet Explorer外部阻止) 
> - 完整 URL 路径块可以应用于域级别以及所有未加密的 URL
>
> 延迟时间可能最多为 2 小时 (通常) 操作和阻止 URL 和 IP 之间的延迟时间通常较少。

使用警告模式时，可以配置以下控件：

**绕过功能**：

- Edge 中的"允许"按钮
- Toast 和非 Microsoft (上的"允许") 
- 指示器上的绕过持续时间参数
- 跨 Microsoft 和非 Microsoft 浏览器绕过强制

**重定向 URL：**

- 指示器上的重定向 URL 参数
- Edge 中的重定向 URL
- Toast 上的重定向 URL (非 Microsoft 浏览器) 

有关详细信息，请参阅管理 [Microsoft Defender for Endpoint 发现的应用](/cloud-app-security/mde-govern)。

## <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>从设置页面为 IP、URL 或域创建指示器

1. 在导航窗格中，选择"设置 \> **规则"** 下 (\> **终结点**) 。

2. 选择 **"IP 地址或 URL/域"** 选项卡。

3. 选择 **"添加项目"。**

4. 指定以下详细信息：
   - 指示器 - 指定实体详细信息并定义指示器的过期时间。
   - 操作 - 指定要采取的操作并提供说明。
   - Scope - 定义计算机组的范围。

5. 查看"摘要"选项卡中的详细信息，然后单击"保存 **"。**

## <a name="related-topics"></a>相关主题

- [创建指示器](manage-indicators.md)
- [创建文件指示器](indicator-file.md)
- [创建基于证书的指示器](indicator-certificates.md)
- [管理指示器](indicator-manage.md)
