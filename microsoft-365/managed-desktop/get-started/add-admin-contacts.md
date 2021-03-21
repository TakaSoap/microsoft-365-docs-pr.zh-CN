---
title: 在管理门户中添加和验证管理员联系人
description: 告诉我们要针对每个焦点区域与谁联系。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925888"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="8ab62-104">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="8ab62-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="8ab62-105">Microsoft 托管桌面服务可以多种方式与客户进行通信。</span><span class="sxs-lookup"><span data-stu-id="8ab62-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="8ab62-106">为了简化通信并确保我们正在与合适的人员联系，你需要提供一组管理员联系人。</span><span class="sxs-lookup"><span data-stu-id="8ab62-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="8ab62-107">Microsoft 托管桌面 IT 运营部门将联系这些人员，帮助解决租户的问题。</span><span class="sxs-lookup"><span data-stu-id="8ab62-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ab62-108">你可能已经在管理门户中添加了这些联系人。</span><span class="sxs-lookup"><span data-stu-id="8ab62-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="8ab62-109">如果是这样，请立即仔细检查联系人列表是否准确，因为发生严重事件时，Microsoft 托管桌面必须能够联系他们。 </span><span class="sxs-lookup"><span data-stu-id="8ab62-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="8ab62-110">Microsoft 托管桌面管理门户的 Azure Active Directory 访问权限</span><span class="sxs-lookup"><span data-stu-id="8ab62-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="8ab62-111">Microsoft 托管桌面管理门户要求访问该门户的用户具有以下 Azure Active Directory (AD) 角色之一：</span><span class="sxs-lookup"><span data-stu-id="8ab62-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="8ab62-112">全局管理员</span><span class="sxs-lookup"><span data-stu-id="8ab62-112">Global Administrator</span></span>
- <span data-ttu-id="8ab62-113">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="8ab62-113">Intune Service Administrator</span></span>
- <span data-ttu-id="8ab62-114">全局读取者</span><span class="sxs-lookup"><span data-stu-id="8ab62-114">Global Reader</span></span>
- <span data-ttu-id="8ab62-115">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="8ab62-115">Service Support Administrator</span></span>

<span data-ttu-id="8ab62-116">全局管理员必须是在 Microsoft 托管桌面中注册组织的人。</span><span class="sxs-lookup"><span data-stu-id="8ab62-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ab62-117">这五个角色在管理门户中具有相同的访问权限，可以启动和查看任务。</span><span class="sxs-lookup"><span data-stu-id="8ab62-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="8ab62-118">有关在 Azure AD 中分配这些角色的信息，请参阅 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中的管理员角色权限。</span><span class="sxs-lookup"><span data-stu-id="8ab62-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="8ab62-119">管理员重点关注的联系人区域</span><span class="sxs-lookup"><span data-stu-id="8ab62-119">Admin contact areas of focus</span></span>

<span data-ttu-id="8ab62-120">管理员联系人应该是可以回答问题并针对不同关注领域做出决策的最佳人员或组。</span><span class="sxs-lookup"><span data-stu-id="8ab62-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="8ab62-121">**对于涉及客户提交的支持请求的问题，Microsoft 托管桌面操作将联系这些管理员联系人。**</span><span class="sxs-lookup"><span data-stu-id="8ab62-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="8ab62-122">这些管理员联系人将收到支持请求更新和新邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="8ab62-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="8ab62-123">这些方面包括：</span><span class="sxs-lookup"><span data-stu-id="8ab62-123">These areas include:</span></span>

