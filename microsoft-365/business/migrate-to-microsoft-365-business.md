---
title: 从 Office 365 商业高级版迁移到 Microsoft 365 商业版
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: 了解如何将企业移动到 Microsoft 365 商业版。
ms.openlocfilehash: a3f77bd18b9b900151c50f923b705e4ff0150519
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982433"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="f6297-103">从 Office 365 商业高级版迁移到 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="f6297-103">Migrate to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="f6297-104">如果已有 Office 365 for business 订阅（例如，Office 365 商业高级版），则可以轻松地将许可证添加到 Microsoft 365 商业，并将其分配给部分或所有用户。</span><span class="sxs-lookup"><span data-stu-id="f6297-104">If you already have an Office 365 for business subscription, for example, Office 365 Business Premium, you can easily add licenses to Microsoft 365 Business, and assign them to some, or all users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6297-105">您不能使用 "[切换计划](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton)" 按钮来升级到 Microsoft 365 商业版。</span><span class="sxs-lookup"><span data-stu-id="f6297-105">You can't use the [Switch plans](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) button to upgrade to Microsoft 365 Business yet.</span></span> 
  
## <a name="add-microsoft-365-business-licenses"></a><span data-ttu-id="f6297-106">添加 Microsoft 365 商业版许可证</span><span class="sxs-lookup"><span data-stu-id="f6297-106">Add Microsoft 365 Business licenses</span></span>

<span data-ttu-id="f6297-107">你可以通过两种方式获取 Microsoft 365 商业版。</span><span class="sxs-lookup"><span data-stu-id="f6297-107">You have two ways to get Microsoft 365 Business.</span></span> <span data-ttu-id="f6297-108">合作伙伴可以从[Microsoft 合作伙伴中心](get-microsoft-365-business.md)为你购买 Microsoft 365 商业版。</span><span class="sxs-lookup"><span data-stu-id="f6297-108">A partner can purchase Microsoft 365 Business for you from [Microsoft Partner Center](get-microsoft-365-business.md).</span></span> <span data-ttu-id="f6297-109">您的合作伙伴还可以帮助您过渡到 Microsoft 365 业务。</span><span class="sxs-lookup"><span data-stu-id="f6297-109">Your partner can also help you transition to Microsoft 365 Business.</span></span>
  
