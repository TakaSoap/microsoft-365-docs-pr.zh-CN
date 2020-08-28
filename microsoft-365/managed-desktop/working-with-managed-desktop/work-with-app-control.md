---
title: 使用应用程序控制
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289455"
---
# <a name="work-with-app-control"></a>使用应用程序控制

一旦在您的环境中部署了应用程序控制，您和 Microsoft 托管的桌面操作都将承担持续的责任。 例如，您可能想要在环境中添加新的应用程序，或添加 (或删除) 受信任的签名人。 为了提高安全性，在将所有应用发布给用户之前，应对其进行代码签名。 应用的发布者详细信息包括有关签署人的信息。


## <a name="add-a-new-app"></a>添加新应用

若要添加新应用程序，请按照下列步骤操作：

1. 将应用程序添加到 [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)。
2. 将应用程序部署到测试环中的任何设备。 
3. 根据您的标准业务流程测试您的应用程序。 
4. 检查 " **应用程序和服务" Logs\Microsoft\Windows\AppLocker**下的 "事件查看器"，查找任何 **8003** 或 **8006** 事件。 这些事件指示应用程序将被阻止。 有关所有应用程序锁定程序事件及其含义的详细信息，请参阅将 [事件查看器与 AppLocker 结合使用](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。
5. 如果找到这些事件中的任何事件，请使用 Microsoft 托管桌面操作打开签名者请求。

## <a name="add-or-remove-a-trusted-signer"></a>添加 (或删除受信任的签名人) 

打开签名者请求时，需要先提供一些重要的发布者详细信息。 然后，按照以下步骤操作：

1. [收集发布者详细信息](#gather-publisher-details)。
2. 使用 Microsoft 托管桌面操作打开票证以请求签署人规则，并包括以下详细信息：  
    - 应用程序名称 
    - 应用程序版本 
    - 说明 
    - 更改类型 ( "添加" 或 "删除" )   
    - Publisher 详细信息 (例如： "O = <publisher name> ，L = <location> ，S = State，C = Country" )  

> [!NOTE]
> 若要删除对应用的信任，请执行相同步骤，但将 **更改类型** 设置为 " *删除*"。

按照此计划，操作将逐步将策略部署到部署组：


|部署组  |策略类型  |Timing  |
|---------|---------|---------|
|测试     |  Audit       |  第0天       |
|First     | Enforced        | 第 1 天        |
|快速     | Enforced        |  第 2 天       |
|宽泛     | Enforced        |  第 3 天       |


可以在首次部署过程中随时暂停或回滚部署。 为此，请打开另一个包含操作的服务请求。

> [!NOTE]
> 如果暂停签署人规则，则必须在另一个首展启动前回滚或完成该规则。

## <a name="gather-publisher-details"></a>收集发布者详细信息

若要访问应用程序的发布者数据，请按照以下步骤操作：

1. 在应用了审核模式策略的测试环中查找 Microsoft 托管桌面设备。 
2. 尝试在设备上安装应用程序。
3. 在该设备上打开事件查看器。 
4. 在事件查看器中，导航到 **Application And service Logs\Microsoft\Windows**，然后选择 **AppLocker**。 
5. 查找任何 **8003** 或 **8006** 事件，然后从事件中复制信息： 
    - 应用程序名称 
    - 应用程序版本 
    - 说明 
    - Publisher 详细信息 (例如： "O = <publisher name> ，L = <location> ，S = State，C = Country" )  
