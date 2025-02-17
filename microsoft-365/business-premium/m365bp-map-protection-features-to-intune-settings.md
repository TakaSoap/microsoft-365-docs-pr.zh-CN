---
title: 保护功能如何Microsoft 365 商业高级版映射到Intune设置
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
ms.date: 04/01/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: 了解保护功能如何Microsoft 365 商业高级版映射到Intune设置。 订阅会为您提供修改设置Intune许可证。
ms.openlocfilehash: cd3bf2c9db6379b70e02a14b6f07d56b3552cbd2
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635201"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>保护功能如何Microsoft 365 商业高级版映射到Intune设置

> [!NOTE]
> Microsoft Defender 商业版 2022 年 3 Microsoft 365 商业高级版 1 开始向客户推出。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../security/defender-business/mdb-overview.md)。

## <a name="android-and-ios-application-protection-settings"></a>Android 和 iOS 应用程序保护设置

下表详细介绍了 Android 和 iOS 应用程序策略设置如何映射到 Intune 设置。
  
若要查找Intune设置，请Microsoft 365 商业高级版管理员凭据登录，然后转到管理中心，**Intune。**
  
 > [!IMPORTANT]
 > 
 > 一Microsoft 365 商业高级版订阅会为你提供一个许可证，用于修改所有Intune设置。 请参阅[入门Intune简介。](/intune/introduction-intune)
  
选择想要的策略名称 &mdash; （例如，适用于 Android &mdash; 的应用程序策略）然后选择" **策略设置"**。
  
在" **设备丢失或被盗时保护工作文件**"下
  
|**Android 或 iOS 应用程序策略设置**|**Intune 设置**|
|:-----|:-----|
|在以下时间后，从非活动设备删除工作文件  |擦除应用数据之前的脱机时间间隔(天)  |
|强制用户将工作文件保存到 OneDrive for Business  <br/> 请注意，仅允许 OneDrive for Business  |选择企业数据可保存到其中的存储服务  |
   
在" **管理用户在移动设备上访问 Office 文件的方式**"下
  
|**Android 或 iOS 应用程序策略设置**|**Intune 设置**|
|:-----|:-----|
|在以下时间后，从非活动设备删除工作文件  |擦除应用数据之前的脱机时间间隔(天)  |
|强制用户将工作文件保存到 OneDrive for Business  <br/> 请注意，仅允许 OneDrive for Business  |选择企业数据可保存到其中的存储服务  |
|对工作文件进行加密  |对应用数据进行加密  |
|在" **管理用户在移动设备上访问 Office 文件的方式**"下 ||
|需要 PIN 或指纹才能访问 Office 应用  | 需要 PIN 才能访问  <br/>  这还进行以下设置：  <br/> 将" **允许简单的 PIN**"设置为" **是**" <br/> 将" **PIN 长度**"设置为 4  <br/> 将" **允许使用指纹而不允许使用 PIN**"设置为" **是**" <br/> 将" **管理设备 PIN 时禁用应用 PIN**"设置为" **否**" |
|登录失败此次数时重置 PIN (如果不需要 PIN，则禁用)   |重置 PIN 前的尝试次数  |
|要求用户在应用处于空闲Office后重新登录 (如果不需要 PIN，则禁用)   | 在以下时间后重新检查访问要求(分钟)  <br/>  这还进行以下设置：  <br/> 将" **超时**"设置为几分钟  <br/>  这与在 Microsoft 365 商业版中设置的分钟数相同。  <br/> 将默认" **脱机宽限期**"设置为 720 分钟  |
|在已越狱或取得 root 权限的设备上拒绝对工作文件的访问  |阻止托管的应用在已越狱或取得 root 权限的设备上运行  |
|允许用户从 Office 应用将内容复制到个人应用  | 限制使用其他应用剪切、复制和粘贴  <br/>  如果Microsoft 365 商业高级版选项设置为 **"打开**"，则这三个选项也设置为"应用中的所有Intune：  <br/> **允许应用将数据传输到其他应用** <br/> **允许应用从其他应用接收数据** <br/> **限制使用其他应用进行剪切、复制和粘贴操作** <br/>  如果 Microsoft 365 商业版选项设置为" **开**"，则所有 Intune 选项均设置为：  <br/> " **允许应用将数据传输到其他应用**"设置为" **策略托管的应用**" <br/> " **允许应用从其他应用接收数据**"设置为" **所有应用**" <br/> " **限制使用其他应用进行剪切、复制和粘贴操作**"设置为" **带粘贴的策略托管应用**" |
   
## <a name="windows-10-app-protection-settings"></a>Windows 10 应用保护设置

下表详细介绍了 Windows 10 应用程序策略设置如何映射到 Intune 设置。
  
