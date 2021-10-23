---
title: 启用“首次看到时阻止”来在几秒内检测恶意软件
description: 打开“首次看到时阻止”功能来在几秒内检测和阻止恶意软件。
keywords: 扫描，首次看到时阻止，恶意软件，首次看到，云，Defender，防病毒
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 10/18/2021
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 53ef056a61da1dca83c1c6bdf611e37a50dc9008
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60552832"
---
# <a name="turn-on-block-at-first-sight"></a>打开“首次看到时阻止”

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

此文章解释了名为“首次看到时阻止”的防病毒/防恶意软件功能，并介绍了如何为组织启用“首次看到时阻止”功能。

> [!TIP]
> 此文章适合的读者为管理组织安全设置的企业管理员和 IT 专业人员。 如果你不是企业管理员或 IT 专业人员，但你对“首次看到时阻止”有疑问，请参阅[不是企业管理员或 IT 专业人员？](#not-an-enterprise-admin-or-it-pro)部分。

## <a name="what-is-block-at-first-sight"></a>什么是“首次看到时阻止”？

“首次看到时阻止”是下一代保护的一种威胁保护功能，它能够在几秒内检测新的恶意软件并将其阻止。 “首次看到时阻止”的启用方式是启用某些特定的安全设置。 这些设置包括：

- 云端保护；
- 指定的示例提交超时（比如 50 秒）；以及
- 高文件阻止级别。

在大多数企业组织中，需要启用“首次看到时阻止”的设置都已在部署 Microsoft Defender 防病毒时配置了。

## <a name="how-it-works"></a>运作方式

当 Microsoft Defender 防病毒软件遇到未检测到的可疑文件时，它会查询云保护后端。 云后端将应用启发式、机器学习以及自动文件分析，以确定文件是恶意文件还是非威胁文件。

Microsoft Defender 防病毒使用多种检测和防护技术来提供准确、智能、实时的保护。

![Microsoft Defender AV 引擎列表。](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> 若要了解更多信息，请参阅[（博客）了解 Microsoft Defender for Endpoint 下一代保护的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>关于“首次看到时阻止”的一些须知

- 在 Windows 10 1803 版本或更高版本中，“首次看到时阻止”现在可以阻止不可移植的可执行文件（如 JS、VBS 或宏）和可执行文件。

- “首次看到时阻止”仅对从 Internet 下载或者源自 Internet 区域的可执行文件和不可移植的可执行文件使用云保护后端。 通过云后端检查 .exe 文件的哈希值，确定之前是否未检测过此文件。

- 如果云后端无法做出决定，Microsoft Defender 防病毒会锁定该文件，同时将副本上传到云。 云将执行更多分析以得出结论：以后遇到该文件，是允许运行还是阻止（具体取决于它确定文件是恶意文件还是非威胁文件）。

- 在许多情况下，此过程可将对新恶意软件的响应时间从几小时减少到几秒。

- 你可以[指定当基于云的保护服务在分析文件时，过多久后阻止文件运行](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。 另外，当文件被阻止时，你可以[自定义用户桌面上显示的消息](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)。 可更改公司名称、联系信息、消息 URL。

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>用 Microsoft Intune 打开“首次看到时阻止”

> [!TIP]
> Microsoft Intune 现属于 Microsoft Endpoint Manager。

1. 在 Microsoft Endpoint Manager 管理中心 (<https://endpoint.microsoft.com>)，导航到“**设备**”\>“**配置用户配置**”。

2. 使用“**设备限制**”用户配置类型选择或创建用户配置。

3. 在设备限制用户配置的“**配置设置**”中，在“**Microsoft Defender 防病毒**”下设置或确认以下设置：

   - **云端保护**：启用
   - **文件阻止级别**：高
   - **云扫描文件的时长拓展**：50
   - **在提交示例之前提示用户**：在不提示的情况下发送所有数据

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="首次看到 Intune 配置时阻止。":::

4. 保存设置。

> [!TIP]
>
> - 将文件阻止级别设置为 **高** 将应用高强度检测级别。 如果发生了意外情况，导致对合法文件做出了误报检测，你的安全操作团队可以[还原隔离的文件](./restore-quarantined-files-microsoft-defender-antivirus.md)。
> - 有关在 Intune 中配置 Microsoft Defender 防病毒设备限制的详细信息，请参阅[在 Microsoft Intune 中配置设备限制设置](/intune/device-restrictions-configure)。
> - 有关 Intune 中的 Microsoft Defender 防病毒设备限制的列表，请参阅 [Intune 中 Windows 10（和更高版本）设置的设备限制](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>用 Microsoft Endpoint Manager 打开“首次看到时阻止”

> [!TIP]
> 如果你在找 Microsoft Endpoint Configuration Manager，它现在属于 Microsoft Endpoint Manager。

1. 在 Microsoft Endpoint Manager (<https://endpoint.microsoft.com>) 中，转到 **Endpoint 安全性** \> **防病毒**。

2. 选择现有策略，或使用 **Microsoft Defender 防病毒** 用户配置类型创建新策略。

3. 设置或确认以下配置设置：

   - **打开云端保护**：是
   - **云端保护等级**：高
   - **Defender 云扩展超时（秒）**：50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Endpoint Manager 中的“首次看到时阻止”。":::

4. 应用 Windows Defender 防病毒的用户配置到组，例如“**所有用户**”、“**所有设备**”或“**所有用户和设备**”。

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>使用组策略打开“首次看到时阻止”

> [!NOTE]
> 我们建议使用 Intune 或 Microsoft Endpoint Manager 来打开“首次看到时阻止”。

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择 **编辑**。

2. 使用“**组策略管理编辑器**”转到“**计算机配置**”\>“**管理模板**”\>“**Windows 组件**”\>“**Microsoft Defender 防病毒**”\>“**MAPS**”。

3. 在“MAPS”节中，双击“**配置“首次看到时阻止”功能**”，将其设为“**启用**”，然后选择“**OK**”。

    > [!IMPORTANT]
    > 设为 **始终提示 (0)** 会降低设备的保护状态。 设为始 **终不发送 (2)** 意味着“首次看到时阻止”将不起作用。

4. 在“MAPS”节中，双击“**需要进一步分析时发送文件样本**”，将其设为“**启用**”。 在“**需要进一步分析时发送文件样本**”下，选择“**发送所有样本**”，然后选择“**OK**”。

5. 如往常一样在网络上中心部署你的组策略对象。

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>在客户端上确认“首次看到时阻止”是否已启用

可以使用 Windows 安全应用来确认“首次看到时阻止”功能是否已在某个客户端设备上启用。 只要同时启用了 **云端保护** 和 **自动提交样本**，就会自动启用“首次看到时阻止”。

1. 打开 Windows 安全应用。

2. 选择“**病毒和威胁防护**”，然后在“**病毒和威胁防护设置**”下选择“**管理设置**”。

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Windows 安全应用中病毒和威胁防护设置标签的屏幕截图":::

3. 确认 **云端保护** 和 **自动提交样本** 已开启。

> [!NOTE]
>
> - 如果已使用组策略配置并部署了先决条件设置，本部分所述的设置将灰显，并且在个别终结点上不可用。
> - 通过组策略对象进行的更改必须先部署到个别终结点，然后 Windows 设置中的相关设置才会更新。

## <a name="validate-block-at-first-sight-is-working"></a>验证“首次看到时阻止”是否正常工作

若要验证该功能是否正常工作，请下载[“首次看到时阻止”示例文件](https://demo.wd.microsoft.com/Page/BAFS)。 若要下载该文件，你需要在 Azure AD 中拥有分配有安全管理员或全局管理员角色的帐户。

若要验证该功能是否正常工作，请按照[验证网络和云之间的连接](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)中的指导进行操作。

## <a name="turn-off-block-at-first-sight"></a>关闭“首次看到时阻止”

> [!CAUTION]
> 关闭“首次看到时阻止”会降低设备和网络的保护状态。

如果希望保留先决条件设置，而不使用“首次看到时阻止”保护，则可以选择禁用“首次看到时阻止”。 你可以暂时关闭“首次看到时阻止”来看看这对你的网络有什么影响。 但是，我们不建议长期禁用“首次看到时阻止”。

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>用 Microsoft Endpoint Manager 关闭“首次看到时阻止”

1. 转到 Microsoft Endpoint Manager 管理中心 (<https://endpoint.microsoft.com>) 并登录。

2. 转到“**终结点安全**”\>“**防病毒**”，然后选择你的 Microsoft Defender 防病毒策略。

3. 在“**管理**”下，选择“**属性**”。

4. 选择“**配置设置**”旁的“**编辑**”。

5. 请执行下列一项或多项操作：

   - 将“**打开云端保护**”设为“**不**”或“**未配置**”。
   - 将“**云端保护级别**”设为“**未配置**”。
   - 清空 **Defender 云扩展超时（秒）** 复选框。

6. 检查并保存你的设置。

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>使用组策略关闭“首次看到时阻止”

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择“**编辑**”。

2. 在 **策略管理编辑器** 中， 转到“**计算机配置**”并选择“**管理模板**”。

3. 将树展开到 “**Windows 组件**”\>“**Windows Defender 防病毒**”\>“**MAPS**”。

4. 双击“**配置“首次看到时阻止”功能**”，并将该选项设置为“**禁用**”。

    > [!NOTE]
    > 禁用“首次看到时阻止”不会禁用或更改先决条件组策略。

## <a name="not-an-enterprise-admin-or-it-pro"></a>不是企业管理员或 IT 专业人士？

如果你不是企业管理员或 IT 专业人员，但你对“首次看到时阻止”有疑问的话，请阅读此节。 “首次看到时阻止”是一种威胁保护功能，它能够在几秒内检测和阻止恶意软件。 其实没有某个设置叫“首次看到时阻止”，此功能的启用是通过配置设备上的某些设置来实现的。

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>如果在自己的设备上管理“首次看到时阻止”的开启与关闭

如果你的个人设备不受组织管理，你可能想知道如何开启或关闭“首次看到时阻止”。 你可以使用 Windows 安全应用来管理“首次看到时阻止”。

1. 在你的 Windows 10 或 Windows 11 电脑上，打开 Windows 安全中心应用。

2. 选择“**病毒和威胁防护**”。

3. 在“**病毒和威胁防护设置**”下选择“**管理设置**”。

4. 采取以下步骤之一：

   - 若要启用“首次看到时阻止”，请确保同时启用了“**云端保护**”和“**自动提交样本**”。

   - 若要禁用启用“首次看到时阻止”，请禁用“**云端保护**”或“**自动提交样本**”。

     > [!CAUTION]
     > 关闭“首次看到时阻止”会降低设备的保护级别。 我们不建议长期禁用“首次看到时阻止”。


## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)
- [通过 Windows 安全持续受到保护](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
