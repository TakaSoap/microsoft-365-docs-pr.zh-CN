---
title: 网络钓鱼电子邮件攻击的示例
description: 逐步完成网络钓鱼攻击的示例分析。
keywords: 事件, 警报, 调查, 关联, 攻击, 计算机, 设备, 用户, 标识, 标识, 邮箱, 电子邮件, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a2c73ce5e1c3060d88572f4fa7afe63e193f46
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299984"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="c29cd-104">网络钓鱼电子邮件攻击的示例</span><span class="sxs-lookup"><span data-stu-id="c29cd-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c29cd-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="c29cd-105">**Applies to:**</span></span>
- <span data-ttu-id="c29cd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c29cd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c29cd-107">Microsoft 365Defender 可以帮助检测通过电子邮件传递的恶意附件。</span><span class="sxs-lookup"><span data-stu-id="c29cd-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="c29cd-108">由于[Office 365](https://protection.office.com/)安全与合规中心与 Microsoft 365 Defender 集成，因此安全分析师可以了解来自 Office 365 的威胁，例如通过电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="c29cd-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="c29cd-109">例如，为分析员分配了一个多阶段事件。</span><span class="sxs-lookup"><span data-stu-id="c29cd-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="多阶段事件的示例"::: 

<span data-ttu-id="c29cd-111">在 **事件的"警报**"选项卡中，将显示来自 Defender 的Office 365和Microsoft Cloud App Security警报。</span><span class="sxs-lookup"><span data-stu-id="c29cd-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="c29cd-112">分析员可以通过选择电子邮件Office 365深入了解 Defender for Office 365 警报。</span><span class="sxs-lookup"><span data-stu-id="c29cd-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="c29cd-113">警报的详细信息显示在侧窗格中。</span><span class="sxs-lookup"><span data-stu-id="c29cd-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="电子邮件警报示例":::
 
<span data-ttu-id="c29cd-115">通过进一步向下滚动，将显示更多信息，显示受到影响的恶意文件和用户。</span><span class="sxs-lookup"><span data-stu-id="c29cd-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="电子邮件警报的用户和文件影响示例":::
  
<span data-ttu-id="c29cd-117">选择 **"打开** 警报"页，可让你查看特定警报，通过选择链接可更详细地查看各种信息。</span><span class="sxs-lookup"><span data-stu-id="c29cd-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="c29cd-118">通过向面板底部选择"在 **资源管理器** 中查看邮件"可以查看实际电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c29cd-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="警报详细信息示例"::: 

<span data-ttu-id="c29cd-120">这会将分析师打开"威胁管理"页，其中显示电子邮件"主题、收件人、发件人和其他信息"。</span><span class="sxs-lookup"><span data-stu-id="c29cd-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="c29cd-121">**"特殊\*\*\*\*操作"下的** ZAP 告诉分析师"零时差自动清除"功能已实现。</span><span class="sxs-lookup"><span data-stu-id="c29cd-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="c29cd-122">ZAP 自动检测并删除整个组织邮箱中的恶意邮件和垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c29cd-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="c29cd-123">有关详细信息，请参阅 EXCHANGE ONLINE 中的零[时差自动清除 (ZAP) 。](../office-365-security/zero-hour-auto-purge.md)</span><span class="sxs-lookup"><span data-stu-id="c29cd-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="c29cd-124">可以通过选择操作 来对特定邮件执行其他 **操作**。</span><span class="sxs-lookup"><span data-stu-id="c29cd-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="可以针对电子邮件执行的其他操作的示例"::: 

## <a name="next-step"></a><span data-ttu-id="c29cd-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c29cd-126">Next step</span></span>

<span data-ttu-id="c29cd-127">请参阅 [基于身份的攻击调查](first-incident-path-identity.md) 路径。</span><span class="sxs-lookup"><span data-stu-id="c29cd-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="c29cd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c29cd-128">See also</span></span>

- [<span data-ttu-id="c29cd-129">事件概述</span><span class="sxs-lookup"><span data-stu-id="c29cd-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c29cd-130">调查事件</span><span class="sxs-lookup"><span data-stu-id="c29cd-130">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="c29cd-131">管理事件</span><span class="sxs-lookup"><span data-stu-id="c29cd-131">Manage incidents</span></span>](manage-incidents.md)
