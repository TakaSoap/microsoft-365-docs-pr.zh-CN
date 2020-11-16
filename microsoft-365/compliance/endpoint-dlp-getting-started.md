---
title: Microsoft 365 终结点数据丢失防护入门
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 设置 Microsoft 365 终结点数据丢失防护，以监视文件活动并将针对这些文件的保护措施实施到终结点。
ms.openlocfilehash: 6ba3b83d634f946f818890a732a83166f346162d
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073091"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="5c564-103">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="5c564-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="5c564-p101">Microsoft 终结点数据丢失防护（终结点 DLP）是 Microsoft 365 数据丢失防护 (DLP) 功能套件的一部分，可用于发现和保护 Microsoft 365 服务中的敏感项目。有关 Microsoft 所有 DLP 产品/服务的更多信息，请参阅[数据丢失防护概述](data-loss-prevention-policies.md)。若要了解“终点 DLP”的详细信息，请参阅[了解终结点数据丢失防护](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="5c564-p101">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services. For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md). To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="5c564-p102">通过 Microsoft 终结点 DLP，你可以监视 Windows 10 设备并检测何时使用和共享敏感项目。这为你提供了所需的可见性和控制力，以确保正确使用和保护它们，并帮助防止可能危害它们的危险行为。</span><span class="sxs-lookup"><span data-stu-id="5c564-p102">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared. This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5c564-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="5c564-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="5c564-110">SKU/订阅许可</span><span class="sxs-lookup"><span data-stu-id="5c564-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="5c564-p103">在开始使用终结点 DLP 之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)以及任何加载项。若要访问和使用终结点 DLP 功能，必须具有这些订阅或加载项中的一个。</span><span class="sxs-lookup"><span data-stu-id="5c564-p103">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons. To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="5c564-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5c564-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="5c564-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="5c564-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="5c564-115">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="5c564-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="5c564-116">Microsoft 365 A5 合规</span><span class="sxs-lookup"><span data-stu-id="5c564-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="5c564-117">Microsoft 365 E5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="5c564-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="5c564-118">Microsoft 365 A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="5c564-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="5c564-119">权限</span><span class="sxs-lookup"><span data-stu-id="5c564-119">Permissions</span></span>

<span data-ttu-id="5c564-120">若要启用设备管理，你使用的帐户必须是以下任何一个角色的成员：</span><span class="sxs-lookup"><span data-stu-id="5c564-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="5c564-121">全局管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-121">Global admin</span></span>
- <span data-ttu-id="5c564-122">安全管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-122">Security admin</span></span>
- <span data-ttu-id="5c564-123">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-123">Compliance admin</span></span>

<span data-ttu-id="5c564-124">如果要使用自定义帐户查看设备管理设置，该帐户必须具有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="5c564-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="5c564-125">全局管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-125">Global admin</span></span>
- <span data-ttu-id="5c564-126">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-126">Compliance admin</span></span>
- <span data-ttu-id="5c564-127">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-127">Compliance data admin</span></span>
- <span data-ttu-id="5c564-128">全局读取者</span><span class="sxs-lookup"><span data-stu-id="5c564-128">Global reader</span></span>

<span data-ttu-id="5c564-129">如果要使用自定义帐户访问载入/载出页面，该帐户必须具有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="5c564-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="5c564-130">全局管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-130">Global admin</span></span>
- <span data-ttu-id="5c564-131">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-131">Compliance admin</span></span>

<span data-ttu-id="5c564-132">如果要使用自定义帐户打开/关闭设备监视，该帐户必须具有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="5c564-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="5c564-133">全局管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-133">Global admin</span></span>
- <span data-ttu-id="5c564-134">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-134">Compliance admin</span></span>

