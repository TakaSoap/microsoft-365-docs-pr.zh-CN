---
title: 在 Microsoft 365 安全中心中打开 Microsoft 威胁防护
description: 了解如何启用 Microsoft 威胁防护并开始集成安全事件和响应。
keywords: 入门、启用 MTP、Microsoft 威胁防护、M365、security、data location、必需权限、许可证资格、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 73c4c9864713432d318b0b3cec9fbaf395deff45
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374140"
---
# <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="b58b2-104">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="b58b2-104">Turn on Microsoft Threat Protection</span></span>

<span data-ttu-id="b58b2-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b58b2-105">**Applies to:**</span></span>
- <span data-ttu-id="b58b2-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="b58b2-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b58b2-107">Microsoft 威胁防护通过集成 Microsoft Defender 高级威胁防护 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的关键功能来统一事件响应流程。</span><span class="sxs-lookup"><span data-stu-id="b58b2-107">Microsoft Threat Protection unifies your incident response process by integrating key capabilities across Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b58b2-108">这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。</span><span class="sxs-lookup"><span data-stu-id="b58b2-108">This unified experience adds powerful features you can access in the Microsoft 365 security center.</span></span>

<span data-ttu-id="b58b2-109">若要获得最佳保护并优化 Microsoft 威胁防护，建议在网络上部署所有适用的受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="b58b2-109">To get the best protection and optimize Microsoft Threat Protection, we recommend deploying all applicable supported services on your network.</span></span> <span data-ttu-id="b58b2-110">有关详细信息，请[参阅部署支持的服务](deploy-supported-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b58b2-110">For more information, [read about deploying supported services](deploy-supported-services.md).</span></span>

## <a name="check-license-eligibility-and-required-permissions"></a><span data-ttu-id="b58b2-111">检查许可证资格和必需权限</span><span class="sxs-lookup"><span data-stu-id="b58b2-111">Check license eligibility and required permissions</span></span>
<span data-ttu-id="b58b2-112">Microsoft 365 E5、E5 Security、A5 或 A5 安全许可证或有效的许可证组合提供了对受支持的服务的访问权限，并允许您在 Microsoft 365 安全中心中使用 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="b58b2-112">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

<span data-ttu-id="b58b2-113">有关许可的详细信息，请[阅读许可要求](prerequisites.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="b58b2-113">For detailed licensing information, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

### <a name="check-your-role"></a><span data-ttu-id="b58b2-114">检查你的角色</span><span class="sxs-lookup"><span data-stu-id="b58b2-114">Check your role</span></span>
<span data-ttu-id="b58b2-115">您必须是**全局管理员**或 Azure Active Directory 中的**安全管理员**才能打开 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="b58b2-115">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft Threat Protection.</span></span> [<span data-ttu-id="b58b2-116">在 Azure AD 中查看你的角色</span><span class="sxs-lookup"><span data-stu-id="b58b2-116">View your roles in Azure AD</span></span>](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a><span data-ttu-id="b58b2-117">开始使用服务</span><span class="sxs-lookup"><span data-stu-id="b58b2-117">Start using the service</span></span>
<span data-ttu-id="b58b2-118">Microsoft 威胁防护从各种集成服务中聚合数据。</span><span class="sxs-lookup"><span data-stu-id="b58b2-118">Microsoft Threat Protection aggregates data from the various integrated services.</span></span> <span data-ttu-id="b58b2-119">它将集中处理和存储数据，以确定新的见解并使集中响应工作流成为可能。</span><span class="sxs-lookup"><span data-stu-id="b58b2-119">It will process and store data centrally to identify new insights and make centralized response workflows possible.</span></span>

<span data-ttu-id="b58b2-120">在你打开服务之前，Microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）会在你选择 "**事件**"、"**操作中心**" 或 "导航窗格" 中的 "**搜寻**" 时显示 microsoft 威胁防护欢迎页面。</span><span class="sxs-lookup"><span data-stu-id="b58b2-120">Before you turn on the service, the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) shows the Microsoft Threat Protection welcome page when you select **Incidents**, **Action center**, or **Hunting** from the navigation pane.</span></span> <span data-ttu-id="b58b2-121">如果你不符合使用 Microsoft 威胁防护的条件，则不会显示这些导航选项。</span><span class="sxs-lookup"><span data-stu-id="b58b2-121">These navigation options are not shown if you are not eligible to use Microsoft Threat Protection.</span></span>

<span data-ttu-id="b58b2-122">![Microsoft](../../media/mtp-welcome.png)
*365 安全中心中*未打开 microsoft 威胁防护欢迎页面时显示的 microsoft 威胁防护欢迎页面的图像</span><span class="sxs-lookup"><span data-stu-id="b58b2-122">![Image of the Microsoft Threat Protection welcome page shown if Microsoft Threat Protection has not been turned on](../../media/mtp-welcome.png)
*Microsoft Threat Protection welcome page in Microsoft 365 security center*</span></span>

<span data-ttu-id="b58b2-123">若要打开 Microsoft 威胁防护，只需从欢迎页面完成此过程即可。</span><span class="sxs-lookup"><span data-stu-id="b58b2-123">To turn on Microsoft Threat Protection, simply complete the process from the welcome page.</span></span> <span data-ttu-id="b58b2-124">您还可以通过在导航窗格中访问**设置**（[security.microsoft.com/settings](https://security.microsoft.com/settings)）并选择 " **microsoft 威胁防护**" 来打开 microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="b58b2-124">You can also turn on Microsoft Threat Protection by accessing **Settings** ([security.microsoft.com/settings](https://security.microsoft.com/settings)) in the navigation pane and selecting **Microsoft Threat Protection**.</span></span>

>[!NOTE]
><span data-ttu-id="b58b2-125">如果在导航窗格中看不到**设置**或无法访问页面，请检查您的权限和许可证。</span><span class="sxs-lookup"><span data-stu-id="b58b2-125">If you don't see **Settings** in the navigation pane or couldn't access the page, check your permissions and licenses.</span></span>

### <a name="select-data-center-location"></a><span data-ttu-id="b58b2-126">选择数据中心位置</span><span class="sxs-lookup"><span data-stu-id="b58b2-126">Select data center location</span></span>
<span data-ttu-id="b58b2-127">如果已为组织设置了 Microsoft Defender ATP，则数据将在为 [Microsoft Defender ATP 数据](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)选择的同一数据中心位置进行存储和处理。</span><span class="sxs-lookup"><span data-stu-id="b58b2-127">If Microsoft Defender ATP has been provisioned for your organization, data will be stored and processed in the same data center location you have selected for [your Microsoft Defender ATP data](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span> <span data-ttu-id="b58b2-128">如果你没有 Microsoft Defender ATP，系统将要求你选择一个专门用于 Microsoft 威胁防护的新数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="b58b2-128">If you don't have Microsoft Defender ATP, you will be asked to choose a new data center location specifically for Microsoft Threat Protection.</span></span> 

<span data-ttu-id="b58b2-129">您需要先提供许可，然后才能在服务和聚合之间共享数据。</span><span class="sxs-lookup"><span data-stu-id="b58b2-129">You need to provide consent before data is shared between services and aggregated.</span></span>

### <a name="confirm-that-the-service-is-on"></a><span data-ttu-id="b58b2-130">确认服务已开启</span><span class="sxs-lookup"><span data-stu-id="b58b2-130">Confirm that the service is on</span></span>
<span data-ttu-id="b58b2-131">设置服务后，它将添加：</span><span class="sxs-lookup"><span data-stu-id="b58b2-131">Once the service is provisioned, it adds:</span></span>

- [<span data-ttu-id="b58b2-132">事件管理</span><span class="sxs-lookup"><span data-stu-id="b58b2-132">Incidents management</span></span>](incidents-overview.md)
- <span data-ttu-id="b58b2-133">用于管理[自动调查和响应](mtp-autoir.md)的操作中心</span><span class="sxs-lookup"><span data-stu-id="b58b2-133">An action center for managing [automated investigation and response](mtp-autoir.md)</span></span>
- <span data-ttu-id="b58b2-134">[高级搜寻](advanced-hunting-overview.md)功能</span><span class="sxs-lookup"><span data-stu-id="b58b2-134">[Advanced hunting](advanced-hunting-overview.md) capabilities</span></span>

<span data-ttu-id="b58b2-135">![Microsoft 365 security center 导航窗格的图像与 microsoft 威胁防护功能](../../media/mtp-on.png)
*microsoft 365 security center with 事件管理和其他 Microsoft 威胁防护功能*</span><span class="sxs-lookup"><span data-stu-id="b58b2-135">![Image of Microsoft 365 security center navigation pane with Microsoft Threat Protection features](../../media/mtp-on.png)
*Microsoft 365 security center with incidents management and other Microsoft Threat Protection capabilities*</span></span>

### <a name="getting-azure-atp-data"></a><span data-ttu-id="b58b2-136">获取 Azure ATP 数据</span><span class="sxs-lookup"><span data-stu-id="b58b2-136">Getting Azure ATP data</span></span>
<span data-ttu-id="b58b2-137">要使用 Microsoft 威胁防护共享 Azure ATP 数据，请确保已打开 Microsoft Cloud App Security 和 Azure ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="b58b2-137">To share Azure ATP data with Microsoft Threat Protection, ensure that Microsoft Cloud App Security and Azure ATP integration is turned on.</span></span> [<span data-ttu-id="b58b2-138">了解有关此集成的更多信息</span><span class="sxs-lookup"><span data-stu-id="b58b2-138">Learn more about this integration</span></span>](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a><span data-ttu-id="b58b2-139">关闭 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="b58b2-139">Turn off Microsoft Threat Protection</span></span>
<span data-ttu-id="b58b2-140">要停止使用 Microsoft 威胁防护，请转到 Microsoft 365 安全中心中的“**设置**” > “**Microsoft 威胁防护**” > “**选择加入/选择退出**”。</span><span class="sxs-lookup"><span data-stu-id="b58b2-140">To stop using Microsoft Threat Protection, go to **Settings** > **Microsoft Threat Protection** > **Opt-in / Opt-out** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b58b2-141">取消选择**打开 Microsoft 威胁防护**并保存更改。</span><span class="sxs-lookup"><span data-stu-id="b58b2-141">Unselect **Turn on Microsoft Threat Protection** and save the changes.</span></span>

<span data-ttu-id="b58b2-142">将从 Microsoft 365 安全中心删除相应的功能。</span><span class="sxs-lookup"><span data-stu-id="b58b2-142">Corresponding features will be removed from the Microsoft 365 security center.</span></span>

## <a name="get-assistance"></a><span data-ttu-id="b58b2-143">获取帮助</span><span class="sxs-lookup"><span data-stu-id="b58b2-143">Get assistance</span></span>

<span data-ttu-id="b58b2-144">Microsoft 支持人员可帮助设置或取消设置或取消设置租户上的服务和相关资源。</span><span class="sxs-lookup"><span data-stu-id="b58b2-144">Microsoft support staff can help provision or deprovision the service and related resources on your tenant.</span></span> <span data-ttu-id="b58b2-145">若要获取帮助，请在 Microsoft 365 安全中心中选择 **"需要帮助？** "。</span><span class="sxs-lookup"><span data-stu-id="b58b2-145">For assistance, select **Need help?** in the Microsoft 365 security center.</span></span> <span data-ttu-id="b58b2-146">联系支持时，请提及 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="b58b2-146">When contacting support, mention Microsoft Threat Protection.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b58b2-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="b58b2-147">Related topics</span></span>

- [<span data-ttu-id="b58b2-148">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="b58b2-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="b58b2-149">许可要求和其他先决条件</span><span class="sxs-lookup"><span data-stu-id="b58b2-149">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="b58b2-150">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="b58b2-150">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="b58b2-151">Microsoft Defender ATP 概述</span><span class="sxs-lookup"><span data-stu-id="b58b2-151">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="b58b2-152">Office 365 ATP 概述</span><span class="sxs-lookup"><span data-stu-id="b58b2-152">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="b58b2-153">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="b58b2-153">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="b58b2-154">Azure ATP 概述</span><span class="sxs-lookup"><span data-stu-id="b58b2-154">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [<span data-ttu-id="b58b2-155">Microsoft Defender ATP 数据存储</span><span class="sxs-lookup"><span data-stu-id="b58b2-155">Microsoft Defender ATP data storage</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
