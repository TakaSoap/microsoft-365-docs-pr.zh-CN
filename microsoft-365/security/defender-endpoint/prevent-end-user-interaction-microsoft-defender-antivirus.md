---
title: 隐藏 Microsoft Defender 防病毒界面
description: 你可以隐藏 Windows 安全应用中的病毒和威胁防护磁贴。
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
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274912"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="9d68e-104">阻止用户查看 Microsoft Defender 防病毒用户界面或与之交互</span><span class="sxs-lookup"><span data-stu-id="9d68e-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9d68e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9d68e-105">**Applies to:**</span></span>

- [<span data-ttu-id="9d68e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9d68e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9d68e-107">可以使用组策略阻止终结点上的用户看到 Microsoft Defender 防病毒界面。</span><span class="sxs-lookup"><span data-stu-id="9d68e-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="9d68e-108">还可以阻止他们暂停扫描。</span><span class="sxs-lookup"><span data-stu-id="9d68e-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="9d68e-109">隐藏 Microsoft Defender 防病毒界面</span><span class="sxs-lookup"><span data-stu-id="9d68e-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="9d68e-110">在 Windows 10 版本 1703 中，隐藏界面将隐藏 Microsoft Defender 防病毒通知，并防止病毒 & 威胁防护磁贴显示在 Windows 安全应用中。</span><span class="sxs-lookup"><span data-stu-id="9d68e-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="9d68e-111">将设置设置为"**已启用"：**</span><span class="sxs-lookup"><span data-stu-id="9d68e-111">With the setting set to **Enabled**:</span></span>

![无防护图标和病毒和威胁防护部分 Windows 安全屏幕截图](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="9d68e-113">将设置设置为"已 **禁用"** 或未配置：</span><span class="sxs-lookup"><span data-stu-id="9d68e-113">With the setting set to **Disabled** or not configured:</span></span>

![显示防护图标以及病毒和威胁防护部分 Windows 安全性的屏幕截图](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="9d68e-115">隐藏界面还会阻止在终结点上显示 Microsoft Defender 防病毒通知。</span><span class="sxs-lookup"><span data-stu-id="9d68e-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="9d68e-116">Microsoft Defender for Endpoint 通知仍将显示。</span><span class="sxs-lookup"><span data-stu-id="9d68e-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="9d68e-117">还可以单独 [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9d68e-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="9d68e-118">在早期版本的 Windows 10 中，该设置将隐藏Windows Defender客户端接口。</span><span class="sxs-lookup"><span data-stu-id="9d68e-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="9d68e-119">如果用户尝试打开它，他们将收到一条警告，指出"你的系统管理员已限制对此应用的访问"。</span><span class="sxs-lookup"><span data-stu-id="9d68e-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![在早于 1703 的 Windows 10 版本中启用无头模式时显示警告消息](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="9d68e-121">使用组策略向用户隐藏 Microsoft Defender AV 界面</span><span class="sxs-lookup"><span data-stu-id="9d68e-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="9d68e-122">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="9d68e-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9d68e-123">使用组 **策略管理编辑器转到** 计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="9d68e-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="9d68e-124">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="9d68e-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="9d68e-125">将树展开到 **Microsoft Defender 防病毒>客户端**> Windows 组件。</span><span class="sxs-lookup"><span data-stu-id="9d68e-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="9d68e-126">双击启用 **无头 UI 模式** 设置，将选项设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="9d68e-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="9d68e-127">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9d68e-127">Click **OK**.</span></span> 

<span data-ttu-id="9d68e-128">有关 [阻止用户修改其电脑保护](configure-local-policy-overrides-microsoft-defender-antivirus.md) 的更多选项，请参阅防止用户在本地修改策略设置。</span><span class="sxs-lookup"><span data-stu-id="9d68e-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="9d68e-129">阻止用户暂停扫描</span><span class="sxs-lookup"><span data-stu-id="9d68e-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="9d68e-130">你可以阻止用户暂停扫描，这有助于确保计划扫描或按需扫描不会被用户中断。</span><span class="sxs-lookup"><span data-stu-id="9d68e-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="9d68e-131">此设置在 Windows 10 上不受支持。</span><span class="sxs-lookup"><span data-stu-id="9d68e-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="9d68e-132">使用组策略阻止用户暂停扫描</span><span class="sxs-lookup"><span data-stu-id="9d68e-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="9d68e-133">在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，**然后单击编辑。**</span><span class="sxs-lookup"><span data-stu-id="9d68e-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9d68e-134">使用组 **策略管理编辑器转到** 计算机 **配置**。</span><span class="sxs-lookup"><span data-stu-id="9d68e-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="9d68e-135">单击 **"管理模板"。**</span><span class="sxs-lookup"><span data-stu-id="9d68e-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="9d68e-136">将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **扫描**。</span><span class="sxs-lookup"><span data-stu-id="9d68e-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="9d68e-137">双击允许用户暂停 **扫描设置** ，将选项设置为 **已禁用**。</span><span class="sxs-lookup"><span data-stu-id="9d68e-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="9d68e-138">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="9d68e-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="9d68e-139">相关文章</span><span class="sxs-lookup"><span data-stu-id="9d68e-139">Related articles</span></span>

- [<span data-ttu-id="9d68e-140">配置终结点上显示的通知</span><span class="sxs-lookup"><span data-stu-id="9d68e-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="9d68e-141">配置最终用户与 Microsoft Defender 防病毒的交互</span><span class="sxs-lookup"><span data-stu-id="9d68e-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="9d68e-142">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="9d68e-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)