---
title: 处理报告
description: 各种报告Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729964"
---
# <a name="work-with-reports"></a><span data-ttu-id="1b053-104">处理报告</span><span class="sxs-lookup"><span data-stu-id="1b053-104">Work with reports</span></span>

<span data-ttu-id="1b053-105">Microsoft 托管桌面提供了几个报告和仪表板，您的组织中的 IT 管理员可以使用这些报表和仪表板了解设备数量的各个方面。</span><span class="sxs-lookup"><span data-stu-id="1b053-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="1b053-106">你将在两个位置找到报告：在 Microsoft Endpoint Manager[和](https://endpoint.microsoft.com)Microsoft 365[管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)中。</span><span class="sxs-lookup"><span data-stu-id="1b053-106"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="1b053-107">报告Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="1b053-107">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="1b053-108">Microsoft Endpoint Manager控制台将多个产品的报告汇集到一个位置，帮助你监视和调查 Azure AD 组织（"租户 (配置和设备) 问题。</span><span class="sxs-lookup"><span data-stu-id="1b053-108">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="1b053-109">Microsoft 托管桌面在主菜单中的"报告"下有一个部分，你可以找到特定于Microsoft 托管桌面注册设备的管理的报告。</span><span class="sxs-lookup"><span data-stu-id="1b053-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="1b053-110">这些报告包括：</span><span class="sxs-lookup"><span data-stu-id="1b053-110">These reports include:</span></span>
- <span data-ttu-id="1b053-111">**托管设备**  > **功能更新**：此视图显示跨设备更新功能Microsoft 托管桌面状态。</span><span class="sxs-lookup"><span data-stu-id="1b053-111">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="1b053-112">**托管设备**  > **Office更新**： 此视图显示跨 Office 设备更新Microsoft 托管桌面状态。</span><span class="sxs-lookup"><span data-stu-id="1b053-112">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="1b053-113">此外，你可以在整个 Microsoft Endpoint Manager 多个位置筛选来自其他产品组的报告，以专门包含或排除由 Microsoft 托管桌面 管理的设备。</span><span class="sxs-lookup"><span data-stu-id="1b053-113">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1b053-114">这些报告集成了此筛选功能：</span><span class="sxs-lookup"><span data-stu-id="1b053-114">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="1b053-115">所有设备</span><span class="sxs-lookup"><span data-stu-id="1b053-115">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="1b053-116">设备合规性</span><span class="sxs-lookup"><span data-stu-id="1b053-116">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="1b053-117">不符合要求的设备</span><span class="sxs-lookup"><span data-stu-id="1b053-117">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="1b053-118">自定义Microsoft 托管桌面角色保证仅访问Microsoft 托管桌面报告。</span><span class="sxs-lookup"><span data-stu-id="1b053-118">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="1b053-119">若要访问其他Microsoft Endpoint Manager，如所有 **设备**，请参阅基于角色的访问控制 [和](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="1b053-119">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 


 ## <a name="inventory-data"></a><span data-ttu-id="1b053-120">清单数据</span><span class="sxs-lookup"><span data-stu-id="1b053-120">Inventory data</span></span>

<span data-ttu-id="1b053-121">除了其他报告之外，还可以导出有关由设备管理的设备Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="1b053-121">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1b053-122">在 **"设备"** 视图中的"设备"Microsoft Endpoint Manager，使用"导出所有"选项卡 [下载详细的清单报告](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="1b053-122">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>