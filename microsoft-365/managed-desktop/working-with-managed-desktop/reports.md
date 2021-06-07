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
ms.openlocfilehash: b37ce09a0781aa83970502224ddbb3658ed07d69
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771881"
---
# <a name="work-with-reports"></a><span data-ttu-id="1f84d-104">处理报告</span><span class="sxs-lookup"><span data-stu-id="1f84d-104">Work with reports</span></span>

<span data-ttu-id="1f84d-105">Microsoft 托管桌面提供了几个报告和仪表板，您的组织中的 IT 管理员可以使用这些报表和仪表板了解设备数量的各个方面。</span><span class="sxs-lookup"><span data-stu-id="1f84d-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="1f84d-106">报告Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="1f84d-106">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="1f84d-107">Microsoft Endpoint Manager控制台将多个产品的报告汇集到一个位置，帮助你监视和调查 Azure AD 组织（"租户 (配置和设备) 问题。</span><span class="sxs-lookup"><span data-stu-id="1f84d-107">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="1f84d-108">Microsoft 托管桌面在主菜单中的"报告"下有一个部分，你可以找到特定于Microsoft 托管桌面注册设备的管理的报告。</span><span class="sxs-lookup"><span data-stu-id="1f84d-108">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="1f84d-109">这些报告包括：</span><span class="sxs-lookup"><span data-stu-id="1f84d-109">These reports include:</span></span>
- <span data-ttu-id="1f84d-110">**托管设备**  > **功能更新**：此视图显示跨设备更新功能Microsoft 托管桌面状态。</span><span class="sxs-lookup"><span data-stu-id="1f84d-110">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="1f84d-111">**托管设备**  > **Office更新**： 此视图显示跨 Office 设备更新Microsoft 托管桌面状态。</span><span class="sxs-lookup"><span data-stu-id="1f84d-111">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="1f84d-112">此外，你可以在整个 Microsoft Endpoint Manager 多个位置筛选来自其他产品组的报告，以专门包含或排除由 Microsoft 托管桌面 管理的设备。</span><span class="sxs-lookup"><span data-stu-id="1f84d-112">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1f84d-113">这些报告集成了此筛选功能：</span><span class="sxs-lookup"><span data-stu-id="1f84d-113">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="1f84d-114">所有设备</span><span class="sxs-lookup"><span data-stu-id="1f84d-114">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="1f84d-115">设备合规性</span><span class="sxs-lookup"><span data-stu-id="1f84d-115">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="1f84d-116">不符合要求的设备</span><span class="sxs-lookup"><span data-stu-id="1f84d-116">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="1f84d-117">自定义Microsoft 托管桌面角色保证仅访问Microsoft 托管桌面报告。</span><span class="sxs-lookup"><span data-stu-id="1f84d-117">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="1f84d-118">若要访问其他Microsoft Endpoint Manager，如所有 **设备**，请参阅基于角色的访问控制 [和](/mem/intune/fundamentals/role-based-access-control)Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="1f84d-118">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 

## <a name="endpoint-analytics"></a><span data-ttu-id="1f84d-119">终结点分析</span><span class="sxs-lookup"><span data-stu-id="1f84d-119">Endpoint analytics</span></span>
<span data-ttu-id="1f84d-120">Microsoft 托管桌面现在与[Endpoint Analytics 集成](/mem/analytics/overview)。</span><span class="sxs-lookup"><span data-stu-id="1f84d-120">Microsoft Managed Desktop is now integrated with [Endpoint analytics](/mem/analytics/overview).</span></span> <span data-ttu-id="1f84d-121">这些报告可让你深入了解如何衡量组织的运行方式以及为用户提供的体验质量。</span><span class="sxs-lookup"><span data-stu-id="1f84d-121">These reports give you insights for measuring how your organization is working and the quality of the experience delivered to your users.</span></span> <span data-ttu-id="1f84d-122">终结点分析位于终结点 **分析的"** 报告 ["Microsoft Endpoint Manager。](https://endpoint.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="1f84d-122">Endpoint analytics is in the **Reports** menu of [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="1f84d-123">若要透视分数以仅包含由管理的设备Microsoft 托管桌面转到任何报告，请选择"筛选器"下拉列表，然后选择"Microsoft 托管桌面 **设备"。** </span><span class="sxs-lookup"><span data-stu-id="1f84d-123">To pivot a score to only include devices being managed by Microsoft Managed Desktop go to any report, select the **Filter** drop down, and then select **Microsoft Managed Desktop devices**.</span></span>

<span data-ttu-id="1f84d-124">如果在注册期间未自动为 Azure AD ("租户") 配置终结点分析，可以自己执行。</span><span class="sxs-lookup"><span data-stu-id="1f84d-124">If Endpoint analytics wasn't automatically configured for your Azure AD organization ("tenant") during enrollment, you can do that yourself.</span></span> <span data-ttu-id="1f84d-125">有关详细信息，请参阅终结点 [分析门户中的载入](/mem/analytics/enroll-intune#bkmk_onboard)。</span><span class="sxs-lookup"><span data-stu-id="1f84d-125">For more information, see [Onboard in the Endpoint analytics portal](/mem/analytics/enroll-intune#bkmk_onboard).</span></span> <span data-ttu-id="1f84d-126">你可以注册所有设备，或者如果你希望仅包括Microsoft 托管桌面，请为"测试"、第一个、"快速"和"广泛"选择现代工作区设备组。</span><span class="sxs-lookup"><span data-stu-id="1f84d-126">You can enroll all your devices or, if you want to include only Microsoft Managed Desktop devices, select the **modern workplace device** groups for Test, First, Fast, and Broad.</span></span> <span data-ttu-id="1f84d-127">这些报告可能需要不同的权限。</span><span class="sxs-lookup"><span data-stu-id="1f84d-127">These reports might require different permissions.</span></span> <span data-ttu-id="1f84d-128">有关详细信息，请参阅 [确保](/mem/analytics/overview#permissions) 正确分配角色的权限。</span><span class="sxs-lookup"><span data-stu-id="1f84d-128">For more information, see [Permissions](/mem/analytics/overview#permissions) to ensure you have roles appropriately assigned.</span></span>

> [!NOTE]
> <span data-ttu-id="1f84d-129">为了更好地尊重隐私用户隐私，必须Microsoft 托管桌面终结点分析的设备使用此筛选器。</span><span class="sxs-lookup"><span data-stu-id="1f84d-129">To better respect privacy user privacy, there must be more than 10 Microsoft Managed Desktop devices enrolled with Endpoint analytics to use this filter.</span></span>

 ## <a name="inventory-data"></a><span data-ttu-id="1f84d-130">清单数据</span><span class="sxs-lookup"><span data-stu-id="1f84d-130">Inventory data</span></span>

<span data-ttu-id="1f84d-131">除了其他报告之外，还可以导出有关由设备管理的设备Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="1f84d-131">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="1f84d-132">在 **"设备"** 视图中的"设备"Microsoft Endpoint Manager，使用"导出所有"选项卡 [下载详细的清单报告](device-inventory-report.md)。</span><span class="sxs-lookup"><span data-stu-id="1f84d-132">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>
