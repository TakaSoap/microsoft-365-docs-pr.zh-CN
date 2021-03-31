---
title: 使用 Microsoft 咨询服务
description: 使用 MCS 打包应用的准备工作和后续步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1441ca3305a5f3e5a83ddd5e1547812f08d7d96b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445692"
---
# <a name="working-with-microsoft-consulting-services"></a><span data-ttu-id="5d739-104">使用 Microsoft 咨询服务</span><span class="sxs-lookup"><span data-stu-id="5d739-104">Working with Microsoft Consulting Services</span></span>

<span data-ttu-id="5d739-105">你可以与 Microsoft 咨询服务 (MCS) ，以打包应用以与 Microsoft 托管桌面一同使用。</span><span class="sxs-lookup"><span data-stu-id="5d739-105">You can engage with Microsoft Consulting Services (MCS) to get your apps packaged for use with Microsoft Managed Desktop.</span></span> <span data-ttu-id="5d739-106">有关确切详细信息，请与你的帐户代表联系 MCS，并确定特定应用打包项目的范围。</span><span class="sxs-lookup"><span data-stu-id="5d739-106">For exact details, work with your account representative to contact MCS and scope your specific app packaging project.</span></span>

## <a name="roles-and-responsibilities"></a><span data-ttu-id="5d739-107">角色和职责</span><span class="sxs-lookup"><span data-stu-id="5d739-107">Roles and responsibilities</span></span>

<span data-ttu-id="5d739-108">若要使用 MCS 应用打包 **，必须提供以下元素**：</span><span class="sxs-lookup"><span data-stu-id="5d739-108">To work with MCS app packaging, **you must provide these elements**:</span></span>

- <span data-ttu-id="5d739-109">源安装程序文件 (例如，setup.exe .msi) 。</span><span class="sxs-lookup"><span data-stu-id="5d739-109">The source installer files (for example, setup.exe or .msi).</span></span>
- <span data-ttu-id="5d739-110">安装说明，指定最终安装的外观的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d739-110">The installation instructions, specifying details about how the final installation should look.</span></span> <span data-ttu-id="5d739-111">例如，应用应该有桌面快捷方式吗？</span><span class="sxs-lookup"><span data-stu-id="5d739-111">For example, should there be a desktop shortcut to the app?</span></span> <span data-ttu-id="5d739-112">应用的可见性应该是什么？</span><span class="sxs-lookup"><span data-stu-id="5d739-112">What should the app's visibility be?</span></span> <span data-ttu-id="5d739-113">应用应连接到服务器，如果是，应连接到哪一台服务器？</span><span class="sxs-lookup"><span data-stu-id="5d739-113">Should the app connect to a server and if so, which one?</span></span> <span data-ttu-id="5d739-114">有关详细信息，请参阅应用程序 [打包请求模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。</span><span class="sxs-lookup"><span data-stu-id="5d739-114">For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</span></span>
- <span data-ttu-id="5d739-115">你必须执行自己的验收测试，以验证应用是否可像你需要在你的环境中一样工作。</span><span class="sxs-lookup"><span data-stu-id="5d739-115">You must perform your own acceptance testing to verify that the app works as you need it to in your environment.</span></span>

<span data-ttu-id="5d739-116">**MCS 将处理以下操作：**</span><span class="sxs-lookup"><span data-stu-id="5d739-116">**MCS will take care of these actions:**</span></span>

- <span data-ttu-id="5d739-117">检查 Microsoft 托管桌面环境中是否禁止或限制应用。</span><span class="sxs-lookup"><span data-stu-id="5d739-117">Checking whether the app is prohibited or restricted in the Microsoft Managed Desktop environment.</span></span>
- <span data-ttu-id="5d739-118">测试应用的安装、启动和卸载以确保与 Windows 10 兼容。</span><span class="sxs-lookup"><span data-stu-id="5d739-118">Testing of installation, starting, and uninstallation of the app to ensure compatibility with Windows 10.</span></span> <span data-ttu-id="5d739-119">如果 MCS 发现兼容性问题，他们将向应用保证计划提供该应用进行[](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure)修正。</span><span class="sxs-lookup"><span data-stu-id="5d739-119">If MCS discovers a compatibility issue, they will hand off the app to the [App Assure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) program for remediation.</span></span>
- <span data-ttu-id="5d739-120">将应用打包到规范中，然后使用 Microsoft Intune 测试应用部署。</span><span class="sxs-lookup"><span data-stu-id="5d739-120">Packaging the app to your specification and then testing app deployment by using Microsoft Intune.</span></span>