<span data-ttu-id="8ab62-124">焦点区域</span><span class="sxs-lookup"><span data-stu-id="8ab62-124">Area of focus</span></span> | <span data-ttu-id="8ab62-125">有关</span><span class="sxs-lookup"><span data-stu-id="8ab62-125">For questions about</span></span>
--- | ---
<span data-ttu-id="8ab62-126">应用打包</span><span class="sxs-lookup"><span data-stu-id="8ab62-126">App packaging</span></span> | <span data-ttu-id="8ab62-127">应用打包疑难解答</span><span class="sxs-lookup"><span data-stu-id="8ab62-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="8ab62-128">设备</span><span class="sxs-lookup"><span data-stu-id="8ab62-128">Devices</span></span> | <span data-ttu-id="8ab62-129">设备运行状况，Microsoft 托管桌面设备疑难解答</span><span class="sxs-lookup"><span data-stu-id="8ab62-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="8ab62-130">安全性</span><span class="sxs-lookup"><span data-stu-id="8ab62-130">Security</span></span> | <span data-ttu-id="8ab62-131">Microsoft 托管桌面设备的安全问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="8ab62-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="8ab62-132">IT 技术支持</span><span class="sxs-lookup"><span data-stu-id="8ab62-132">IT help desk</span></span> | <span data-ttu-id="8ab62-133">如果支持人员在 Microsoft 托管桌面支持区域之外接管用户票证</span><span class="sxs-lookup"><span data-stu-id="8ab62-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="8ab62-134">其他</span><span class="sxs-lookup"><span data-stu-id="8ab62-134">Other</span></span> | <span data-ttu-id="8ab62-135">对于其他方面未涵盖的问题</span><span class="sxs-lookup"><span data-stu-id="8ab62-135">For issues not covered by other areas</span></span>

<span data-ttu-id="8ab62-136">**为这些联系人选择的任何人都需要具备针对 Microsoft 托管桌面环境做出决策的知识和权威。**</span><span class="sxs-lookup"><span data-stu-id="8ab62-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="8ab62-137">当你载入 Microsoft 托管桌面环境时，系统将提示你为本地支持人员和安全添加联系人。</span><span class="sxs-lookup"><span data-stu-id="8ab62-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="8ab62-138">提交支持请求时 [需要管理员联系人](../service-description/support.md)。</span><span class="sxs-lookup"><span data-stu-id="8ab62-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="8ab62-139">你需要有一个管理员联系人来联系支持请求的重点关注区域。</span><span class="sxs-lookup"><span data-stu-id="8ab62-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="8ab62-140">**添加管理员联系人**</span><span class="sxs-lookup"><span data-stu-id="8ab62-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="8ab62-141">登录到 [Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="8ab62-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="8ab62-142">在 **"支持"** 下，**选择"管理员联系人"。**</span><span class="sxs-lookup"><span data-stu-id="8ab62-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![支持菜单，顶部附近的管理员联系人已选定](../../media/admincontacts.png)

3. <span data-ttu-id="8ab62-144">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="8ab62-144">Select **Add**.</span></span>

    ![管理门户的"添加"按钮，在"导出"和"刷新"左侧](../../media/adminadd.png)

4.  <span data-ttu-id="8ab62-146">选择 **一个焦点区域** ，然后输入联系人的信息。</span><span class="sxs-lookup"><span data-stu-id="8ab62-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![焦点区域列表，例如"其他"、"应用"和"安全"](../../media/areaoffocus.png)

5. <span data-ttu-id="8ab62-148">对每个焦点区域重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="8ab62-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="8ab62-149">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="8ab62-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="8ab62-150">在管理门户中添加和验证管理员 (本主题) </span><span class="sxs-lookup"><span data-stu-id="8ab62-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="8ab62-151">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="8ab62-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="8ab62-152">分配许可证</span><span class="sxs-lookup"><span data-stu-id="8ab62-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="8ab62-153">在设备上安装 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="8ab62-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="8ab62-154">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="8ab62-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="8ab62-155">设置 Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="8ab62-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="8ab62-156">为用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="8ab62-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="8ab62-157">将应用部署到设备</span><span class="sxs-lookup"><span data-stu-id="8ab62-157">Deploy apps to devices</span></span>](deploy-apps.md)