---
title: 将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用
f1.keywords:
- NOCSH
keywords: 集成， Microsoft Defender， Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 一起，获取有关针对你的设备和电子邮件内容的威胁的更多详细信息。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904076"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="8ebc9-104">将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用</span><span class="sxs-lookup"><span data-stu-id="8ebc9-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8ebc9-105">[Microsoft Defender for Office 365](defender-for-office-365.md)可以配置为与[Microsoft Defender for Endpoint 一起运行](/windows/security/threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="8ebc9-106">将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 可帮助你的安全操作团队监视用户设备存在风险并快速采取措施。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="8ebc9-107">例如，启用集成后，安全运营团队将能够看到受检测到的电子邮件潜在影响的设备，以及 Microsoft Defender for Endpoint 中为这些设备生成的最近警报数。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8ebc9-108">下图描述了启用 Microsoft Defender  for Endpoint 集成后"设备"选项卡的外观：</span><span class="sxs-lookup"><span data-stu-id="8ebc9-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![启用 Microsoft Defender for Endpoint 后，你可以看到具有警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="8ebc9-110">在此例中，可以看到检测到的电子邮件的收件人有四个设备，一个设备具有警报。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="8ebc9-111">单击设备的链接将在以前Microsoft 365 [Defender](../defender-endpoint/microsoft-defender-security-center.md) (中打开Microsoft Defender 安全中心) 。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="8ebc9-112">Microsoft 365 Defender 门户将替换Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="8ebc9-113">请参阅[Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="8ebc9-114">要求</span><span class="sxs-lookup"><span data-stu-id="8ebc9-114">Requirements</span></span>

- <span data-ttu-id="8ebc9-115">你的组织必须具有 Microsoft Defender for Office 365 (或 Office 365 E5) 和 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="8ebc9-116">您必须是全局管理员或具有安全管理员角色 (例如安全管理员) 分配Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="8ebc9-117"> (请参阅 [安全与合规中心&中的权限](permissions-in-the-security-and-compliance-center.md)) </span><span class="sxs-lookup"><span data-stu-id="8ebc9-117">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="8ebc9-118">你必须有权访问 Explorer ([或实时检测) 。 ](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="8ebc9-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="8ebc9-119">将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="8ebc9-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8ebc9-120">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成在 Defender for Endpoint 和 Defender for Office 365 中设置。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="8ebc9-121">作为全局管理员或安全管理员，转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-121">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="8ebc9-122"> (这会将你Office 365安全&中心。) </span><span class="sxs-lookup"><span data-stu-id="8ebc9-122">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="8ebc9-123">在导航窗格中，选择"**威胁管理资源管理器** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="8ebc9-123">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![威胁管理菜单中的资源管理器](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="8ebc9-125">In the upper right corner of the screen， choose **Defender for Endpoint 设置 (MDE 设置)**.</span><span class="sxs-lookup"><span data-stu-id="8ebc9-125">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="8ebc9-126">在 Microsoft Defender for Endpoint 连接对话框中 **，连接 Microsoft Defender for Endpoint。**</span><span class="sxs-lookup"><span data-stu-id="8ebc9-126">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender for Endpoint 连接](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="8ebc9-128">转到 Defender Microsoft 365门户 [https://security.microsoft.com](https://security.microsoft.com) (。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-128">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="8ebc9-129">在导航栏中，选择 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="8ebc9-129">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="8ebc9-130">然后，在"常规 **"** 下，选择 **"高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="8ebc9-130">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="8ebc9-131">向下滚动到 **Office 365智能连接，** 然后打开该连接。</span><span class="sxs-lookup"><span data-stu-id="8ebc9-131">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365威胁情报连接](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="8ebc9-133">相关文章</span><span class="sxs-lookup"><span data-stu-id="8ebc9-133">Related articles</span></span>

[<span data-ttu-id="8ebc9-134">威胁调查和响应功能在Office 365</span><span class="sxs-lookup"><span data-stu-id="8ebc9-134">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="8ebc9-135">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="8ebc9-135">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="8ebc9-136">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ebc9-136">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
