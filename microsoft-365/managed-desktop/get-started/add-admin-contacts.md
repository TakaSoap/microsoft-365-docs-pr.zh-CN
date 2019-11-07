---
title: 在管理门户中添加和验证管理员联系人
description: 告诉我们每个焦点区域的联系人。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3f77a5f6f0af83ea82d2ab3cea0798b95e27c2d2
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012063"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="1382f-104">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="1382f-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="1382f-105">Microsoft 托管桌面服务与客户进行通信有几种方式。</span><span class="sxs-lookup"><span data-stu-id="1382f-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="1382f-106">为了简化通信并确保使用正确的人员进行检查，您需要提供一组管理员联系人。</span><span class="sxs-lookup"><span data-stu-id="1382f-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="1382f-107">Microsoft 托管桌面 IT 操作将与这些人员联系，以帮助解决你的租户问题。</span><span class="sxs-lookup"><span data-stu-id="1382f-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1382f-108">您可能已经在管理门户中添加了这些联系人。</span><span class="sxs-lookup"><span data-stu-id="1382f-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="1382f-109">如果是这样，请立即花些时间仔细检查联系人列表是否准确，因为 Microsoft 托管桌面**必须**能够在发生严重事件时访问它们。</span><span class="sxs-lookup"><span data-stu-id="1382f-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="1382f-110">Microsoft 托管桌面管理门户的 Azure Active Directory 访问</span><span class="sxs-lookup"><span data-stu-id="1382f-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="1382f-111">Microsoft 托管桌面管理门户要求访问门户的用户拥有以下 Azure Active Directory （AD）角色之一：</span><span class="sxs-lookup"><span data-stu-id="1382f-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="1382f-112">全局管理员</span><span class="sxs-lookup"><span data-stu-id="1382f-112">Global Administrator</span></span>
- <span data-ttu-id="1382f-113">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="1382f-113">Intune Service Administrator</span></span>
- <span data-ttu-id="1382f-114">记帐管理员</span><span class="sxs-lookup"><span data-stu-id="1382f-114">Billing Administrator</span></span>
- <span data-ttu-id="1382f-115">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="1382f-115">Service Support Administrator</span></span>

<span data-ttu-id="1382f-116">全局管理员必须是在 Microsoft 托管桌面中注册您的组织的管理员。</span><span class="sxs-lookup"><span data-stu-id="1382f-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1382f-117">在管理门户中，所有五个角色都具有相同的访问权限，以启动和查看任务。</span><span class="sxs-lookup"><span data-stu-id="1382f-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="1382f-118">有关在 Azure AD 中分配这些角色的详细信息，请参阅[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="1382f-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="1382f-119">管理联系人焦点区域</span><span class="sxs-lookup"><span data-stu-id="1382f-119">Admin contact areas of focus</span></span>

<span data-ttu-id="1382f-120">管理员联系人应是可以回答问题并针对不同关注领域做出决定的最佳人员或组。</span><span class="sxs-lookup"><span data-stu-id="1382f-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="1382f-121">**Microsoft 托管桌面操作将与这些管理员联系人联系，以了解涉及客户存档的支持请求的问题。**</span><span class="sxs-lookup"><span data-stu-id="1382f-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="1382f-122">这些管理员联系人将接收支持请求更新和新邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="1382f-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="1382f-123">这些领域包括：</span><span class="sxs-lookup"><span data-stu-id="1382f-123">These areas include:</span></span>

<span data-ttu-id="1382f-124">焦点区域</span><span class="sxs-lookup"><span data-stu-id="1382f-124">Area of focus</span></span> | <span data-ttu-id="1382f-125">有关的问题</span><span class="sxs-lookup"><span data-stu-id="1382f-125">For questions about</span></span>
--- | ---
<span data-ttu-id="1382f-126">应用程序打包</span><span class="sxs-lookup"><span data-stu-id="1382f-126">App packaging</span></span> | <span data-ttu-id="1382f-127">应用程序打包故障排除</span><span class="sxs-lookup"><span data-stu-id="1382f-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="1382f-128">设备</span><span class="sxs-lookup"><span data-stu-id="1382f-128">Devices</span></span> | <span data-ttu-id="1382f-129">设备运行状况，使用 Microsoft 托管桌面设备进行故障排除</span><span class="sxs-lookup"><span data-stu-id="1382f-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="1382f-130">安全性</span><span class="sxs-lookup"><span data-stu-id="1382f-130">Security</span></span> | <span data-ttu-id="1382f-131">Microsoft 托管桌面设备的安全问题故障排除</span><span class="sxs-lookup"><span data-stu-id="1382f-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="1382f-132">IT 技术支持人员</span><span class="sxs-lookup"><span data-stu-id="1382f-132">IT help desk</span></span> | <span data-ttu-id="1382f-133">如果我们的支持人员在 Microsoft 托管桌面支持区域之外的最终用户票据上进行了干预</span><span class="sxs-lookup"><span data-stu-id="1382f-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="1382f-134">Other</span><span class="sxs-lookup"><span data-stu-id="1382f-134">Other</span></span> | <span data-ttu-id="1382f-135">对于未被其他区域覆盖的问题</span><span class="sxs-lookup"><span data-stu-id="1382f-135">For issues not covered by other areas</span></span>

<span data-ttu-id="1382f-136">**你为这些联系人选择的任何人都需要了解有关 Microsoft 托管桌面环境的决策的知识和权威。**</span><span class="sxs-lookup"><span data-stu-id="1382f-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="1382f-137">在集成 Microsoft 托管桌面环境时，系统会提示你为本地帮助台和安全添加联系人。</span><span class="sxs-lookup"><span data-stu-id="1382f-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="1382f-138">[提交支持请求](../working-with-managed-desktop/support.md)时，需要管理员联系人。</span><span class="sxs-lookup"><span data-stu-id="1382f-138">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="1382f-139">您需要具有管理员联系人的支持请求的焦点区域。</span><span class="sxs-lookup"><span data-stu-id="1382f-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="1382f-140">**添加管理员联系人**</span><span class="sxs-lookup"><span data-stu-id="1382f-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="1382f-141">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="1382f-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="1382f-142">在 "**支持**" 下，选择 "**管理联系人**"。</span><span class="sxs-lookup"><span data-stu-id="1382f-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![支持菜单、管理员联系人](images/admincontacts.png)

3. <span data-ttu-id="1382f-144">选择“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1382f-144">Select **Add**.</span></span>

    ![管理门户添加按钮](images/adminadd.png)

4.  <span data-ttu-id="1382f-146">选择**焦点区域**并输入联系人的信息。</span><span class="sxs-lookup"><span data-stu-id="1382f-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![焦点区域的列表](images/areaoffocus.png)

5. <span data-ttu-id="1382f-148">对每个焦点区域重复此操作。</span><span class="sxs-lookup"><span data-stu-id="1382f-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="1382f-149">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="1382f-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="1382f-150">在管理门户中添加和验证管理员联系人（本主题）</span><span class="sxs-lookup"><span data-stu-id="1382f-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="1382f-151">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="1382f-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="1382f-152">分配许可证</span><span class="sxs-lookup"><span data-stu-id="1382f-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="1382f-153">在设备上安装 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="1382f-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="1382f-154">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="1382f-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="1382f-155">设置 Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="1382f-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="1382f-156">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="1382f-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="1382f-157">将应用程序部署到设备</span><span class="sxs-lookup"><span data-stu-id="1382f-157">Deploy apps to devices</span></span>](deploy-apps.md)