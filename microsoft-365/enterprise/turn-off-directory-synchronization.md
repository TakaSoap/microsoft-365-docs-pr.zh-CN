---
title: 关闭目录同步Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 本文查找有关使用 PowerShell 关闭目录同步的信息，Microsoft 365。
ms.openlocfilehash: 83a3d66493994800a71a1910332a5eb2cdb003cd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209557"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>关闭目录同步Microsoft 365
可以使用 PowerShell 关闭目录同步，并将同步的用户转换为仅云。 但是，不建议关闭目录同步作为疑难解答步骤。 如果需要有关目录同步疑难解答的帮助，请参阅修复目录同步[Microsoft 365文章。](fix-problems-with-directory-synchronization.md) 
  
[如果需要，](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 请联系商业产品支持人员。
  
## <a name="turn-off-directory-synchronization"></a>关闭目录同步  
若要关闭目录同步，请执行：
  
1. 首先，安装所需的软件并连接到 Microsoft 365 订阅。 有关说明，请参阅[连接模块Microsoft Azure Active Directory模块Windows PowerShell。](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
2. 使用 [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) 禁用目录同步： 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>如果使用此命令，则必须等待 72 小时，然后才能重新启用目录同步。
>
