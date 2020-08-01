---
title: 为 Microsoft 托管桌面准备映射的驱动器
description: 确保执行的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: e6311c0ad11d68c870b0c8185974b8913735e2a2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530171"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a><span data-ttu-id="8695f-104">为 Microsoft 托管桌面准备映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="8695f-104">Prepare mapped drives for Microsoft Managed Desktop</span></span>

<span data-ttu-id="8695f-105">许多企业环境都具有对映射驱动器的旧版要求，以允许其用户或团队共享和存储文件，或用于本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="8695f-105">Many enterprise environments have legacy requirements for mapped drives to allow their users or teams to share and store files, or for on-premises applications.</span></span> <span data-ttu-id="8695f-106">Microsoft 不建议使用 Microsoft 托管桌面的映射驱动器。</span><span class="sxs-lookup"><span data-stu-id="8695f-106">Microsoft does not recommend the use of mapped drives with the Microsoft Managed Desktop.</span></span> <span data-ttu-id="8695f-107">相反，我们建议您将文件访问解决方案现代化，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8695f-107">Instead, we recommend that you modernize your file access solutions as follows:</span></span>
  
- <span data-ttu-id="8695f-108">将单个用户使用的映射驱动器迁移到 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="8695f-108">Migrate mapped drives used by individual users to OneDrive for Business.</span></span> 
- <span data-ttu-id="8695f-109">迁移团队使用的映射驱动器以将文件共享到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="8695f-109">Migrate mapped drives used by teams to share files to SharePoint Online.</span></span> 
- <span data-ttu-id="8695f-110">将使用本地文件共享的任何应用程序现代化或替换为删除该要求。</span><span class="sxs-lookup"><span data-stu-id="8695f-110">Modernize or replace any applications that use on-premises file shares to remove that requirement.</span></span>
  
<span data-ttu-id="8695f-111">新式化这些服务将允许在 Microsoft 托管桌面中获得最佳的最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="8695f-111">Modernizing these services will allow the best end-user experience with Microsoft Managed Desktop.</span></span> <span data-ttu-id="8695f-112">Microsoft FastTrack 服务可帮助你使用 Microsoft 云服务新式化你的环境。</span><span class="sxs-lookup"><span data-stu-id="8695f-112">Microsoft FastTrack Services can assist you in modernizing your environment by using Microsoft Cloud Services.</span></span> <span data-ttu-id="8695f-113">您可以检查是否符合[符合条件的服务和计划](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)的 FastTrack 服务，然后直接与他们联系以准备好 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="8695f-113">You can check whether you're eligible for FastTrack services at [Eligible Services and Plans](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) and then contact them directly to prepare for Microsoft Managed Desktop.</span></span> <span data-ttu-id="8695f-114">有关 FastTrack OneDrive for Business 或 SharePoint Online 迁移的背景，请参阅[数据迁移](https://docs.microsoft.com/fasttrack/o365-data-migration)。</span><span class="sxs-lookup"><span data-stu-id="8695f-114">For background about FastTrack OneDrive for Business or SharePoint Online Migration, see [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).</span></span>

## <a name="mapped-drives-on-microsoft-managed-desktop"></a><span data-ttu-id="8695f-115">Microsoft 托管桌面上的映射驱动器</span><span class="sxs-lookup"><span data-stu-id="8695f-115">Mapped drives on Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="8695f-116">如果无法删除或替换某些用例的映射驱动器，应在 Microsoft 托管桌面管理门户中提交支持请求，以将其部署到 Microsoft 托管桌面用户。</span><span class="sxs-lookup"><span data-stu-id="8695f-116">If you cannot remove or replace mapped drives for some use cases, you should submit a support request in the Microsoft Managed Desktop admin portal to have them deployed to Microsoft Managed Desktop users.</span></span>
    
<span data-ttu-id="8695f-117">对于此类请求，必须在支持请求中提供以下详细信息：</span><span class="sxs-lookup"><span data-stu-id="8695f-117">For such a request, you'll have to provide the following details in the support request:</span></span> 

- <span data-ttu-id="8695f-118">将需要为 Microsoft 托管桌面设备映射的文件共享位置的所有 UNC 路径</span><span class="sxs-lookup"><span data-stu-id="8695f-118">All UNC paths to file share locations that will need to be mapped for Microsoft Managed Desktop devices</span></span> 
- <span data-ttu-id="8695f-119">需要访问这些文件共享位置的用户组</span><span class="sxs-lookup"><span data-stu-id="8695f-119">User groups that require access to these file share locations</span></span> 
- <span data-ttu-id="8695f-120">任何需要分配的特定驱动器号（如有必要）</span><span class="sxs-lookup"><span data-stu-id="8695f-120">Any specific drive letter that needs to be assigned (if necessary)</span></span>

