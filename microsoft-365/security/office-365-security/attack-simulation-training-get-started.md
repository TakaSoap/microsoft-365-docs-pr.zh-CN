---
title: 开始使用攻击模拟培训
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何使用攻击模拟培训在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 组织中运行模拟网络钓鱼和密码攻击。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad86f77399cfa2a3a780d3fed7e483e3c11bc08d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082896"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="0c20f-103">开始使用攻击模拟培训</span><span class="sxs-lookup"><span data-stu-id="0c20f-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0c20f-104">**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="0c20f-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="0c20f-105">如果你的组织拥有 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2（包括[](office-365-ti.md)威胁调查和响应功能）。可以使用 Microsoft 365 Defender 门户中的攻击模拟培训在组织中运行真实的攻击方案。</span><span class="sxs-lookup"><span data-stu-id="0c20f-105">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="0c20f-106">这些模拟攻击可以帮助你在真实攻击影响你的最后一线之前识别和查找易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="0c20f-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="0c20f-107">阅读本文可了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="0c20f-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="0c20f-108">攻击模拟培训取代了 Microsoft Defender for Office 365 攻击模拟器中所述的旧攻击[模拟器 v1 体验](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="0c20f-108">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0c20f-109">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0c20f-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0c20f-110">若要打开 Microsoft 365 Defender 门户，请转到 <https://security.microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="0c20f-110">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="0c20f-111">攻击模拟培训位于电子邮件和 **协作** \> **攻击模拟培训中**。</span><span class="sxs-lookup"><span data-stu-id="0c20f-111">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="0c20f-112">若要直接转到攻击模拟培训，请打开 <https://security.microsoft.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="0c20f-112">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="0c20f-113">有关跨不同订阅提供攻击模拟培训Microsoft 365，请参阅 Microsoft Defender for Office 365 [service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="0c20f-113">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="0c20f-114">您需在 Microsoft 365 Defender 门户或 Azure Active Directory 分配权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="0c20f-114">You need to be assigned permissions in the Microsoft 365 Defender portal or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="0c20f-115">具体来说，你需要是组织管理、安全 **管理员** 或以下角色之一的成员： </span><span class="sxs-lookup"><span data-stu-id="0c20f-115">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="0c20f-116">**攻击模拟器管理员**：创建和管理攻击模拟活动的所有方面。</span><span class="sxs-lookup"><span data-stu-id="0c20f-116">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="0c20f-117">**攻击模拟器有效负载作者**：创建管理员稍后可以启动的攻击负载。</span><span class="sxs-lookup"><span data-stu-id="0c20f-117">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="0c20f-118">有关详细信息，请参阅管理门户[中的权限Microsoft 365 Defender或](permissions-microsoft-365-security-center.md)[关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="0c20f-118">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="0c20f-119">没有用于攻击模拟培训的相应 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0c20f-119">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="0c20f-120">攻击模拟和培训相关的数据与其他客户数据存储在一起，Microsoft 365服务。</span><span class="sxs-lookup"><span data-stu-id="0c20f-120">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="0c20f-121">有关详细信息，请参阅[Microsoft 365位置](../../enterprise/o365-data-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="0c20f-121">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="0c20f-122">攻击模拟可用于以下区域：NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN 和 EUR。</span><span class="sxs-lookup"><span data-stu-id="0c20f-122">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

- <span data-ttu-id="0c20f-123">自 2021 年 6 月 15 日起，攻击模拟培训在 GCC。</span><span class="sxs-lookup"><span data-stu-id="0c20f-123">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="0c20f-124">如果你的组织拥有 Office 365 G5 GCC 或 Microsoft Defender for Office 365 (计划 2) 政府版，可以使用 Microsoft 365 Defender 门户中的攻击模拟培训在组织中运行实际攻击方案，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="0c20f-124">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="0c20f-125">攻击模拟培训尚未在高GCC DoD 环境中提供。</span><span class="sxs-lookup"><span data-stu-id="0c20f-125">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="0c20f-126">攻击模拟培训将一部分功能作为试用版向 E3 客户提供。</span><span class="sxs-lookup"><span data-stu-id="0c20f-126">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="0c20f-127">试用版包含使用凭据获取有效负载的能力，以及选择"ISA 网络钓鱼"或"批量市场网络钓鱼"培训体验的能力。</span><span class="sxs-lookup"><span data-stu-id="0c20f-127">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="0c20f-128">E3 试用版产品/服务中没有任何其他功能。</span><span class="sxs-lookup"><span data-stu-id="0c20f-128">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="0c20f-129">模拟</span><span class="sxs-lookup"><span data-stu-id="0c20f-129">Simulations</span></span>

<span data-ttu-id="0c20f-130">*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="0c20f-130">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="0c20f-131">*网络钓鱼* 是分类为社交工程的技术子集 _的一部分_。</span><span class="sxs-lookup"><span data-stu-id="0c20f-131">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="0c20f-132">在攻击模拟培训中，提供了多种社交工程技术：</span><span class="sxs-lookup"><span data-stu-id="0c20f-132">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="0c20f-133">**凭据获取**：攻击者向收件人发送包含 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="0c20f-133">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="0c20f-134">当收件人单击 URL 时，他们会被带至一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="0c20f-134">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="0c20f-135">通常，目标页面以表示已知网站为标题，以在用户中建立信任。</span><span class="sxs-lookup"><span data-stu-id="0c20f-135">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="0c20f-136">**恶意软件** 附件：攻击者向收件人发送包含附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="0c20f-136">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="0c20f-137">当收件人打开附件时， (代码，例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步自我编写代码。</span><span class="sxs-lookup"><span data-stu-id="0c20f-137">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="0c20f-138">**附件中的链接**：这是凭据获取的混合。</span><span class="sxs-lookup"><span data-stu-id="0c20f-138">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="0c20f-139">攻击者向收件人发送一封邮件，其中包含附件内的 URL。</span><span class="sxs-lookup"><span data-stu-id="0c20f-139">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="0c20f-140">当收件人打开附件并单击该 URL 时，他们会访问一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="0c20f-140">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="0c20f-141">通常，目标页面以表示已知网站为标题，以在用户中建立信任。</span><span class="sxs-lookup"><span data-stu-id="0c20f-141">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="0c20f-142">**链接到恶意软件**：攻击者向收件人发送一封邮件，其中包含指向已知文件共享网站上附件的链接 (例如，SharePoint Online 或 Dropbox) 。</span><span class="sxs-lookup"><span data-stu-id="0c20f-142">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="0c20f-143">当收件人单击 URL 时，附件将打开并任意代码 (例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步安装代码。</span><span class="sxs-lookup"><span data-stu-id="0c20f-143">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="0c20f-144">**按 URL 驱动器**：攻击者向收件人发送包含 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="0c20f-144">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="0c20f-145">当收件人单击 URL 时，他们会被带至尝试运行后台代码的网站。</span><span class="sxs-lookup"><span data-stu-id="0c20f-145">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="0c20f-146">此后台代码尝试收集有关收件人的信息或在设备上部署任意代码。</span><span class="sxs-lookup"><span data-stu-id="0c20f-146">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="0c20f-147">通常，目标网站是已遭到入侵的已知网站或已知网站的克隆。</span><span class="sxs-lookup"><span data-stu-id="0c20f-147">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="0c20f-148">熟悉网站有助于让用户确信链接可安全单击。</span><span class="sxs-lookup"><span data-stu-id="0c20f-148">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="0c20f-149">此技术也称为水 _洞攻击_。</span><span class="sxs-lookup"><span data-stu-id="0c20f-149">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="0c20f-150">在网络钓鱼活动中使用该 URL 之前，请检查模拟网络钓鱼 URL 在受支持的 Web 浏览器中的可用性。</span><span class="sxs-lookup"><span data-stu-id="0c20f-150">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="0c20f-151">虽然我们与许多 URL 信誉供应商合作以始终允许这些模拟 URL，但我们不会始终具有完全覆盖范围 (例如，Google 保险箱浏览) 。</span><span class="sxs-lookup"><span data-stu-id="0c20f-151">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="0c20f-152">大多数供应商提供的指导允许你始终允许特定 URL (例如 <https://support.google.com/chrome/a/answer/7532419> ，) 。</span><span class="sxs-lookup"><span data-stu-id="0c20f-152">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="0c20f-153">攻击模拟培训使用的 URL 如下列表所述：</span><span class="sxs-lookup"><span data-stu-id="0c20f-153">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="0c20f-154">创建模拟</span><span class="sxs-lookup"><span data-stu-id="0c20f-154">Create a simulation</span></span>

<span data-ttu-id="0c20f-155">有关如何创建和发送新模拟的分步说明，请参阅 [模拟网络钓鱼攻击](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="0c20f-155">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="0c20f-156">创建有效负载</span><span class="sxs-lookup"><span data-stu-id="0c20f-156">Create a payload</span></span>

<span data-ttu-id="0c20f-157">有关如何创建负载以用于模拟的分步说明，请参阅为 [攻击模拟培训创建自定义负载](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="0c20f-157">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="0c20f-158">获取见解</span><span class="sxs-lookup"><span data-stu-id="0c20f-158">Gaining insights</span></span>

<span data-ttu-id="0c20f-159">有关如何通过报告获取见解的分步说明，请参阅通过 [攻击模拟培训获取见解](attack-simulation-training-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="0c20f-159">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0c20f-160">攻击模拟器使用 保险箱 Links in Defender for Office 365 安全跟踪发送给网络钓鱼活动的目标收件人的有效负载邮件中 URL 的单击数据，即使 保险箱 链接策略中已打开"不跟踪用户单击"设置。</span><span class="sxs-lookup"><span data-stu-id="0c20f-160">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
