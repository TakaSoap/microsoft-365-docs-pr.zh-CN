---
title: 配置Microsoft Defender 防病毒通知
description: 了解如何在终结点上配置和自定义标准Microsoft Defender 防病毒通知。
keywords: 通知， defender， 防病毒， 终结点， 管理， 管理员
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985404"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="ba74e-104">配置Microsoft Defender 防病毒终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="ba74e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ba74e-105">**Applies to:**</span></span>

- [<span data-ttu-id="ba74e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba74e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ba74e-107">在Windows 10中，有关恶意软件检测和修正的应用程序通知更加可靠、一致且简洁。</span><span class="sxs-lookup"><span data-stu-id="ba74e-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="ba74e-108">Microsoft Defender 防病毒扫描完成并检测到威胁时，终结点上会显示通知。</span><span class="sxs-lookup"><span data-stu-id="ba74e-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="ba74e-109">通知遵循计划扫描和手动触发的扫描。</span><span class="sxs-lookup"><span data-stu-id="ba74e-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="ba74e-110">这些通知还会显示在 **通知中心** 中，并且扫描和威胁检测的摘要会定期显示。</span><span class="sxs-lookup"><span data-stu-id="ba74e-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="ba74e-111">如果你是组织安全团队的一员，可以配置通知在终结点上的显示方式，例如提示系统重启或指示已检测并修复威胁的通知。</span><span class="sxs-lookup"><span data-stu-id="ba74e-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="ba74e-112">使用组策略或应用配置Windows 安全中心通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="ba74e-113">可以在应用和组策略中配置其他通知的显示，如Windows 安全中心[威胁](microsoft-defender-security-center-antivirus.md)检测摘要。</span><span class="sxs-lookup"><span data-stu-id="ba74e-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="ba74e-114">在 Windows 10 版本 1607 中，该功能称为增强型通知，在 Windows 设置  >  **Update & security Windows Defender**  >  **下配置**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="ba74e-115">在所有版本的通知的组策略Windows 10，通知功能称为增强 **型通知**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="ba74e-116">使用组策略禁用其他通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="ba74e-117">在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="ba74e-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="ba74e-118">右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="ba74e-119">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="ba74e-120">选择 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="ba74e-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="ba74e-121">展开树以Windows   >  **Reporting**Microsoft Defender 防病毒>\*\* 组件。</span><span class="sxs-lookup"><span data-stu-id="ba74e-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="ba74e-122">双击关闭 **增强型通知**，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="ba74e-123">然后，选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ba74e-123">Then select **OK**.</span></span> <span data-ttu-id="ba74e-124">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="ba74e-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba74e-125">禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。</span><span class="sxs-lookup"><span data-stu-id="ba74e-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="ba74e-126">使用 Windows 安全中心 应用禁用其他通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="ba74e-127">通过Windows 安全中心任务栏中的防护图标或搜索"安全"的"开始"菜单打开"安全 **"菜单。**</span><span class="sxs-lookup"><span data-stu-id="ba74e-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="ba74e-128">选择 **病毒&威胁** 防护磁贴 (或左侧菜单栏上的防护图标) ，然后选择病毒防护& **威胁防护设置**</span><span class="sxs-lookup"><span data-stu-id="ba74e-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="ba74e-129">滚动到通知 **部分** ，然后选择更改 **通知设置**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="ba74e-130">将开关滑动到 **"关闭"** 或" **打开** "以禁用或启用其他通知。</span><span class="sxs-lookup"><span data-stu-id="ba74e-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba74e-131">禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。</span><span class="sxs-lookup"><span data-stu-id="ba74e-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="ba74e-132">使用组策略配置终结点上的标准通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="ba74e-133">可以使用组策略：</span><span class="sxs-lookup"><span data-stu-id="ba74e-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="ba74e-134">当用户需要执行一个操作时，在终结点上显示其他自定义文本</span><span class="sxs-lookup"><span data-stu-id="ba74e-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="ba74e-135">隐藏终结点上的所有通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="ba74e-136">隐藏终结点上的重启通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="ba74e-137">当你无法隐藏整个通知界面时，隐藏通知Microsoft Defender 防病毒很有用。</span><span class="sxs-lookup"><span data-stu-id="ba74e-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="ba74e-138">有关详细信息[，请参阅防止用户查看 Microsoft Defender 防病毒用户界面](prevent-end-user-interaction-microsoft-defender-antivirus.md)或与之交互。</span><span class="sxs-lookup"><span data-stu-id="ba74e-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="ba74e-139">隐藏通知将仅在策略已部署到的终结点上发生。</span><span class="sxs-lookup"><span data-stu-id="ba74e-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="ba74e-140">与在监视仪表板和报告上 (必须) 操作Microsoft Endpoint Manager Endpoint Protection[通知](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="ba74e-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="ba74e-141">若要将自定义联系人信息添加到终结点通知，请参阅[自定义](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)组织的 Windows 安全中心 应用。</span><span class="sxs-lookup"><span data-stu-id="ba74e-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="ba74e-142">使用组策略隐藏通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="ba74e-143">在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="ba74e-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="ba74e-144">右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="ba74e-145">在组 **策略管理编辑器中** ，转到计算机 **配置** ，然后选择 **管理模板**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="ba74e-146">展开树以Windows **客户端**  >  **Microsoft Defender 防病毒**  >  **组件**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="ba74e-147">双击"**取消所有通知"，** 将该选项设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="ba74e-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="ba74e-148">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ba74e-148">Select **OK**.</span></span> <span data-ttu-id="ba74e-149">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="ba74e-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="ba74e-150">使用组策略隐藏重启通知</span><span class="sxs-lookup"><span data-stu-id="ba74e-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="ba74e-151">在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="ba74e-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="ba74e-152">右键单击要配置的组策略对象， **然后选择编辑**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="ba74e-153">在组 **策略管理编辑器中** ，转到计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="ba74e-154">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="ba74e-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="ba74e-155">展开树以Windows **客户端**  >  **Microsoft Defender 防病毒**  >  **组件**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="ba74e-156">双击取消 **重启通知，** 将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="ba74e-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="ba74e-157">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ba74e-157">Select **OK**.</span></span> <span data-ttu-id="ba74e-158">这将阻止显示其他通知。</span><span class="sxs-lookup"><span data-stu-id="ba74e-158">This will prevent additional notifications from appearing.</span></span>