<span data-ttu-id="5c564-p104">可在[活动资源管理器](data-classification-activity-explorer.md)中查看终结点 DLP 中的数据。有四个角色可向活动资源管理器授予权限，用于访问数据的帐户必须是其中任何一个的成员。</span><span class="sxs-lookup"><span data-stu-id="5c564-p104">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="5c564-137">全局管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-137">Global admin</span></span>
- <span data-ttu-id="5c564-138">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-138">Compliance admin</span></span>
- <span data-ttu-id="5c564-139">安全管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-139">Security admin</span></span>
- <span data-ttu-id="5c564-140">合规性数据管理员</span><span class="sxs-lookup"><span data-stu-id="5c564-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="5c564-141">准备终结点</span><span class="sxs-lookup"><span data-stu-id="5c564-141">Prepare your endpoints</span></span>

<span data-ttu-id="5c564-142">确保你计划部署终结点 DLP 的 Windows 10 设备满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="5c564-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="5c564-143">必须运行 Windows 10 x64 内部版本 1809 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5c564-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="5c564-p105">反恶意软件客户端的版本为 4.18.2009.7 或更高版本。若要查看当前版本，请打开“Windows 安全中心”应用，选择“设置”图标，然后选择“关于”。“反恶意软件客户端版本”下列出了版本号。通过安装 Windows 更新 KB4052623，更新到最新的反恶意软件客户端版本。注意：任何 Windows 安全中心组件都无需处于活动状态，你可以独立于 Windows 安全中心状态运行终结点 DLP。</span><span class="sxs-lookup"><span data-stu-id="5c564-p105">Antimalware Client Version is 4.18.2009.7 or newer. Check your current version by opening Windows Security app, select the Settings icon, and then select About. The version number is listed under Antimalware Client Version. Update to the latest Antimalware Client Version by installing Windows Update KB4052623. Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="5c564-p106">已安装以下 Windows 更新。注意：这些更新不是将设备加入终结点 DLP 的先决条件，但它们包含对重要问题的修复，因此必须在使用该产品之前完成安装。</span><span class="sxs-lookup"><span data-stu-id="5c564-p106">The following Windows Updates are installed. Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="5c564-151">对于 Windows 10 1809 - KB4559003、KB4577069、KB4580390</span><span class="sxs-lookup"><span data-stu-id="5c564-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="5c564-152">对于 Windows 10 1903 或 1909 - KB4559004、KB4577062、KB4580386</span><span class="sxs-lookup"><span data-stu-id="5c564-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="5c564-153">对于 Windows 10 2004 - KB4568831、KB4577063</span><span class="sxs-lookup"><span data-stu-id="5c564-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="5c564-154">对于运行 Office 2016（而未运行任何其他 Office 版本）的设备 - KB4577063</span><span class="sxs-lookup"><span data-stu-id="5c564-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="5c564-155">所有设备必须[已建立 Azure Active Directory (Azure AD) 联接](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) 或已建立混合 Azure AD 联接。</span><span class="sxs-lookup"><span data-stu-id="5c564-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="5c564-p107">在终结点设备上安装 Microsoft Chromium Edge 浏览器，以对上传到云活动执行策略操作。请参见[下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)。</span><span class="sxs-lookup"><span data-stu-id="5c564-p107">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity. See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="5c564-p108">如果使用的是 Microsoft 365 应用版的月度企业版 2004-2008，则终结点 DLP 的已知问题会分类 Office 内容，需要更新到版本 2009 或更高版本。参见 [Microsoft 365 应用版的更新历史记录（按日期列出）](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)。如需了解有关此问题的更多信息，请参见[有关 2020 年当前频道发行的发行说明](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27)的 Office 套件部分。</span><span class="sxs-lookup"><span data-stu-id="5c564-p108">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later. See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions. To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="5c564-161">将设备载入设备管理</span><span class="sxs-lookup"><span data-stu-id="5c564-161">Onboarding devices into device management</span></span>

