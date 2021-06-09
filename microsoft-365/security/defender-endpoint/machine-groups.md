---
title: 在 Microsoft Defender for Endpoint 中创建和管理设备组
description: 通过确认适用于该组的规则，创建设备组并设置其自动修正级别
keywords: 设备组， 组， 修正， 级别， 规则， aad 组， 角色， 分配， 排名
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d4f62acde4e7d790c7a7c8635f51c99f0823687d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842766"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="eff05-104">创建和管理设备组</span><span class="sxs-lookup"><span data-stu-id="eff05-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eff05-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="eff05-105">**Applies to:**</span></span>
- <span data-ttu-id="eff05-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eff05-106">Azure Active Directory</span></span>
- <span data-ttu-id="eff05-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="eff05-107">Office 365</span></span>

> <span data-ttu-id="eff05-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="eff05-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eff05-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="eff05-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="eff05-110">在企业方案中，通常会为安全运营团队分配一组设备。</span><span class="sxs-lookup"><span data-stu-id="eff05-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="eff05-111">这些设备根据一组属性（如域、计算机名称或指定标记）分组在一起。</span><span class="sxs-lookup"><span data-stu-id="eff05-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="eff05-112">在 Microsoft Defender for Endpoint 中，你可以创建设备组，并使用它们：</span><span class="sxs-lookup"><span data-stu-id="eff05-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="eff05-113">将相关警报和数据的访问权限限制为具有已分配[RBAC](rbac.md)角色的特定 Azure AD 用户组</span><span class="sxs-lookup"><span data-stu-id="eff05-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="eff05-114">为不同的设备集配置不同的自动修正设置</span><span class="sxs-lookup"><span data-stu-id="eff05-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="eff05-115">分配特定修正级别以在自动调查期间应用</span><span class="sxs-lookup"><span data-stu-id="eff05-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="eff05-116">在调查中，使用组筛选器 **将"设备** "列表筛选到特定 **设备** 组。</span><span class="sxs-lookup"><span data-stu-id="eff05-116">In an investigation, filter the **Devices list** to specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="eff05-117">可以在基于角色的访问 (RBAC) 上下文中创建设备组，以控制哪些人可以通过将设备组 () 分配给用户组来控制哪些人可以采取特定操作或查看信息。</span><span class="sxs-lookup"><span data-stu-id="eff05-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="eff05-118">有关详细信息，请参阅使用基于角色 [的访问控制管理门户访问](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="eff05-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="eff05-119">有关 RBAC 应用程序的全面了解，请阅读 [：SOC 是否使用 RBAC 运行平面](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)。</span><span class="sxs-lookup"><span data-stu-id="eff05-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="eff05-120">在创建设备组的过程中，你将：</span><span class="sxs-lookup"><span data-stu-id="eff05-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="eff05-121">设置该组的自动修正级别。</span><span class="sxs-lookup"><span data-stu-id="eff05-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="eff05-122">有关修正级别的信息，请参阅使用 [自动调查调查和修正威胁](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="eff05-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="eff05-123">根据设备名称、域、标记和操作系统平台指定匹配规则，以确定哪些设备组属于该组。</span><span class="sxs-lookup"><span data-stu-id="eff05-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="eff05-124">如果设备还与其他组匹配，则只会将设备添加到排名最高的设备组中。</span><span class="sxs-lookup"><span data-stu-id="eff05-124">If a device is also matched to other groups, it's added only to the highest ranked device group.</span></span>
- <span data-ttu-id="eff05-125">选择应有权访问设备组的 Azure AD 用户组。</span><span class="sxs-lookup"><span data-stu-id="eff05-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="eff05-126">创建设备组后，相对于其他组对设备组进行排名。</span><span class="sxs-lookup"><span data-stu-id="eff05-126">Rank the device group relative to other groups after it's created.</span></span>

>[!NOTE]
><span data-ttu-id="eff05-127">如果未向设备组分配任何 Azure AD 组，则所有用户均可访问该设备组。</span><span class="sxs-lookup"><span data-stu-id="eff05-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="eff05-128">创建设备组</span><span class="sxs-lookup"><span data-stu-id="eff05-128">Create a device group</span></span>

1. <span data-ttu-id="eff05-129">在导航窗格中，选择 **"设置**  >  **设备组"。**</span><span class="sxs-lookup"><span data-stu-id="eff05-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="eff05-130">单击 **"添加设备组"。**</span><span class="sxs-lookup"><span data-stu-id="eff05-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="eff05-131">输入组名称和自动化设置，并指定用于确定哪些设备属于该组的匹配规则。</span><span class="sxs-lookup"><span data-stu-id="eff05-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="eff05-132">请参阅 [自动调查如何启动](automated-investigations.md#how-the-automated-investigation-starts)。</span><span class="sxs-lookup"><span data-stu-id="eff05-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="eff05-133">如果要按组织单位对设备进行分组，可以配置组附属项的注册表项。</span><span class="sxs-lookup"><span data-stu-id="eff05-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="eff05-134">有关设备标记详细信息，请参阅创建 [和管理设备标记](machine-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="eff05-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="eff05-135">预览将匹配此规则的几个设备。</span><span class="sxs-lookup"><span data-stu-id="eff05-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="eff05-136">如果您对规则感到满意，请单击"用户访问 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="eff05-136">If you're satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="eff05-137">分配可以访问你创建的设备组的用户组。</span><span class="sxs-lookup"><span data-stu-id="eff05-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="eff05-138">只能向已分配给 RBAC 角色的 Azure AD 用户组授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="eff05-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="eff05-139">单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="eff05-139">Click **Close**.</span></span> <span data-ttu-id="eff05-140">将应用配置更改。</span><span class="sxs-lookup"><span data-stu-id="eff05-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="eff05-141">管理设备组</span><span class="sxs-lookup"><span data-stu-id="eff05-141">Manage device groups</span></span>

<span data-ttu-id="eff05-142">你可以升级或降级设备组的排名，以便它在匹配期间获得更高或更低的优先级。</span><span class="sxs-lookup"><span data-stu-id="eff05-142">You can promote or demote the rank of a device group so that it's given higher or lower priority during matching.</span></span> <span data-ttu-id="eff05-143">当设备与多个组匹配时，它只会添加到排名最高的组中。</span><span class="sxs-lookup"><span data-stu-id="eff05-143">When a device is matched to more than one group, it's added only to the highest ranked group.</span></span> <span data-ttu-id="eff05-144">还可以编辑和删除组。</span><span class="sxs-lookup"><span data-stu-id="eff05-144">You can also edit and delete groups.</span></span>



>[!WARNING]
><span data-ttu-id="eff05-145">删除设备组可能会影响电子邮件通知规则。</span><span class="sxs-lookup"><span data-stu-id="eff05-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="eff05-146">如果根据电子邮件通知规则配置了设备组，将从该规则中删除该组。</span><span class="sxs-lookup"><span data-stu-id="eff05-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="eff05-147">如果设备组是配置了电子邮件通知的唯一组，该电子邮件通知规则将随设备组一起删除。</span><span class="sxs-lookup"><span data-stu-id="eff05-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="eff05-148">默认情况下，具有门户访问权限的所有用户均可访问设备组。</span><span class="sxs-lookup"><span data-stu-id="eff05-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="eff05-149">可以通过将 Azure AD 用户组分配给设备组来更改默认行为。</span><span class="sxs-lookup"><span data-stu-id="eff05-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="eff05-150">不匹配任何组的设备将添加到未分组的设备 (默认) 组中。</span><span class="sxs-lookup"><span data-stu-id="eff05-150">Devices that aren't matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="eff05-151">无法更改或删除此组的排名。</span><span class="sxs-lookup"><span data-stu-id="eff05-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="eff05-152">但是，你可以更改此组的修正级别，并定义可以访问该组的 Azure AD 用户组。</span><span class="sxs-lookup"><span data-stu-id="eff05-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="eff05-153">将更改应用于设备组配置可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="eff05-153">Applying changes to device group configuration may take up to several minutes.</span></span>


### <a name="add-device-group-definitions"></a><span data-ttu-id="eff05-154">添加设备组定义</span><span class="sxs-lookup"><span data-stu-id="eff05-154">Add device group definitions</span></span>
<span data-ttu-id="eff05-155">设备组定义还可以包含每个条件的多个值。</span><span class="sxs-lookup"><span data-stu-id="eff05-155">Device group definitions can also include multiple values for each condition.</span></span> <span data-ttu-id="eff05-156">你可以将多个标记、设备名称和域设置为单个设备组的定义。</span><span class="sxs-lookup"><span data-stu-id="eff05-156">You can set multiple tags, device names, and domains to the definition of a single device group.</span></span>

1. <span data-ttu-id="eff05-157">创建新的设备组，然后选择" **设备"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="eff05-157">Create a new device group, then select **Devices** tab.</span></span>
2. <span data-ttu-id="eff05-158">为其中一个条件添加第一个值。</span><span class="sxs-lookup"><span data-stu-id="eff05-158">Add the first value for one of the conditions.</span></span>
3. <span data-ttu-id="eff05-159">选择 `+` 以添加更多相同属性类型的行。</span><span class="sxs-lookup"><span data-stu-id="eff05-159">Select `+` to add more rows of the same property type.</span></span>

>[!TIP]
> <span data-ttu-id="eff05-160">在同一条件类型的行之间使用"OR"运算符，这允许每个属性具有多个值。</span><span class="sxs-lookup"><span data-stu-id="eff05-160">Use the 'OR' operator between rows of the same condition type, which allows multiple values per property.</span></span>
> <span data-ttu-id="eff05-161">您最多可以添加 10 行 (每个) 类型的值 - 标记、设备名称、域。</span><span class="sxs-lookup"><span data-stu-id="eff05-161">You can add up to 10 rows (values) for each property type - tag, device name, domain.</span></span>

<span data-ttu-id="eff05-162">有关链接到设备组定义的信息，请参阅设备[组 -](https://sip.security.microsoft.com/homepage)Microsoft 365安全。</span><span class="sxs-lookup"><span data-stu-id="eff05-162">For more information on linking to device groups definitions, see [Device groups - Microsoft 365 security](https://sip.security.microsoft.com/homepage).</span></span>

## <a name="related-topics"></a><span data-ttu-id="eff05-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="eff05-163">Related topics</span></span>

- [<span data-ttu-id="eff05-164">使用基于角色的访问控制管理门户访问</span><span class="sxs-lookup"><span data-stu-id="eff05-164">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="eff05-165">创建和管理设备标签</span><span class="sxs-lookup"><span data-stu-id="eff05-165">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="eff05-166">使用租户 API 获取租户设备Graph列表</span><span class="sxs-lookup"><span data-stu-id="eff05-166">Get list of tenant device groups using Graph API</span></span>](/graph/api/device-list-memberof)
