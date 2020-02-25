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
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238370"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="e0779-103">管理设备的许可证</span><span class="sxs-lookup"><span data-stu-id="e0779-103">Manage licenses for devices</span></span>

<span data-ttu-id="e0779-104">如果您有 Office 365 专业增强版教育版（设备），您可以使用 Azure AD 组将许可证分配给设备。</span><span class="sxs-lookup"><span data-stu-id="e0779-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="e0779-105">当设备具有许可证时，使用该设备的任何人都可以使用 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e0779-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="e0779-106">例如，假设你的组织中的人员使用20台膝上型电脑和平板电脑。</span><span class="sxs-lookup"><span data-stu-id="e0779-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="e0779-107">将许可证分配给每个设备时，登录到其中一个设备的每个人都将使用 Office 365，而无需自己的许可证。</span><span class="sxs-lookup"><span data-stu-id="e0779-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0779-108">Office 365 专业增强版教育版（设备）仅适用于教育版 A3 和 A5 批量许可客户。</span><span class="sxs-lookup"><span data-stu-id="e0779-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="e0779-109">若要开始，请在 Azure Active Directory 管理中心中创建一个组，然后将设备分配到该组。</span><span class="sxs-lookup"><span data-stu-id="e0779-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="e0779-110">若要了解有关设备许可的详细信息（包括设备要求、可以使用哪些类型的组以及如何将 Office 365 专业增强版配置为使用设备许可），请参阅[适用于 office 365 专业增强版的设备许可教育客户](https://go.microsoft.com/fwlink/p/?linkid=2094216)。</span><span class="sxs-lookup"><span data-stu-id="e0779-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0779-111">您必须是全局管理员才能完成本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="e0779-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="e0779-112">将许可证分配给设备</span><span class="sxs-lookup"><span data-stu-id="e0779-112">Assign licenses to devices</span></span>

<span data-ttu-id="e0779-113">将许可证分配给组时，会将许可证分配给组中的所有设备。</span><span class="sxs-lookup"><span data-stu-id="e0779-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="e0779-114">您只能将一个订阅分配给任何单个组。</span><span class="sxs-lookup"><span data-stu-id="e0779-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="e0779-115">在 Microsoft 365 管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e0779-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="e0779-116">在 "**许可证**" 页上，选择 " **Office 365 专业增强版教育版（设备）**"。</span><span class="sxs-lookup"><span data-stu-id="e0779-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="e0779-117">在 " **Office 365 专业增强版教育版（设备）** " 页上，选择 "订阅"，然后选择 "**分配许可证**"。</span><span class="sxs-lookup"><span data-stu-id="e0779-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="e0779-118">在 "**将许可证分配给组**" 窗格中，开始键入组名称，然后从结果中选择它以将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="e0779-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="e0779-119">选择 "**分配**"，然后选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e0779-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="e0779-120">从设备中取消分配许可证</span><span class="sxs-lookup"><span data-stu-id="e0779-120">Unassign licenses from devices</span></span>

<span data-ttu-id="e0779-121">从组中取消分配许可证时，将从组内的所有设备中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="e0779-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="e0779-122">所有应用及其关联的数据都是只读的。</span><span class="sxs-lookup"><span data-stu-id="e0779-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="e0779-123">在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="e0779-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="e0779-124">在 "**许可证**" 页上，选择 " **Office 365 专业增强版教育版（设备）**"。</span><span class="sxs-lookup"><span data-stu-id="e0779-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="e0779-125">在 " **Office 365 专业增强版教育版（设备）** " 页上，选择 "订阅"，选择 "**更多操作**"，然后选择 "未**分配许可证**"。</span><span class="sxs-lookup"><span data-stu-id="e0779-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="e0779-126">在 "未**分配许可证**" 对话框中，选择 "未**分配**"。</span><span class="sxs-lookup"><span data-stu-id="e0779-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>