<span data-ttu-id="8695f-121">例如：</span><span class="sxs-lookup"><span data-stu-id="8695f-121">For example:</span></span>

| <span data-ttu-id="8695f-122">驱动器号</span><span class="sxs-lookup"><span data-stu-id="8695f-122">Drive letter</span></span> | <span data-ttu-id="8695f-123">UNC 路径</span><span class="sxs-lookup"><span data-stu-id="8695f-123">UNC path</span></span> | <span data-ttu-id="8695f-124">用户组</span><span class="sxs-lookup"><span data-stu-id="8695f-124">User group</span></span> |
|--------------|----------|------------|
| <span data-ttu-id="8695f-125">版</span><span class="sxs-lookup"><span data-stu-id="8695f-125">X:</span></span>  | <span data-ttu-id="8695f-126">\\\server\share\Marketing</span><span class="sxs-lookup"><span data-stu-id="8695f-126">\\\server\share\Marketing</span></span> | <span data-ttu-id="8695f-127">ContosoMarketing</span><span class="sxs-lookup"><span data-stu-id="8695f-127">ContosoMarketing</span></span> |

<span data-ttu-id="8695f-128">确保用户和组拥有和维护访问文件共享位置的适当权限，并且仍可访问本地文件服务，这完全是您的责任。</span><span class="sxs-lookup"><span data-stu-id="8695f-128">It's entirely your responsibility to ensure that users and groups have and maintain the right permissions to access file share locations and that the on-premises file services remain accessible.</span></span> <span data-ttu-id="8695f-129">此外，您还应尽快删除对此类文件共享的要求。</span><span class="sxs-lookup"><span data-stu-id="8695f-129">Also, you should remove your requirements for such file shares as soon as possible.</span></span>

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a><span data-ttu-id="8695f-130">在 Microsoft 托管桌面中部署映射驱动器</span><span class="sxs-lookup"><span data-stu-id="8695f-130">To have mapped drives deployed in Microsoft Managed Desktop</span></span>
 
<span data-ttu-id="8695f-131">请确保无法避免映射的驱动器，并且在提交任何服务请求之前仔细查看了要求。</span><span class="sxs-lookup"><span data-stu-id="8695f-131">Make sure that mapped drives cannot be avoided and you have carefully reviewed the requirements before submitting any service request.</span></span> <span data-ttu-id="8695f-132">然后，按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="8695f-132">Then follow these steps:</span></span>

1. <span data-ttu-id="8695f-133">导航到[Microsoft 托管桌面门户](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="8695f-133">Navigate to the [Microsoft Managed Desktop portal](https://aka.ms/mmdportal).</span></span>  
2. <span data-ttu-id="8695f-134">通过 "**支持 > 支持请求**" 部分提交标题为 "映射驱动器部署" 的支持请求，并提供所有必需的文件共享详细信息。</span><span class="sxs-lookup"><span data-stu-id="8695f-134">Submit a support request titled “Mapped drives deployment” through the **Support > Support requests** section and provide all the required file share details.</span></span>  
3. <span data-ttu-id="8695f-135">Microsoft 托管桌面 IT 操作将在请求完成时使用支持请求更新通知。</span><span class="sxs-lookup"><span data-stu-id="8695f-135">Microsoft Managed Desktop IT Operations will advise, by using support request updates, when the request has been completed.</span></span> <span data-ttu-id="8695f-136">最初，此配置将仅部署到测试部署组中的设备。</span><span class="sxs-lookup"><span data-stu-id="8695f-136">Initially this configuration will only be deployed to devices in the Test deployment group.</span></span>  
4. <span data-ttu-id="8695f-137">您必须测试和确认由 Microsoft 托管桌面 IT 操作部署的配置是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="8695f-137">You must test and confirm whether the configuration deployed by the Microsoft Managed Desktop IT Operations works as you expect.</span></span> <span data-ttu-id="8695f-138">使用支持请求中的 "讨论" 选项卡进行答复，以在完成测试后通知 Microsoft 托管的桌面 IT 操作。</span><span class="sxs-lookup"><span data-stu-id="8695f-138">Reply using the Discussion tab in the Support request to notify Microsoft Managed Desktop IT Operations once you've completed your testing.</span></span>  
5. <span data-ttu-id="8695f-139">Microsoft 托管桌面 IT 操作团队随后会将配置部署到其他部署组。</span><span class="sxs-lookup"><span data-stu-id="8695f-139">Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups.</span></span> 