<span data-ttu-id="5c564-p109">必须先启用设备监视功能并载入终结点，然后才能监视和保护设备上的敏感项目。这两项操作都在 Microsoft 365 合规门户中完成。</span><span class="sxs-lookup"><span data-stu-id="5c564-p109">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device. Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="5c564-p110">当你想载入尚未载入的设备时，你需要下载适当的脚本并将其部署到那些设备上。按照[载入设备程序](endpoint-dlp-getting-started.md#onboarding-devices)进行操作。</span><span class="sxs-lookup"><span data-stu-id="5c564-p110">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices. Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="5c564-p111">已载入到 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) 的设备将显示在“托管设备”列表中。按照[与设备载入到 Microsoft Defender for Endpoint 相关过程](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint)进行操作。</span><span class="sxs-lookup"><span data-stu-id="5c564-p111">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list. Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="5c564-168">载入设备</span><span class="sxs-lookup"><span data-stu-id="5c564-168">Onboarding devices</span></span>

<span data-ttu-id="5c564-169">在此部署方案中，你将载入尚未载入的设备，并且只想监视和保护敏感项目，防止 Windows 10 设备上发生意外共享。</span><span class="sxs-lookup"><span data-stu-id="5c564-169">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="5c564-170">打开“[Microsoft 合规中心](https://compliance.microsoft.com)”。</span><span class="sxs-lookup"><span data-stu-id="5c564-170">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="5c564-171">打开合规中心设置页面，然后选择“ **载入设备** ”。</span><span class="sxs-lookup"><span data-stu-id="5c564-171">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c564-172">![启用设备管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="5c564-172">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="5c564-173">设备载入通常需要大约 60 秒才能启用，请先等待 30 分钟，然后再与 Microsoft 支持人员接洽。</span><span class="sxs-lookup"><span data-stu-id="5c564-173">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="5c564-p112">选择“ **设备管理** ”，以打开“ **设备** ”列表。在载入设备之前，此列表将为空。</span><span class="sxs-lookup"><span data-stu-id="5c564-p112">Choose **Device management** to open the **Devices** list. The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="5c564-176">选择“ **载入** ”以开始载入流程。</span><span class="sxs-lookup"><span data-stu-id="5c564-176">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="5c564-177">从“ **部署方法** ”列表中选择要部署到这些额外设备的方式，然后 **下载程序包** 。</span><span class="sxs-lookup"><span data-stu-id="5c564-177">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c564-178">![部署方法](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="5c564-178">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="5c564-p113">按照[适用于 Windows 10 计算机的载入工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的相应程序进行操作。此链接会将你定位到登录页面，你可以在其中访问与在步骤 5 中选择的部署程序包相匹配的 Microsoft Defender for Endpoint 过程：</span><span class="sxs-lookup"><span data-stu-id="5c564-p113">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="5c564-181">使用组策略载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-181">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="5c564-182">使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-182">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="5c564-183">使用移动设备管理工具载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-183">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="5c564-184">使用本地脚本载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-184">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="5c564-185">载入非持久性虚拟桌面基础结构 (VDI) 计算机。</span><span class="sxs-lookup"><span data-stu-id="5c564-185">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="5c564-186">完成操作并启用终结点后，它应该在设备列表中可见，并且还应开始向活动资源管理器报告审核活动日志。</span><span class="sxs-lookup"><span data-stu-id="5c564-186">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="5c564-p114">此体验根据许可证强制实施。如果没有所需的许可证，数据将不可见或不可访问。</span><span class="sxs-lookup"><span data-stu-id="5c564-p114">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="5c564-189">与设备载入到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c564-189">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="5c564-p115">在此方案中，已经部署了 Microsoft Defender for Endpoint，并且在其中报告了终结点。所有这些终结点都将显示在托管设备列表中。可通过使用[载入设备程序](endpoint-dlp-getting-started.md#onboarding-devices)将新设备继续载入到终结点 DLP 中，以扩展覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="5c564-p115">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in. All these endpoints will appear in the managed devices list. You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="5c564-193">打开“[Microsoft 合规中心](https://compliance.microsoft.com)”。</span><span class="sxs-lookup"><span data-stu-id="5c564-193">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="5c564-194">打开合规中心设置页面，然后选择“ **启用设备监视** ”。</span><span class="sxs-lookup"><span data-stu-id="5c564-194">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="5c564-p116">选择“ **设备管理** ”，以打开“ **设备** ”列表。你应该会看到已经向 Microsoft Defender for Endpoint 报告的设备列表。</span><span class="sxs-lookup"><span data-stu-id="5c564-p116">Choose **Device management** to open the **Devices** list. You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c564-197">![设备管理](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="5c564-197">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="5c564-198">如果需要载入附加设备，请选择“ **载入** ”。</span><span class="sxs-lookup"><span data-stu-id="5c564-198">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="5c564-199">从“ **部署方法** ”列表中选择要部署到这些额外设备的方式，然后 **下载程序包** 。</span><span class="sxs-lookup"><span data-stu-id="5c564-199">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="5c564-p117">按照[适用于 Windows 10 计算机的载入工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)中的相应程序进行操作。此链接会将你定位到登录页面，你可以在其中访问与在步骤 5 中选择的部署程序包相匹配的 Microsoft Defender for Endpoint 过程：</span><span class="sxs-lookup"><span data-stu-id="5c564-p117">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="5c564-202">使用组策略载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-202">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="5c564-203">使用 Microsoft Endpoint Configuration Manager 载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-203">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="5c564-204">使用移动设备管理工具载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-204">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="5c564-205">使用本地脚本载入 Windows 10 计算机</span><span class="sxs-lookup"><span data-stu-id="5c564-205">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="5c564-206">载入非持久性虚拟桌面基础结构 (VDI) 计算机。</span><span class="sxs-lookup"><span data-stu-id="5c564-206">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="5c564-207">完成操作并载入终结点后，它应该在“ **设备** ”表下可见，并且还应开始向 **活动资源管理器** 报告审核日志。</span><span class="sxs-lookup"><span data-stu-id="5c564-207">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="5c564-p118">此体验根据许可证强制实施。如果没有所需的许可证，数据将不可见或不可访问。</span><span class="sxs-lookup"><span data-stu-id="5c564-p118">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="5c564-210">在 DLP 警报管理仪表板中查看“终点 DLP 警报”</span><span class="sxs-lookup"><span data-stu-id="5c564-210">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="5c564-211">打开 Microsoft 365 安全合规中心的“数据丢失防护”页，然后选择“警报”。</span><span class="sxs-lookup"><span data-stu-id="5c564-211">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="5c564-212">请参阅 [如何配置和查看 DLP 策略的警报](dlp-configure-view-alerts-policies.md) 中的过程，以查看你的终结点 DLP 策略警报。</span><span class="sxs-lookup"><span data-stu-id="5c564-212">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="5c564-213">在活动资源管理器中查看终结点 DLP 数据</span><span class="sxs-lookup"><span data-stu-id="5c564-213">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="5c564-214">在 Microsoft 365 合规中心中打开域的“[数据分类页面](https://compliance.microsoft.com/dataclassification?viewid=overview)”，然后选择“活动资源管理器”。</span><span class="sxs-lookup"><span data-stu-id="5c564-214">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="5c564-215">请参考[活动资源管理器入门](data-classification-activity-explorer.md)中的程序，以访问和筛选终结点设备的所有数据。</span><span class="sxs-lookup"><span data-stu-id="5c564-215">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5c564-216">![终结点设备的活动资源管理器筛选器](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="5c564-216">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c564-217">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5c564-217">Next steps</span></span>
<span data-ttu-id="5c564-218">现在，你已载入设备，并且可以在“活动资源管理器”中查看活动数据，那么就可以继续下一步，在其中创建保护敏感项目的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="5c564-218">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="5c564-219">使用终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="5c564-219">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="5c564-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c564-220">See also</span></span>

- [<span data-ttu-id="5c564-221">了解终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="5c564-221">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="5c564-222">使用终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="5c564-222">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="5c564-223">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="5c564-223">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="5c564-224">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="5c564-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="5c564-225">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="5c564-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="5c564-226">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5c564-226">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="5c564-227">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="5c564-227">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="5c564-228">Microsoft 365 订阅</span><span class="sxs-lookup"><span data-stu-id="5c564-228">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="5c564-229">已建立 Azure AD 联接的设备</span><span class="sxs-lookup"><span data-stu-id="5c564-229">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="5c564-230">下载基于 Chromium 的新 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5c564-230">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
