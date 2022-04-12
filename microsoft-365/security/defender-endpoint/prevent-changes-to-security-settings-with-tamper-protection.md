---
title: 使用篡改保护保护安全设置
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: 使用篡改保护可防止恶意应用更改重要的安全设置。
keywords: 恶意软件、defender、防病毒、篡改防护
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.technology: mde
ms.date: 04/07/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: bcdf933de412a8141f0abc208f06cc55609f12c5
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788933"
---
# <a name="protect-security-settings-with-tamper-protection"></a>使用篡改保护保护安全设置

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

篡改保护适用于运行以下Windows版本之一的设备：

- Windows 11
- Windows 11 企业版多会话 
- Windows 10
- Windows 10 企业版多会话
- Windows Server 2022
- Windows Server 2019
- Windows服务器版本 1803 或更高版本
- Windows Server 2016
- Windows Server 2012 R2

> [!NOTE]
> Windows Server 2012 R2 中的篡改保护适用于使用新式统一解决方案包载入的设备。 有关详细信息，请参阅[将Windows服务器载入到Microsoft Defender for Endpoint服务](/microsoft-365/security/defender-endpoint/configure-server-endpoints)。


## <a name="overview"></a>概述

在某些类型的网络攻击中，不良行为者尝试在计算机上禁用安全功能，例如防病毒保护。 不良执行组件喜欢禁用安全功能，以便更轻松地访问数据、安装恶意软件或以其他方式利用数据、标识和设备。 篡改保护有助于防止发生此类事件。 通过篡改保护，恶意应用会阻止执行以下操作：

- 禁用病毒和威胁防护
- 禁用实时保护
- 关闭行为监视
- 禁用防病毒 (，例如 IOfficeAntivirus (IOAV) ) 
- 禁用云提供的保护
- 删除安全智能更新
- 对检测到的威胁禁用自动操作

### <a name="how-it-works"></a>运作方式

篡改保护实质上锁定Microsoft Defender 防病毒到其安全的默认值，并防止通过应用和方法更改安全设置，例如：

- 在Windows设备上的注册表编辑器中配置设置
- 通过 PowerShell cmdlet 更改设置
- 通过组策略编辑或删除安全设置

篡改保护不会阻止查看安全设置。 而且，篡改保护不会影响非 Microsoft 防病毒应用向Windows 安全中心应用注册的方式。 如果组织使用 Windows 10 企业版 E5，则单个用户无法更改篡改保护设置;在这些情况下，篡改保护由安全团队管理。

### <a name="what-do-you-want-to-do"></a>要执行什么操作？

