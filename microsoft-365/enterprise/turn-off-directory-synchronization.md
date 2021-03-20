---
title: 关闭 Microsoft 365 的目录同步
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: 本文查找有关使用 PowerShell 关闭 Microsoft 365 目录同步的信息。
ms.openlocfilehash: 036130b70382e28ad9d8cb10786ad5e266375c20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909306"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>关闭 Microsoft 365 的目录同步
可以使用 PowerShell 关闭目录同步。 但是，不建议关闭目录同步作为疑难解答步骤。 如果需要有关目录同步疑难解答的帮助，请参阅修复 [Microsoft 365](fix-problems-with-directory-synchronization.md) 目录同步问题一文。 
  
[如果需要，](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 请联系商业产品支持人员。
  
## <a name="turn-off-directory-synchronization"></a>关闭目录同步  
若要关闭目录同步，请执行：
  
1. 首先，安装所需的软件并连接到 Microsoft 365 订阅。 有关说明，请参阅 [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。
    
2. 使用 [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) 禁用目录同步： 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>如果使用此命令，则必须等待 72 小时，然后才能重新启用目录同步。
>
