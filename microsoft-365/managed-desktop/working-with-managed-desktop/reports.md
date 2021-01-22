---
title: 处理报告
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a80616b58298ba544b9eab1d19ffb77f0e6825d4
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921346"
---
# <a name="work-with-reports"></a><span data-ttu-id="d0754-103">处理报告</span><span class="sxs-lookup"><span data-stu-id="d0754-103">Work with reports</span></span>

<span data-ttu-id="d0754-104">Microsoft 托管桌面提供了多个报表和仪表板，你的组织中 IT 管理员可以使用这些报表和仪表板来了解设备数量的各个方面。</span><span class="sxs-lookup"><span data-stu-id="d0754-104">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="d0754-105">你将在两个位置找到报告 [：Microsoft Endpoint Manager](https://endpoint.microsoft.com) 和 Microsoft [365 管理中心](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。</span><span class="sxs-lookup"><span data-stu-id="d0754-105"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="d0754-106">Microsoft Endpoint Manager 中的报告</span><span class="sxs-lookup"><span data-stu-id="d0754-106">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="d0754-107">Microsoft Endpoint Manager 控制台将多个产品的报告汇集到一个位置，帮助你监视和调查 Azure AD 组织 ("租户") 和设备的问题。</span><span class="sxs-lookup"><span data-stu-id="d0754-107">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="d0754-108">Microsoft 托管桌面在主菜单中的"报告"下有一部分，您可以在其中找到特定于 Microsoft 托管桌面对已注册设备的管理的报告。</span><span class="sxs-lookup"><span data-stu-id="d0754-108">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="d0754-109">这些报告包括：</span><span class="sxs-lookup"><span data-stu-id="d0754-109">These reports include:</span></span>
- <span data-ttu-id="d0754-110">**托管设备**  > **功能更新**：此视图显示整个 Microsoft 托管桌面设备中的功能更新的总体状态。</span><span class="sxs-lookup"><span data-stu-id="d0754-110">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="d0754-111">**托管设备**  > **Office 更新**：此视图显示 Microsoft 托管桌面设备中的 Office 更新的总体状态。</span><span class="sxs-lookup"><span data-stu-id="d0754-111">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="d0754-112">此外，可以在 Microsoft Endpoint Manager 中的多个位置筛选来自其他产品组的报表，以专门包含或排除由 Microsoft 托管桌面管理的设备。</span><span class="sxs-lookup"><span data-stu-id="d0754-112">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0754-113">这些报告集成了此筛选功能：</span><span class="sxs-lookup"><span data-stu-id="d0754-113">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="d0754-114">所有设备</span><span class="sxs-lookup"><span data-stu-id="d0754-114">All devices</span></span>](https://docs.microsoft.com/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="d0754-115">设备合规性</span><span class="sxs-lookup"><span data-stu-id="d0754-115">Device compliance</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="d0754-116">不符合要求的设备</span><span class="sxs-lookup"><span data-stu-id="d0754-116">Noncompliant devices</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="d0754-117">自定义 Microsoft 托管桌面角色保证仅访问 Microsoft 托管桌面报告。</span><span class="sxs-lookup"><span data-stu-id="d0754-117">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="d0754-118">若要访问 Microsoft Endpoint Manager 的其他部分（如所有设备），请参阅[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)中的基于角色的访问控制。</span><span class="sxs-lookup"><span data-stu-id="d0754-118">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).</span></span> 

## <a name="reports-in-microsoft-365-admin-center"></a><span data-ttu-id="d0754-119">Microsoft 365 管理中心中的报告</span><span class="sxs-lookup"><span data-stu-id="d0754-119">Reports in Microsoft 365 Admin Center</span></span>

<span data-ttu-id="d0754-120">可以通过打开 Microsoft [365](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)管理中心，然后导航到"报表"并选择 **"Microsoft** 托管桌面"来查找 Microsoft 托管桌面见解报告。</span><span class="sxs-lookup"><span data-stu-id="d0754-120">You can find Microsoft Managed Desktop insights reports by opening the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop), and then navigating to **Reports** and selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="d0754-121">也可以按照从主页 **上的 Microsoft** 托管桌面选项卡上的 Microsoft Endpoint Manager 直接链接到 [这些报告](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="d0754-121">You can also follow the direct link to these reports from the **Microsoft Managed Desktop** tab on the homepage [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span> 

<span data-ttu-id="d0754-122">这些报告包括：</span><span class="sxs-lookup"><span data-stu-id="d0754-122">These reports include:</span></span> 

- <span data-ttu-id="d0754-123">[使用情况见解](usage-insights.md) - 此视图提供 Microsoft 托管桌面设备的使用指标。</span><span class="sxs-lookup"><span data-stu-id="d0754-123">[Usage insights](usage-insights.md) - This view provides usage metrics for your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="d0754-124">[可靠性见解](reliability-insights.md) - 此视图为您提供托管设备的运行状况摘要。</span><span class="sxs-lookup"><span data-stu-id="d0754-124">[Reliability insights](reliability-insights.md) - This view provides you with a health summary of your managed devices.</span></span>
- <span data-ttu-id="d0754-125">[电池见解](battery-insights.md) - 此视图显示有关应用中的能耗和环境中设备预计电池使用时间的信息。</span><span class="sxs-lookup"><span data-stu-id="d0754-125">[Battery insights](battery-insights.md) - This view shows you information about the energy consumption of apps and projected battery life for devices in your environment.</span></span>
- <span data-ttu-id="d0754-126">[Windows 安全更新见解](security-update-insights.md) - 此视图显示有关 Microsoft 托管桌面设备安全更新状态的信息。</span><span class="sxs-lookup"><span data-stu-id="d0754-126">[Windows security update insights](security-update-insights.md) - This view shows you information about the status of security updates for your Microsoft Managed Desktop devices.</span></span>

 ## <a name="inventory-data"></a><span data-ttu-id="d0754-127">清单数据</span><span class="sxs-lookup"><span data-stu-id="d0754-127">Inventory data</span></span>

<span data-ttu-id="d0754-128">除了其他报告外，还可以导出有关由 Microsoft 托管桌面管理的设备的信息。</span><span class="sxs-lookup"><span data-stu-id="d0754-128">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="d0754-129">在Microsoft Endpoint Manager的"设备"区域中的"设备"视图中，使用"导出所有 **"选项卡**[下载详细的清单报告](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="d0754-129">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>
