---
title: 在 Microsoft Defender for Endpoint 中创建和管理设备组
description: 通过确认适用于该组的规则，创建设备组并设置其自动修正级别
keywords: 设备组， 组， 修正， 级别， 规则， aad 组， 角色， 分配， 排名
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ad66a651406706d0e2730f9913839540418bb02b
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170641"
---
# <a name="create-and-manage-device-groups"></a>创建和管理设备组

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- Azure Active Directory
- Office 365
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

在企业方案中，通常会为安全运营团队分配一组设备。 这些设备根据一组属性（如域、计算机名称或指定标记）分组在一起。

在 Microsoft Defender for Endpoint 中，你可以创建设备组并使用它们：

- 将相关警报和数据的访问权限限制为Azure AD [RBAC](rbac.md)角色的特定组
- 为不同的设备集配置不同的自动修正设置
- 分配特定修正级别以在自动调查期间应用
- 在调查中，使用组筛选器 **将"设备** "列表筛选到特定 **设备** 组。

可以在基于角色的访问 (RBAC) 上下文中创建设备组，以控制哪些人可以通过将设备组 () 分配给用户组来查看信息。 有关详细信息，请参阅使用基于角色 [的访问控制管理门户访问](rbac.md)。

> [!TIP]
> 有关 RBAC 应用程序的全面了解，请阅读 [：SOC 是否使用 RBAC 运行平面](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)。

在创建设备组的过程中，你将：

- 设置该组的自动修正级别。 有关修正级别详细信息，请参阅使用 [自动调查调查和修正威胁](automated-investigations.md)。
- 根据设备名称、域、标记和操作系统平台指定匹配规则，以确定哪些设备组属于该组。 如果设备还与其他组匹配，则只会将设备添加到排名最高的设备组中。
- 选择Azure AD组的用户组。
- 创建设备组后，相对于其他组对设备组进行排名。

> [!NOTE]
> 如果你未向设备组分配任何组，则Azure AD组。

## <a name="create-a-device-group"></a>创建设备组

1. 在导航窗格中，**选择"设置** \>  \> **终结点权限设备** \> **组"。**

2. 单击 **"添加设备组"。**

3. 输入组名称和自动化设置，并指定用于确定哪些设备属于该组的匹配规则。 请参阅 [自动调查如何启动](automated-investigations.md#how-the-automated-investigation-starts)。

    > [!TIP]
    > 如果要按组织单位对设备进行分组，可以配置组附属项的注册表项。 有关设备标记详细信息，请参阅创建 [和管理设备标记](machine-tags.md)。

4. 预览将匹配此规则的几个设备。 如果您对规则感到满意，请单击"用户访问 **"** 选项卡。

5. 分配可以访问你创建的设备组的用户组。

    > [!NOTE]
    > 只能向已Azure AD RBAC 角色的用户组授予访问权限。

6. 单击“关闭”。 将应用配置更改。

## <a name="manage-device-groups"></a>管理设备组

你可以升级或降级设备组的排名，以便它在匹配期间获得更高或更低的优先级。 当设备与多个组匹配时，它只会添加到排名最高的组中。 还可以编辑和删除组。

> [!WARNING]
> 删除设备组可能会影响电子邮件通知规则。 如果根据电子邮件通知规则配置了设备组，将从该规则中删除该组。 如果设备组是配置了电子邮件通知的唯一组，该电子邮件通知规则将随设备组一起删除。

默认情况下，具有门户访问权限的所有用户均可访问设备组。 可以通过向设备组分配Azure AD用户组来更改默认行为。

不匹配任何组的设备将添加到未分组设备 (默认) 组中。 无法更改或删除此组的排名。 但是，您可以更改此组的修正级别，并定义Azure AD访问该组的用户组的级别。

> [!NOTE]
> 将更改应用于设备组配置可能需要几分钟。

### <a name="add-device-group-definitions"></a>添加设备组定义

设备组定义还可以包含每个条件的多个值。 你可以将多个标记、设备名称和域设置为单个设备组的定义。

1. 创建新的设备组，然后选择" **设备"** 选项卡。
2. 为其中一个条件添加第一个值。
3. 选择 `+` 以添加更多相同属性类型的行。

> [!TIP]
> 在同一条件类型的行之间使用"OR"运算符，这允许每个属性具有多个值。
> 您最多可以添加 10 行 (每个) 类型的值 - 标记、设备名称、域。

有关链接到设备组定义的信息，请参阅设备组 - Microsoft 365[安全](https://sip.security.microsoft.com/homepage)。

## <a name="related-topics"></a>相关主题

- [使用基于角色的访问控制管理门户访问](rbac.md)
- [创建和管理设备标签](machine-tags.md)
- [使用租户 API 获取租户设备Graph列表](/graph/api/device-list-memberof)
