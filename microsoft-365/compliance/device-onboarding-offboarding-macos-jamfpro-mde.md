---
title: 使用适用于 Microsoft Defender for Endpoint 客户的 JAMF Pro 将 macOS 设备载入和卸载到合规性解决方案（预览版）
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: '了解如何使用适用于 Endpoint 客户的 JAMF Pro 将 macOS 设备载入和载出到 Microsoft 365 合规性解决方案中， (预览版) '
ms.openlocfilehash: f260d901f8f02c2c02007b2cc0d49ab9ee57dafd
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716312"
---
# <a name="onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview"></a>使用适用于 Microsoft Defender for Endpoint 客户的 JAMF Pro 将 macOS 设备载入和卸载到合规性解决方案（预览版）

可以使用 JAMF Pro macOS 设备载入Microsoft 365合规性解决方案。

> [!IMPORTANT]
> 如果你 ***已经将*** Microsoft Defender for Endpoint (MDE) macOS 设备，请使用此过程

**适用于：**

- 将 MDE 部署到其 macOS 设备的客户。
- [Microsoft 365终结点数据丢失防护 （DLP）](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)


## <a name="before-you-begin"></a>开始之前

- 确保你的 [macOS 设备通过 JAMF 专业](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)版进行管理，并通过 JAMF 或 Intune (Azure AD UPN) 标识连接关联。
- 在 macOS 设备上安装 v95+ Edge 浏览器

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>使用 JAMF Microsoft 365将设备载入到合规性Pro

将 macOS 设备载入合规性解决方案是一个多阶段过程。

### <a name="download-the-configuration-files"></a>下载配置文件

1. 此过程需要这些文件。

|文件所需的 |source |
|---------|---------|
|辅助功能 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
完全磁盘访问     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|MDE 首选项 |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/schema/schema.json)

> [!TIP]
> 您可以单独下载 *.mobileconfig* 文件，也可以将这些文件下载到包含以下项的 [单个](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 组合文件中：
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
>
>如果其中任何一个文件已更新，则需要再次下载组合的文件或单独下载单个更新的文件。

### <a name="update-the-existing-mde-preference-domain-profile-using-the-jamf-pro-console"></a>使用 JAMF PRO 控制台更新现有 MDE 首选项域配置文件

1. 使用schema.xml **的 schema.json** 文件更新该配置文件。

1. 在 **"MDE 首选项域属性"下** ，选择这些设置
    - 功能 
        - 使用系统扩展： `enabled` - 对于加泰罗尼亚语上的网络扩展是必需的
        - 使用数据丢失防护： `enabled`

1. 选择" **范围"** 选项卡。

1. 选择要将此配置文件部署到的组。

1. 选择“**保存**”。 

### <a name="update-the-configuration-profile-for-grant-full-disk-access"></a>更新配置文件以授予完全磁盘访问权限

1. 使用 **fulldisk.mobileconfig** 文件更新现有完整磁盘访问配置文件。

1. Upload **fulldisk.mobileconfig 文件** 更新为 JAMF。 请参阅[使用 JAMF 部署自定义配置文件Pro](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)。

### <a name="grant-accessibility-access-to-dlp"></a>授予对 DLP 的辅助功能访问权限

1. 使用之前下载的 accessibility.mobileconfig 文件。

1. Upload JAMF，如[使用 Jamf](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro) 部署自定义配置文件中所述Pro。

### <a name="check-the-macos-device"></a>检查 macOS 设备 

1. 重新启动 macOS 设备。

1. 打开 **"系统首选项** > **""文件"**。

1. 你应该会看到：
    - 辅助性
    - 完全磁盘访问
    - 内核扩展配置文件
    - MAU
    - MDATP 载入
    - MDE 首选项
    - 管理配置文件
    - 网络筛选器
    - 通知
    - 系统扩展配置文件

## <a name="offboard-macos-devices-using-jamf-pro"></a>使用 JAMF 设备的载 macOS Pro

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。

若要将 macOS 设备载出，请按照以下步骤操作

 1. 在 **"MDE 首选项域属性"** 下，删除这些设置的值
    - 功能 
        - 使用系统扩展
        - 使用数据丢失防护

1. 选择“**保存**”。
