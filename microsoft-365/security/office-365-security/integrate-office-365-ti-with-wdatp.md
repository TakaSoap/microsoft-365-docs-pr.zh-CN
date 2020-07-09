---
title: 将 Office 365 ATP 与 Microsoft Defender ATP 集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 将 Office 365 高级威胁防护与 Microsoft Defender 高级威胁防护集成，以查看更详细的威胁管理信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086702"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="cb117-103">将 Office 365 高级威胁防护与 Microsoft Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="cb117-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="cb117-104">可以配置[office 365 高级威胁防护](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)（OFFICE 365 ATP），以使用[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection)（Microsoft defender ATP）。</span><span class="sxs-lookup"><span data-stu-id="cb117-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="cb117-105">将 Office 365 ATP 与 Microsoft Defender ATP 集成可帮助你的安全操作团队监控并快速采取行动（如果用户的设备存在风险）。</span><span class="sxs-lookup"><span data-stu-id="cb117-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="cb117-106">例如，在启用集成后，安全操作团队将能够查看检测到的电子邮件可能影响的设备，以及这些设备在 Microsoft Defender ATP 中所具有的最近通知数。</span><span class="sxs-lookup"><span data-stu-id="cb117-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="cb117-107">下图描述了 "**设备**" 选项卡的外观，如已启用 MICROSOFT Defender ATP 集成：</span><span class="sxs-lookup"><span data-stu-id="cb117-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![启用 Microsoft Defender ATP 后，你可以看到包含警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="cb117-109">在此示例中，可以看到检测到的电子邮件的收件人有四台设备，并且有一个警报。</span><span class="sxs-lookup"><span data-stu-id="cb117-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="cb117-110">单击设备的链接将在 Microsoft Defender 安全中心（）中打开其页面 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="cb117-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="cb117-111">**[了解有关 Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)**（也称为 MICROSOFT defender ATP 门户）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cb117-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="cb117-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="cb117-112">Requirements</span></span>

- <span data-ttu-id="cb117-113">您的组织必须具有 Office 365 ATP 计划2（或 Office 365 E5）和 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="cb117-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="cb117-114">您必须是全局管理员或具有安全[ &amp; 合规性中心](https://protection.office.com)中分配的安全管理员角色（例如安全管理员）。</span><span class="sxs-lookup"><span data-stu-id="cb117-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="cb117-115">（请参阅[安全 &amp; 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)）</span><span class="sxs-lookup"><span data-stu-id="cb117-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="cb117-116">您必须有权访问安全 & 合规性中心和 Microsoft Defender 安全中心中的[资源管理器（或实时检测）](threat-explorer.md) 。</span><span class="sxs-lookup"><span data-stu-id="cb117-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="cb117-117">将 Office 365 ATP 与 Microsoft Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="cb117-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="cb117-118">通过使用安全 & 合规性中心和 Microsoft Defender 安全中心，将 Office 365 ATP 与 Microsoft Defender ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="cb117-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="cb117-119">作为全局管理员或安全管理员，请转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="cb117-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="cb117-120">（这会将您带到 Office 365 安全 & 合规中心。）</span><span class="sxs-lookup"><span data-stu-id="cb117-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="cb117-121">在导航窗格中，选择 "**威胁管理**  >  **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="cb117-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="cb117-122">![威胁管理菜单中的资源管理器](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="cb117-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="cb117-123">在屏幕的右上角，选择 " **WDATP 设置**"。</span><span class="sxs-lookup"><span data-stu-id="cb117-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="cb117-124">在 "Microsoft Defender ATP 连接" 对话框中，启用 "**连接到 WINDOWS ATP**"。</span><span class="sxs-lookup"><span data-stu-id="cb117-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="cb117-125">![Microsoft Defender ATP 连接](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="cb117-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="cb117-126">转到 Microsoft Defender 安全中心（ [https://securitycenter.windows.com](https://securitycenter.windows.com) ）。</span><span class="sxs-lookup"><span data-stu-id="cb117-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="cb117-127">在导航栏中，选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="cb117-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="cb117-128">然后，在 "**常规**" 下，选择 "**高级功能**"。</span><span class="sxs-lookup"><span data-stu-id="cb117-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="cb117-129">向下滚动到 " **Office 365 威胁智能连接**"，然后打开连接。</span><span class="sxs-lookup"><span data-stu-id="cb117-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="cb117-130">![Office 365 威胁智能连接](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="cb117-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="cb117-131">相关文章</span><span class="sxs-lookup"><span data-stu-id="cb117-131">Related articles</span></span>

[<span data-ttu-id="cb117-132">Office 365 中的威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="cb117-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="cb117-133">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="cb117-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="cb117-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="cb117-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
