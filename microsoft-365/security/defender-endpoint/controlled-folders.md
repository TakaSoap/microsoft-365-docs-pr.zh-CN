---
title: 保护重要文件夹免受勒索软件攻击，防止通过受控文件夹访问权限加密文件
description: 可以保护默认文件夹中的文件免受恶意应用更改。 阻止勒索软件加密文件。
keywords: 受控文件夹访问权限， windows 10， windows defender， 勒索软件， 保护， 文件， 文件夹
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b937dd41f0296f2cf4102f41f8ab10bd55e1c35d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200277"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="54a05-105">使用受控文件夹访问权限保护重要文件夹</span><span class="sxs-lookup"><span data-stu-id="54a05-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="54a05-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="54a05-106">**Applies to:**</span></span>
- [<span data-ttu-id="54a05-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="54a05-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="54a05-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54a05-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="54a05-109">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="54a05-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="54a05-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="54a05-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="54a05-111">什么是受控文件夹访问权限？</span><span class="sxs-lookup"><span data-stu-id="54a05-111">What is controlled folder access?</span></span>

<span data-ttu-id="54a05-112">受控文件夹访问权限有助于保护你有价值的数据免受恶意应用和威胁（如勒索软件）的侵害。</span><span class="sxs-lookup"><span data-stu-id="54a05-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="54a05-113">受控文件夹访问权限通过针对已知受信任应用列表检查应用来保护你的数据。</span><span class="sxs-lookup"><span data-stu-id="54a05-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="54a05-114">在 Windows Server 2019 和 Windows 10 客户端上受支持，受控文件夹访问权限可以使用 Windows 安全应用、Microsoft Endpoint Configuration Manager 或 Intune (for managed devices) 打开。</span><span class="sxs-lookup"><span data-stu-id="54a05-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="54a05-115">脚本引擎不受信任，你无法允许它们访问受控的受保护文件夹。</span><span class="sxs-lookup"><span data-stu-id="54a05-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="54a05-116">例如，即使允许使用证书和文件指示器，PowerShell 也不受受控文件夹访问权限 [信任](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)。</span><span class="sxs-lookup"><span data-stu-id="54a05-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="54a05-117">受控文件夹访问权限最适用于 [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，它为你提供有关受控文件夹访问权限事件的详细报告，并作为常用的警报调查方案的一 [部分进行阻止](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="54a05-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="54a05-118">受控文件夹访问块不会在警报队列中 [生成警报](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="54a05-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="54a05-119">但是，可以在设备时间线视图中查看有关受控文件夹访问块的信息[](investigate-machines.md)，同时使用高级搜寻或[](advanced-hunting-overview.md)[自定义检测规则](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="54a05-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="54a05-120">受控文件夹访问权限是如何工作的？</span><span class="sxs-lookup"><span data-stu-id="54a05-120">How does controlled folder access work?</span></span>

<span data-ttu-id="54a05-121">受控文件夹访问权限的工作方式是仅允许受信任的应用访问受保护的文件夹。</span><span class="sxs-lookup"><span data-stu-id="54a05-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="54a05-122">在配置受控文件夹访问权限时指定受保护的文件夹。</span><span class="sxs-lookup"><span data-stu-id="54a05-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="54a05-123">通常，常用文件夹（如用于文档、图片、下载等的文件夹）包含在受控文件夹列表中。</span><span class="sxs-lookup"><span data-stu-id="54a05-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="54a05-124">受控文件夹访问权限适用于受信任应用列表。</span><span class="sxs-lookup"><span data-stu-id="54a05-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="54a05-125">受信任软件列表中包含的应用将正常工作。</span><span class="sxs-lookup"><span data-stu-id="54a05-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="54a05-126">列表中未包含的应用无法对受保护文件夹内的文件进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="54a05-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="54a05-127">根据应用的普遍程度和信誉将应用添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="54a05-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="54a05-128">在整个组织中非常普遍且从未显示任何被视为恶意行为的应用被视为可信赖。</span><span class="sxs-lookup"><span data-stu-id="54a05-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="54a05-129">这些应用会自动添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="54a05-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="54a05-130">还可使用 Configuration Manager 或 Intune 将应用手动添加到受信任的列表中。</span><span class="sxs-lookup"><span data-stu-id="54a05-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="54a05-131">其他操作（如 [添加](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) 应用的文件指示器）可以从安全中心控制台执行。</span><span class="sxs-lookup"><span data-stu-id="54a05-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="54a05-132">受控文件夹访问权限为什么很重要</span><span class="sxs-lookup"><span data-stu-id="54a05-132">Why controlled folder access is important</span></span>

<span data-ttu-id="54a05-133">受控文件夹访问权限在帮助保护文档和信息免受勒索软件攻击 [方面尤其有用](https://www.microsoft.com/wdsi/threats/ransomware)。</span><span class="sxs-lookup"><span data-stu-id="54a05-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="54a05-134">在勒索软件攻击中，你的文件可以加密并保存。</span><span class="sxs-lookup"><span data-stu-id="54a05-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="54a05-135">受控文件夹访问权限就位后，应用尝试对受保护文件夹中的文件进行更改的计算机上将显示一条通知。</span><span class="sxs-lookup"><span data-stu-id="54a05-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="54a05-136">可以使用 [公司详细信息和](customize-attack-surface-reduction.md#customize-the-notification) 联系信息自定义通知。</span><span class="sxs-lookup"><span data-stu-id="54a05-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="54a05-137">您还可以单独启用规则以自定义功能监视的技术。</span><span class="sxs-lookup"><span data-stu-id="54a05-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="54a05-138">受保护的 [文件夹包括](#review-controlled-folder-access-events-in-windows-event-viewer) 公用系统文件夹 (包括启动) ，你可以 [添加更多文件夹](customize-controlled-folders.md#protect-additional-folders)。</span><span class="sxs-lookup"><span data-stu-id="54a05-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="54a05-139">还可以允许 [应用](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) 向它们授予对受保护文件夹的访问权限。</span><span class="sxs-lookup"><span data-stu-id="54a05-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="54a05-140">可以使用审核 [模式评估](audit-windows-defender.md) 受控文件夹访问权限启用后对组织的影响。</span><span class="sxs-lookup"><span data-stu-id="54a05-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="54a05-141">您还可以访问 Windows Defender Test ground [网站，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 确认功能是否正常工作并查看其工作方式。</span><span class="sxs-lookup"><span data-stu-id="54a05-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="54a05-142">受控文件夹访问权限在下列版本的 Windows 上受支持：</span><span class="sxs-lookup"><span data-stu-id="54a05-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="54a05-143">[Windows 10 版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 和更高版本</span><span class="sxs-lookup"><span data-stu-id="54a05-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="54a05-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="54a05-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="54a05-145">默认情况下，Windows 系统文件夹受到保护</span><span class="sxs-lookup"><span data-stu-id="54a05-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="54a05-146">默认情况下，Windows 系统文件夹以及其他一些文件夹都受到保护：</span><span class="sxs-lookup"><span data-stu-id="54a05-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="54a05-147">你可以将其他文件夹配置为受保护，但无法删除默认情况下受保护的 Windows 系统文件夹。</span><span class="sxs-lookup"><span data-stu-id="54a05-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="54a05-148">受控文件夹访问权限的要求</span><span class="sxs-lookup"><span data-stu-id="54a05-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="54a05-149">受控文件夹访问权限需要启用 [Microsoft Defender 防病毒实时保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="54a05-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="54a05-150">在 Microsoft Defender 安全中心中查看受控文件夹访问权限事件</span><span class="sxs-lookup"><span data-stu-id="54a05-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="54a05-151">Defender for Endpoint 提供事件的详细报告和阻止，作为警报调查方案的 [一部分](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="54a05-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="54a05-152">可以使用高级搜寻查询 Microsoft Defender 的终结点 [数据](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="54a05-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="54a05-153">如果你使用的是审核[模式](audit-windows-defender.md)，可以使用高级搜寻查看受控文件夹[](advanced-hunting-overview.md)访问权限设置在启用后将如何影响你的环境。</span><span class="sxs-lookup"><span data-stu-id="54a05-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="54a05-154">示例查询：</span><span class="sxs-lookup"><span data-stu-id="54a05-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="54a05-155">在 Windows 事件查看器中查看受控文件夹访问权限事件</span><span class="sxs-lookup"><span data-stu-id="54a05-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="54a05-156">你可以查看 Windows 事件日志，以查看当受控文件夹访问权限阻止应用 (或审核应用) 创建的事件：</span><span class="sxs-lookup"><span data-stu-id="54a05-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="54a05-157">下载 [评估包](https://aka.ms/mp7z2w) ，将文件 *cfa-events.xml* 到设备上易于访问的位置。</span><span class="sxs-lookup"><span data-stu-id="54a05-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="54a05-158">在 **"开始"** 菜单中键入事件查看器以打开 Windows 事件查看器。</span><span class="sxs-lookup"><span data-stu-id="54a05-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="54a05-159">在左侧面板的"操作 **"下**，选择 **"导入自定义视图..."。**</span><span class="sxs-lookup"><span data-stu-id="54a05-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="54a05-160">导航到提取 *内容cfa-events.xml并选择* 它。</span><span class="sxs-lookup"><span data-stu-id="54a05-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="54a05-161">或者，[直接复制 XML。](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="54a05-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="54a05-162">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="54a05-162">Select **OK**.</span></span>

<span data-ttu-id="54a05-163">下表显示与受控文件夹访问权限相关的事件：</span><span class="sxs-lookup"><span data-stu-id="54a05-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="54a05-164">事件 ID</span><span class="sxs-lookup"><span data-stu-id="54a05-164">Event ID</span></span> | <span data-ttu-id="54a05-165">说明</span><span class="sxs-lookup"><span data-stu-id="54a05-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="54a05-166">5007</span><span class="sxs-lookup"><span data-stu-id="54a05-166">5007</span></span> | <span data-ttu-id="54a05-167">更改设置时的事件</span><span class="sxs-lookup"><span data-stu-id="54a05-167">Event when settings are changed</span></span> |
|<span data-ttu-id="54a05-168">1124</span><span class="sxs-lookup"><span data-stu-id="54a05-168">1124</span></span> | <span data-ttu-id="54a05-169">已审核的受控文件夹访问事件</span><span class="sxs-lookup"><span data-stu-id="54a05-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="54a05-170">1123</span><span class="sxs-lookup"><span data-stu-id="54a05-170">1123</span></span> | <span data-ttu-id="54a05-171">阻止的受控文件夹访问事件</span><span class="sxs-lookup"><span data-stu-id="54a05-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="54a05-172">查看或更改受保护的文件夹列表</span><span class="sxs-lookup"><span data-stu-id="54a05-172">View or change the list of protected folders</span></span>

<span data-ttu-id="54a05-173">可以使用 Windows 安全应用查看受受控文件夹访问权限保护的文件夹列表。</span><span class="sxs-lookup"><span data-stu-id="54a05-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="54a05-174">在 Windows 10 设备上，打开 Windows 安全应用。</span><span class="sxs-lookup"><span data-stu-id="54a05-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="54a05-175">选择 **病毒&威胁防护**。</span><span class="sxs-lookup"><span data-stu-id="54a05-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="54a05-176">在 **勒索软件保护下**，选择 **管理勒索软件保护**。</span><span class="sxs-lookup"><span data-stu-id="54a05-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="54a05-177">如果关闭受控文件夹访问权限，你需要将其打开。</span><span class="sxs-lookup"><span data-stu-id="54a05-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="54a05-178">选择 **受保护的文件夹**。</span><span class="sxs-lookup"><span data-stu-id="54a05-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="54a05-179">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="54a05-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="54a05-180">若要添加文件夹，请选择 **" + 添加受保护的文件夹"。**</span><span class="sxs-lookup"><span data-stu-id="54a05-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="54a05-181">若要删除文件夹，请选择该文件夹，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="54a05-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="54a05-182">[默认情况下，Windows](#windows-system-folders-are-protected-by-default) 系统文件夹受到保护，你无法从列表中删除它们。</span><span class="sxs-lookup"><span data-stu-id="54a05-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="54a05-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54a05-183">See also</span></span>

- [<span data-ttu-id="54a05-184">评估受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="54a05-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="54a05-185">自定义受控文件夹访问权限</span><span class="sxs-lookup"><span data-stu-id="54a05-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="54a05-186">保护更多文件夹</span><span class="sxs-lookup"><span data-stu-id="54a05-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
