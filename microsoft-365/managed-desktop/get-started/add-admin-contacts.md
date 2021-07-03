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
ms.openlocfilehash: ba4f1b0e4b2e00334dbffb4bf0aa9edb1b8c5622
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286917"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="87b85-104">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="87b85-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="87b85-105">有多种方式可以Microsoft 托管桌面与客户进行通信。</span><span class="sxs-lookup"><span data-stu-id="87b85-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="87b85-106">为了简化通信并确保我们正在与合适的人员联系，你需要提供一组管理员联系人。</span><span class="sxs-lookup"><span data-stu-id="87b85-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="87b85-107">Microsoft 托管桌面IT 运营部门将联系这些人员，帮助解决租户的问题。</span><span class="sxs-lookup"><span data-stu-id="87b85-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87b85-108">你可能已经在管理门户中添加了这些联系人。</span><span class="sxs-lookup"><span data-stu-id="87b85-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="87b85-109">如果是，请立即仔细检查联系人列表是否准确，因为Microsoft 托管桌面发生严重事件时必须能够联系他们。 </span><span class="sxs-lookup"><span data-stu-id="87b85-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="87b85-110">Azure Active Directory管理Microsoft 托管桌面的访问权限</span><span class="sxs-lookup"><span data-stu-id="87b85-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="87b85-111">Microsoft 托管桌面管理门户要求访问该门户的用户具有以下 AD Azure Active Directory (角色) 之一：</span><span class="sxs-lookup"><span data-stu-id="87b85-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>

- <span data-ttu-id="87b85-112">全局管理员</span><span class="sxs-lookup"><span data-stu-id="87b85-112">Global Administrator</span></span>
- <span data-ttu-id="87b85-113">Intune 服务管理员</span><span class="sxs-lookup"><span data-stu-id="87b85-113">Intune Service Administrator</span></span>
- <span data-ttu-id="87b85-114">全局读取者</span><span class="sxs-lookup"><span data-stu-id="87b85-114">Global Reader</span></span>
- <span data-ttu-id="87b85-115">服务支持管理员</span><span class="sxs-lookup"><span data-stu-id="87b85-115">Service Support Administrator</span></span>

