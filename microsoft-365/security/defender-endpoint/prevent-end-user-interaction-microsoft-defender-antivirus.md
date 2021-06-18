---
title: 隐藏Microsoft Defender 防病毒界面
description: 可以在应用内隐藏病毒和威胁防护Windows 安全中心磁贴。
keywords: ui 锁定， 无头模式， 隐藏应用， 隐藏设置， 隐藏界面
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
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007656"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="a942a-104">阻止用户查看或与用户界面Microsoft Defender 防病毒交互</span><span class="sxs-lookup"><span data-stu-id="a942a-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a942a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a942a-105">**Applies to:**</span></span>

- [<span data-ttu-id="a942a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a942a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a942a-107">可以使用组策略阻止终结点上的用户看到 Microsoft Defender 防病毒 界面。</span><span class="sxs-lookup"><span data-stu-id="a942a-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="a942a-108">还可以阻止他们暂停扫描。</span><span class="sxs-lookup"><span data-stu-id="a942a-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="a942a-109">隐藏Microsoft Defender 防病毒界面</span><span class="sxs-lookup"><span data-stu-id="a942a-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="a942a-110">在 Windows 10 版本 1703 中，隐藏界面将隐藏 Microsoft Defender 防病毒 通知，并防止病毒 & 威胁防护磁贴显示在 Windows 安全中心 应用中。</span><span class="sxs-lookup"><span data-stu-id="a942a-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="a942a-111">将设置设置为"**已启用"：**</span><span class="sxs-lookup"><span data-stu-id="a942a-111">With the setting set to **Enabled**:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows 安全中心防护图标以及病毒和威胁防护部分":::

<span data-ttu-id="a942a-113">将设置设置为"已 **禁用"** 或未配置：</span><span class="sxs-lookup"><span data-stu-id="a942a-113">With the setting set to **Disabled** or not configured:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="具有防护Windows 安全中心和威胁防护部分的内容屏幕截图":::

>[!NOTE]
><span data-ttu-id="a942a-115">隐藏界面还会阻止Microsoft Defender 防病毒在终结点上显示通知。</span><span class="sxs-lookup"><span data-stu-id="a942a-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="a942a-116">Microsoft Defender for Endpoint 通知仍将显示。</span><span class="sxs-lookup"><span data-stu-id="a942a-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="a942a-117">还可以单独 [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a942a-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="a942a-118">在早期版本的 Windows 10 中，该设置将隐藏Windows Defender客户端接口。</span><span class="sxs-lookup"><span data-stu-id="a942a-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="a942a-119">如果用户尝试打开它，他们将收到一条警告，指出"你的系统管理员已限制对此应用的访问"。</span><span class="sxs-lookup"><span data-stu-id="a942a-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="在早于 1703 Windows 10无头模式时显示警告消息":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="a942a-121">使用组策略向用户隐藏 Microsoft Defender AV 界面</span><span class="sxs-lookup"><span data-stu-id="a942a-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="a942a-122">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="a942a-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="a942a-123">使用组 **策略管理编辑器转到** 计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="a942a-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a942a-124">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="a942a-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="a942a-125">展开树以Windows **客户端> Microsoft Defender 防病毒 >组件**。</span><span class="sxs-lookup"><span data-stu-id="a942a-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="a942a-126">双击启用 **无头 UI 模式** 设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="a942a-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="a942a-127">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a942a-127">Click **OK**.</span></span> 

<span data-ttu-id="a942a-128">有关 [阻止用户修改其电脑保护](configure-local-policy-overrides-microsoft-defender-antivirus.md) 的更多选项，请参阅防止用户在本地修改策略设置。</span><span class="sxs-lookup"><span data-stu-id="a942a-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="a942a-129">阻止用户暂停扫描</span><span class="sxs-lookup"><span data-stu-id="a942a-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="a942a-130">你可以阻止用户暂停扫描，这有助于确保计划扫描或按需扫描不会被用户中断。</span><span class="sxs-lookup"><span data-stu-id="a942a-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="a942a-131">此设置在系统上不受Windows 10。</span><span class="sxs-lookup"><span data-stu-id="a942a-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="a942a-132">使用组策略阻止用户暂停扫描</span><span class="sxs-lookup"><span data-stu-id="a942a-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="a942a-133">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="a942a-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="a942a-134">使用组 **策略管理编辑器转到** 计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="a942a-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a942a-135">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="a942a-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="a942a-136">展开树以Windows **扫描**  >  **Microsoft Defender 防病毒**  >  **组件**。</span><span class="sxs-lookup"><span data-stu-id="a942a-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="a942a-137">双击允许用户暂停 **扫描设置** ，将选项设置为 **已禁用**。</span><span class="sxs-lookup"><span data-stu-id="a942a-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="a942a-138">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a942a-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="a942a-139">相关文章</span><span class="sxs-lookup"><span data-stu-id="a942a-139">Related articles</span></span>

- [<span data-ttu-id="a942a-140">配置终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="a942a-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="a942a-141">配置最终用户与最终用户的Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="a942a-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="a942a-142">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="a942a-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)