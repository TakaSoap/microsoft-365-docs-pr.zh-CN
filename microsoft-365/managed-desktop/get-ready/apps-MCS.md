---
title: 使用 Microsoft 咨询服务
description: 使用 MCS 来打包应用程序需要遵循的准备和步骤
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用、MCS、打包
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918717"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="bf9c3-104">使用 Microsoft 咨询服务</span><span class="sxs-lookup"><span data-stu-id="bf9c3-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="bf9c3-105">你可以与 Microsoft 咨询服务 (MCS) 接洽, 以获取打包用于 Microsoft 托管桌面的应用。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="bf9c3-106">有关详细信息, 请与你的帐户代表联系 MCS 并将你的特定应用打包项目限定为范围。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="bf9c3-107">角色和职责</span><span class="sxs-lookup"><span data-stu-id="bf9c3-107">Roles and responsibilities</span></span>

<span data-ttu-id="bf9c3-108">若要使用 MCS 应用程序打包,**您必须提供以下元素**:</span><span class="sxs-lookup"><span data-stu-id="bf9c3-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="bf9c3-109">源安装程序文件 (例如, setup.exe 或 .msi)。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-109">The source installer files (e.g., setup.exe or .msi).</span></span>
- <span data-ttu-id="bf9c3-110">安装说明, 指定有关最终安装的外观的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="bf9c3-111">例如, 是否应有应用程序的桌面快捷方式？</span><span class="sxs-lookup"><span data-stu-id="bf9c3-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="bf9c3-112">应用程序的可见性是什么？</span><span class="sxs-lookup"><span data-stu-id="bf9c3-112">What should the app's visibility be?</span></span> <span data-ttu-id="bf9c3-113">应用是否应连接到服务器, 如果是, 是否应使用哪一个？</span><span class="sxs-lookup"><span data-stu-id="bf9c3-113">Should the app connect to a server and if so, which one?</span></span> <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- <span data-ttu-id="bf9c3-114">您必须执行自己的验收测试, 以验证应用程序在您的环境中是否按需运行。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-114">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="bf9c3-115">**MCS 将负责执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="bf9c3-115">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="bf9c3-116">在 Microsoft 托管桌面环境中检查是否禁止或限制应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-116">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="bf9c3-117">测试应用程序的安装、启动和卸载, 以确保与 Windows 10 兼容。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-117">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="bf9c3-118">如果 MCS 发现兼容性问题, 则会将应用程序分发到[桌面应用](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure)程序, 从而确保程序的补救。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-118">If MCS discovers a compatibility issue, they will hand off the app to the [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) program for remediation.</span></span>
- <span data-ttu-id="bf9c3-119">将应用程序打包到规范, 然后使用 Microsoft Intune 测试应用程序部署。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-119">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="bf9c3-120">应用程序交付计划</span><span class="sxs-lookup"><span data-stu-id="bf9c3-120">App delivery schedule</span></span>

<span data-ttu-id="bf9c3-121">通过将应用程序信息上载到 Microsoft 托管桌面门户来启动打包过程。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-121">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="bf9c3-122">打包团队每星期四查看一次新的提交。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-122">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="bf9c3-123">查看和打包后, 打包后的应用程序将在下星期五提供。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-123">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="bf9c3-124">可以将每周最长5个应用打包到开始, 但服务可进行扩展以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-124">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![显示应用程序评审、打包和交付日期的日历](images/MCS-cal.png)

<span data-ttu-id="bf9c3-126">一旦应用程序被传递, 你将收到通知。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-126">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="bf9c3-127">在这种情况下, 你有21天的时间执行验收测试, 并对 Microsoft 托管桌面门户中的工作进行签名。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-127">At that point, you have 21 days to perform acceptance testing and sign off on the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="bf9c3-128">如果在接受测试过程中发现应用程序出现问题, 请在 Microsoft 托管桌面门户中拒绝应用程序, 并通过电子邮件通过 MCS 包装程序进行连接, 以了解并解决该问题。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-128">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="bf9c3-129">测试帐户和环境</span><span class="sxs-lookup"><span data-stu-id="bf9c3-129">Testing accounts and environment</span></span>

<span data-ttu-id="bf9c3-130">对于打包团队, 若要完成到 Microsoft Intune 的迁移, 我们建议您提供某些权限:</span><span class="sxs-lookup"><span data-stu-id="bf9c3-130">For the packaging team to complete the migration to Microsoft Intune we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="bf9c3-131">对包装程序的 Microsoft Intune 应用程序部署功能的访问权限, 以添加和分配应用程序</span><span class="sxs-lookup"><span data-stu-id="bf9c3-131">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="bf9c3-132">测试组、用户帐户和 packagers 的许可证, 以便能够测试应用程序</span><span class="sxs-lookup"><span data-stu-id="bf9c3-132">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="bf9c3-133">MCS 将使用这些权限执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="bf9c3-133">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="bf9c3-134">确保应用程序在为 Microsoft 托管桌面配置的虚拟机上运行</span><span class="sxs-lookup"><span data-stu-id="bf9c3-134">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="bf9c3-135">将应用程序上载到 Microsoft Intune 以部署到你的用户</span><span class="sxs-lookup"><span data-stu-id="bf9c3-135">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="bf9c3-136">如果没有这些权限, MCS 可以向前移动, 但不能将应用程序上传到您的环境。</span><span class="sxs-lookup"><span data-stu-id="bf9c3-136">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>