<span data-ttu-id="f6297-110">如果你管理自己的订阅，可以[联系 sales](https://www.microsoft.com/microsoft-365/business)以购买 Microsoft 365 商业版许可证。</span><span class="sxs-lookup"><span data-stu-id="f6297-110">If you manage your own subscription, you can [contact sales](https://www.microsoft.com/microsoft-365/business) to purchase Microsoft 365 Business licenses.</span></span> 
  
<span data-ttu-id="f6297-111">请参阅[添加、更改或删除订阅顾问合作伙伴](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff)，了解如何开始使用合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="f6297-111">See [Add, change, or delete a subscription advisor partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) to find out how you can start working with a partner.</span></span> 
  
<span data-ttu-id="f6297-112">如果提供了购买许可证的链接，您将完成如下所示的向导。</span><span class="sxs-lookup"><span data-stu-id="f6297-112">If you are given a link to purchase your licences, you will walk through a wizard like the one below.</span></span> <span data-ttu-id="f6297-113">选择 **"是，将它添加到我的帐户**"。</span><span class="sxs-lookup"><span data-stu-id="f6297-113">Choose **Yes, add it to my account**.</span></span> <span data-ttu-id="f6297-114">您还可以选取许可数量和付款方法。</span><span class="sxs-lookup"><span data-stu-id="f6297-114">You can also pick the number of licences and the method of payment.</span></span>
  
![在 Microsoft 365 Business direct 买链接上，选择添加到你的当前帐户，或注册一个新帐户。](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a><span data-ttu-id="f6297-116">分配 Microsoft 365 许可证</span><span class="sxs-lookup"><span data-stu-id="f6297-116">Assign Microsoft 365 licenses</span></span>

1. <span data-ttu-id="f6297-117">一旦购买了新的许可证，并且这是您首次执行此操作，Microsoft 365 企业版的安装标题将显示在管理中心的顶部。</span><span class="sxs-lookup"><span data-stu-id="f6297-117">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f6297-118">安装标题是添加新用户、新域和为新用户迁移电子邮件的机会。</span><span class="sxs-lookup"><span data-stu-id="f6297-118">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users.</span></span> <span data-ttu-id="f6297-119">如果不打算执行任何操作，则仍应完成向导并选择 "默认选项"，使其从管理主页中消失。</span><span class="sxs-lookup"><span data-stu-id="f6297-119">If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![选择 "在 Microsoft 365 企业上启动安装程序" 已准备好设置横幅。](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="f6297-121">选择" **开始设置**"。</span><span class="sxs-lookup"><span data-stu-id="f6297-121">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="f6297-122">在 "**个性化登录和电子邮件**" 页上，如果要使用此机会将其他域添加到订阅中，则可以通过选择 "**连接您已拥有的域**" 来添加域。</span><span class="sxs-lookup"><span data-stu-id="f6297-122">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="f6297-123">如果您已经设置了一个域，则第二个字段将指示并将显示 "**继续使用** \<_域名_\> **进行电子邮件" 和 "登录"**。  </span><span class="sxs-lookup"><span data-stu-id="f6297-123">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**.</span></span> <span data-ttu-id="f6297-124">如果你未设置与订阅的域，则将**继续使用** \<_贵公司的 name.onmicrosoft.com_ \> **电子邮件并登录**。  </span><span class="sxs-lookup"><span data-stu-id="f6297-124">If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="f6297-125">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f6297-125">Choose **Next**.</span></span>
    
    ![在 "个性化登录和电子邮件" 页上，选择 "添加域" 或 "使用您已使用的域"。](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="f6297-127">在 "**添加新用户**" 页上，如果您有要向其分配 Microsoft 365 业务许可证的新员工，则可以添加新用户。</span><span class="sxs-lookup"><span data-stu-id="f6297-127">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="f6297-128">如果你没有要添加的新员工，并且想要将许可证分配给现有用户，请选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f6297-128">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="f6297-129">在 \* \* 迁移电子邮件 \* \* 页面上，您可以选择为您在步骤3中添加的任何新用户迁移电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f6297-129">On the \*\* Migrate email messages \*\* page you can choose to migrate email for any of the new users you added in step 3.</span></span> <span data-ttu-id="f6297-130">您也可以跳过这一步。</span><span class="sxs-lookup"><span data-stu-id="f6297-130">You can skip this step also.</span></span> <span data-ttu-id="f6297-131">选择 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="f6297-131">Choose **Next**.</span></span>
    
5. <span data-ttu-id="f6297-132">在最后一页上，选择 **"转到管理中心**"，然后继续安装。</span><span class="sxs-lookup"><span data-stu-id="f6297-132">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="f6297-133">在管理中心中，转到 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="f6297-133">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="f6297-134">选择要向其分配**Microsoft 365 业务**许可证的用户，然后选择 "**产品许可证**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="f6297-134">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![在用户卡中，选择 "产品许可证" 旁边的 "编辑"。](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. <span data-ttu-id="f6297-136">在**产品许可证**中，将**Microsoft 365 企业**幻灯片保存到 **"** \> **保存**"，然后**关闭**。</span><span class="sxs-lookup"><span data-stu-id="f6297-136">In **Product licenses** slide **Microsoft 365 Business** to **On** \> **Save**, and then **Close**.</span></span>
    
<span data-ttu-id="f6297-137">购买 Microsoft 365 商业版的初始许可证后，你现在可以在**帐单** \> **购买服务**中添加更多的许可证。</span><span class="sxs-lookup"><span data-stu-id="f6297-137">Once you have purchased the initial license for Microsoft 365 Business, you can now also add more in **Billing** \> **Purchase services**.</span></span> <span data-ttu-id="f6297-138">在 "**购买服务**" 页上，可以单击**Microsoft 365 名片**上的省略号，然后选择 "**更改许可证数量**" 以购买更多。</span><span class="sxs-lookup"><span data-stu-id="f6297-138">On the **Purchase services** page you can click on the ellipses on the **Microsoft 365 Business** card, and choose **Change license quantity** to purchase more.</span></span> 
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="f6297-139">保护用户设备和文件</span><span class="sxs-lookup"><span data-stu-id="f6297-139">Protect user devices and files</span></span>

<span data-ttu-id="f6297-140">为 Microsoft 365 商业版分配许可证之后，可以开始保护用户的设备和文件。</span><span class="sxs-lookup"><span data-stu-id="f6297-140">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>
  
1. <span data-ttu-id="f6297-141">在管理中心的左侧导航中，转到 "**设备** \> **策略**"。</span><span class="sxs-lookup"><span data-stu-id="f6297-141">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="f6297-142">在 "**设备策略**" 页上，选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="f6297-142">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="f6297-143">在 "**添加策略**" 窗格中，为策略指定一个名称，然后从下拉类型中选择一个**策略类型**。</span><span class="sxs-lookup"><span data-stu-id="f6297-143">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="f6297-144">您可以设置应用程序策略来保护 Android 和 iPhone 设备上的文件以及 Windows 10，还可以为公司拥有的 Windows 10 设备设置设备配置策略。</span><span class="sxs-lookup"><span data-stu-id="f6297-144">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="f6297-145">有关详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="f6297-145">See the following links for details:</span></span>
    
  - [<span data-ttu-id="f6297-146">设置 Android 或 iOS 设备的应用保护设置</span><span class="sxs-lookup"><span data-stu-id="f6297-146">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="f6297-147">设置 Windows 10 设备的应用程序保护设置</span><span class="sxs-lookup"><span data-stu-id="f6297-147">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="f6297-148">设置 Windows 10 电脑的设备保护设置</span><span class="sxs-lookup"><span data-stu-id="f6297-148">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
   ![在 "添加策略" 窗格中，为其输入名称，然后从下拉菜单中选择策略类型。](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. <span data-ttu-id="f6297-150">设置策略后，你和你的员工可以设置设备：</span><span class="sxs-lookup"><span data-stu-id="f6297-150">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="f6297-151">如果 windows Pro Creator 更新中还没有您的 Windows，则需要将[其升级到 Windows Pro 创意者更新](upgrade-to-windows-pro-creators-update.md)。</span><span class="sxs-lookup"><span data-stu-id="f6297-151">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="f6297-152">有关 Windows 设备的步骤，请参阅为[Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="f6297-152">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="f6297-153">有关 Android 手机和 Iphone 的步骤，请参阅为[Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="f6297-153">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
    
5. <span data-ttu-id="f6297-154">若要自动安装 Office 客户端应用，请参阅[Prepare For office client deployment By Microsoft 365 Business](prepare-for-office-client-deployment.md)和[在 Windows 10 设备上自动安装或卸载 office](auto-install-or-uninstall-office.md)。</span><span class="sxs-lookup"><span data-stu-id="f6297-154">To automatically install Office client apps, see [Prepare for Office client deployment by Microsoft 365 Business](prepare-for-office-client-deployment.md) and [Automatically install or uninstall Office on Windows 10 devices](auto-install-or-uninstall-office.md).</span></span>
    


