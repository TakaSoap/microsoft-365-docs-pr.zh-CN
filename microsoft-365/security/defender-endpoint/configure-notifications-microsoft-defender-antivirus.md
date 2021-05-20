---
title: 配置Microsoft Defender 防病毒通知
description: 了解如何在终结点上配置和自定义标准Microsoft Defender 防病毒通知。
keywords: 通知， defender， 防病毒， 终结点， 管理， 管理员
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572341"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="bb927-104">配置终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="bb927-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="bb927-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="bb927-105">**Applies to:**</span></span>

- [<span data-ttu-id="bb927-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bb927-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bb927-107">在Windows 10中，有关恶意软件检测和修正的应用程序通知更加可靠、一致且简洁。</span><span class="sxs-lookup"><span data-stu-id="bb927-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="bb927-108">完成手动触发和计划的扫描并检测到威胁后，终结点上会显示通知。</span><span class="sxs-lookup"><span data-stu-id="bb927-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="bb927-109">这些通知还会显示在 **通知中心** 中，并且扫描和威胁检测的摘要会定期显示。</span><span class="sxs-lookup"><span data-stu-id="bb927-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="bb927-110">还可以配置标准通知在终结点上的显示方式，例如重启通知或检测到并修正威胁时的通知。</span><span class="sxs-lookup"><span data-stu-id="bb927-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="bb927-111">配置终结点上显示的其他通知</span><span class="sxs-lookup"><span data-stu-id="bb927-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="bb927-112">可以在应用和组策略中配置其他通知的显示，如Windows 安全中心[威胁](microsoft-defender-security-center-antivirus.md)检测摘要。</span><span class="sxs-lookup"><span data-stu-id="bb927-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="bb927-113">在 Windows 10 版本 1607 中，该功能称为增强型通知，可以在 Windows 设置  >  **Update & security Windows Defender**  >  **下配置**。</span><span class="sxs-lookup"><span data-stu-id="bb927-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="bb927-114">在所有版本的组策略设置中Windows 10，它称为增强 **型通知**。</span><span class="sxs-lookup"><span data-stu-id="bb927-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb927-115">禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。</span><span class="sxs-lookup"><span data-stu-id="bb927-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="bb927-116">**使用Windows 安全中心应用禁用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="bb927-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="bb927-117">通过Windows 安全中心任务栏中的防护图标或搜索"安全"的"开始"菜单打开"安全 **"菜单。**</span><span class="sxs-lookup"><span data-stu-id="bb927-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="bb927-118">选择 **病毒&威胁** 防护磁贴 (或左侧菜单栏上的防护图标) ，然后选择病毒防护& **威胁防护设置**</span><span class="sxs-lookup"><span data-stu-id="bb927-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="bb927-119">滚动到通知 **部分** ，然后单击更改 **通知设置**。</span><span class="sxs-lookup"><span data-stu-id="bb927-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="bb927-120">将开关滑动到 **"关闭"** 或" **打开** "以禁用或启用其他通知。</span><span class="sxs-lookup"><span data-stu-id="bb927-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="bb927-121">**使用组策略禁用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="bb927-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="bb927-122">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="bb927-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="bb927-123">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="bb927-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="bb927-124">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="bb927-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="bb927-125">展开树以Windows **报告> Microsoft Defender 防病毒 >组件**。</span><span class="sxs-lookup"><span data-stu-id="bb927-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="bb927-126">双击关闭 **增强型通知，** 将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="bb927-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="bb927-127">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bb927-127">Click **OK**.</span></span> <span data-ttu-id="bb927-128">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="bb927-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="bb927-129">在终结点上配置标准通知</span><span class="sxs-lookup"><span data-stu-id="bb927-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="bb927-130">可以使用组策略：</span><span class="sxs-lookup"><span data-stu-id="bb927-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="bb927-131">当用户需要执行一个操作时，在终结点上显示其他自定义文本</span><span class="sxs-lookup"><span data-stu-id="bb927-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="bb927-132">隐藏终结点上的所有通知</span><span class="sxs-lookup"><span data-stu-id="bb927-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="bb927-133">隐藏终结点上的重启通知</span><span class="sxs-lookup"><span data-stu-id="bb927-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="bb927-134">当你无法隐藏整个通知界面时，隐藏通知Microsoft Defender 防病毒很有用。</span><span class="sxs-lookup"><span data-stu-id="bb927-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="bb927-135">有关详细信息[，请参阅防止用户查看 Microsoft Defender 防病毒用户界面](prevent-end-user-interaction-microsoft-defender-antivirus.md)或与之交互。</span><span class="sxs-lookup"><span data-stu-id="bb927-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="bb927-136">隐藏通知将仅在策略已部署到的终结点上发生。</span><span class="sxs-lookup"><span data-stu-id="bb927-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="bb927-137">与在监视仪表板和报告上 (必须) 操作Microsoft Endpoint Manager Endpoint Protection[通知](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="bb927-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="bb927-138">有关[将自定义联系人信息添加到用户](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)计算机上看到的通知的说明，请参阅为组织自定义 Windows 安全中心 应用。</span><span class="sxs-lookup"><span data-stu-id="bb927-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="bb927-139">**使用组策略隐藏通知：**</span><span class="sxs-lookup"><span data-stu-id="bb927-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="bb927-140">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="bb927-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="bb927-141">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="bb927-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="bb927-142">展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。</span><span class="sxs-lookup"><span data-stu-id="bb927-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="bb927-143">双击"**取消所有通知"，** 将该选项设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="bb927-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="bb927-144">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bb927-144">Click **OK**.</span></span> <span data-ttu-id="bb927-145">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="bb927-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="bb927-146">**使用组策略隐藏重启通知：**</span><span class="sxs-lookup"><span data-stu-id="bb927-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="bb927-147">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="bb927-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="bb927-148">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="bb927-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="bb927-149">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="bb927-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="bb927-150">展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。</span><span class="sxs-lookup"><span data-stu-id="bb927-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="bb927-151">双击取消 **重启通知，** 将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="bb927-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="bb927-152">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bb927-152">Click **OK**.</span></span> <span data-ttu-id="bb927-153">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="bb927-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb927-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="bb927-154">Related topics</span></span>

- [<span data-ttu-id="bb927-155">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="bb927-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="bb927-156">配置最终用户与最终用户的Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="bb927-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
