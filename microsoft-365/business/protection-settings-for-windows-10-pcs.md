---
title: 设置 Windows 10 电脑的设备保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 了解默认和其他 Microsoft 365 业务保护 Windows 10 设备中可用的设置。
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865395"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>设置 Windows 10 电脑的设备保护设置

## <a name="secure-windows-10-devices"></a>保护 Windows 10 设备

查看有关如何使用 Microsoft 365 商业版保护 Windows 10 设备的视频：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. 使用全局管理员凭据登录 [Microsoft 365 商业版](https://portal.office.com)。 
    
2. 在管理中心内的" **设备策略**"卡上，选择" **添加策略**"。
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 
    
4. 在" **策略类型**"下，选择" **Windows 10 设备配置**"。
    
5. 展开**Secure Windows 10 设备**\>配置方式的设置。有关详细信息，请参阅[可用的设置](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings)。 
    
    始终可使用" **重置默认设置**"链接返回到默认设置。 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. 接下来决定**用户会收到这些设置？** 如果您不想要使用的默认**所有用户**安全组中，选择**更改**，搜索的安全组，用户会收到这些设置\>**选择**。
    
7. 最后，选择" **完成**"以保存该策略，并将其分配到设备。 
    
## <a name="available-settings"></a>可用设置

所有设置均默认为" **开启**"状态。可使用以下设置：
  
有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。 
  
|||
|:-----|:-----|
|设置  <br/> |说明  <br/> |
|使用 Windows Defender 防病毒软件帮助保护电脑免遭病毒和其他威胁  <br/> |需要启用 Windows Defender 防病毒软件，保护电脑免遭连接 Internet 产生的危险。  <br/> |
|帮助保护电脑免遭 Microsoft Edge 中基于 Web 的威胁  <br/> |在 Microsoft Edge 中启用有助于保护用户免遭恶意网站和下载威胁的设置。  <br/> |
|使用减少设备攻击面的规则  <br/> |启用此规则后，攻击面减少有助于阻止通常被恶意软件用来感染设备的操作和应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。请参阅[减少攻击面](https://go.microsoft.com/fwlink/?linkid=870417)以了解详细信息。  <br/> |
|保护文件夹免受勒索软件等威胁  <br/> |此设置使用受控文件夹访问来保护公司数据免受可疑或恶意应用（如勒索软件）的修改。无法在受保护的文件夹中更改这些类型的应用。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。有关详细信息，请参阅[使用受控文件夹访问保护文件夹](https://go.microsoft.com/fwlink/?linkid=870418)。  <br/> |
|防止网络访问 Internet 上的潜在恶意内容  <br/> |使用此设置可阻止出站用户连接到可能承载网络钓鱼诈骗、漏洞利用或其他恶意内容的低信誉 Internet 位置。仅当 Windows Defender 防病毒设置为"开启"时，此设置才可用。有关详细信息，请参阅[保护网络](https://go.microsoft.com/fwlink/?linkid=870419)。  <br/> |
|使用 BitLocker 帮助保护 PC 上的文件和文件夹免遭未经授权的访问  <br/> |Bitlocker 通过加密计算机硬盘来保护数据，在计算机丢失或被盗时防止数据泄露。有关详细信息，请参阅 [Bitlocker 常见问题解答](https://go.microsoft.com/fwlink/?linkid=871000)。  <br/> |
|允许用户从 Microsoft Store 下载应用  <br/> |允许用户从 Microsoft Store 下载和安装应用。应用种类繁多，囊括了游戏和生产力工具，因此将此设置保留为" **开**"，但可将其关闭以增强安全性。  <br/> |
|允许用户访问 Cortana  <br/> |Cortana 非常有用！该功能可为你打开/关闭设置、发出指令并确保你按时赴约，因此此设置默认保留为" **开**"。  <br/> |
|允许用户接收来自 Microsoft 的 Windows 提示和广告  <br/> |Windows 提示非常方便，可在新功能发布时为用户提供指导。  <br/> |
|让 Windows 10 设备自动保持最新状态  <br/> |确保 Windows 10 设备会自动接收最新的更新。  <br/> |
|在空闲此时长后关闭设备屏幕  <br/> |确保用户空闲时，公司数据受到保护。用户可能会在咖啡店等公共场所工作，短暂离开或心不在焉，此时其设备可能被人随机看到。借助此设置，可控制用户空闲状态多长时间后关闭屏幕。  <br/> |
   
  

