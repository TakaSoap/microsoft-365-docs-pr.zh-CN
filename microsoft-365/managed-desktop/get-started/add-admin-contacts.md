---
title: 在管理门户中添加和验证管理员联系人
description: 告诉我们每个焦点区域的联系人。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8a5775d90f592aa5f64dd5f379fb37278032d87
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529799"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="fcdd0-104">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="fcdd0-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="fcdd0-105">Microsoft 托管桌面服务与客户进行通信有几种方式。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="fcdd0-106">为了简化通信并确保使用正确的人员进行检查，您需要提供一组管理员联系人。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="fcdd0-107">Microsoft 托管桌面 IT 操作将与这些人员联系，以帮助解决你的租户问题。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcdd0-108">您可能已经在管理门户中添加了这些联系人。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="fcdd0-109">如果是这样，请立即花些时间仔细检查联系人列表是否准确，因为 Microsoft 托管桌面**必须**能够在发生严重事件时访问它们。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="fcdd0-110">Microsoft 托管桌面管理门户的 Azure Active Directory 访问</span><span class="sxs-lookup"><span data-stu-id="fcdd0-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="fcdd0-111">Microsoft 托管桌面管理门户要求访问门户的用户拥有以下 Azure Active Directory （AD）角色之一：</span><span class="sxs-lookup"><span data-stu-id="fcdd0-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="fcdd0-112">全局管理员</span><span class="sxs-lookup"><span data-stu-id="fcdd0-112">Global Administrator</span></span>
- <span data-ttu-id="fcdd0-113">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="fcdd0-113">Intune Service Administrator</span></span>
- <span data-ttu-id="fcdd0-114">全局读取者</span><span class="sxs-lookup"><span data-stu-id="fcdd0-114">Global Reader</span></span>
- <span data-ttu-id="fcdd0-115">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="fcdd0-115">Service Support Administrator</span></span>

<span data-ttu-id="fcdd0-116">全局管理员必须是在 Microsoft 托管桌面中注册您的组织的管理员。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="fcdd0-117">在管理门户中，所有五个角色都具有相同的访问权限，以启动和查看任务。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="fcdd0-118">有关在 Azure AD 中分配这些角色的详细信息，请参阅[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="fcdd0-119">管理联系人焦点区域</span><span class="sxs-lookup"><span data-stu-id="fcdd0-119">Admin contact areas of focus</span></span>

<span data-ttu-id="fcdd0-120">管理员联系人应是可以回答问题并针对不同关注领域做出决定的最佳人员或组。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="fcdd0-121">**Microsoft 托管桌面操作将与这些管理员联系人联系，以了解涉及客户存档的支持请求的问题。**</span><span class="sxs-lookup"><span data-stu-id="fcdd0-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="fcdd0-122">这些管理员联系人将接收支持请求更新和新邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="fcdd0-123">这些领域包括：</span><span class="sxs-lookup"><span data-stu-id="fcdd0-123">These areas include:</span></span>

<span data-ttu-id="fcdd0-124">焦点区域</span><span class="sxs-lookup"><span data-stu-id="fcdd0-124">Area of focus</span></span> | <span data-ttu-id="fcdd0-125">有关的问题</span><span class="sxs-lookup"><span data-stu-id="fcdd0-125">For questions about</span></span>
--- | ---
<span data-ttu-id="fcdd0-126">应用程序打包</span><span class="sxs-lookup"><span data-stu-id="fcdd0-126">App packaging</span></span> | <span data-ttu-id="fcdd0-127">应用程序打包故障排除</span><span class="sxs-lookup"><span data-stu-id="fcdd0-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="fcdd0-128">设备</span><span class="sxs-lookup"><span data-stu-id="fcdd0-128">Devices</span></span> | <span data-ttu-id="fcdd0-129">设备运行状况，使用 Microsoft 托管桌面设备进行故障排除</span><span class="sxs-lookup"><span data-stu-id="fcdd0-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="fcdd0-130">安全性</span><span class="sxs-lookup"><span data-stu-id="fcdd0-130">Security</span></span> | <span data-ttu-id="fcdd0-131">Microsoft 托管桌面设备的安全问题故障排除</span><span class="sxs-lookup"><span data-stu-id="fcdd0-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="fcdd0-132">IT 技术支持人员</span><span class="sxs-lookup"><span data-stu-id="fcdd0-132">IT help desk</span></span> | <span data-ttu-id="fcdd0-133">如果我们的支持人员在 Microsoft 托管桌面支持区域之外的最终用户票据上进行了干预</span><span class="sxs-lookup"><span data-stu-id="fcdd0-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="fcdd0-134">其他</span><span class="sxs-lookup"><span data-stu-id="fcdd0-134">Other</span></span> | <span data-ttu-id="fcdd0-135">对于未被其他区域覆盖的问题</span><span class="sxs-lookup"><span data-stu-id="fcdd0-135">For issues not covered by other areas</span></span>

<span data-ttu-id="fcdd0-136">**你为这些联系人选择的任何人都需要了解有关 Microsoft 托管桌面环境的决策的知识和权威。**</span><span class="sxs-lookup"><span data-stu-id="fcdd0-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="fcdd0-137">在集成 Microsoft 托管桌面环境时，系统会提示你为本地帮助台和安全添加联系人。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="fcdd0-138">[提交支持请求](../service-description/support.md)时，需要管理员联系人。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="fcdd0-139">您需要具有管理员联系人的支持请求的焦点区域。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="fcdd0-140">**添加管理员联系人**</span><span class="sxs-lookup"><span data-stu-id="fcdd0-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="fcdd0-141">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="fcdd0-142">在 "**支持**" 下，选择 "**管理联系人**"。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![支持菜单，在所选顶部附近为管理员联系人](../../media/admincontacts.png)

3. <span data-ttu-id="fcdd0-144">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-144">Select **Add**.</span></span>

    !["管理门户"、"添加" 按钮（位于 "导出" 和 "刷新" 的左侧）](../../media/adminadd.png)

4.  <span data-ttu-id="fcdd0-146">选择**焦点区域**并输入联系人的信息。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![焦点区域的列表，如其他、应用程序和安全性](../../media/areaoffocus.png)

5. <span data-ttu-id="fcdd0-148">对每个焦点区域重复此操作。</span><span class="sxs-lookup"><span data-stu-id="fcdd0-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="fcdd0-149">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="fcdd0-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="fcdd0-150">在管理门户中添加和验证管理员联系人（本主题）</span><span class="sxs-lookup"><span data-stu-id="fcdd0-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="fcdd0-151">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="fcdd0-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="fcdd0-152">分配许可证</span><span class="sxs-lookup"><span data-stu-id="fcdd0-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="fcdd0-153">在设备上安装 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="fcdd0-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="fcdd0-154">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="fcdd0-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="fcdd0-155">设置 Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="fcdd0-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="fcdd0-156">为用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="fcdd0-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="fcdd0-157">将应用部署到设备</span><span class="sxs-lookup"><span data-stu-id="fcdd0-157">Deploy apps to devices</span></span>](deploy-apps.md)
