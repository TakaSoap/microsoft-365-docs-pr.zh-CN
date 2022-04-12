---
title: 使用 JAMF Pro 将 macOS 设备载入和卸载到 Microsoft 365 合规性解决方案（预览版）
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
description: '了解如何使用 JAMF Pro (预览版将 macOS 设备载入和卸载到Microsoft 365合规性解决方案中) '
ms.openlocfilehash: 44e57e482c08b486563200010671b5c79329f7b2
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783812"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview"></a>使用 JAMF Pro 将 macOS 设备载入和卸载到 Microsoft 365 合规性解决方案（预览版）

可以使用 JAMF Pro将 macOS 设备载入Microsoft 365合规性解决方案，例如 Endpoint 数据丢失防护。

> [!IMPORTANT]
> 如果 ***未*** 将Microsoft Defender for Endpoint (MDE) 部署到 macOS 设备，请使用此过程

**适用于：**

- [Microsoft 365终结点数据丢失防护 （DLP）](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>准备工作

- 确保 [macOS 设备通过 JAMF 专业人员进行管理](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)，并与标识关联 (Azure AD通过 JAMF 连接或Intune加入 UPN) 。
- 在 macOS 设备上安装 v95+ Edge 浏览器

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>使用 JAMF Pro将设备载入Microsoft 365合规性解决方案

1. 此过程需要这些文件。

|文件所需的文件|Source|
|---|---|
|载入包|从合规性门户 **加入包** 下载，文件名 *DeviceComplianceOnboarding.plist*|
|辅助功能|[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
完全磁盘访问|[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|网络筛选器| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)
|系统扩展|[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/sysext.mobileconfig)
|MDE 首选项|[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/schema.json)|
|MAU 首选项|[com.microsoft.autoupdate2.plist](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.plist)|
|安装包|从合规性门户 **安装包** 下载的文件名 *\*wdav.pkg*\*|

> [!TIP]
> 可以单独或在包含以下内容的 [单个组合文件](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig)中下载 *.mobileconfig* 文件：
>
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - sysext.mobileconfig
>
>如果这些单个文件中的任何一个已更新，则需要再次下载组合文件或单独下载单个更新的文件。

将 macOS 设备载入合规性解决方案是一个多阶段过程。

### <a name="get-the-device-onboarding-package"></a>获取设备载入包

1. 在 **合规中心** 打开 **设置** > **Device 载入** 并选择 **加入**。

1. 若 **要选择操作系统以启动载入过程，** 请选择 **macOS**

1. 对于 **部署方法**，请选择 **移动设备管理/Microsoft Intune**

1. 选择 **“下载载入”包**

1. 提取设备载入包的内容。 在 JAMF 文件夹中，应会看到 *DeviceComplainceOnboarding.plist* 文件。

### <a name="create-a-jamf-pro-configuration-profile-for-the-onboarding-package"></a>为载入包创建 JAMF Pro配置文件

1. 在 JAMF Pro中创建新的配置文件。 请参阅 [JAMF Pro管理员指南](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 使用以下值：
    - 名称：`MDATP onboarding for macOS`
    - 描述： `MDATP EDR onboarding for macOS`
    - 类别： `none`
    - 分发方法： `install automatically`
    - 水平： `computer level`

2. 在 JAMF Pro控制台>**应用程序&自定义设置**，选择 **上传**，然后 **添加**。 使用此值：
    - 首选项域： `com.microsoft.wdav.atp`

3. 选择 **上传** 并选择载入文件 **DeviceComplianceOnboarding.plist**。

4. 选择 **“范围** ”选项卡。

5. 选择目标计算机。

6. 选择“**保存**”。

7. 选择 **“完成”**。

### <a name="configure-preference-domain-using-the-jamf-pro-console"></a>使用 JAMF PRO 控制台配置首选项域

> [!IMPORTANT]
> 必须使用 ***com.microsoft.wdav** _ 作为首选项域值。 Microsoft Defender for Endpoint使用此名称和 _ *_com.microsoft.wdav.ext_** 加载其托管设置。

1. 在 JAMF Pro中创建新的配置文件。 请参阅 [JAMF Pro管理员指南](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 使用以下值：
    - 名称：`MDATP MDAV configuration settings`
    - 说明：将此留空
    - 类别： `none`
    - 分发方法： `install automatically`
    - 水平： `computer level`

1. 在“**应用程序&自定义设置**”选项卡上，选择 **“外部应用程序**”，选择 **“添加**”并选择首选项域的 **“自定义架构**”。 使用此值：
    - 首选项域： `com.microsoft.wdav`

1. 选择 **“添加架构****”并Upload** 上传 *schema.json* 文件。

1. 选择“**保存**”。

1. 在 **“首选项域属性”** 下选择这些设置
    - 功能
        - 使用系统扩展： `enabled` - Catalina 上的网络扩展需要
        - 使用数据丢失防护： `enabled`
    - 防病毒引擎>被动模式： `true|false`. 仅部署 DLP 时使用 `true`。 如果部署 DLP 和 Microsoft Defender for Endpoint (MDE) ，请使用`false`或不分配值。

1. 选择“ **作用域** ”选项卡。

1. 选择要将此配置文件部署到的组。

1. 选择“**保存**”。

### <a name="create-and-deploy-a-configuration-profile-for-microsoft-autoupdate-mau"></a>为 Microsoft AutoUpdate (MAU) 创建和部署配置文件

1. 使用 **com.microsoft.autoupdate2.plist** 创建 JAMF Pro配置文件。 请参阅 [JAMF Pro管理员指南](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 使用以下值：
    - 名称：`MDATP MDAV MAU settings`
    - 描述： `Microsoft AutoUPdate settings for MDATP for macOS`
    - 类别： `none`
    - 分发方法： `install automatically`
    - 水平： `computer level`

1. 在 **应用程序&自定义设置** 选择 **Upload** 和 **添加**。

1. 在 **“首选项”域中** 输入`com.microsoft.autoupdate2`，然后选择 **Upload**。

1. 选择 **com.microsoft.autoupdate2.plist** 文件。

1. 选择“**保存**”。

1. 选择“ **作用域** ”选项卡。

1. 选择目标计算机。

1. 选择“**保存**”。

1. 选择 **“完成”**。

### <a name="create-and-deploy-a-configuration-profile-for-grant-full-disk-access"></a>创建和部署配置文件以授予完全磁盘访问权限

1. 使用 **fulldisk.mobileconfig** 文件。

1. 将 **fulldisk.mobileconfig** 文件Upload到 JAMF。 请参阅[使用 JAMF Pro部署自定义配置文件](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)。

### <a name="create-and-deploy-a-configuration-profile-for-system-extensions"></a>为系统扩展创建和部署配置文件

1. 使用 [JAMF Pro管理员指南中的过程创建 JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)配置文件。 使用以下值：
    - 名称：`MDATP MDAV System Extensions`
    - 描述： `MDATP system extensions`
    - 类别： `none`
    - 分发方法： `install automatically`
    - 水平： `computer level`

1. 在 **系统扩展** 配置文件中，输入以下值：
    - 显示名称： `Microsoft Corp. System Extensions`
    - 系统扩展类型： `Allowed System Extensions`
    - 团队标识符： `UBF8T346G9`
    - 允许的系统扩展： `com.microsoft.wdav.epsext`和 `com.microsoft.wdav.netext`

1. 选择“ **作用域** ”选项卡。

1. 选择目标计算机。

1. 选择“**保存**”。

1. 选择 **“完成”**。

### <a name="configure-network-extension"></a>配置网络扩展

1. 使用从GitHub下载的 **netfilter.mobileconfig** 文件。

2. Upload到 JAMF，如[使用 Jamf Pro 部署自定义配置文件中](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)所述。

### <a name="grant-accessibility-access-to-dlp"></a>授予对 DLP 的辅助功能访问权限

1. 使用从GitHub下载的 **accessibility.mobileconfig** 文件。

2. Upload到 JAMF，如[使用 Jamf Pro 部署自定义配置文件中](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)所述。

### <a name="get-the-installation-package"></a>获取安装包

1. 在 **合规中心** 打开 **设置** > **Device 载入** 并选择 **加入**。

1. 若 **要选择操作系统以启动载入过程，** 请选择 **macOS**

1. 对于 **部署方法**，请选择 **移动设备管理/Microsoft Intune**

1. 选择 **“下载安装包**”。 这将提供 *wdav.pkg* 文件。

### <a name="deploy-the-installation-package"></a>部署安装包

1. 导航到保存 `wdav.pkg` 文件的位置。

1. 打开 JAMF Pro仪表板。

1. 选择计算机，然后单击顶部的齿轮，然后选择 **“计算机管理**”。

1. 在 **“包** ”中选择 **“+新建**”。 输入以下详细信息：
    - 显示名称：留空，因为选择 .pkg 文件时会重置它。
    - 类别：无 (默认) 
    - 文件名：选择文件，在此示例中选择 `wdav.pkg` 文件。

1. 选择"打开"。 设置：
    - **显示名称**： `Microsoft Endpoint Technology`
    - **清单文件**：不需要
    - **“选项”选项卡**：保留默认值
    - **限制选项卡**：保留默认值

1. 选择“**保存**”。 这会将包上传到 JAMF Pro。

1. 打开“ **策略** ”页。

1. 选择 **“+新建** ”以创建新策略。

1. 输入这些值
    - **显示名称**： `MDATP Onboarding200329 v100.86.92 or later`

1. 选择 **定期签入**。

1. 选择“**保存**”。

1. 选择 **PackagesConfigure** > 。

1. 选择“**添加**”。

1. 选择“**保存**”。

1. 选择“ **作用域** ”选项卡。

1. 选择目标计算机。

1. 选择“**添加**”。

1. 选择 **自助服务**。

1. 选择 **“完成”**。

### <a name="check-the-macos-device"></a>检查 macOS 设备

1. 重启 macOS 设备。

1. 打开 **系统首选项** > **Profiles**。

1. 应会看到：
    - Accessiblity
    - 完全磁盘访问
    - 茂
    - MDATP 载入
    - MDE 首选项
    - 管理配置文件
    - 网络筛选器
    - 系统扩展配置文件

## <a name="offboard-macos-devices-using-jamf-pro"></a>使用 JAMF Pro 载入 macOS 设备

1. 如果未使用 MDE) ，请卸载应用程序 (
    1. 请参阅 JAMF Pro文档 - 包部署 - [JAMF Pro管理员 guideJamf](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) Pro管理员指南

1. 重启 macOS 设备 - 某些应用程序可能会失去打印功能，直到重新启动

> [!IMPORTANT]
> 卸载会导致设备停止将传感器数据发送到门户，但设备中的数据（包括对已保留的任何警报的引用）将保留长达 6 个月。
