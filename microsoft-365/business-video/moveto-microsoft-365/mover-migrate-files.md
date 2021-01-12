---
title: '将 Google 文件迁移到 Microsoft 365 商业版 '
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何使用 Mover 将 Google 文件迁移到 Microsoft 365 商业版。
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794580"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="9ae8c-103">将 Google 文件迁移到 Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="9ae8c-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="9ae8c-104">迁移到 Microsoft 365 商业版时，需要从 Google Drive 迁移文件。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="9ae8c-105">可以使用 Mover 应用从个人驱动器和共享驱动器移动文件。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="9ae8c-106">有关详细信息，请参阅 [Mover 云迁移](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="9ae8c-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="9ae8c-107">Mover 将创建文件副本，将副本移动到 Microsoft 365 商业版。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="9ae8c-108">原始文件也将留在 Google Drives 中。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9ae8c-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="9ae8c-109">Before you start</span></span>

<span data-ttu-id="9ae8c-110">所有用户都应已登录 Microsoft 365 商业版并设置其 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="9ae8c-111">为此，请转到office.com，使用[](https://office.com)Microsft 365 商业版凭据登录，然后选择 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="9ae8c-112">试一试！</span><span class="sxs-lookup"><span data-stu-id="9ae8c-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="9ae8c-113">安装 Mover</span><span class="sxs-lookup"><span data-stu-id="9ae8c-113">Install Mover</span></span>

1. <span data-ttu-id="9ae8c-114">登录 Google Workspace 管理控制台[，admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="9ae8c-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="9ae8c-115">选择 **"应用\*\*\*\*"，"Google Workspace Marketplace"应用\*\*\*\*，然后将应用添加到域安装列表**。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="9ae8c-116">搜索 Mover 并选择它。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="9ae8c-117">选择 **"域安装**"，然后 **继续**。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="9ae8c-118">查看权限，选中复选框以同意条款，然后选择"允许"，选择"下一步"，然后选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="9ae8c-119">创建连接器并运行迁移</span><span class="sxs-lookup"><span data-stu-id="9ae8c-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="9ae8c-120">返回到 **Google Workspace Marketplace 应用**。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="9ae8c-121">刷新浏览器，然后选择 **Mover** 应用。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="9ae8c-122">向下滚动并选择通用导航链接。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="9ae8c-123">Select **Authorize New Connector，** locate **G Suite (Admin) ，** and choose **Authorize**.</span><span class="sxs-lookup"><span data-stu-id="9ae8c-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="9ae8c-124">如果需要 **，请** 更改显示名称，然后选择"授权 **"。**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="9ae8c-125">选择 Google 管理员帐户，查看权限，然后选择"**允许"。**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="9ae8c-126">Mover 显示发现的团队驱动器数和用户驱动器数。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="9ae8c-127">在 **"选择目标**"下，**选择"授权新连接器**"，找到 **Office 365，** 然后选择"**授权"。**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="9ae8c-128">若要向 Azure Active Directory 中的 Mover 应用授予权限， [请导航到](https://aka.ms/Office365MoverAuth)aka.ms/Office365MoverAuth。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="9ae8c-129">Select **Office 365 Mover**， **Permissions，** **Grant admin consent for your company.**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="9ae8c-130">选择您的帐户，查看权限，然后选择"**接受"。**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="9ae8c-131">选择 **"** 属性"并验证 **用户分配是否必需？** 已打开。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="9ae8c-132">返回到 Mover 应用，更改显示名称，如果需要，请选择"授权 **"，然后选择** Microsoft 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="9ae8c-133">Mover 将通知你发现的 SharePoint Online (或 SPO) 用户的数量。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="9ae8c-134">选择 **"继续迁移设置**"， **选择"添加用户"，** 然后 **自动发现和添加用户**。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="9ae8c-135">Mover 应用将尝试将驱动器从 Google 中的源路径映射到 Microsoft 365 中的目标路径。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="9ae8c-136">如果驱动器未自动映射，请将其目标路径添加到 CSV 文件，稍后我们将使用该路径将共享驱动器迁移到 SharePoint 文档库。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="9ae8c-137">在这种情况下，我们添加了一个称为"已迁移文件"的 SharePoint 网站，并记下了文档页的 URL。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="9ae8c-138">然后，我们使用源路径、目标路径和标记的格式创建了 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="9ae8c-139">有关详细信息 [，请参阅](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)aka.ms/movercsv。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="9ae8c-140">添加目标路径 URL 时，删除共享文档之后的所有内容，例如，此完整 URL 不起作用： `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="9ae8c-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="9ae8c-141">将其更改为：`https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="9ae8c-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="9ae8c-142">CSV 文件准备就绪后，选择" **迁移** 操作 **"，"** 添加到迁移 **"，选择要上载的文件**。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="9ae8c-143">导航到 CSV 文件，选择它，然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="9ae8c-144">选择要迁移其文件的用户驱动器，然后选择"**开始迁移用户"。**</span><span class="sxs-lookup"><span data-stu-id="9ae8c-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="9ae8c-145">查看迁移信息，选择何时开始迁移，同意条款和条件，然后选择"**继续"。** </span><span class="sxs-lookup"><span data-stu-id="9ae8c-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="9ae8c-146">Mover 应用将在迁移过程完成时通知你。</span><span class="sxs-lookup"><span data-stu-id="9ae8c-146">The Mover app will inform you when the migration process is complete.</span></span>