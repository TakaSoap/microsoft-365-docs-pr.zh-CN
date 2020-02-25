---
title: 设备列表 CSV-文件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 了解如何为 AutoPilo tin Microsoft 365 商业版创建 CSV 文件。
ms.openlocfilehash: cd317bd5edaa3fdaea8a704f79a269387e8fe1c1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252455"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="22a70-103">设备列表 CSV-文件</span><span class="sxs-lookup"><span data-stu-id="22a70-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="22a70-104">设备列表 .csv 文件格式</span><span class="sxs-lookup"><span data-stu-id="22a70-104">Device list .csv file format</span></span>

<span data-ttu-id="22a70-105">若要通过 Windows Autopilot 管理和部署设备，您需要一个包含有关设备的特定信息的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="22a70-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="22a70-106">设备列表文件中的列必须按指定的顺序包含以下标头：</span><span class="sxs-lookup"><span data-stu-id="22a70-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="22a70-107">列 A：设备序列号</span><span class="sxs-lookup"><span data-stu-id="22a70-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="22a70-108">列 B：留空</span><span class="sxs-lookup"><span data-stu-id="22a70-108">Column B: leave blank</span></span>

- <span data-ttu-id="22a70-109">列 C：硬件哈希</span><span class="sxs-lookup"><span data-stu-id="22a70-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="22a70-110">可从硬件供应商获取此信息，也可以使用将生成 CSV 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。</span><span class="sxs-lookup"><span data-stu-id="22a70-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="22a70-111">添加设备时，还需要将其添加到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="22a70-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="22a70-112">配置文件用于将 AutoPilot 部署配置文件应用于一个或一组设备。</span><span class="sxs-lookup"><span data-stu-id="22a70-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="22a70-113">相关文章</span><span class="sxs-lookup"><span data-stu-id="22a70-113">Related articles</span></span>

<span data-ttu-id="22a70-114">[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)（Microsoft 365 Business 文档和资源）</span><span class="sxs-lookup"><span data-stu-id="22a70-114">[Microsoft 365 Business documentation and resources](https://go.microsoft.com/fwlink/p/?linkid=853701)</span></span>
  
[<span data-ttu-id="22a70-115">Microsoft 365 Business 入门</span><span class="sxs-lookup"><span data-stu-id="22a70-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="22a70-116">管理 Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="22a70-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  