<span data-ttu-id="87b85-116">全局管理员必须是在组织中注册Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="87b85-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="87b85-117">这五个角色在管理门户中具有相同的访问权限，可以启动和查看任务。</span><span class="sxs-lookup"><span data-stu-id="87b85-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="87b85-118">有关在 Azure AD 中分配这些角色的信息，请参阅管理员[角色权限Azure Active Directory。](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="87b85-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="87b85-119">管理员重点关注的联系人区域</span><span class="sxs-lookup"><span data-stu-id="87b85-119">Admin contact areas of focus</span></span>

<span data-ttu-id="87b85-120">管理员联系人应该是可以回答问题并针对不同关注领域做出决策的最佳人员或组。</span><span class="sxs-lookup"><span data-stu-id="87b85-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="87b85-121">**Microsoft 托管桌面对于涉及客户提交的支持请求的问题，操作将联系这些管理员联系人。**</span><span class="sxs-lookup"><span data-stu-id="87b85-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="87b85-122">这些管理员联系人将收到支持请求更新和新邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="87b85-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="87b85-123">这些方面包括：</span><span class="sxs-lookup"><span data-stu-id="87b85-123">These areas include:</span></span>

<span data-ttu-id="87b85-124">焦点区域</span><span class="sxs-lookup"><span data-stu-id="87b85-124">Area of focus</span></span> | <span data-ttu-id="87b85-125">有关</span><span class="sxs-lookup"><span data-stu-id="87b85-125">For questions about</span></span>
--- | ---
<span data-ttu-id="87b85-126">应用打包</span><span class="sxs-lookup"><span data-stu-id="87b85-126">App packaging</span></span> | <span data-ttu-id="87b85-127">应用打包疑难解答</span><span class="sxs-lookup"><span data-stu-id="87b85-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="87b85-128">设备</span><span class="sxs-lookup"><span data-stu-id="87b85-128">Devices</span></span> | <span data-ttu-id="87b85-129">设备运行状况，Microsoft 托管桌面疑难解答</span><span class="sxs-lookup"><span data-stu-id="87b85-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="87b85-130">安全性</span><span class="sxs-lookup"><span data-stu-id="87b85-130">Security</span></span> | <span data-ttu-id="87b85-131">解决设备Microsoft 托管桌面安全问题</span><span class="sxs-lookup"><span data-stu-id="87b85-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="87b85-132">IT 技术支持</span><span class="sxs-lookup"><span data-stu-id="87b85-132">IT help desk</span></span> | <span data-ttu-id="87b85-133">如果支持人员在支持区域外将用户票证Microsoft 托管桌面的情况</span><span class="sxs-lookup"><span data-stu-id="87b85-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="87b85-134">其他</span><span class="sxs-lookup"><span data-stu-id="87b85-134">Other</span></span> | <span data-ttu-id="87b85-135">对于其他方面未涵盖的问题</span><span class="sxs-lookup"><span data-stu-id="87b85-135">For issues not covered by other areas</span></span>

<span data-ttu-id="87b85-136">**无论为这些联系人选择谁，都需要有知识和权威来针对您的Microsoft 托管桌面决策。**</span><span class="sxs-lookup"><span data-stu-id="87b85-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="87b85-137">当你载入Microsoft 托管桌面环境时，系统将提示你为本地支持人员和安全添加联系人。</span><span class="sxs-lookup"><span data-stu-id="87b85-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="87b85-138">提交支持请求时 [需要管理员联系人](../service-description/support.md)。</span><span class="sxs-lookup"><span data-stu-id="87b85-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="87b85-139">你需要有一个管理员联系人来联系支持请求的重点关注区域。</span><span class="sxs-lookup"><span data-stu-id="87b85-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span>

<span data-ttu-id="87b85-140">**添加管理员联系人**</span><span class="sxs-lookup"><span data-stu-id="87b85-140">**To add admin contacts**</span></span>

1. <span data-ttu-id="87b85-141">登录到[Microsoft Endpoint Manager](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="87b85-141">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span>

2. <span data-ttu-id="87b85-142">在 **"租户管理**"下，**查找**"Microsoft 托管桌面"部分，然后选择"**管理员联系人"。**</span><span class="sxs-lookup"><span data-stu-id="87b85-142">Under **Tenant administration**, look for the **Microsoft Managed Desktop** section then select **Admin contacts**.</span></span>

3. <span data-ttu-id="87b85-143">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="87b85-143">Select **Add**.</span></span>

4. <span data-ttu-id="87b85-144">选择 **一个焦点区域** ，然后输入联系人的信息。</span><span class="sxs-lookup"><span data-stu-id="87b85-144">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![焦点区域列表，例如"其他"、"应用"和"安全"](../../media/areaoffocus.png)

5. <span data-ttu-id="87b85-146">对每个焦点区域重复上述步骤。</span><span class="sxs-lookup"><span data-stu-id="87b85-146">Repeat for each area of focus.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="87b85-147">开始使用 Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="87b85-147">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="87b85-148">在管理门户中添加和验证管理员 (本主题) </span><span class="sxs-lookup"><span data-stu-id="87b85-148">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="87b85-149">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="87b85-149">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="87b85-150">分配许可证</span><span class="sxs-lookup"><span data-stu-id="87b85-150">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="87b85-151">在设备上安装 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="87b85-151">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="87b85-152">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="87b85-152">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="87b85-153">设置 Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="87b85-153">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="87b85-154">为用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="87b85-154">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="87b85-155">将应用部署到设备</span><span class="sxs-lookup"><span data-stu-id="87b85-155">Deploy apps to devices</span></span>](deploy-apps.md)
