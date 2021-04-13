---
title: 配置 Microsoft Defender 防病毒通知
description: 了解如何在终结点上配置和自定义标准和其他 Microsoft Defender 防病毒通知。
keywords: 通知， defender， 防病毒， 终结点， 管理， 管理员
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82ca54e383943f4994f9647ce1e110a6621b1327
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690209"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="25e2e-104">配置终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="25e2e-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25e2e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="25e2e-105">**Applies to:**</span></span>

- [<span data-ttu-id="25e2e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="25e2e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="25e2e-107">在 Windows 10 中，有关恶意软件检测和修正的应用程序通知更加可靠、一致且简洁。</span><span class="sxs-lookup"><span data-stu-id="25e2e-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="25e2e-108">完成手动触发和计划的扫描并检测到威胁后，终结点上会显示通知。</span><span class="sxs-lookup"><span data-stu-id="25e2e-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="25e2e-109">这些通知还会显示在 **通知中心** 中，并且扫描和威胁检测的摘要会定期显示。</span><span class="sxs-lookup"><span data-stu-id="25e2e-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="25e2e-110">还可以配置标准通知在终结点上的显示方式，例如重启通知或检测到并修正威胁时的通知。</span><span class="sxs-lookup"><span data-stu-id="25e2e-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="25e2e-111">配置终结点上显示的其他通知</span><span class="sxs-lookup"><span data-stu-id="25e2e-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="25e2e-112">可以在 [Windows](microsoft-defender-security-center-antivirus.md) 安全应用和组策略中配置其他通知的显示，如最近的威胁检测摘要。</span><span class="sxs-lookup"><span data-stu-id="25e2e-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="25e2e-113">在 Windows 10 版本 1607中，该功能称为增强型通知，可以在 **Windows** 设置更新和安全&  >  **下**  >  **Windows Defender。**</span><span class="sxs-lookup"><span data-stu-id="25e2e-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="25e2e-114">在所有版本的 Windows 10 的组策略设置中，它称为增强 **型通知**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25e2e-115">禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。</span><span class="sxs-lookup"><span data-stu-id="25e2e-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="25e2e-116">**使用 Windows 安全应用禁用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="25e2e-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="25e2e-117">通过单击任务栏中的防护图标或搜索 Defender 的开始菜单打开 Windows 安全 **应用**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="25e2e-118">单击病毒&**威胁** 防护磁贴 (左侧菜单栏上的防护图标) 然后单击病毒防护威胁防护 **&标签：**</span><span class="sxs-lookup"><span data-stu-id="25e2e-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows 安全应用中的病毒&威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="25e2e-120">滚动到通知 **部分** ，然后单击更改 **通知设置**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="25e2e-121">将开关滑动到 **"关闭"** 或" **打开** "以禁用或启用其他通知。</span><span class="sxs-lookup"><span data-stu-id="25e2e-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="25e2e-122">**使用组策略禁用其他通知：**</span><span class="sxs-lookup"><span data-stu-id="25e2e-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="25e2e-123">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="25e2e-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="25e2e-124">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="25e2e-125">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="25e2e-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="25e2e-126">将树展开到 Microsoft Defender 防病毒 **>报告中的 Windows >组件**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="25e2e-127">双击关闭 **增强型通知，** 将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="25e2e-128">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="25e2e-128">Click **OK**.</span></span> <span data-ttu-id="25e2e-129">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="25e2e-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="25e2e-130">在终结点上配置标准通知</span><span class="sxs-lookup"><span data-stu-id="25e2e-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="25e2e-131">可以使用组策略：</span><span class="sxs-lookup"><span data-stu-id="25e2e-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="25e2e-132">当用户需要执行一个操作时，在终结点上显示其他自定义文本</span><span class="sxs-lookup"><span data-stu-id="25e2e-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="25e2e-133">隐藏终结点上的所有通知</span><span class="sxs-lookup"><span data-stu-id="25e2e-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="25e2e-134">隐藏终结点上的重启通知</span><span class="sxs-lookup"><span data-stu-id="25e2e-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="25e2e-135">当你无法隐藏整个 Microsoft Defender 防病毒界面时，隐藏通知可能很有用。</span><span class="sxs-lookup"><span data-stu-id="25e2e-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="25e2e-136">有关详细信息 [，请参阅阻止用户查看或](prevent-end-user-interaction-microsoft-defender-antivirus.md) 与 Microsoft Defender 防病毒用户界面交互。</span><span class="sxs-lookup"><span data-stu-id="25e2e-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="25e2e-137">隐藏通知将仅在策略已部署到的终结点上发生。</span><span class="sxs-lookup"><span data-stu-id="25e2e-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="25e2e-138">与必须采取的操作（ (重启）相关的) 仍将显示在 [Microsoft Endpoint Manager Endpoint Protection](/configmgr/protect/deploy-use/monitor-endpoint-protection)监视仪表板和报告上。</span><span class="sxs-lookup"><span data-stu-id="25e2e-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="25e2e-139">有关 [将自定义联系人信息](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 添加到用户计算机上看到的通知的说明，请参阅为组织自定义 Windows 安全中心应用。</span><span class="sxs-lookup"><span data-stu-id="25e2e-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="25e2e-140">**使用组策略隐藏通知：**</span><span class="sxs-lookup"><span data-stu-id="25e2e-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="25e2e-141">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="25e2e-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="25e2e-142">在组 **策略管理编辑器中** ，转到计算机 **配置，** 然后单击 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="25e2e-143">将树展开到 **Microsoft Defender 防病毒>客户端**> Windows 组件。</span><span class="sxs-lookup"><span data-stu-id="25e2e-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="25e2e-144">双击"**取消所有通知"，** 将该选项设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="25e2e-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="25e2e-145">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="25e2e-145">Click **OK**.</span></span> <span data-ttu-id="25e2e-146">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="25e2e-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="25e2e-147">**使用组策略隐藏重启通知：**</span><span class="sxs-lookup"><span data-stu-id="25e2e-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="25e2e-148">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="25e2e-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="25e2e-149">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="25e2e-150">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="25e2e-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="25e2e-151">将树展开到 **Microsoft Defender 防病毒>客户端**> Windows 组件。</span><span class="sxs-lookup"><span data-stu-id="25e2e-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="25e2e-152">双击取消 **重启通知，** 将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="25e2e-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="25e2e-153">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="25e2e-153">Click **OK**.</span></span> <span data-ttu-id="25e2e-154">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="25e2e-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25e2e-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="25e2e-155">Related topics</span></span>

- [<span data-ttu-id="25e2e-156">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="25e2e-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="25e2e-157">配置最终用户与 Microsoft Defender 防病毒的交互</span><span class="sxs-lookup"><span data-stu-id="25e2e-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)