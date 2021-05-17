---
title: 设备列表 CSV 文件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 了解如何在适用于企业Microsoft 365 AutoPilot 创建 CSV 文件。
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579214"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="8bb57-103">设备列表 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="8bb57-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="8bb57-104">设备列表.csv文件格式</span><span class="sxs-lookup"><span data-stu-id="8bb57-104">Device list .csv file format</span></span>

<span data-ttu-id="8bb57-105">若要通过 Autopilot Windows和部署设备，你需要一个.csv设备特定信息的文件。</span><span class="sxs-lookup"><span data-stu-id="8bb57-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="8bb57-106">设备列表文件的列必须按指定顺序具有以下标题：</span><span class="sxs-lookup"><span data-stu-id="8bb57-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="8bb57-107">列 A：设备序列号</span><span class="sxs-lookup"><span data-stu-id="8bb57-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="8bb57-108">列 B：保留为空</span><span class="sxs-lookup"><span data-stu-id="8bb57-108">Column B: leave blank</span></span>

- <span data-ttu-id="8bb57-109">列 C：硬件哈希</span><span class="sxs-lookup"><span data-stu-id="8bb57-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="8bb57-110">可从硬件供应商获取此信息，也可以使用将生成 CSV 文件的 [G-et-WindowsAutoPilotInfo PowerShell 脚本](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)获取。</span><span class="sxs-lookup"><span data-stu-id="8bb57-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="8bb57-111">添加设备时，还需要将它们添加到配置文件。</span><span class="sxs-lookup"><span data-stu-id="8bb57-111">When you add devices, you also need to add them to a Profile.</span></span> <span data-ttu-id="8bb57-112">配置文件用于将 AutoPilot 部署配置文件应用于设备或一组设备。</span><span class="sxs-lookup"><span data-stu-id="8bb57-112">A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8bb57-113">相关文章</span><span class="sxs-lookup"><span data-stu-id="8bb57-113">Related articles</span></span>

[<span data-ttu-id="8bb57-114">Microsoft 365文档和资源</span><span class="sxs-lookup"><span data-stu-id="8bb57-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="8bb57-115">企业Microsoft 365入门</span><span class="sxs-lookup"><span data-stu-id="8bb57-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="8bb57-116">管理Microsoft 365企业部署</span><span class="sxs-lookup"><span data-stu-id="8bb57-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
