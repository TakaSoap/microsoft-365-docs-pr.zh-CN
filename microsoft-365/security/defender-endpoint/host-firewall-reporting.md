---
title: Microsoft Defender for Endpoint 中的主机防火墙报告
description: 在安全中心托管和查看Microsoft 365报告。
keywords: windows defender， 防火墙
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809224"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="dd2bd-104">Microsoft Defender for Endpoint 中的主机防火墙报告</span><span class="sxs-lookup"><span data-stu-id="dd2bd-104">Host firewall reporting in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd2bd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="dd2bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="dd2bd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dd2bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dd2bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dd2bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="dd2bd-108">如果你是管理员，你现在可以将防火墙报告托管到Microsoft 365[中心](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-108">If you are an admin, you can now host firewall reporting to [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="dd2bd-109">此功能使您能够从集中Windows 10查看 Windows Server 2019 防火墙报告。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-109">This feature enables you to view Windows 10 and Windows Server 2019 firewall reporting from a centralized location.</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dd2bd-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="dd2bd-110">What do you need to know before you begin?</span></span> 

- <span data-ttu-id="dd2bd-111">您必须运行 Windows 10 或 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-111">You must be running Windows 10 or Windows Server 2019.</span></span>
- <span data-ttu-id="dd2bd-112">若要将设备载入到 Microsoft Defender for Endpoint 服务，请参阅 [此处](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-112">To onboard devices to the Microsoft Defender for Endpoint service, see [here](onboard-configure.md).</span></span> 
- <span data-ttu-id="dd2bd-113">若要Microsoft 365安全中心开始接收数据，必须启用高级安全Windows Defender 防火墙审核事件： </span><span class="sxs-lookup"><span data-stu-id="dd2bd-113">For Microsoft 365 security center to start receiving the data, you must enable **Audit Events** for Windows Defender Firewall with Advanced Security:</span></span> 
    - [<span data-ttu-id="dd2bd-114">审核筛选平台数据包丢弃</span><span class="sxs-lookup"><span data-stu-id="dd2bd-114">Audit Filtering Platform Packet Drop</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [<span data-ttu-id="dd2bd-115">审核筛选平台连接</span><span class="sxs-lookup"><span data-stu-id="dd2bd-115">Audit Filtering Platform Connection</span></span>](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- <span data-ttu-id="dd2bd-116">使用组策略对象编辑器、本地安全策略或命令启用这些事件auditpol.exe命令。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-116">Enable these events by using Group Policy Object Editor, Local Security Policy, or the auditpol.exe commands.</span></span> <span data-ttu-id="dd2bd-117">有关详细信息，请参阅 [此处](/windows/win32/fwp/auditing-and-logging)。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-117">For more information, see [here](/windows/win32/fwp/auditing-and-logging).</span></span> 
    - <span data-ttu-id="dd2bd-118">两个 PowerShell 命令是：</span><span class="sxs-lookup"><span data-stu-id="dd2bd-118">The two PowerShell commands are:</span></span>
        - <span data-ttu-id="dd2bd-119">**auditpol /set /subcategory："Filtering Platform Packet Drop" /failure：enable**</span><span class="sxs-lookup"><span data-stu-id="dd2bd-119">**auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**</span></span> 
        - <span data-ttu-id="dd2bd-120">**auditpol /set /subcategory："Filtering Platform Connection" /failure：enable**</span><span class="sxs-lookup"><span data-stu-id="dd2bd-120">**auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**</span></span> 

## <a name="the-process"></a><span data-ttu-id="dd2bd-121">过程</span><span class="sxs-lookup"><span data-stu-id="dd2bd-121">The process</span></span>
> [!NOTE]
> <span data-ttu-id="dd2bd-122">请务必按照上述部分中的说明操作，并正确配置设备，以参与早期预览。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-122">Make sure to follow the instructions from the section above and properly configure your devices for the early preview participation.</span></span>

- <span data-ttu-id="dd2bd-123">启用事件后，Microsoft 365安全中心将开始监视数据。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-123">After enabling the events, Microsoft 365 security center will start to monitor the data.</span></span>
    - <span data-ttu-id="dd2bd-124">远程 IP、远程端口、本地端口、本地 IP、计算机名称、跨入站和出站连接的进程。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-124">Remote IP, Remote Port, Local Port, Local IP, Computer Name, Process across inbound and outbound connections.</span></span>
- <span data-ttu-id="dd2bd-125">管理员现在可以在此处Windows主机防火墙[活动](https://security.microsoft.com/firewall)。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-125">Admins can now see Windows host firewall activity [here](https://security.microsoft.com/firewall).</span></span>
    - <span data-ttu-id="dd2bd-126">通过下载自定义报告脚本以使用自定义报告[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)脚本监视活动，Windows Defender 防火墙报告Power BI。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-126">Additional reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 
    - <span data-ttu-id="dd2bd-127">可能需要 12 小时才能反映数据。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-127">It can take up to 12 hours before the data is reflected.</span></span>

## <a name="supported-scenarios"></a><span data-ttu-id="dd2bd-128">支持的方案</span><span class="sxs-lookup"><span data-stu-id="dd2bd-128">Supported scenarios</span></span>
<span data-ttu-id="dd2bd-129">Ring0 Preview 期间支持以下方案。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-129">The following scenarios are supported during Ring0 Preview.</span></span> 

### <a name="firewall-reporting-in-security-center"></a><span data-ttu-id="dd2bd-130">安全中心中的防火墙报告</span><span class="sxs-lookup"><span data-stu-id="dd2bd-130">Firewall reporting in security center</span></span>

<span data-ttu-id="dd2bd-131">以下是防火墙报告页面的一些示例。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-131">Here is a couple of examples of the firewall report pages.</span></span> <span data-ttu-id="dd2bd-132">您将在此处找到入站、出站和应用程序活动的摘要。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-132">Here you will find a summary of inbound, outbound, and application activity.</span></span> <span data-ttu-id="dd2bd-133">可以通过访问 直接访问此页面 https://security.microsoft.com/firewall 。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-133">You can access this page directly by going to https://security.microsoft.com/firewall.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd2bd-134">![主机防火墙报告页面](\images\host-firewall-reporting-page.png)</span><span class="sxs-lookup"><span data-stu-id="dd2bd-134">![Host firewall reporting page](\images\host-firewall-reporting-page.png)</span></span>

<span data-ttu-id="dd2bd-135">也可以访问这些报告，方式为访问位于"防火墙阻止的入站连接 (底部的) 报告安全报告  >    >  **设备**"部分。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-135">These reports can also be accessed by going to **Reports** > **Security Report** > **Devices** (section) located at the bottom of the **Firewall Blocked Inbound Connections** card.</span></span>

### <a name="from-computers-with-a-blocked-connection-to-device"></a><span data-ttu-id="dd2bd-136">从"连接被阻止的计算机"到设备</span><span class="sxs-lookup"><span data-stu-id="dd2bd-136">From "Computers with a blocked connection" to device</span></span>

<span data-ttu-id="dd2bd-137">卡片支持交互式对象。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-137">Cards support interactive objects.</span></span> <span data-ttu-id="dd2bd-138">可以通过单击设备名称（将在新选项卡中启动）来深入了解设备的活动，并直接进入"设备 https://securitycenter.microsoft.com **时间线** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-138">You can drill into the activity of a device by clicking on the device name, which will launch https://securitycenter.microsoft.com in a new tab, and take you directly to the **Device Timeline** tab.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd2bd-139">![连接被阻止的计算机](\images\firewall-reporting-blocked-connection.png)</span><span class="sxs-lookup"><span data-stu-id="dd2bd-139">![Computers with a blocked connection](\images\firewall-reporting-blocked-connection.png)</span></span>

<span data-ttu-id="dd2bd-140">你现在可以选择时间线 **选项卡** ，这将提供与该设备关联的事件列表。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-140">You can now select the **Timeline** tab, which will give you a list of events associated with that device.</span></span> 

<span data-ttu-id="dd2bd-141">单击 **查看窗格右上角** 的"筛选器"按钮后，选择您想要的事件类型。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-141">After clicking on the **Filters** button on the upper right-hand corner of the viewing pane, select the type of event you want.</span></span> <span data-ttu-id="dd2bd-142">在这种情况下，请选择 **"防火墙事件"，** 窗格将筛选为"防火墙事件"。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-142">In this case, select **Firewall events** and the pane will be filtered to Firewall events.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd2bd-143">!["筛选器"按钮](\images\firewall-reporting-filters-button.png)</span><span class="sxs-lookup"><span data-stu-id="dd2bd-143">![Filters button](\images\firewall-reporting-filters-button.png)</span></span>

### <a name="drill-into-advanced-hunting-preview-refresh"></a><span data-ttu-id="dd2bd-144">深入了解高级搜寻 (预览刷新) </span><span class="sxs-lookup"><span data-stu-id="dd2bd-144">Drill into advanced hunting (preview refresh)</span></span>

<span data-ttu-id="dd2bd-145">防火墙报告支持通过单击"打开高级搜寻"按钮直接从卡钻取到高级 **搜寻**。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-145">Firewall reports support drilling from the card directly into **Advanced Hunting** by clicking the **Open Advanced hunting** button.</span></span> <span data-ttu-id="dd2bd-146">查询将预填充。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-146">The query will be pre-populated.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd2bd-147">![打开高级搜寻按钮](\images\firewall-reporting-advanced-hunting.png)</span><span class="sxs-lookup"><span data-stu-id="dd2bd-147">![Open Advanced hunting button](\images\firewall-reporting-advanced-hunting.png)</span></span>

<span data-ttu-id="dd2bd-148">现在可以执行查询，并且可以浏览过去 30 天内的所有其他相关防火墙事件。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-148">The query can now be executed, and all related Firewall events from the last 30 days can be explored.</span></span> 

<span data-ttu-id="dd2bd-149">对于其他报告或自定义更改，可以将查询导出到Power BI进一步分析。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-149">For additional reporting, or custom changes, the query can be exported into Power BI for further analysis.</span></span> <span data-ttu-id="dd2bd-150">通过下载自定义报告脚本以使用自定义报告[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)脚本监视自定义报告活动，Windows Defender 防火墙实现Power BI。</span><span class="sxs-lookup"><span data-stu-id="dd2bd-150">Custom reporting can be facilitated by downloading the [Custom Reporting script](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) to monitor the Windows Defender Firewall activities using Power BI.</span></span> 

 