若要查找Intune设置，请通过 Microsoft 365 商业高级版 管理员凭据登录，然后转到"Azure 门户["](https://portal.azure.com)。 选择 **"更多服务**"，Intune筛选器中 **键入"服务"**。 选择 **Intune应用保护** \> **应用策略"**。
  
 > [!IMPORTANT]
 >
 >通过Microsoft 365 商业高级版订阅，可以仅修改映射到 Intune 中可用设置Microsoft 365 商业高级版。 
  
若要浏览可用的设置，请选择所需的策略名称，然后从左侧导航窗格中选择常规、分配、允许的应用、豁免应用、必需设置或高级设置。 
  
|**Windows 10 应用程序策略设置**|**Intune 设置**|
|:-----|:-----|
|对工作文件进行加密  |" **高级设置**"\>" **数据保护**"：" **取消注册时撤销加密密钥**"和" **撤销对注册到 MDM 的受保护数据设备的访问**"均设置为" **开**"。  |
|防止用户将公司数据复制到个人文件。  |" **必需设置**"\>" **Windows 信息保护模式**"。 **In** Microsoft 365 商业高级版映射到：**隐藏替代****，关闭** Microsoft 365 商业高级版映射到：**关闭**。  |
|Office 文档访问控制  | 如果在"设置 **"中，** Microsoft 365 商业高级版"打开"，则  <br/> " **高级设置**"\>" **访问**"、" **使用 Windows Hello 企业版作为登录 Windows 的方法**"设置为" **开**"，并进行以下设置：  <br/> 将" **设置 PIN 所需的最少字符数**"设置为" **4**"。  <br/> 将" **在 Windows Hello 企业版 PIN 中配置大写字母的使用**"设置为" **不允许对 PIN 使用大写字母**"。  <br/> 将" **在 Windows Hello 企业版 PIN 中配置小写字母的使用**"设置为" **不允许对 PIN 使用小写字母**"。  <br/> 将" **在 Windows Hello 企业版 PIN 中配置特殊字符的使用**"设置为" **不允许对 PIN 使用特殊字符**"。  <br/> **指定在 (更改) PIN** 之前可以使用的时间段（以天 **表示）。**  <br/> 将" **指定可以与无法重复使用的用户帐户相关联的之前的 PIN 数**"设置为" **0**"。  <br/> 将" **擦除设备前允许身份验证失败的次数**"设置为与 Microsoft 365 商业版中相同的次数（默认为 5）。  <br/> 将" **设备空闲后，导致设备锁定 PIN 或密码前允许的最长时间(以分钟为单位)**"设置为与 Microsoft 365 商业版中相同的时间。  |
|启用受保护数据的恢复  |" **高级设置**"\>" **数据保护**"：" **显示企业数据保护图标**"和" **使用 Azure RMS for WIP**"均设置为" **开**"。  |
|保护其他公司云位置  |" **高级设置**"\>" **受保护的域**"和" **云资源**"显示域和 SharePoint 网站。  |
|这些应用所用的文件受到保护  |受保护的应用列表在" **允许的应用**"中列出。  |
   
## <a name="windows-10-device-protection-settings"></a>Windows 10 设备保护设置

下表详细介绍了 Windows 10 设备配置设置如何映射到 Intune 设置。
  
若要查找 Intune 设置，使用 Microsoft 365 商业高级版 管理员凭据登录，然后转到 [Azure 门户](https://portal.azure.com)，然后选择"更多服务"，然后在"筛选器"中键入 Intune，选择"Intune **设备** \> **配置文件**\>"。 Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Windows 10 设备策略设置**|**Intune 设置**|
|:-----|:-----|
|使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁  |允许实时监视 = 开  <br/> 允许云保护 = 开  <br/> 提示用户提交示例 = 自动发送安全示例(默认非 PII 自动提交)  |
|帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁  |" **Microsoft Edge 浏览器设置**"中的" **Microsoft SmartScreen**"设置为" **必需**"。  |
|在闲置此时长后关闭设备屏幕(分钟)  |幕锁定前的最大非活动分钟数  |
|允许用户从 Microsoft Store 下载应用  |自定义 URI 策略  |
|允许用户访问 Cortana  |**常规** \>**Cortana** 设置为 **"在Intune** 中设置为 **"** 关闭"时，Microsoft 365 商业高级版。  |
|允许用户接收来自 Microsoft 的 Windows 提示和广告  |**Windows聚焦**，如果设置为在聚焦中关闭，则所有Microsoft 365 商业高级版。  |
|让 Windows 10 设备自动保持最新状态  | 此设置位于"Microsoft Intune  \> **服务更新 - Windows 10更新** 圈"中，选择"Windows 10设备的更新策略"，然后选择"**属性**\>设置 **"**。  <br/>  当Microsoft 365 商业高级版设置为 **"打开"** 时，将设置以下所有设置：  <br/> **在 CBB** **中关闭** 服务分支 (设置为 CB Microsoft 365 商业高级版) 。  <br/> " **Microsoft 产品更新**"设置为" **允许**"。  <br/> 将" **Windows 驱动程序**"设置为" **允许**"。  <br/> 将" **自动更新行为**"设置为" **维护时自动安装**"，其中：  <br/> " **开始时间**"设置为" **上午 6 点**"。  <br/> " **活动结束时间**"设置为" **晚上 10 点**"。  <br/> " **质量更新延迟期(天)**"设置为" **0**"。  <br/> " **功能更新延迟期(天)**"设置为" **0**"。  <br/> " **交付优化下载模式**"设置为" **与相同 NAT 后面的对等互连混合的 HTTP**"。  |

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../admin/security-and-compliance/secure-your-business-data.md)