|执行此任务...|请参阅本部分...|
|---|---|
|管理租户中的篡改保护 <p> 使用Microsoft 365 Defender门户打开或关闭篡改保护|[使用Microsoft 365 Defender管理组织的篡改保护](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)|
|微调组织中的篡改保护设置 <p> 使用Intune (Microsoft Endpoint Manager) 打开或关闭篡改保护。 可以使用此方法为某些或所有用户配置篡改保护。|[使用Microsoft Endpoint Manager管理组织的篡改保护](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)|
|使用Configuration Manager为组织启用 (或关闭) 的篡改保护|[将租户附加与 Configuration Manager 版本 2006 配合使用来管理组织的篡改保护](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)|
|在单个设备的 (或关闭) 上启用篡改保护|[管理单个设备上的篡改保护](#manage-tamper-protection-on-an-individual-device)|
|查看有关在设备上篡改尝试的详细信息|[查看有关篡改尝试的信息](#view-information-about-tampering-attempts)|
|查看安全建议|[查看安全建议](#review-your-security-recommendations)|
|查看常见问题解答 () 的常见问题列表|[浏览常见问题解答](#view-information-about-tampering-attempts)|

## <a name="potential-dependency-on-cloud-protection"></a>云保护的潜在依赖关系  
  
根据用于启用篡改保护的方法或管理工具，可能依赖于 [云提供的保护](cloud-protection-microsoft-defender-antivirus.md) 云提供的保护也称为云保护，或者 Microsoft 高级保护服务 (MAPS) 。

下表提供了有关方法、工具和依赖项的详细信息。

| 如何启用篡改保护 | 对云保护的依赖关系 |
|---|---|
|Microsoft Intune|否|
|使用租户附加Microsoft Endpoint Configuration Manager|否|
|Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com)|是|

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal"></a>使用Microsoft 365 Defender门户管理组织的篡改保护

可以使用Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 为租户启用或关闭篡改保护。 下面是要记住的几个要点：

- 目前，对于新部署，在Microsoft 365 Defender门户中管理篡改保护的选项默认处于启用状态。 对于现有部署，可选择加入篡改保护。 若要选择加入，<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">请在Microsoft 365 Defender门户</a>中选择 **设置** \> **终结点** \> **高级功能** \> **篡改保护**。
- 使用Microsoft 365 Defender门户管理篡改保护时，无需使用Intune或租户附加方法。
- 在Microsoft 365 Defender门户中管理篡改保护时，该设置将应用到租户范围，从而影响运行Windows 10、Windows 10 企业版多会话、Windows 11、Windows 11 企业版多会话的所有设备，Windows Server 2012 R2、Windows Server 2016、Windows Server 2019 或 Windows Server 2022。 若要微调篡改保护 (（例如为某些设备启用篡改保护，但针对其他设备关闭）) ，请对[租户附加](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)使用[Microsoft Endpoint Manager](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)或Configuration Manager。
- 如果有混合环境，则在Intune中配置的篡改保护设置优先于Microsoft 365 Defender门户中配置的设置。

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中管理篡改保护的要求

- 必须分配适当的 [权限](/microsoft-365/security/defender-endpoint/assign-portal-access) ，例如全局管理员、安全管理员或安全操作。

- Windows设备必须运行以下Windows版本之一：
  
  - Windows 11
  - Windows 11 企业版多会话 
  - Windows 10
  - Windows 10 企业版多会话
  - Windows Server 2022
  - Windows Server 2019
  - Windows服务器版本 1803 或更高版本
  - Windows Server 2016
  - Windows Server 2012 R2

有关版本的详细信息，请参阅[Windows 10发布信息](/windows/release-health/release-information)。

- 设备必须[载入到Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding)。
- 设备必须使用反恶意软件平台版本 (或更高版本 `4.18.2010.7`) 和反恶意软件引擎版本 (或更高版本 `1.1.17600.5`) 。  ([管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md).) 
- 必须启用[云传递的保护](enable-cloud-protection-microsoft-defender-antivirus.md)。

> [!NOTE]
> 通过Microsoft 365 Defender门户启用篡改保护时，需要云提供的保护，以便可以控制已启用的篡改保护状态。  
> 从 2021 年 11 月更新 (平台版本`4.18.2111.5`) 开始，如果未为设备启用云传递的保护并在 Microsoft 365 Defender 门户中启用篡改保护，则将自动为该设备启用云提供的保护以及篡改保护。   

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中打开 (或关闭) 的篡改保护

:::image type="content" source="../../media/mde-turn-tamperprotectionon.png" alt-text="在Microsoft 365 Defender门户中启用篡改保护" lightbox="../../media/mde-turn-tamperprotectionon.png":::

1. 转到Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 选择 **设置** \> **终结点**。

3. 转到 **常规** \> **高级功能**，然后启用篡改保护。

## <a name="manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager"></a>使用Microsoft Endpoint Manager管理组织的篡改保护

如果你的组织使用Microsoft Endpoint Manager (MEM) 可以在Microsoft Endpoint Manager管理中心[https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 中对组织 (或关闭) 进行篡改保护。 想要微调篡改保护设置时，请使用Intune。 例如，如果要在某些设备（但不是全部）上启用篡改保护，请使用Intune。

### <a name="requirements-for-managing-tamper-protection-in-endpoint-manager"></a>在Endpoint Manager中管理篡改保护的要求

- 设备必须[载入到Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding)。
- 必须分配适当的 [权限](/microsoft-365/security/defender-endpoint/assign-portal-access) ，例如全局管理员、安全管理员或安全操作。
- 组织使用[Microsoft Endpoint Manager来管理设备](/mem/endpoint-manager-getting-started)。  (Microsoft Endpoint Manager (需要 MEM) 许可证;MEM 包含在Microsoft 365 E3/E5、企业移动性 + 安全性 E3/E5、Microsoft 365 商业高级版、Microsoft 365 F1/F3、Microsoft 365政府 G3/G5 和相应的教育许可证中。) 
- Windows设备必须运行Windows 11或Windows 10 [1709](/windows/release-health/status-windows-10-1709)、[1803](/windows/release-health/status-windows-10-1803)、[1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) 或更高版本。  (有关版本的详细信息，请[参阅Windows 10发布信息](/windows/release-health/release-information)。) 
- 必须将Windows安全性与更新到版本 1.287.60.0 (或更高版本[的安全智能](https://www.microsoft.com/wdsi/definitions)配合使用) 。
- 设备必须使用反恶意软件平台版本 4.18.1906.3 (或更高版本) 和反恶意软件引擎版本 (或更高版本 `1.1.15500.X`) 。  ([管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md).) 

### <a name="turn-tamper-protection-on-or-off-in-microsoft-endpoint-manager"></a>在Microsoft Endpoint Manager中打开 (或关闭) 的篡改保护

:::image type="content" source="images/turnontamperprotectinmem.png" alt-text="启用篡改保护Intune" lightbox="images/turnontamperprotectinmem.png":::

1. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **Endpoint Security** \> **防病毒**，然后选择 **+创建策略**。

   - 在 **平台** 列表中，选择 **Windows 10及更高版本**。
   - 在 **配置文件** 列表中，选择 **Windows 安全中心体验**。

2. 创建包含以下设置的配置文件：

    - **启用篡改保护以防止禁用 Microsoft Defender：启用**

3. 将配置文件分配给一个或多个组。
 
### <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>使用 Configuration Manager 版本 2006 管理组织的篡改保护

如果使用的是 [版本 2006 的 Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)，则可以在Windows 10、Windows 10 企业版多会话、Windows 11 Windows 11 企业版多会话上管理篡改保护设置，使用名为“*租户附加*”的方法Windows Server 2012 R2、Windows Server 2016、Windows Server 2019 和 Windows Server 2022。 租户附加使你可以将仅本地Configuration Manager设备同步到Microsoft Endpoint Manager管理中心，然后将终结点安全配置策略传送到设备&本地集合。

> [!NOTE]
> 该过程可用于将篡改保护扩展到运行Windows 10、Windows 10 企业版多会话、Windows 11、Windows 11 企业版多会话、Windows服务器 2019 和 Windows Server 2022 的设备。 请务必查看此过程中提到的资源中的先决条件和其他信息。 对于运行新式统一解决方案[版本 2203 Configuration Manager的 Windows Server 2012 R2](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2203)。

1. 设置租户附加。 若要了解详细信息，请参阅[开始：从管理中心创建和部署终结点安全策略](/mem/configmgr/tenant-attach/endpoint-security-get-started)。

2. 在 [Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，转到 **Endpoint Security** \> **防病毒**，然后选择 **+创建策略**。

   - 在 **平台** 列表中，选择 **Windows 10、Windows 11和Windows服务器 (ConfigMgr)**。
   - 在 **配置文件** 列表中，选择 **Windows 安全中心体验 (预览)**。

3. 将策略部署到设备集合。

#### <a name="need-help-with-this-method"></a>需要此方法的帮助？

参阅以下资源：

- [Microsoft Intune中Windows 安全中心体验配置文件的设置](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [技术Community博客：宣布对Configuration Manager租户附加客户端进行篡改保护](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>管理单个设备上的篡改保护

> [!NOTE]
> 篡改保护阻止尝试通过注册表修改Microsoft Defender 防病毒设置。
>
> 若要帮助确保篡改保护不会干扰修改这些设置的非 Microsoft 安全产品或企业安装脚本，请转到 **Windows 安全中心** 并将 **安全智能** 更新到版本 1.287.60.0 或更高版本。  (请参阅 [安全智能更新](https://www.microsoft.com/wdsi/definitions)。) 完成此更新后，篡改保护将继续保护注册表设置，日志会尝试在不返回错误的情况下对其进行修改。

如果你是家庭用户，或者不受安全团队管理的设置约束，则可以使用Windows 安全中心应用来管理篡改保护。 必须在设备上拥有适当的管理员权限才能更改安全设置，例如篡改保护。

下面是你在Windows 安全中心应用中看到的内容：

:::image type="content" source="images/tamperprotectionturnedon.png" alt-text="在Windows 10 家庭版中启用篡改保护" lightbox="images/tamperprotectionturnedon.png":::

1. 选择 **“开始**”，然后开始键入 *“安全性*”。 在搜索结果中，选择 **Windows 安全中心**。

2. 选择 **病毒&威胁防护** \> **病毒&威胁防护设置**。

3. 将 **篡改保护** 设置为 **“打开** ”或 **“关闭**”。

## <a name="are-you-using-windows-server-2012-r2-2016-or-windows-version-1709-1803-or-1809"></a>是使用 Windows Server 2012 R2、2016 还是Windows版本 1709、1803 或 1809？

如果使用新式统一解决方案（Windows Server 2016版本 1709 Windows 10、1803 或 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)）使用 Windows Server 2012 R2，则不会在Windows 安全中心应用中看到 **Tamper Protection**。 可以改用 PowerShell 来确定是否启用篡改保护。

Windows Server 2016，启用篡改保护时，设置应用将无法准确反映实时保护的状态。

#### <a name="use-powershell-to-determine-whether-tamper-protection-and-real-time-protection-are-turned-on"></a>使用 PowerShell 确定是否启用篡改保护和实时保护

1. 打开Windows PowerShell应用。

2. 使用 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet。

3. 在结果列表中，查找 `IsTamperProtected` 或 `RealTimeProtectionEnabled`。  (*true* 值意味着启用篡改保护。) 

## <a name="view-information-about-tampering-attempts"></a>查看有关篡改尝试的信息

篡改尝试通常表示更大的网络攻击。 不良执行组件尝试更改安全设置，以保持未被发现状态。 如果你是组织安全团队的一员，则可以查看有关此类尝试的信息，然后采取适当的措施来缓解威胁。

检测到篡改尝试时，[会在Microsoft 365 Defender门户](/microsoft-365/security/defender-endpoint/portal-overview)中引发警报 () [https://security.microsoft.com](https://security.microsoft.com) 。

:::image type="content" source="images/tamperattemptalert.png" alt-text="Microsoft 365 Defender 门户" lightbox="images/tamperattemptalert.png":::

使用[Microsoft Defender for Endpoint中的终结点检测和响应](overview-endpoint-detection-response.md)和[高级搜寻](advanced-hunting-overview.md)功能，安全运营团队可以调查和解决此类尝试。

## <a name="review-your-security-recommendations"></a>查看安全建议

篡改防护与 [威胁&漏洞管理](next-gen-threat-and-vuln-mgt.md) 功能集成。 [安全建议](tvm-security-recommendation.md) 包括确保启用篡改保护。 例如，可以在 *篡改* 时进行搜索。 在结果中，可以选择 **“启用篡改保护”** 以了解详细信息并将其打开。

:::image type="content" source="images/tamperprotectsecurityrecos.png" alt-text="在Microsoft Defender 安全中心门户中启用篡改保护" lightbox="images/tamperprotectsecurityrecos.png":::

若要详细了解威胁&漏洞管理，请参阅[仪表板见解 - 危险和漏洞管理](tvm-dashboard-insights.md#dashboard-insights---threat-and-vulnerability-management)。

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="on-which-versions-of-windows-can-i-configure-tamper-protection"></a>在哪些版本的Windows可以配置篡改保护？

- Windows 11
- Windows 11 企业版多会话
- Windows 10 OS [1709](/windows/release-health/status-windows-10-1709)、[1803](/windows/release-health/status-windows-10-1803)、[1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) 或更高版本以及[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)。
- Windows 10 企业版多会话
  
如果在租户附加的情况下使用 Configuration Manager 版本 2006，则可以将篡改保护扩展到 Windows Server 2012 R2、Windows Server 2016、Windows Server 2019 和 Windows Server 2022。 请参阅 [租户附加：从管理中心创建和部署终结点安全防病毒策略 (预览) ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)。

### <a name="will-tamper-protection-affect-non-microsoft-antivirus-registration-in-the-windows-security-app"></a>篡改保护是否会影响Windows 安全中心应用中的非 Microsoft 防病毒注册？

不是。 非 Microsoft 防病毒产品/服务将继续向Windows 安全中心应用程序注册。

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>如果Microsoft Defender 防病毒在设备上未处于活动状态，会发生什么情况？

载入到Microsoft Defender for Endpoint的设备将在被动模式下运行Microsoft Defender 防病毒。 在这些情况下，篡改保护将继续保护服务及其功能。

### <a name="how-do-i-turn-tamper-protection-on-or-off"></a>如何实现打开或关闭篡改保护？

如果你是家庭用户，请参阅 [管理单个设备上的篡改保护](#manage-tamper-protection-on-an-individual-device)。

如果你是使用[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)的组织，则应该能够管理Intune类似于管理其他终结点保护功能的方式的篡改保护。 请参阅本文的以下部分：

- [使用Microsoft Endpoint Manager管理篡改保护](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)
- [使用Microsoft 365 Defender门户管理篡改保护](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-with-group-policy"></a>在Intune中配置篡改保护如何影响我如何使用组策略管理Microsoft Defender 防病毒？

组策略不适用于篡改保护。 当启用篡改保护时，将忽略对Microsoft Defender 防病毒设置所做的更改。

### <a name="if-we-use-microsoft-intune-to-configure-tamper-protection-does-it-apply-only-to-the-entire-organization"></a>如果我们使用Microsoft Intune来配置篡改保护，它是否仅适用于整个组织？

你可以灵活地使用Intune配置篡改保护。 可以面向整个组织，也可以选择特定的设备和用户组。

### <a name="can-i-configure-tamper-protection-with-microsoft-endpoint-configuration-manager"></a>是否可以使用Microsoft Endpoint Configuration Manager配置篡改保护？

如果使用的是租户附加，则可以使用Microsoft Endpoint Configuration Manager。 参阅以下资源：

- [使用 Configuration Manager 版本 2006 管理组织的篡改保护](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [技术Community博客：宣布对Configuration Manager租户附加客户端进行篡改保护](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>我有Windows E3 注册。 是否可以在Intune中使用配置篡改保护？

目前，在Intune中配置篡改保护仅[适用于Microsoft Defender for Endpoint的客户](/microsoft-365/security/defender-endpoint)。

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>如果尝试在设备上启用篡改防护时，在Intune、Microsoft Endpoint Configuration Manager和Windows管理检测中更改Microsoft Defender for Endpoint设置会发生什么情况？

无法更改受篡改保护保护的功能;忽略此类更改请求。

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>我是企业客户。 本地管理员是否可以更改其设备上的篡改保护？

不是。 本地管理员无法更改或修改篡改保护设置。

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>如果我的设备载入了Microsoft Defender for Endpoint，然后进入脱机状态，会发生什么情况？

如果设备从Microsoft Defender for Endpoint中卸载，则会启用篡改保护，这是非托管设备的默认状态。

### <a name="if-the-status-of-tamper-protection-changes-are-alerts-shown-in-the-microsoft-365-defender-portal"></a>如果篡改保护的状态发生更改，警报是否显示在Microsoft 365 Defender门户中？

是。 警报显示在 [https://security.microsoft.com](https://security.microsoft.com)**“警报**”下。

安全运营团队还可以使用搜寻查询，如以下示例：

`AlertInfo|where Title == "Tamper Protection bypass"`

[查看有关篡改尝试的信息](#view-information-about-tampering-attempts)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="see-also"></a>另请参阅

- [使用Microsoft Intune的Endpoint Protection帮助保护Windows电脑](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [获取 Microsoft Defender for Endpoint 概述](/microsoft-365/security/defender-endpoint)
- [更好地结合：Microsoft Defender 防病毒软件和 Microsoft Defender for Endpoint](why-use-microsoft-defender-antivirus.md)
