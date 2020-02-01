---
title: 从 Office 365 商业高级版升级到 Microsoft 365 商业版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 将你的企业从 Office 365 商业高级升级到 Microsoft 365 业务的步骤。
ms.openlocfilehash: 0732f76e5bd8540e5954bd7ea7b88061326901b5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593671"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="9492e-103">从 Office 365 商业高级版升级到 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="9492e-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="9492e-104">如果你有[office 365 for business 订阅](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)（例如 Office 365 商业高级版），你可以轻松地升级到 Microsoft 365 business。</span><span class="sxs-lookup"><span data-stu-id="9492e-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="9492e-105">如果要添加以下内容，请升级到 Microsoft 365 商业版：</span><span class="sxs-lookup"><span data-stu-id="9492e-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="9492e-106">Windows 10 专业版（对运行 Windows 8 或更高版本的电脑）</span><span class="sxs-lookup"><span data-stu-id="9492e-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="9492e-107">管理设备上的业务数据的简单控件</span><span class="sxs-lookup"><span data-stu-id="9492e-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="9492e-108">高级安全功能。</span><span class="sxs-lookup"><span data-stu-id="9492e-108">Advanced security capabilities.</span></span>
<span data-ttu-id="9492e-109">有关[Microsoft.com](https://www.microsoft.com/microsoft-365/business)的详细信息，请参阅 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="9492e-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="9492e-110">Office 365 商业高级版和 Microsoft 365 商业版之间的区别是什么？</span><span class="sxs-lookup"><span data-stu-id="9492e-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="9492e-111">我们已将这两个计划的并行比较添加到[Microsoft 365 业务服务说明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)中。</span><span class="sxs-lookup"><span data-stu-id="9492e-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="9492e-112">开始前的准备</span><span class="sxs-lookup"><span data-stu-id="9492e-112">Before you get started</span></span>

- <span data-ttu-id="9492e-113">**我应该何时选择升级？**</span><span class="sxs-lookup"><span data-stu-id="9492e-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="9492e-114">如果要升级分配给单个计划的**所有用户**，则升级是正确的选择。</span><span class="sxs-lookup"><span data-stu-id="9492e-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="9492e-115">当您选择 "升级" 时，所有计划用户都会同时切换到另一个计划。</span><span class="sxs-lookup"><span data-stu-id="9492e-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="9492e-116">如果您不想将每个分配到单个计划的用户进行升级，请为新计划购买许可证（在此示例中为 Microsoft 365 企业版），并[将这些许可证单独分配](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)给您要升级的每个用户。</span><span class="sxs-lookup"><span data-stu-id="9492e-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="9492e-117">**某些加载项可能会阻止升级**如果您尝试启动升级且您的加载项无法继续运行，则可以先删除加载项，以后再将其添加回来（如果仍需要）。</span><span class="sxs-lookup"><span data-stu-id="9492e-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span> 
- <span data-ttu-id="9492e-118">**如果预付计划**预付计划没有直接的升级路径。</span><span class="sxs-lookup"><span data-stu-id="9492e-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="9492e-119">你会知道你是否拥有预付计划，因为你使用可能已在商店中购买的产品 ID 设置你的计划。</span><span class="sxs-lookup"><span data-stu-id="9492e-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="9492e-120">联系合作伙伴，转到 Microsoft Store，或等到预付计划过期，以切换到新计划。</span><span class="sxs-lookup"><span data-stu-id="9492e-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="9492e-121">升级到 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="9492e-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="9492e-122">通过在[新管理中心](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)中执行以下步骤来购买你的许可证：</span><span class="sxs-lookup"><span data-stu-id="9492e-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="9492e-123">登录到管理员中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>。</span><span class="sxs-lookup"><span data-stu-id="9492e-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="9492e-124">转到导航窗格，然后选择 "**计费** \> **产品 & 服务**"。</span><span class="sxs-lookup"><span data-stu-id="9492e-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="9492e-125">查找你的 Office 365 订阅并将其选中以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="9492e-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![屏幕截图显示如何在管理中心查找和选择订阅。](media/FindYourSubscription.png)

3. <span data-ttu-id="9492e-127">在下一个页面上，选择 "**升级**"。</span><span class="sxs-lookup"><span data-stu-id="9492e-127">On the next page, select **Upgrade**.</span></span> 

      ![屏幕截图显示在管理中心中选择 "升级" 的位置。](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="9492e-129">如果您看到一条消息，指出**在 Azure Active Directory 中不支持将订阅升级到基于组的许可证**，则可以安全地忽略此消息，除非您的组织非常大。</span><span class="sxs-lookup"><span data-stu-id="9492e-129">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="9492e-130">已选择此选项的组织将知道他们使用的是基于组的许可。</span><span class="sxs-lookup"><span data-stu-id="9492e-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="9492e-131">接下来，您可以查看可以升级到的 Office 计划的列表。</span><span class="sxs-lookup"><span data-stu-id="9492e-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="9492e-132">在这种情况下，请查找 Microsoft 365 商业版计划。</span><span class="sxs-lookup"><span data-stu-id="9492e-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="9492e-133">如果想要查看此计划中包含的所有 Office 应用和服务，可以向下滚动。</span><span class="sxs-lookup"><span data-stu-id="9492e-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="9492e-134">在**Microsoft 365 商业**版下，选择 "**升级**" 以将 Microsoft 365 业务添加到你的购物车。</span><span class="sxs-lookup"><span data-stu-id="9492e-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="9492e-135">在购物车中：</span><span class="sxs-lookup"><span data-stu-id="9492e-135">In the cart:</span></span>
    1. <span data-ttu-id="9492e-136">我们将自动为你的所有当前用户包含许可证。</span><span class="sxs-lookup"><span data-stu-id="9492e-136">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="9492e-137">如果你需要更多或更少的许可证，你需要[单独购买并分配这些许可证](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="9492e-137">If you need more or fewer licenses, you need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="9492e-138">您可以调整您想要支付的方式：每月或每年。</span><span class="sxs-lookup"><span data-stu-id="9492e-138">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="9492e-139">选择下拉菜单以做出选择。</span><span class="sxs-lookup"><span data-stu-id="9492e-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="9492e-140">选择您将看到购买摘要的 "**转到签出**"，其中包括此帐户的付款方式。</span><span class="sxs-lookup"><span data-stu-id="9492e-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="9492e-141">您还可以在此处添加促销代码（如果有的话）。</span><span class="sxs-lookup"><span data-stu-id="9492e-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="9492e-142">选择 "**下订单**" 以完成购买。</span><span class="sxs-lookup"><span data-stu-id="9492e-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="9492e-143">需要 Microsoft 几分钟的时间来设置新的服务计划。</span><span class="sxs-lookup"><span data-stu-id="9492e-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="9492e-144">若要查看进度，请选择 "**检查升级状态**"。</span><span class="sxs-lookup"><span data-stu-id="9492e-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="9492e-145">计划准备就绪后，您可能需要在管理中心完成一些额外的设置步骤。</span><span class="sxs-lookup"><span data-stu-id="9492e-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="9492e-146">在导航窗格中，选择 "**主页**" 以完成任何其他设置步骤。</span><span class="sxs-lookup"><span data-stu-id="9492e-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="9492e-147">你将收到一个你不再需要的 Office 365 许可证的按比例退款。</span><span class="sxs-lookup"><span data-stu-id="9492e-147">You'll receive a prorated refund for the Office 365 licenses that you no longer need.</span></span> <span data-ttu-id="9492e-148">在设置新计划后，您的银行帐户或信用卡将会在两天内收取费用。</span><span class="sxs-lookup"><span data-stu-id="9492e-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="9492e-149">保护用户设备和文件</span><span class="sxs-lookup"><span data-stu-id="9492e-149">Protect user devices and files</span></span>

<span data-ttu-id="9492e-150">现在已分配 Microsoft 365 业务许可证，请完成启动保护设备和文件的步骤。</span><span class="sxs-lookup"><span data-stu-id="9492e-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="9492e-151">你将使用管理中心导航窗格中包含的一些新选项。</span><span class="sxs-lookup"><span data-stu-id="9492e-151">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="9492e-152">在 "管理中心" 的导航窗格中，转到 "**设备** \> **策略**"。</span><span class="sxs-lookup"><span data-stu-id="9492e-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="9492e-153">在 "**设备策略**" 页上，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9492e-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="9492e-154">在 "**添加策略**" 窗格中，为策略指定一个名称（例如，"保护工作文件"），然后从下拉列表中选择一个**策略类型**。</span><span class="sxs-lookup"><span data-stu-id="9492e-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span> 
    
    <span data-ttu-id="9492e-155">您可以设置应用程序策略来保护 Android 和 iPhone 设备上的文件以及 Windows 10，还可以为公司拥有的 Windows 10 设备设置设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="9492e-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="9492e-156">有关详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="9492e-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="9492e-157">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="9492e-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="9492e-158">设置 Windows 10 设备的应用程序保护设置</span><span class="sxs-lookup"><span data-stu-id="9492e-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="9492e-159">设置 Windows 10 电脑的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="9492e-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="9492e-160">设置策略后，你和你的员工可以设置设备：</span><span class="sxs-lookup"><span data-stu-id="9492e-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="9492e-161">如果你的 Windows 设备尚未使用 Windows Pro Creator 更新，则需要将[其升级到 Windows Pro 创意者更新](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="9492e-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="9492e-162">有关 Windows 设备的步骤，请参阅为[Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9492e-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="9492e-163">有关 Android 手机和 Iphone 的步骤，请参阅为[Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="9492e-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
