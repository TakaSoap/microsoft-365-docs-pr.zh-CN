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
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="ce3d0-103">关闭 Microsoft 365 的目录同步</span><span class="sxs-lookup"><span data-stu-id="ce3d0-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="ce3d0-104">可以使用 PowerShell 关闭目录同步。</span><span class="sxs-lookup"><span data-stu-id="ce3d0-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="ce3d0-105">但是，不建议关闭目录同步作为疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="ce3d0-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="ce3d0-106">如果需要有关目录同步疑难解答的帮助，请参阅修复 [Microsoft 365](fix-problems-with-directory-synchronization.md) 目录同步问题一文。</span><span class="sxs-lookup"><span data-stu-id="ce3d0-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="ce3d0-107">[如果需要，](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 请联系商业产品支持人员。</span><span class="sxs-lookup"><span data-stu-id="ce3d0-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="ce3d0-108">关闭目录同步</span><span class="sxs-lookup"><span data-stu-id="ce3d0-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="ce3d0-109">若要关闭目录同步，请执行：</span><span class="sxs-lookup"><span data-stu-id="ce3d0-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="ce3d0-110">首先，安装所需的软件并连接到 Microsoft 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="ce3d0-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="ce3d0-111">有关说明，请参阅 [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ce3d0-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="ce3d0-112">使用 [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) 禁用目录同步：</span><span class="sxs-lookup"><span data-stu-id="ce3d0-112">Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="ce3d0-113">如果使用此命令，则必须等待 72 小时，然后才能重新启用目录同步。</span><span class="sxs-lookup"><span data-stu-id="ce3d0-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
