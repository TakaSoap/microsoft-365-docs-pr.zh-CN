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
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921344"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="e7e75-103">开始使用攻击模拟培训</span><span class="sxs-lookup"><span data-stu-id="e7e75-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e7e75-104">如果你的组织拥有 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2，其中包括威胁调查和响应功能，可以在 Microsoft 安全中心内使用攻击模拟培训在组织中运行真实的攻击方案。 [](office-365-ti.md)</span><span class="sxs-lookup"><span data-stu-id="e7e75-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="e7e75-105">这些模拟攻击可以帮助你在真实攻击影响你的最后一线之前识别和查找易受攻击的用户。</span><span class="sxs-lookup"><span data-stu-id="e7e75-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="e7e75-106">阅读本文可了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="e7e75-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="e7e75-107">攻击模拟培训取代了 Microsoft [Defender for Office 365](attack-simulator.md)中攻击模拟器中所述的旧攻击模拟器 v1 体验。</span><span class="sxs-lookup"><span data-stu-id="e7e75-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e7e75-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="e7e75-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e7e75-109">若要打开 Microsoft 安全中心，请转到 <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="e7e75-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="e7e75-110">攻击模拟培训位于电子邮件和 **协作** \> **攻击模拟培训中**。</span><span class="sxs-lookup"><span data-stu-id="e7e75-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="e7e75-111">若要直接转到攻击模拟培训，请打开 <https://security.microsoft.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="e7e75-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="e7e75-112">有关不同 Microsoft 365 订阅中攻击模拟培训的可用性详细信息，请参阅 [Microsoft Defender for Office 365 服务说明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="e7e75-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="e7e75-113">您需在安全与合规中心或 Azure Active Directory &分配权限，然后才能执行本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="e7e75-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="e7e75-114">具体来说，你需要是组织管理、安全 **管理员** 或以下角色之一的成员： </span><span class="sxs-lookup"><span data-stu-id="e7e75-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="e7e75-115">**攻击模拟器管理员**：创建和管理攻击模拟活动的所有方面。</span><span class="sxs-lookup"><span data-stu-id="e7e75-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="e7e75-116">**攻击模拟器有效负载作者**：创建管理员稍后可以启动的攻击负载。</span><span class="sxs-lookup"><span data-stu-id="e7e75-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="e7e75-117">有关详细信息，请参阅安全[与合规中心&权限或](permissions-in-the-security-and-compliance-center.md)[关于管理员角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e75-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="e7e75-118">没有用于攻击模拟培训的相应 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7e75-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="e7e75-119">攻击模拟和培训相关的数据与 Microsoft 365 服务的其他客户数据存储在一起。</span><span class="sxs-lookup"><span data-stu-id="e7e75-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="e7e75-120">有关详细信息，请参阅 [Microsoft 365 数据位置](../../enterprise/o365-data-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e75-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="e7e75-121">攻击模拟可用于以下区域：NAM、APC、EUR、IND、CAN、AUS、FRA、GBR、JPN 和 EUR。</span><span class="sxs-lookup"><span data-stu-id="e7e75-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="e7e75-122">模拟</span><span class="sxs-lookup"><span data-stu-id="e7e75-122">Simulations</span></span>

<span data-ttu-id="e7e75-123">*网络钓鱼* 是电子邮件攻击的一个通用术语，它尝试窃取看起来来自合法或受信任的发件人的邮件中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e7e75-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="e7e75-124">*网络钓鱼* 是分类为社交工程的技术子集 _的一部分_。</span><span class="sxs-lookup"><span data-stu-id="e7e75-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="e7e75-125">在攻击模拟培训中，提供了多种社交工程技术：</span><span class="sxs-lookup"><span data-stu-id="e7e75-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="e7e75-126">**凭据获取**：攻击者向收件人发送包含 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="e7e75-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="e7e75-127">当收件人单击 URL 时，他们会被带至一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e7e75-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="e7e75-128">通常，目标页面以表示已知网站为标题，以在用户中建立信任。</span><span class="sxs-lookup"><span data-stu-id="e7e75-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="e7e75-129">**恶意软件** 附件：攻击者向收件人发送包含附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="e7e75-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="e7e75-130">当收件人打开附件时， (代码，例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步自我编写代码。</span><span class="sxs-lookup"><span data-stu-id="e7e75-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="e7e75-131">**附件中的链接**：这是凭据获取的混合。</span><span class="sxs-lookup"><span data-stu-id="e7e75-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="e7e75-132">攻击者向收件人发送一封邮件，其中包含附件内的 URL。</span><span class="sxs-lookup"><span data-stu-id="e7e75-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="e7e75-133">当收件人打开附件并单击该 URL 时，他们会访问一个网站，该网站通常显示一个对话框，要求用户输入用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e7e75-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="e7e75-134">通常，目标页面以表示已知网站为标题，以在用户中建立信任。</span><span class="sxs-lookup"><span data-stu-id="e7e75-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="e7e75-135">链接到 **恶意软件**：攻击者向收件人发送一封邮件，其中包含指向已知文件共享网站 (例如，SharePoint Online 或 Dropbox) 的附件的链接。</span><span class="sxs-lookup"><span data-stu-id="e7e75-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="e7e75-136">当收件人单击 URL 时，附件将打开并任意代码 (例如，宏) 在用户设备上运行，以帮助攻击者安装其他代码或进一步安装代码。</span><span class="sxs-lookup"><span data-stu-id="e7e75-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="e7e75-137">**按 URL 驱动器**：攻击者向收件人发送包含 URL 的邮件。</span><span class="sxs-lookup"><span data-stu-id="e7e75-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="e7e75-138">当收件人单击 URL 时，他们会被带至尝试运行后台代码的网站。</span><span class="sxs-lookup"><span data-stu-id="e7e75-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="e7e75-139">此后台代码尝试收集有关收件人的信息或在设备上部署任意代码。</span><span class="sxs-lookup"><span data-stu-id="e7e75-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="e7e75-140">通常，目标网站是已遭到入侵的已知网站或已知网站的克隆。</span><span class="sxs-lookup"><span data-stu-id="e7e75-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="e7e75-141">熟悉网站有助于让用户确信链接可安全单击。</span><span class="sxs-lookup"><span data-stu-id="e7e75-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="e7e75-142">此技术也称为水 _洞攻击_。</span><span class="sxs-lookup"><span data-stu-id="e7e75-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="e7e75-143">在网络钓鱼活动中使用该 URL 之前，请检查模拟网络钓鱼 URL 在受支持的 Web 浏览器中的可用性。</span><span class="sxs-lookup"><span data-stu-id="e7e75-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="e7e75-144">虽然我们与许多 URL 信誉供应商合作，始终允许这些模拟 URL，但我们并不总是具有完全覆盖 (例如，Google 安全浏览) 。</span><span class="sxs-lookup"><span data-stu-id="e7e75-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="e7e75-145">大多数供应商提供的指导允许你始终允许特定 URL (例如 <https://support.google.com/chrome/a/answer/7532419> ，) 。</span><span class="sxs-lookup"><span data-stu-id="e7e75-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="e7e75-146">攻击模拟培训使用的 URL 如下列表所述：</span><span class="sxs-lookup"><span data-stu-id="e7e75-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="e7e75-147">创建模拟</span><span class="sxs-lookup"><span data-stu-id="e7e75-147">Create a simulation</span></span>

<span data-ttu-id="e7e75-148">有关如何创建和发送新模拟的分步说明，请参阅 [模拟网络钓鱼攻击](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e75-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="e7e75-149">创建有效负载</span><span class="sxs-lookup"><span data-stu-id="e7e75-149">Create a payload</span></span>

<span data-ttu-id="e7e75-150">有关如何创建负载以用于模拟的分步说明，请参阅为 [攻击模拟培训创建自定义负载](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e75-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="e7e75-151">获取见解</span><span class="sxs-lookup"><span data-stu-id="e7e75-151">Gaining insights</span></span>

<span data-ttu-id="e7e75-152">有关如何通过报告获取见解的分步说明，请参阅通过 [攻击模拟培训获取见解](attack-simulation-training-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="e7e75-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7e75-153">攻击模拟器使用 Defender for Office 365 中的安全链接安全跟踪发送给网络钓鱼活动的目标收件人的有效负载消息中 URL 的单击数据，即使安全链接策略中的"不跟踪用户单击"设置已打开。</span><span class="sxs-lookup"><span data-stu-id="e7e75-153">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>