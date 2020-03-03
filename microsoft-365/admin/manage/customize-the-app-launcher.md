---
title: 向应用启动器添加自定义磁贴
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: '通过将自定义磁贴添加到应用启动器中，创建指向您的电子邮件、文档、应用程序、SharePoint 网站、外部网站和其他资源的快速链接。 '
ms.openlocfilehash: 65c8da7aa0cdb68f4bf32a52b21140413a38a69a
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361977"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a><span data-ttu-id="7a283-103">向应用启动器添加自定义磁贴</span><span class="sxs-lookup"><span data-stu-id="7a283-103">Add custom tiles to the app launcher</span></span>

<span data-ttu-id="7a283-p101">在 Office 365 中，可使用 Office 365 应用启动器快速轻松地访问电子邮件、日历、文档和应用（[了解详细信息](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)）。这些应用包括使用 Office 365 获得的所有应用以及从 [SharePoint 应用商店](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx)或 [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher) 添加的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="7a283-p101">In Office 365, you can quickly and easily get to your email, calendars, documents, and apps using the Office 365 app launcher ([learn more](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). These are apps you get with Office 365 as well as custom apps that you add from the [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) or [Azure AD](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).</span></span>
  
<span data-ttu-id="7a283-p102">可将自己的自定义磁贴添加到应用启动器，这些磁贴指向 SharePoint 网站、外部网站、旧版应用等。自定义磁贴显示在应用启动器的" **全部**"应用下，可将其固定到" **主页**"应用，并指示用户执行相同操作。这样做便于查找相关网站、应用和资源来完成工作。 在以下示例中，名为"Contoso 门户"的自定义磁贴用于访问组织的主要 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="7a283-p102">You can add your own custom tiles to the app launcher that point to SharePoint sites, external sites, legacy apps, and more. The custom tile appears under the app launcher's **All** apps, but you can pin it to the **Home** apps and instruct your users to do the same. This makes it easy to find the relevant sites, apps, and resources to do your job. In the below example, a custom tile called "Contoso Portal" is used to access an organization's SharePoint intranet site.</span></span> 
  
![Office 365 应用启动器](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a><span data-ttu-id="7a283-111">向应用启动器添加自定义磁贴</span><span class="sxs-lookup"><span data-stu-id="7a283-111">Add a custom tile to the app launcher</span></span>

1. <span data-ttu-id="7a283-112">在管理中心中，转到 "**设置** > **设置**"，然后选择 "**组织配置文件**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7a283-112">In the admin center, go to the **Settings** > **Settings** and choose **Organization profile** tab.</span></span>
    
2. <span data-ttu-id="7a283-113">在 "**组织配置文件**" 选项卡上，选择 "**自定义应用启动器" 磁贴**。</span><span class="sxs-lookup"><span data-stu-id="7a283-113">On the **Organization profile** tab, choose **Custom app launcher tiles**.</span></span>
  
3. <span data-ttu-id="7a283-114">选择 "**添加自定义磁贴**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-114">Select **Add a custom tile**.</span></span> 
  
4. <span data-ttu-id="7a283-115">为新磁贴输入" **磁贴名称**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-115">Enter a **Tile name** for the new tile.</span></span> <span data-ttu-id="7a283-116">该名称将显示在磁贴中。</span><span class="sxs-lookup"><span data-stu-id="7a283-116">The name will appear in the tile.</span></span> 
    
5. <span data-ttu-id="7a283-117">为磁贴输入**网站的 URL** 。</span><span class="sxs-lookup"><span data-stu-id="7a283-117">Enter a **URL of website** for the tile.</span></span> <span data-ttu-id="7a283-118">这是您希望用户在应用启动器上选择磁贴时要转到的位置。</span><span class="sxs-lookup"><span data-stu-id="7a283-118">This is the location where you want your users to go when they select the tile on the app launcher.</span></span> <span data-ttu-id="7a283-119">在 URL 中使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="7a283-119">Use HTTPS in the URL.</span></span><br/><span data-ttu-id="7a283-120">提示：如果要为 SharePoint 网站创建磁贴，请导航到该网站，复制该 URL，然后将其粘贴到此处。</span><span class="sxs-lookup"><span data-stu-id="7a283-120">TIP: If you're creating a tile for a SharePoint site, navigate to that site, copy the URL, and paste it here.</span></span> <span data-ttu-id="7a283-121">默认团队网站的 URL 如下所示：`https://<company_name>.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="7a283-121">The URL of your default team site looks like this: `https://<company_name>.sharepoint.com`</span></span> 
  
6. <span data-ttu-id="7a283-122">输入图块的**图像的 URL** 。</span><span class="sxs-lookup"><span data-stu-id="7a283-122">Enter an **URL of the image** for the tile.</span></span> <span data-ttu-id="7a283-123">此图像显示在"我的应用"页面上和应用启动器中。</span><span class="sxs-lookup"><span data-stu-id="7a283-123">The image appears on the My apps page and app launcher.</span></span><br/><span data-ttu-id="7a283-124">提示：图像应为60x60 像素，并且可供组织中的所有人使用，而无需进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7a283-124">TIP: The image should be 60x60 pixels and be available to everyone in your organization without requiring authentication.</span></span>

7. <span data-ttu-id="7a283-125">为磁贴输入" **说明**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-125">Enter a **Description** for the tile.</span></span> <span data-ttu-id="7a283-126">当您在 "我的应用程序" 页上选择磁贴并选择 "**应用程序详细信息**" 时，会看到此</span><span class="sxs-lookup"><span data-stu-id="7a283-126">You see this when you select the tile on the My apps page and select **App details**.</span></span> 
  
8. <span data-ttu-id="7a283-127">选择 "**保存更改**" 以创建自定义磁贴。</span><span class="sxs-lookup"><span data-stu-id="7a283-127">Select **Save changes** to create the custom tile.</span></span> 
    
<span data-ttu-id="7a283-128">自定义磁贴现显示在应用启动器中的" **全部**"选项卡上。</span><span class="sxs-lookup"><span data-stu-id="7a283-128">Your custom tile now appears in the app launcher on the **All** tab for you and your users.</span></span> 
  
## <a name="promote-the-tile-to-app-launcher"></a><span data-ttu-id="7a283-129">将磁贴升级到应用启动器</span><span class="sxs-lookup"><span data-stu-id="7a283-129">Promote the tile to App Launcher</span></span>

1. <span data-ttu-id="7a283-130">选择应用启动器图标并选择 "**所有应用**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-130">Select the app launcher icon and select the **All apps**.</span></span> 
    
2. <span data-ttu-id="7a283-131">找到您的应用程序的新磁贴，选择省略号，然后选择 "**固定到启动器**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-131">Locate the new tile for your app, select the ellipsis, and choose **Pin to launcher**.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="7a283-p108">如果看不到先前步骤中创建的自定义磁贴，请确保你已分配有 Exchange Online 邮箱，且至少有一次成功登录到邮箱中。这些步骤是 Office 365 中的自定义磁贴所必需的。</span><span class="sxs-lookup"><span data-stu-id="7a283-p108">If you don't see the custom tile created in the previous steps, make sure you have an Exchange Online mailbox assigned to you and you've signed into your mailbox at least once. These steps are required for custom tiles in Office 365.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7a283-134">你和你的用户需要执行这些步骤，才能将"我的应用"页面中的自定义磁贴提升到应用启动器。</span><span class="sxs-lookup"><span data-stu-id="7a283-134">Both you and your users need to perform these steps to promote custom tiles from the My apps page to the app launcher.</span></span> 
  
## <a name="edit-or-delete-a-custom-tile"></a><span data-ttu-id="7a283-135">Edit or delete a custom tile</span><span class="sxs-lookup"><span data-stu-id="7a283-135">Edit or delete a custom tile</span></span>

1. <span data-ttu-id="7a283-136">在管理中心中，转到 "**设置** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">组织配置文件</a>" 页。</span><span class="sxs-lookup"><span data-stu-id="7a283-136">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">Organization profile</a> page.</span></span>
    
2. <span data-ttu-id="7a283-137">在 "**组织配置文件**" 页上的 "为**您的组织添加自定义磁贴**" 旁边，选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-137">On the **Organization profile** page, next to   **Add custom tiles for your organization**, select **Edit**.</span></span>

3. <span data-ttu-id="7a283-138">更新自定义磁贴的" **磁贴名称**"、" **URL**"、" **说明**"或" **图像 URL**"（请参阅[向应用启动器添加自定义磁贴](#add-a-custom-tile-to-the-app-launcher)）。</span><span class="sxs-lookup"><span data-stu-id="7a283-138">Update the **Tile name**, **URL**, **Description**, or **Image URL** for the custom tile (see [Add a custom tile to the app launcher](#add-a-custom-tile-to-the-app-launcher)).</span></span>
    
4. <span data-ttu-id="7a283-139">选择 "**更新** \> **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-139">Select **Update** \> **Close**.</span></span> 
    
<span data-ttu-id="7a283-140">若要删除自定义磁贴，请从 "**自定义磁贴**" 窗口中选择该图块，选择 "**删除磁贴** > **删除**"。</span><span class="sxs-lookup"><span data-stu-id="7a283-140">To delete a custom tile, from the **Custom tiles** window, select the tile, select **Remove tile** > **Delete**.</span></span> 
  
## <a name="whats-next"></a><span data-ttu-id="7a283-141">未来会有哪些更新？</span><span class="sxs-lookup"><span data-stu-id="7a283-141">What's next?</span></span>

<span data-ttu-id="7a283-p109">除了将磁贴添加至应用启动器之外，你可以将应用启动器添加到 Office 365 导航栏（[了解详细信息](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)）。 若要自定义 Office 365 的外观以匹配你所在组织的品牌，请参阅[自定义 Office 365 主题](../setup/customize-your-organization-theme.md)。</span><span class="sxs-lookup"><span data-stu-id="7a283-p109">In addition to adding tiles to the app launcher, you can add app launcher tiles to the Office 365 navigation bar ([learn more](https://support.office.com/article/d536512c-b0f7-49fd-b8db-a8a967e23f23.aspx)). To customize the look and feel of Office 365 to match your organization's brand, see [Customize the Office 365 theme](../setup/customize-your-organization-theme.md).</span></span>
  

