---
title: 编辑或创建电脑的设备Windows 10设置
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 了解适用于企业Microsoft 365保护设备安全Windows 10设置。
ms.openlocfilehash: 8e3de6e2452375ffd44d4039c1e8034bfb9de646
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635199"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a>编辑或创建电脑的设备Windows 10设置

本文适用于Microsoft 365 商业高级版。

> [!NOTE]
> Microsoft Defender 商业版 2022 年 3 Microsoft 365 商业高级版 1 开始向客户推出。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../security/defender-business/mdb-overview.md)。

在"设置"页上设置Windows保护设置后，可以添加适用于所有用户或一组用户的新设置。 还可以编辑已创建的任何文件。

## <a name="watch-create-protection-settings-for-windows-10-devices"></a>观看：为设备创建Windows 10设置

观看一个视频，了解如何使用Windows 10保护Microsoft 365 商业高级版：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。 

2. 在左侧导航上，选择 **"设备策略"** \> **"添加**\>"。

3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 

4. 在" **策略类型**"下，选择" **Windows 10 设备配置**"。

5. Expand **Secure Windows 10 Devices** \> configure the settings how you would like. 有关详细信息，请参阅可用 [设置](#available-settings)。 
    
    始终可使用" **重置默认设置**"链接返回到默认设置。 
    
    ![添加策略窗格，Windows 10"设备配置"。](./../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.

7. 最后，选择" **完成**"以保存该策略，并将其分配到设备。 

## <a name="edit-windows-10-protection-settings"></a>编辑Windows 10保护设置
 
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。     

2. 在左侧导航中，选择 **"设备策略** \> **"** 。

3. 选择现有Windows策略，然后选择"编辑 **"**。

4. 选择 **要** 更改的设置旁边的"编辑"，然后选择"保存 **"**。

## <a name="available-settings"></a>可用设置

所有设置均默认为" **开启**"状态。可使用以下设置：
  
有关详细信息，请参阅保护功能[如何Microsoft 365 高级版映射到Intune设置](m365bp-map-protection-features-to-intune-settings.md)。 


|设置  |说明  |
|:-----|:-----|
|使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁  |需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。  |
|帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁  |在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。  |
|使用减少设备攻击面的规则  |启用此规则后，攻击面减少有助于阻止通常被恶意软件用来感染设备的操作和应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。请参阅[减少攻击面](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)以了解详细信息。    |
|保护文件夹免受勒索软件等威胁  |此设置使用受控文件夹访问来保护公司数据免受可疑或恶意应用（如勒索软件）的修改。 无法在受保护的文件夹中更改这些类型的应用。 仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。 有关详细信息 [，请参阅使用受控文件夹访问权限](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) 保护文件夹。  |
|防止网络访问 Internet 上的潜在恶意内容  |使用此设置可阻止出站用户与可能承载网络钓鱼欺诈、攻击或其他恶意内容的低信誉 Internet 位置的连接。 此设置仅在设置为"打开 **Windows Defender 防病毒可用。** 有关详细信息，请参阅 [保护网络](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。  |
|使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问  |BitLocker 通过加密计算机硬盘驱动器来保护数据，在计算机丢失或被盗时防止数据泄露。 有关详细信息，请参阅 [BitLocker 常见问题](/windows/security/information-protection/BitLocker/BitLocker-frequently-asked-questions)解答。  |
|允许用户从 Microsoft Store 下载应用  |允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。    |
|允许用户访问 Cortana  |Cortana 非常有用！ Cortana可以打开或关闭设置、提供方向，并确保你及时进行约会，因此默认情况下，我们将 **此设置保持打开** 状态。  |
|允许用户接收来自 Microsoft 的 Windows 提示和广告  |Windows 提示非常方便，可在新功能发布时为用户提供指导。  |
|让 Windows 10 设备自动保持最新状态  |确保 Windows 10 设备会自动接收最新的更新。  |
|在空闲此时长后关闭设备屏幕  |确保用户处于空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，其设备有被随意瞥视的风险。借助此设置，可以控制用户处于空闲状态多长时间后关闭屏幕。  |

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../admin/security-and-compliance/secure-your-business-data.md) 