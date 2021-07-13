---
title: Microsoft 365 Lighthouse设备合规性页面概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (MSP) ，Microsoft 365 Lighthouse设备合规性页面。
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395002"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="24615-103">Microsoft 365 Lighthouse设备合规性页面概述</span><span class="sxs-lookup"><span data-stu-id="24615-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="24615-104">本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24615-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="24615-105">如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="24615-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="24615-106">Microsoft 365 Lighthouse通过选择左侧导航窗格中的"设备"打开"设备合规性"页，查看所有租户的 Intune设备合规性相关见解和信息。</span><span class="sxs-lookup"><span data-stu-id="24615-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="24615-107">在此页面中，你可以获取跨租户的合规性状态的概述，查看每个租户的设备列表，并获取有关合规性策略和设置的状态报告。</span><span class="sxs-lookup"><span data-stu-id="24615-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="24615-108">"概述"选项卡</span><span class="sxs-lookup"><span data-stu-id="24615-108">Overview tab</span></span>  
  
<span data-ttu-id="24615-109">在"概述"选项卡上，可以查看租户中的设备合规性状态、查看每月设备合规性趋势，并跟踪设备是否分配有合规性策略。</span><span class="sxs-lookup"><span data-stu-id="24615-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="24615-110">还可以根据条件访问策略查看有关租户设备合规性操作和要求的信息。</span><span class="sxs-lookup"><span data-stu-id="24615-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="&quot;概述&quot;选项卡的屏幕截图。":::

## <a name="devices-tab"></a><span data-ttu-id="24615-112">"设备"选项卡</span><span class="sxs-lookup"><span data-stu-id="24615-112">Devices tab</span></span>

<span data-ttu-id="24615-113">在"设备"选项卡上，可以查看所有租户设备的列表，并基于以下合规性状态筛选该列表：Compliant、Non-compliant、In Grace period 和 Not evaluated。</span><span class="sxs-lookup"><span data-stu-id="24615-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="24615-114">有关不同合规性状态的信息，请参阅监视 [Intune 设备合规性策略](/mem/intune/protect/compliance-policy-monitor)。</span><span class="sxs-lookup"><span data-stu-id="24615-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="24615-115">选择任何设备以查看有关设备为何位于其当前合规性状态详细信息。</span><span class="sxs-lookup"><span data-stu-id="24615-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="24615-116">如果你需要在设备上采取措施，可以选择在设备上查看Microsoft Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="24615-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="&quot;设备&quot;选项卡的屏幕截图。":::

## <a name="policies-tab"></a><span data-ttu-id="24615-118">"策略"选项卡</span><span class="sxs-lookup"><span data-stu-id="24615-118">Policies tab</span></span>

<span data-ttu-id="24615-119">在"策略"选项卡上，可以使用工具栏上的"比较"功能查看租户中的合规性策略，并比较两个或三个相同平台类型的策略。</span><span class="sxs-lookup"><span data-stu-id="24615-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="24615-120">还可以选择任何策略来查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="24615-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="&quot;策略&quot;选项卡的屏幕截图。":::

## <a name="settings-tab"></a><span data-ttu-id="24615-122">设置选项卡</span><span class="sxs-lookup"><span data-stu-id="24615-122">Settings tab</span></span>

<span data-ttu-id="24615-123">"设置"选项卡提供跨租户设备的不兼容设置的聚合报告。</span><span class="sxs-lookup"><span data-stu-id="24615-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="24615-124">选择任一报告行以查看详细信息，包括不兼容设备属于哪些租户。</span><span class="sxs-lookup"><span data-stu-id="24615-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="&quot;设置&quot;选项卡设置屏幕截图。":::

## <a name="related-content"></a><span data-ttu-id="24615-126">相关内容</span><span class="sxs-lookup"><span data-stu-id="24615-126">Related content</span></span>

<span data-ttu-id="24615-127">[Microsoft 365 Lighthouse用户页面概述 (](m365-lighthouse-users-page-overview.md)文章) </span><span class="sxs-lookup"><span data-stu-id="24615-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="24615-128">[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="24615-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
