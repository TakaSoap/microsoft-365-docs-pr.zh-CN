---
title: 将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 一起使用
f1.keywords:
- NOCSH
keywords: 集成、Microsoft Defender、ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 结合使用，以获取有关针对你的设备和电子邮件内容的威胁的更多详细信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f668aa1234509789dacd2b018b94f1bfbc79e2c
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357775"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="3aba9-104">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 一起使用</span><span class="sxs-lookup"><span data-stu-id="3aba9-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3aba9-105">可将[Microsoft defender For Office 365](office-365-atp.md)配置为与[Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)一起使用。</span><span class="sxs-lookup"><span data-stu-id="3aba9-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="3aba9-106">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成可帮助你的安全操作团队监视并快速采取行动（如果用户设备面临风险）。</span><span class="sxs-lookup"><span data-stu-id="3aba9-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="3aba9-107">例如，在启用集成后，安全操作团队将能够查看检测到的电子邮件可能影响的设备，以及在 Microsoft Defender for Endpoint 中为这些设备生成了多少个最近的警报。</span><span class="sxs-lookup"><span data-stu-id="3aba9-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="3aba9-108">下图显示了 " **设备** " 选项卡的外观，并启用了 Microsoft Defender for Endpoint integration：</span><span class="sxs-lookup"><span data-stu-id="3aba9-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![启用 Microsoft Defender for Endpoint 时，你可以看到包含警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="3aba9-110">在此示例中，可以看到检测到的电子邮件的收件人有四台设备，并且有一个警报。</span><span class="sxs-lookup"><span data-stu-id="3aba9-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="3aba9-111">单击设备的链接将在 Microsoft Defender 安全中心 () 中打开其页面 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="3aba9-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="3aba9-112">**[了解有关 Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (也称为 microsoft Defender for Endpoint portal 的详细信息。 ) </span><span class="sxs-lookup"><span data-stu-id="3aba9-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3aba9-113">Requirements</span><span class="sxs-lookup"><span data-stu-id="3aba9-113">Requirements</span></span>

- <span data-ttu-id="3aba9-114">您的组织必须拥有 Microsoft Defender for Office 365 (或 Office 365 E5) 和 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="3aba9-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="3aba9-115">您必须是全局管理员或具有安全管理员角色 (如安全 [ &amp; 合规中心](https://protection.office.com)中分配的安全管理员) 。</span><span class="sxs-lookup"><span data-stu-id="3aba9-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="3aba9-116"> (查看 [安全 &amp; 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)) </span><span class="sxs-lookup"><span data-stu-id="3aba9-116">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="3aba9-117">您必须具有对 [资源管理器 (或实时检测) ](threat-explorer.md) 在安全 & 合规中心和 Microsoft Defender 安全中心中的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3aba9-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="3aba9-118">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="3aba9-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3aba9-119">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 的集成通过使用安全 & 合规中心和 Microsoft Defender 安全中心进行设置。</span><span class="sxs-lookup"><span data-stu-id="3aba9-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="3aba9-120">作为全局管理员或安全管理员，请转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="3aba9-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="3aba9-121"> (此操作将转到 Office 365 安全 & 合规中心。 ) </span><span class="sxs-lookup"><span data-stu-id="3aba9-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="3aba9-122">在导航窗格中，选择 "**威胁管理**  >  **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="3aba9-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="3aba9-123">![威胁管理菜单中的资源管理器](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="3aba9-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="3aba9-124">在屏幕的右上角，选择 " **Defender For Endpoint Settings**"。</span><span class="sxs-lookup"><span data-stu-id="3aba9-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings**.</span></span>
    
4. <span data-ttu-id="3aba9-125">在 "Microsoft Defender for Endpoint connection" 对话框中，启用 " **连接到 Microsoft defender For endpoint**"。</span><span class="sxs-lookup"><span data-stu-id="3aba9-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span><br><span data-ttu-id="3aba9-126">![Microsoft Defender for Endpoint 连接](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="3aba9-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="3aba9-127">请转到 Microsoft Defender 安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 。</span><span class="sxs-lookup"><span data-stu-id="3aba9-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="3aba9-128">在导航栏中，选择 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="3aba9-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="3aba9-129">然后，在 " **常规**" 下，选择 " **高级功能**"。</span><span class="sxs-lookup"><span data-stu-id="3aba9-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="3aba9-130">向下滚动到 " **Office 365 威胁智能连接**"，然后打开连接。</span><span class="sxs-lookup"><span data-stu-id="3aba9-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="3aba9-131">![Office 365 威胁智能连接](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="3aba9-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="3aba9-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="3aba9-132">Related articles</span></span>

[<span data-ttu-id="3aba9-133">Office 365 中的威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="3aba9-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="3aba9-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="3aba9-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="3aba9-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3aba9-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