## <a name="app-delivery-schedule"></a><span data-ttu-id="5d739-121">应用交付计划</span><span class="sxs-lookup"><span data-stu-id="5d739-121">App delivery schedule</span></span>

<span data-ttu-id="5d739-122">将应用信息上载到 Microsoft 托管桌面门户，开始打包过程。</span><span class="sxs-lookup"><span data-stu-id="5d739-122">Start the packaging process by uploading the app information to the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="5d739-123">打包团队每周四审查新提交。</span><span class="sxs-lookup"><span data-stu-id="5d739-123">The packaging team reviews new submissions every Thursday.</span></span> <span data-ttu-id="5d739-124">在查看和打包后，打包的应用在下面的星期五交付。</span><span class="sxs-lookup"><span data-stu-id="5d739-124">After review and packaging, the packaged apps are delivered the following Friday.</span></span> <span data-ttu-id="5d739-125">每周最多可以打包五个应用以启动，但服务可以扩展以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="5d739-125">Up to five apps per week can be packaged to start but the service can scale to meet your needs.</span></span>

![显示应用在此示例) 中周四 (21 日的日历、第二天的媒体验证、 (年 25 日) 周一打包，以及下一个周五 (29 日) ](../../media/MCS-cal.png)

<span data-ttu-id="5d739-127">应用传递后，你将收到通知。</span><span class="sxs-lookup"><span data-stu-id="5d739-127">You'll be notified once the app has been delivered.</span></span> <span data-ttu-id="5d739-128">此时，你有 21 天的时间在 Microsoft 托管桌面门户中执行验收测试和批准工作。</span><span class="sxs-lookup"><span data-stu-id="5d739-128">At that point, you have 21 days to perform acceptance testing and approve the work in the Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="5d739-129">如果在验收测试期间发现应用的一些问题，在 Microsoft 托管桌面门户中拒绝该应用，你将通过电子邮件与 MCS 包装程序进行连接，以了解并解决该问题。</span><span class="sxs-lookup"><span data-stu-id="5d739-129">If discover some problem with the app during your acceptance testing, reject the app in the Microsoft Managed Desktop portal and you will be connected via email with an MCS packager to understand and resolve the issue.</span></span>

## <a name="testing-accounts-and-environment"></a><span data-ttu-id="5d739-130">测试帐户和环境</span><span class="sxs-lookup"><span data-stu-id="5d739-130">Testing accounts and environment</span></span>

<span data-ttu-id="5d739-131">若要让打包团队完成到 Microsoft Intune 的迁移，我们建议你提供某些权限：</span><span class="sxs-lookup"><span data-stu-id="5d739-131">For the packaging team to complete the migration to Microsoft Intune, we recommend that you provide certain permissions:</span></span>
 
-   <span data-ttu-id="5d739-132">访问 Microsoft Intune 的应用部署功能，让包装程序添加和分配应用</span><span class="sxs-lookup"><span data-stu-id="5d739-132">Access to Microsoft Intune’s App Deployment capabilities for the packager to add and assign the app</span></span> 
-   <span data-ttu-id="5d739-133">测试组、用户帐户和许可证，使包装程序能够测试应用</span><span class="sxs-lookup"><span data-stu-id="5d739-133">Test groups, user accounts, and licenses for the packagers to be able to test the apps</span></span>

<span data-ttu-id="5d739-134">MCS 将使用这些权限执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5d739-134">MCS will use those permissions to perform the following actions:</span></span>
 
-   <span data-ttu-id="5d739-135">确保应用适用于为 Microsoft 托管桌面配置的虚拟机</span><span class="sxs-lookup"><span data-stu-id="5d739-135">Ensuring that the app works on virtual machine configured for Microsoft Managed Desktop</span></span>
-   <span data-ttu-id="5d739-136">将应用上传到 Microsoft Intune 以部署到用户</span><span class="sxs-lookup"><span data-stu-id="5d739-136">Uploading the app to Microsoft Intune for deployment to your users</span></span>

<span data-ttu-id="5d739-137">如果没有这些权限，MCS 可能会前进，但无法将应用程序上载到您的环境。</span><span class="sxs-lookup"><span data-stu-id="5d739-137">Without these permissions, it is possible for MCS to move forward, but they will not be able to upload the applications to your environment.</span></span>
