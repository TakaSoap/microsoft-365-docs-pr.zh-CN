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
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083375"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="99edb-104">将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 一起使用</span><span class="sxs-lookup"><span data-stu-id="99edb-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="99edb-105">[Microsoft Defender for Office 365](defender-for-office-365.md)可以配置为与[Microsoft Defender for Endpoint 一起运行](/windows/security/threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="99edb-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="99edb-106">将 Microsoft Defender for Office 365 Microsoft Defender for Endpoint 可帮助你的安全操作团队监视用户设备存在风险并快速采取措施。</span><span class="sxs-lookup"><span data-stu-id="99edb-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="99edb-107">例如，启用集成后，安全运营团队将能够看到受检测到的电子邮件潜在影响的设备，以及 Microsoft Defender for Endpoint 中为这些设备生成的最近警报数。</span><span class="sxs-lookup"><span data-stu-id="99edb-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="99edb-108">下图描述了启用 Microsoft Defender  for Endpoint 集成后"设备"选项卡的外观：</span><span class="sxs-lookup"><span data-stu-id="99edb-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![启用 Microsoft Defender for Endpoint 后，你可以看到具有警报的设备列表。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="99edb-110">在此例中，可以看到检测到的电子邮件的收件人有四个设备，一个设备具有警报。</span><span class="sxs-lookup"><span data-stu-id="99edb-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="99edb-111">单击设备的链接将在之前 Microsoft Defender[](../defender-endpoint/microsoft-defender-security-center.md)安全Microsoft 365 Defender门户 (打开其) 。</span><span class="sxs-lookup"><span data-stu-id="99edb-111">Clicking the link for a device opens its page in [the Microsoft 365 Defender portal](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender security center).</span></span>

> [!TIP]
> <span data-ttu-id="99edb-112">Microsoft 365 Defender门户将替换Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="99edb-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="99edb-113">请参阅[Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="99edb-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="99edb-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="99edb-114">Requirements</span></span>

- <span data-ttu-id="99edb-115">你的组织必须具有 Microsoft Defender for Office 365 (或 Office 365 E5) 和 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="99edb-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="99edb-116">您必须是全局管理员或具有安全管理员角色 (例如安全管理员) 分配Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="99edb-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="99edb-117">有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="99edb-117">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="99edb-118">你必须有权访问 Explorer ([或实时检测) 。 ](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="99edb-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="99edb-119">将 Microsoft Defender for Office 365与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="99edb-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="99edb-120">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成在 Defender for Endpoint 和 Defender for Office 365 中设置。</span><span class="sxs-lookup"><span data-stu-id="99edb-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="99edb-121">作为全局管理员或安全管理员，打开 Microsoft 365 Defender 门户 () 转到"电子邮件& <https://security.microsoft.com> **协作** \> **资源管理器"。**</span><span class="sxs-lookup"><span data-stu-id="99edb-121">As a global administrator or a security administrator, open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Email & collaboration** \> **Explorer**.</span></span> <span data-ttu-id="99edb-122">若要直接转到资源管理器 **页面** ，请使用 <https://security.microsoft.com/threatexplorer> 。</span><span class="sxs-lookup"><span data-stu-id="99edb-122">To go directly to the **Explorer** page, use <https://security.microsoft.com/threatexplorer>.</span></span>

2. <span data-ttu-id="99edb-123">在 **"资源管理器**"页上的屏幕右上角，单击 **"MDE 设置"。**</span><span class="sxs-lookup"><span data-stu-id="99edb-123">On the **Explorer** page, in the upper right corner of the screen, click **MDE Settings**.</span></span>

3. <span data-ttu-id="99edb-124">在出现的 **Microsoft Defender for Endpoint** 连接飞出中，在 连接 上打开"适用于终结点的 Microsoft **Defender** (切换") ![ ](../../media/scc-toggle-on.png) 然后单击关闭图标"关闭 ![ ](../../media/m365-cc-sc-close-icon.png) **"。**</span><span class="sxs-lookup"><span data-stu-id="99edb-124">In the **Microsoft Defender for Endpoint connection** flyout that appears, turn on **Connect to Microsoft Defender for Endpoint** (![Toggle on](../../media/scc-toggle-on.png)) and then click ![Close icon](../../media/m365-cc-sc-close-icon.png) **Close**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 连接":::

4. <span data-ttu-id="99edb-126">返回到导航窗格中，选择 **"设置"。**</span><span class="sxs-lookup"><span data-stu-id="99edb-126">Back in the navigation pane, choose **Settings**.</span></span> <span data-ttu-id="99edb-127">在 **"设置"** 页上，选择 **"终结点"**</span><span class="sxs-lookup"><span data-stu-id="99edb-127">On the **Settings** page, choose **Endpoints**</span></span>

5. <span data-ttu-id="99edb-128">在打开 **的"终结点**"页上，选择"**高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="99edb-128">On the **Endpoints** page that opens, choose **Advanced features**.</span></span>

6. <span data-ttu-id="99edb-129">向下滚动到 **"Office 365** 智能"连接，然后打开" (![ 上的 ](../../media/scc-toggle-on.png) ") "。</span><span class="sxs-lookup"><span data-stu-id="99edb-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn it on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="99edb-130">完成后，单击保存 **首选项**。</span><span class="sxs-lookup"><span data-stu-id="99edb-130">When you're finished, click **Save preferences**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="99edb-131">相关文章</span><span class="sxs-lookup"><span data-stu-id="99edb-131">Related articles</span></span>

[<span data-ttu-id="99edb-132">威胁调查和响应功能在Office 365</span><span class="sxs-lookup"><span data-stu-id="99edb-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="99edb-133">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="99edb-133">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="99edb-134">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99edb-134">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
