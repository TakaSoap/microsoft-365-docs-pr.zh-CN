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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: '了解如何使用 JAMF Microsoft 365预览版将 macOS 设备载入和Pro (合规性) '
ms.openlocfilehash: 1c21251b390209d92696a36962705b9f2517a53c
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111215"
---
# <a name="onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview"></a>使用 JAMF Pro 将 macOS 设备载入和卸载到 Microsoft 365 合规性解决方案（预览版）

可以使用 JAMF Pro macOS 设备载入Microsoft 365合规性解决方案，如终结点数据丢失防护。

> [!IMPORTANT]
> 如果你未将 Microsoft  Defender for Endpoint (MDE) 部署到 macOS 设备，请使用此过程

## <a name="get-registered"></a>注册

若要获取此功能的访问权限，必须向 Microsoft 注册租户。 请参阅[注册 Microsoft 365 macOS 支持](https://aka.ms/EndpointDLPIgnite21-Previews)。

**适用于：**

- [Microsoft 365终结点数据丢失防护 （DLP）](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>开始之前

- 确保[macOS 设备已Azure AD连接](https://docs.jamf.com/10.30.0/jamf-pro/administrator-guide/Azure_AD_Integration.html)
- 确保通过 [JAMF 专业版管理 macOS 设备](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- 在 macOS 设备上安装 v95+ Edge 浏览器 

## <a name="onboard-devices-into-microsoft-365-compliance-solutions-using-jamf-pro"></a>使用 JAMF Microsoft 365将设备载入到合规性Pro

1. 此过程需要这些文件。

|所需的文件 |Source |
|---------|---------|
|载入包    |从合规性门户 **载入程序包下载，** 文件名 *DeviceComplianceOnboarding.plist* |
|辅助功能 |[accessibility.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/accessibility.mobileconfig)|
完全磁盘访问     |[fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig)|
|网络筛选器| [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig)
|系统扩展 |[sysext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/systext.mobileconfig)
|MDE 首选项     |[schema.json](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/data_loss_prevention/schema.json)|
|MAU 首选项|[com.microsoft.autoupdate2.plist](https://github.com/microsoft/mdatp-xplat/blob/master/macos/settings/microsoft_auto_update/com.microsoft.autoupdate2.plist)|
|安装包     |从合规性门户安装程序包 **下载，** 文件名 *\* wdav.pkg*\* |

> [!TIP]
> 您可以单独下载 *.mobileconfig* 文件，也可以将这些文件下载到包含以下项的 [单个](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/combined/mdatp-nokext.mobileconfig) 组合文件中：
> - accessibility.mobileconfig
> - fulldisk.mobileconfig
> - netfilter.mobileconfig
> - sysext.mobileconfig
>
>如果其中任何一个文件已更新，则需要再次下载组合的文件或单独下载单个更新的文件。

将 macOS 设备载入合规性解决方案是一个多阶段过程。

### <a name="get-the-device-onboarding-package"></a>获取设备载入包

1. 在 **"合规性中心**"**中**  >  **设置"设备载入"，** 然后选择 **"载入"。**
 
1. 对于 **"选择操作系统以开始载入过程"选择** **macOS**
 
1. 对于 **"部署"方法**，**选择"移动设备管理/Microsoft Intune**
 
1. 选择 **下载载入程序包**
 
1. 提取设备载入包的内容。 在 JAMF 文件夹中，应看到 *DeviceComplainceOnboarding.plist* 文件。

### <a name="create-a-jamf-pro-configuration-profile-for-the-onboarding-package"></a>为载入Pro创建 JAMF 模式配置文件

1. 在 JAMF 中创建新的配置文件Pro。 请参阅[JAMF Pro管理员指南](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 使用这些值：
    - 名称：`MDATP onboarding for macOS`
    - 说明： `MDATP EDR onboarding for macOS`
    - 类别： `none`
    - 分发方法： `install automatically`
    - 级别： `computer level`

2. In the JAMF Pro console > **Application & Custom settings，** choose **upload** and then **add**. 使用此值：
    - 首选项域： `com.microsoft.wdav.atp`

3. 选择 **上传** 并选择载入文件 **DeviceComplianceOnboarding.plist**。

4. 选择范围 **选项卡** 。

5. 选择目标计算机。

6. 选择“**保存**”。

7. 选择 **“完成”**。

### <a name="configure-preference-domain-using-the-jamf-pro-console"></a>使用 JAMF PRO 控制台配置首选项域

> [!IMPORTANT]
> 必须使用 ***com.microsoft.wdav** _ 作为首选项域值。 Microsoft Defender for Endpoint 使用此名称和 _ *_com.microsoft.wdav.ext_** 加载其托管设置。

1. 在 JAMF 中创建新的配置文件Pro。 请参阅[JAMF Pro管理员指南](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 使用这些值：
    - 名称：`MDATP MDAV configuration settings`
    - 说明：保留此为空白
    - 类别： `none`
    - 分发方法： `install automatically`
    - 级别： `computer level`

1. 在"**应用程序&自定义** 设置选项卡上，选择"外部应用程序 **"，** 选择"**添加**"，然后选择首选项域的 **"** 自定义架构"。 使用此值：
    - 首选项域： `com.microsoft.wdav`

1. 选择 **"添加架构****Upload以** 上载 *schema.json* 文件。

1. 选择“**保存**”。

1. 在 **"首选项域属性"** 下，选择这些设置
    - 功能 
        - 使用系统扩展 `enabled` ：- 对于加泰罗尼亚语上的网络扩展是必需的
        - 使用数据丢失防护： `enabled`
    - 防病毒引擎>被动模式 `true|false` ：。 如果 `true` 仅部署 DLP，请使用 。 如果在 `false` MDE 中部署 DLP 和 Microsoft Defender for Endpoint (，) 。

1. 选择" **范围"** 选项卡。

1. 选择要将此配置文件部署到的组。

1. 选择“**保存**”。 


### <a name="create-and-deploy-a-configuration-profile-for-microsoft-autoupdate-mau"></a>创建和部署 Microsoft AutoUpdate (MAU) 

1. 使用 **com.microsoft.autoupdate2.plist** 创建 JAMF Pro配置文件。 请参阅[JAMF Pro管理员指南](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 使用这些值：
    - 名称：`MDATP MDAV MAU settings`
    - 说明： `Microsoft AutoUPdate settings for MDATP for macOS`
    - 类别： `none`
    - 分发方法： `install automatically`
    - 级别： `computer level`

1. 在 **"应用程序&自定义设置"Upload"** 添加 **"。** 

1. 在 **首选项域中** 输入 `com.microsoft.autoupdate2` ，然后选择"Upload"。 

1. 选择 **com.microsoft.autoupdate2.plist** 文件。

1. 选择“**保存**”。

1. 选择" **范围"** 选项卡。

1. 选择目标计算机。

1. 选择“**保存**”。

1. 选择 **“完成”**。


### <a name="create-and-deploy-a-configuration-profile-for-grant-full-disk-access"></a>为授予完全磁盘访问权限创建和部署配置文件

1. 使用 **fulldisk.mobileconfig** 文件。

1. Upload **fulldisk.mobileconfig 文件** 更新为 JAMF。 请参阅[使用 JAMF 部署自定义配置文件Pro。](https://docs.jamf.com/technical-articles/Deploying_Custom_Configuration_Profiles_Using_Jamf_Pro.html)

### <a name="create-and-deploy-a-configuration-profile-for-system-extensions"></a>为系统扩展创建和部署配置文件

1. 使用 JAMF Pro指南 中的过程创建[JAMF Pro配置文件](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)。 使用这些值：
    - 名称：`MDATP MDAV System Extensions`
    - 说明： `MDATP system extensions`
    - 类别： `none`
    - 分发方法： `install automatically`
    - 级别： `computer level`

1. 在 **"系统扩展配置文件** "中，输入以下值：
    - 显示名称： `Microsoft Corp. System Extensions`
    - 系统 Extenstion 类型： `Allowed System Extensions`
    - 团队标识符： `UBF8T346G9`
    - 允许的系统扩展： `com.microsoft.wdav.epsext` 和 `com.microsoft.wdav.netext`

1. 选择" **范围"** 选项卡。

1. 选择目标计算机。

1. 选择“**保存**”。

1. 选择 **“完成”**。

### <a name="configure-network-extension"></a>配置网络扩展

1.  使用从 Github 下载的 **netfilter.mobileconfig**  文件。

2.  Upload Jamf 部署自定义配置文件中的说明操作[，Pro。](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

### <a name="grant-accessibility-access-to-dlp"></a>授予对 DLP 的辅助功能访问权限

1. 使用从 Github 下载的 **accessibility.mobileconfig** 文件。

2.  Upload Jamf 部署自定义配置文件中的说明操作[，Pro。](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)

### <a name="get-the-installation-package"></a>获取安装包

1. 在 **合规性中心** 中 **，设置"**  >  **设备载入"，** 然后选择 **"载入"。**
 
1. 对于 **"选择操作系统以开始载入过程"选择** **macOS**
 
1. 对于 **"部署"方法**，**选择"移动设备管理/Microsoft Intune**
 
1. 选择 **"下载安装程序包"。** 这将提供 *wdav.pkg* 文件。


### <a name="deploy-the-installation-package"></a>部署安装包

1. 导航到保存文件 `wdav.pkg` 的位置。

1. 打开 JAMF Pro仪表板。

1. 选择计算机，然后单击顶部的齿轮，然后选择计算机 **管理**。

1. 在 **"程序包"** 中，选择 **"+新建"。** 输入以下详细信息：
    - 显示名称：保留为空，因为它将在你选择 .pkg 文件时重置。
    - 类别：默认 (无) 
    - Filname：选择文件，在这种情况下为 `wdav.pkg` 文件。

1. 选择"打开"。 设置：
    - **显示名称**： `Microsoft Endpoint Technology`
    - **清单文件**：不是必需的
    - **"选项"** 选项卡：保留默认值
    - **"限制"选项卡**：保留默认值

1. 选择“**保存**”。 这会将程序包上传到 JAMF Pro。

1. 打开" **策略"** 页。

1. 选择 **"+新建** "以创建新策略。

1. 输入这些值
    - **显示名称**： `MDATP Onboarding200329 v100.86.92 or later`

1. 选择 **"定期签入"。**

1. 选择“**保存**”。

1. 选择 **"程序包**  >  **配置"。**

1. 选择“**添加**”。

1. 选择“**保存**”。 

1. 选择" **范围"** 选项卡。

1. 选择目标计算机。

1. 选择“**添加**”。

1. 选择 **"自助服务"。**

1. 选择 **“完成”**。

### <a name="check-the-macos-device"></a>检查 macOS 设备 

1. 重新启动 macOS 设备。

1. 打开 **系统首选项**  >  **配置文件**。

1. 你应该会看到：
    - 辅助性
    - 完全磁盘访问
    - MAU
    - MDATP 载入
    - MDE 首选项
    - 管理配置文件
    - 网络筛选器
    - 系统扩展配置文件

## <a name="offboard-macos-devices-using-jamf-pro"></a>使用 JAMF 设备的载 macOS Pro

1. 如果未使用 MDE (，请卸载) 
    1. 请参阅 JAMF Pro文档 - 包部署 - [JAMF Pro管理员指南](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)Jamf Pro 管理员指南

1. 重新启动 macOS 设备 - 在重新启动某些应用程序之前，它们可能会失去打印功能

> [!IMPORTANT]
> "载出"会导致设备停止向门户发送传感器数据，但设备数据（包括对已保留的任何警报的引用）最多保留 6 个月。
