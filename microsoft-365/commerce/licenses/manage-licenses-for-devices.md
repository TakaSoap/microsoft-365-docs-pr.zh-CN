---
title: 管理设备的许可证
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911476"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="27209-103">管理设备的许可证</span><span class="sxs-lookup"><span data-stu-id="27209-103">Manage licenses for devices</span></span>

<span data-ttu-id="27209-104">如果你有 Microsoft 365 企业应用版 (设备) 或 Microsoft 365 教育应用版 (设备) ，可以使用 Azure AD 组向设备分配许可证。</span><span class="sxs-lookup"><span data-stu-id="27209-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="27209-105">当设备具有许可证时，使用该设备的任何人都可以使用以前名为 Office 365 专业增强 (Microsoft 365 企业应用版) 。</span><span class="sxs-lookup"><span data-stu-id="27209-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="27209-106">例如，假设你拥有 20 台笔记本电脑和平板电脑，供组织人员使用。</span><span class="sxs-lookup"><span data-stu-id="27209-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="27209-107">向每台设备分配许可证时，登录到其中一台设备的每个人将使用 Microsoft 365 企业应用版，而无需自己的许可证。</span><span class="sxs-lookup"><span data-stu-id="27209-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27209-108">Microsoft 365 企业应用版基于设备的许可仅作为附加许可证提供给一些商业客户和一些教育客户。</span><span class="sxs-lookup"><span data-stu-id="27209-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="27209-109">对于商业客户，许可证是 *Microsoft 365* 企业应用版 (设备) 并且仅通过 企业协议/企业协议 订阅提供。</span><span class="sxs-lookup"><span data-stu-id="27209-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="27209-110">对于教育行业客户，许可证是 *Microsoft 365* 教育应用版 (设备) 并且仅通过注册教育版解决方案 (EES) 。</span><span class="sxs-lookup"><span data-stu-id="27209-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="27209-111">有关详细信息，请阅读有关教育可用性 [的博客文章](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)。</span><span class="sxs-lookup"><span data-stu-id="27209-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="27209-112">要获得商业可用性，请联系你的 Microsoft 帐户代表。</span><span class="sxs-lookup"><span data-stu-id="27209-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="27209-113">首先，在 Azure Active Directory 管理中心创建一个组，然后将设备分配给该组。</span><span class="sxs-lookup"><span data-stu-id="27209-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="27209-114">若要了解有关设备许可（包括设备要求、可以使用的组类型以及如何配置 Microsoft 365 企业应用版以使用设备许可）的信息，请参阅 Microsoft [365](/deployoffice/device-based-licensing)企业应用版基于设备的许可。</span><span class="sxs-lookup"><span data-stu-id="27209-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27209-115">你必须是全局管理员才能完成本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="27209-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="27209-116">向设备分配许可证</span><span class="sxs-lookup"><span data-stu-id="27209-116">Assign licenses to devices</span></span>

<span data-ttu-id="27209-117">将许可证分配给组时，需要将许可证分配给组内的所有设备。</span><span class="sxs-lookup"><span data-stu-id="27209-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="27209-118">只能向任何单个组分配一个订阅。</span><span class="sxs-lookup"><span data-stu-id="27209-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="27209-119">在 Microsoft 365 管理中心中，转到"帐单  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">""许可证"</a>页面。</span><span class="sxs-lookup"><span data-stu-id="27209-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="27209-120">在许可证 **页面上**，选择 **Microsoft 365** 教育应用版 (device) 或 **Microsoft 365 企业应用版 (设备) 。**</span><span class="sxs-lookup"><span data-stu-id="27209-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="27209-121">On the next page， choose a subscription， then choose **Assign licenses**.</span><span class="sxs-lookup"><span data-stu-id="27209-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="27209-122">在 **"将许可证分配给组** "窗格中，开始键入组名称，然后从结果中选择它以将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="27209-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="27209-123">选择 **"分配"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="27209-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="27209-124">取消分配设备中的许可证</span><span class="sxs-lookup"><span data-stu-id="27209-124">Unassign licenses from devices</span></span>

<span data-ttu-id="27209-125">从组取消分配许可证时，会从组内的所有设备中删除许可证。</span><span class="sxs-lookup"><span data-stu-id="27209-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="27209-126">然后，所有应用及其关联数据都是只读的。</span><span class="sxs-lookup"><span data-stu-id="27209-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="27209-127">在管理中心，转到"帐单  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">""许可证"</a>页面。</span><span class="sxs-lookup"><span data-stu-id="27209-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="27209-128">在许可证 **页面上**，选择 **Microsoft 365** 教育应用版 (device) 或 **Microsoft 365 企业应用版 (设备) 。**</span><span class="sxs-lookup"><span data-stu-id="27209-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="27209-129">On the next page， choose a subscription， choose **More actions**， then choose **Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="27209-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="27209-130">在"**取消分配许可证**"对话框中，选择"**取消分配"。**</span><span class="sxs-lookup"><span data-stu-id="27209-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>