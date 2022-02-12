---
title: 可下载的准备情况评估检查器
description: 检查设备和网络设置，包括所需的终结点
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 9e3ad0953cdbd6561f9a0145ccff5aefe24b8dfb
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62765608"
---
# <a name="downloadable-readiness-assessment-checker"></a>可下载的准备情况评估检查器

若要很好地使用Microsoft 托管桌面，设备必须满足硬件和设置的某些要求。 每台设备必须能够到达关键终结点。

下载并运行准备情况评估检查工具，以获取 HTML 报告、查看结果并采取措施。 必须下载该工具和支持文件。 然后，在你想要在设备上注册的每台设备上手动Microsoft 托管桌面。

对于每个检查，该工具将报告三个可能的结果之一：

| 结果 | 含义 |
| ----- | ----- |
| Ready | 完成注册前无需任何操作。 |
| 公告 | 按照工具中的步骤操作，实现注册和用户的最佳体验。 <br><br> *你可以完成* 注册，但在部署第一台设备之前必须修复这些问题。 |
| 未就绪 | **如果不修复** 这些问题，注册将失败。 <br><br> 按照工具中的步骤进行解析。 |

## <a name="obtain-the-checker"></a>获取检查器

从 下载.zip文件 https://aka.ms/mmddratoolv0。

> [!NOTE]
> 运行该工具的用户必须在运行该工具的设备上具有本地管理员权限。

**若要运行该工具，需要执行以下操作：**

1. 将下载.zip文件复制到你想要检查的每个设备。
2. 在压缩的下载中解压缩所有文件。
3. 运行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**。
4. 出现"用户访问控制"提示时，选择" **是"**。 该工具将运行，并打开默认浏览器中的报告。

还可以下载并提取.zip存档到共享位置，从 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe访问邮箱** 。 然后，在本地运行它。

## <a name="checks"></a>检查

可下载的工具会检查这些设备和网络相关项：

| 支票 | 说明 |
| ----- | ----- |
| 硬件 | 设备必须满足特定的硬件要求，以使用Microsoft 托管桌面。 有关详细信息，请参阅设备 [要求](../service-description/device-list.md)。 <br><br> 如果你的设备未通过任何检查，它将与Microsoft 托管桌面。 |
| 网络终结点 | 设备能够访问多个关键[终结点，](network.md)以使用Microsoft 托管桌面。 <br><br> 如果工具报告 **"未** 准备好"结果，请参阅详细报告，了解哪些终结点不可访问。 然后，调整防火墙或其他网络设置以确保可以到达这些终结点。 |

### <a name="other-settings"></a>其他设置

| Setting | 说明 |
| ----- | ----- |
| Enterprise Wi-Fi配置文件 | **公告结果** 意味着你正在使用某些需要证书Wi-Fi配置文件正常运行的配置文件。 有关详细信息，请参阅 [部署证书和 WI-Fi/VPN 配置文件](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。 |
| LAN 配置文件 | **公告结果** 意味着你拥有需要证书和配置文件来正常工作的 LAN。 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面](certs-wifi-lan.md)。 |
| VPN 配置文件 | **公告结果** 意味着你正在使用虚拟专用网络 (VPN) 。 创建部署与证书集成的证书的 VPN Microsoft Intune。 有关详细信息，请参阅准备[证书和网络配置文件Microsoft 托管桌面](certs-wifi-lan.md)。 |
| 映射的驱动器 | **公告结果** 意味着你有一些映射的驱动器，不建议这样做。 有关详细信息，请参阅为[驱动器准备映射Microsoft 托管桌面](mapped-drives.md)。 |
| 打印队列 | **公告结果** 意味着有一些未完成的打印队列，不建议这样做。 一个解决方案是使用云打印。 有关详细信息，请参阅准备[打印资源以用于Microsoft 托管桌面](printing.md)。 |
| 代理 | **公告结果** 意味着您使用了代理服务器。 有关详细信息，请参阅 Network [configuration for Microsoft 托管桌面](network.md)。 |
