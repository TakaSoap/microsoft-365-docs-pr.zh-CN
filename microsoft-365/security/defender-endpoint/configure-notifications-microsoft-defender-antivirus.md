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
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6e11c9394f250a6f3882183224f53954b1390a23
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274624"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="99353-104">配置终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="99353-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="99353-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="99353-105">**Applies to:**</span></span>

- [<span data-ttu-id="99353-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="99353-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="99353-107">在Windows 10中，有关恶意软件检测和修正的应用程序通知更加可靠、一致且简洁。</span><span class="sxs-lookup"><span data-stu-id="99353-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="99353-108">完成手动触发和计划的扫描并检测到威胁后，终结点上会显示通知。</span><span class="sxs-lookup"><span data-stu-id="99353-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="99353-109">这些通知还会显示在 **通知中心** 中，并且扫描和威胁检测的摘要会定期显示。</span><span class="sxs-lookup"><span data-stu-id="99353-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="99353-110">还可以配置标准通知在终结点上的显示方式，例如重启通知或检测到并修正威胁时的通知。</span><span class="sxs-lookup"><span data-stu-id="99353-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="99353-111">配置终结点上显示的其他通知</span><span class="sxs-lookup"><span data-stu-id="99353-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="99353-112">可以在应用和组策略中配置其他通知的显示，如Windows 安全中心[威胁](microsoft-defender-security-center-antivirus.md)检测摘要。</span><span class="sxs-lookup"><span data-stu-id="99353-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="99353-113">在 Windows 10 版本 1607 中，该功能称为增强型通知，可以在 Windows 设置  >  **Update & security Windows Defender**  >  **下配置**。</span><span class="sxs-lookup"><span data-stu-id="99353-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="99353-114">在所有版本的组策略设置中Windows 10，它称为增强 **型通知**。</span><span class="sxs-lookup"><span data-stu-id="99353-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99353-115">禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。</span><span class="sxs-lookup"><span data-stu-id="99353-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="99353-116">**使用Windows 安全中心应用禁用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="99353-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="99353-117">通过Windows 安全中心任务栏中的防护图标或搜索 Defender 的"开始"菜单打开"开始 **"菜单。**</span><span class="sxs-lookup"><span data-stu-id="99353-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="99353-118">单击病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后单击病毒防护威胁防护 **&标签：**</span><span class="sxs-lookup"><span data-stu-id="99353-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot of the Virus & threat protection settings label in the Windows 安全中心 app](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="99353-120">滚动到通知 **部分** ，然后单击更改 **通知设置**。</span><span class="sxs-lookup"><span data-stu-id="99353-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="99353-121">将开关滑动到 **"关闭"** 或" **打开** "以禁用或启用其他通知。</span><span class="sxs-lookup"><span data-stu-id="99353-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="99353-122">**使用组策略禁用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="99353-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="99353-123">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="99353-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="99353-124">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="99353-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="99353-125">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="99353-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="99353-126">展开树以Windows **报告> Microsoft Defender 防病毒 >组件**。</span><span class="sxs-lookup"><span data-stu-id="99353-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="99353-127">双击关闭 **增强型通知，** 将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="99353-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="99353-128">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="99353-128">Click **OK**.</span></span> <span data-ttu-id="99353-129">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="99353-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="99353-130">在终结点上配置标准通知</span><span class="sxs-lookup"><span data-stu-id="99353-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="99353-131">可以使用组策略：</span><span class="sxs-lookup"><span data-stu-id="99353-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="99353-132">当用户需要执行一个操作时，在终结点上显示其他自定义文本</span><span class="sxs-lookup"><span data-stu-id="99353-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="99353-133">隐藏终结点上的所有通知</span><span class="sxs-lookup"><span data-stu-id="99353-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="99353-134">隐藏终结点上的重启通知</span><span class="sxs-lookup"><span data-stu-id="99353-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="99353-135">当你无法隐藏整个通知界面时，隐藏通知Microsoft Defender 防病毒很有用。</span><span class="sxs-lookup"><span data-stu-id="99353-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="99353-136">有关详细信息[，请参阅防止用户查看 Microsoft Defender 防病毒用户界面](prevent-end-user-interaction-microsoft-defender-antivirus.md)或与之交互。</span><span class="sxs-lookup"><span data-stu-id="99353-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="99353-137">隐藏通知将仅在策略已部署到的终结点上发生。</span><span class="sxs-lookup"><span data-stu-id="99353-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="99353-138">与在监视仪表板和报告上 (必须) 操作Microsoft Endpoint Manager Endpoint Protection[通知](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="99353-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="99353-139">有关[将自定义联系人信息添加到用户](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)计算机上看到的通知的说明，请参阅为组织自定义 Windows 安全中心 应用。</span><span class="sxs-lookup"><span data-stu-id="99353-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="99353-140">**使用组策略隐藏通知：**</span><span class="sxs-lookup"><span data-stu-id="99353-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="99353-141">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="99353-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="99353-142">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="99353-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="99353-143">展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。</span><span class="sxs-lookup"><span data-stu-id="99353-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="99353-144">双击"**取消所有通知"，** 将该选项设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="99353-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="99353-145">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="99353-145">Click **OK**.</span></span> <span data-ttu-id="99353-146">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="99353-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="99353-147">**使用组策略隐藏重启通知：**</span><span class="sxs-lookup"><span data-stu-id="99353-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="99353-148">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="99353-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="99353-149">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="99353-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="99353-150">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="99353-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="99353-151">展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。</span><span class="sxs-lookup"><span data-stu-id="99353-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="99353-152">双击取消 **重启通知，** 将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="99353-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="99353-153">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="99353-153">Click **OK**.</span></span> <span data-ttu-id="99353-154">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="99353-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="99353-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="99353-155">Related topics</span></span>

- [<span data-ttu-id="99353-156">Microsoft Defender 防病毒Windows 10</span><span class="sxs-lookup"><span data-stu-id="99353-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="99353-157">配置最终用户与最终用户的Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="99353-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)