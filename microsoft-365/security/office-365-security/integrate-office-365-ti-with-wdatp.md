---
title: 将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 一同使用
f1.keywords:
- NOCSH
keywords: integrate， Microsoft Defender， ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 一起用于获取有关针对设备和电子邮件内容的威胁的更多详细信息。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166083"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="bbbf8-104">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 一同使用</span><span class="sxs-lookup"><span data-stu-id="bbbf8-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bbbf8-105">[Microsoft Defender for Office 365](office-365-atp.md) 可以配置为与 [Microsoft Defender for Endpoint 一起工作](https://docs.microsoft.com/windows/security/threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="bbbf8-106">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成可帮助你的安全操作团队在用户设备存在风险时监视并快速采取措施。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="bbbf8-107">例如，启用集成后，安全运营团队将能够查看受检测到的电子邮件潜在影响的设备，以及 Microsoft Defender for Endpoint 中为这些设备生成的最近警报数。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="bbbf8-108">下图描述了启用 Microsoft Defender  for Endpoint 集成后"设备"选项卡的外观：</span><span class="sxs-lookup"><span data-stu-id="bbbf8-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![启用 Microsoft Defender for Endpoint 后，你可以看到具有警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="bbbf8-110">在此例中，可以看到检测到的电子邮件的收件人具有四台设备，一个设备具有警报。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="bbbf8-111">单击设备的链接将在 Microsoft Defender 安全中心 <https://securitycenter.windows.com> () 。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="bbbf8-112">**[了解有关 Microsoft Defender 安全](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** 中心 (也称为 Microsoft Defender for Endpoint 门户。) </span><span class="sxs-lookup"><span data-stu-id="bbbf8-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="bbbf8-113">要求</span><span class="sxs-lookup"><span data-stu-id="bbbf8-113">Requirements</span></span>

- <span data-ttu-id="bbbf8-114">你的组织必须具有 Microsoft Defender for Office 365 (Office 365 E5) 和 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="bbbf8-115">您必须是全局管理员或具有安全管理员角色 (例如安全) 安全与合规中心& [管理员](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="bbbf8-116"> (安全[与合规中心&权限) ](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="bbbf8-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="bbbf8-117">你必须在安全与 ([和 ](threat-explorer.md) Microsoft Defender 安全中心) 资源管理器&或实时检测。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="bbbf8-118">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="bbbf8-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="bbbf8-119">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成是通过使用安全与合规中心& Microsoft Defender 安全中心设置的。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="bbbf8-120">作为全局管理员或安全管理员，请转到 <https://protection.office.com> 并登录。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="bbbf8-121"> (这会将你带至 Office 365 安全&合规中心.) </span><span class="sxs-lookup"><span data-stu-id="bbbf8-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="bbbf8-122">在导航窗格中，选择 **"威胁管理** \> **资源管理器"。**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   !["威胁管理"菜单中的资源管理器](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="bbbf8-124">在屏幕右上角，选择"适用于 **MDE** 设置" (的 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="bbbf8-125">在 Microsoft Defender for Endpoint 连接对话框中，打开 **"连接到适用于终结点的 Microsoft Defender"。**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender for Endpoint 连接](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="bbbf8-127">转到 Microsoft Defender 安全中心 <https://securitycenter.windows.com> () 。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="bbbf8-128">在导航栏中，选择"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="bbbf8-129">然后，在 **"常规"** 下，**选择"高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="bbbf8-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="bbbf8-130">向下滚动到 **Office 365 威胁智能连接**，然后打开该连接。</span><span class="sxs-lookup"><span data-stu-id="bbbf8-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 威胁情报连接](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="bbbf8-132">相关文章</span><span class="sxs-lookup"><span data-stu-id="bbbf8-132">Related articles</span></span>

[<span data-ttu-id="bbbf8-133">Office 365 中的威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="bbbf8-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="bbbf8-134">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="bbbf8-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="bbbf8-135">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbbf8-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
