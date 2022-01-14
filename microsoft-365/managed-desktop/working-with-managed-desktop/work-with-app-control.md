---
title: 使用应用程序控制
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: d7f4bff519fd06a9e8a43030426d7820d68f5153
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035109"
---
# <a name="work-with-app-control"></a>使用应用程序控制

在环境中部署应用控制后，你和Microsoft 托管桌面操作都承担持续的责任。 例如，你可能想要在环境中添加新应用，或者添加 (或删除) 签名者。 为了提高安全性，所有应用都应先进行代码签名，然后再将其发布给用户。 应用的发布者详细信息包括有关签名者的信息。


## <a name="add-a-new-app"></a>添加新应用

若要添加新应用，请按照以下步骤操作：

1. 将应用添加到[Microsoft Intune](/mem/intune/apps/apps-win32-app-management)。
2. 将应用部署到测试圈中的任意设备。 
3. 根据标准业务流程测试应用。 
4. 检查 Application **and Services Logs\Microsoft\Windows\AppLocker** 下的事件查看器，查找任何 **8003** 或 **8006** 事件。 这些事件指示应用将被阻止。 有关所有应用保险箱事件及其含义的信息，请参阅将事件查看器与 [AppLocker 一同使用](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。
5. 如果找到这些事件中的任意一个，请通过"操作"打开Microsoft 托管桌面请求。

## <a name="add-or-remove-a-trusted-signer"></a>添加 (或删除) 签名者

打开签名者请求时，需要先提供一些重要的发布者详细信息。 然后按照以下步骤操作：

1. [收集发布者详细信息](#gather-publisher-details)。
2. 使用 Microsoft 托管桌面 操作打开票证以请求签署人规则，并包括以下详细信息：  
    - 应用程序名称 
    - 应用程序版本 
    - 说明 
    - 更改类型 ("add"或"remove")   
    - Publisher详细信息 (例如："O= <publisher name> ，L= <location> ，S=State，C=Country")  

> [!NOTE]
> 若要删除对应用的信任，请按照相同步骤操作，但将 **"更改** 类型"设置为 *删除*。

按照此计划，操作将逐步将策略部署到部署组：


|部署组  |策略类型  |Timing  |
|---------|---------|---------|
|测试     |  Audit       |  第 0 天       |
|First     | Enforced        | 第 1 天        |
|快速     | Enforced        |  第 2 天       |
|宽泛     | Enforced        |  第 3 天       |


可以在推出期间随时暂停或回滚部署。 为此，请通过 Operations 打开另一个服务请求。

> [!NOTE]
> 如果暂停签名者规则的发布，则必须回滚或完成该规则，然后才能开始其他推出。

## <a name="gather-publisher-details"></a>收集发布者详细信息

若要访问应用的发布者数据，请按照以下步骤操作：

1. 在Microsoft 托管桌面应用审核模式策略的测试圈中查找设备。 
2. 尝试在设备上安装应用。
3. 打开该设备上的事件查看器。 
4. 在事件查看器中，导航到 **应用程序和服务日志\Microsoft\Windows**，然后选择 **AppLocker**。 
5. 查找任何 **8003** 或 **8006** 事件，然后从事件复制信息： 
    - 应用程序名称 
    - 应用程序版本 
    - 说明 
    - Publisher详细信息 (例如："O= <publisher name> ， L= <location> ， S=State， C=Country") 