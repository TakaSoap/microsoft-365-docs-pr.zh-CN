---
title: 管理设备的许可证
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: 了解如何将许可证分配给组以用于设备。
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826275"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="551d0-103">管理设备的许可证</span><span class="sxs-lookup"><span data-stu-id="551d0-103">Manage licenses for devices</span></span>

<span data-ttu-id="551d0-104">如果您有 Office 365 专业增强版（设备）或 Office 365 专业增强版教育版（设备），您可以使用 Azure AD 组将许可证分配给设备。</span><span class="sxs-lookup"><span data-stu-id="551d0-104">If you have Office 365 ProPlus (device) or Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="551d0-105">当设备具有许可证时，使用该设备的任何人都可以使用 Office 365。</span><span class="sxs-lookup"><span data-stu-id="551d0-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="551d0-106">例如，假设你的组织中的人员使用20台膝上型电脑和平板电脑。</span><span class="sxs-lookup"><span data-stu-id="551d0-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="551d0-107">将许可证分配给每个设备时，登录到其中一个设备的每个人都将使用 Office 365，而无需自己的许可证。</span><span class="sxs-lookup"><span data-stu-id="551d0-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="551d0-108">Office 365 专业增强版的基于设备的许可仅作为一些 commerical 客户和一些教育客户的附加许可证提供。</span><span class="sxs-lookup"><span data-stu-id="551d0-108">Device-based licensing for Office 365 ProPlus is available only as an add-on license for some commerical customers and some education customers.</span></span> <span data-ttu-id="551d0-109">对于商业客户，许可证是*Office 365 专业增强版（设备）* ，并且只能通过企业协议/企业协议订阅提供。</span><span class="sxs-lookup"><span data-stu-id="551d0-109">For commercial customers, the license is *Office 365 ProPlus (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="551d0-110">对于教育版客户，许可证是*Office 365 专业增强版教育版（设备）* ，仅通过注册教育版解决方案（EES）提供。</span><span class="sxs-lookup"><span data-stu-id="551d0-110">For education customers, the license is *Office 365 ProPlus for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="551d0-111">有关详细信息，请阅读 "教育版上的博客文章"[可用性](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)。</span><span class="sxs-lookup"><span data-stu-id="551d0-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="551d0-112">若要获得商业可用性，请联系你的 Microsoft 帐户代表。</span><span class="sxs-lookup"><span data-stu-id="551d0-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="551d0-113">若要开始，请在 Azure Active Directory 管理中心中创建一个组，然后将设备分配到该组。</span><span class="sxs-lookup"><span data-stu-id="551d0-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="551d0-114">若要了解有关设备许可的详细信息（包括设备要求、可以使用的组类型以及如何将 Office 365 专业增强版配置为使用设备许可），请参阅[office 365 专业增强版的基于设备的许可](https://go.microsoft.com/fwlink/p/?linkid=2094216)。</span><span class="sxs-lookup"><span data-stu-id="551d0-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device-based licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="551d0-115">您必须是全局管理员才能完成本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="551d0-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="551d0-116">将许可证分配给设备</span><span class="sxs-lookup"><span data-stu-id="551d0-116">Assign licenses to devices</span></span>

<span data-ttu-id="551d0-117">将许可证分配给组时，会将许可证分配给组中的所有设备。</span><span class="sxs-lookup"><span data-stu-id="551d0-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="551d0-118">您只能将一个订阅分配给任何单个组。</span><span class="sxs-lookup"><span data-stu-id="551d0-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="551d0-119">在 Microsoft 365 管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="551d0-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="551d0-120">在 "**许可证**" 页上，选择 " **Office 365 专业增强版教育版（设备）** " 或 " **office 专业增强版（设备）**"。</span><span class="sxs-lookup"><span data-stu-id="551d0-120">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="551d0-121">在下一页上，选择 "订阅"，然后选择 "**分配许可证**"。</span><span class="sxs-lookup"><span data-stu-id="551d0-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="551d0-122">在 "**将许可证分配给组**" 窗格中，开始键入组名称，然后从结果中选择它以将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="551d0-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="551d0-123">选择 "**分配**"，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="551d0-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="551d0-124">从设备中取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="551d0-124">Unassign licenses from devices</span></span>

<span data-ttu-id="551d0-125">从组中取消分配许可证时，将从组内的所有设备中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="551d0-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="551d0-126">所有应用及其关联的数据都是只读的。</span><span class="sxs-lookup"><span data-stu-id="551d0-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="551d0-127">在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="551d0-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="551d0-128">在 "**许可证**" 页上，选择 " **Office 365 专业增强版教育版（设备）** " 或 " **office 专业增强版（设备）**"。</span><span class="sxs-lookup"><span data-stu-id="551d0-128">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="551d0-129">在下一页上，选择 "订阅"，选择 "**更多操作**"，然后选择 "未**分配许可证**"。</span><span class="sxs-lookup"><span data-stu-id="551d0-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="551d0-130">在 "未**分配许可证**" 对话框中，选择 "未**分配**"。</span><span class="sxs-lookup"><span data-stu-id="551d0-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>