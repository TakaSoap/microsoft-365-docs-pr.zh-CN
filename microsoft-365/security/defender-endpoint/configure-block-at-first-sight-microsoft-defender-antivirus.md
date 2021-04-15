---
title: 启用"首次看到时阻止"以在数秒后检测恶意软件
description: 打开"首次看到时阻止"功能，以在数秒钟内检测和阻止恶意软件。
keywords: 扫描， BAFS， 恶意软件， 首次看到， 首次看到， 云， defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765751"
---
# <a name="turn-on-block-at-first-sight"></a>在首次看到时打开阻止

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

"首次看到时阻止"提供了一种在数秒钟内检测和阻止新恶意软件的方法。 当启用某些先决条件设置时，默认情况下会启用此保护。 这些设置包括云保护、指定的示例提交超时 (如 50 秒) ，以及文件阻止级别较高。 在大多数企业组织中，默认情况下会通过 Microsoft Defender 防病毒部署启用这些设置。 

你可以 [指定在基于云的](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 保护服务分析文件时阻止文件运行的时间。 此外， [还可以自定义在](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 文件被阻止时显示在用户桌面上的消息。 您可以更改公司名称、联系人信息和邮件 URL。

>[!TIP]
>请访问 Microsoft Defender for Endpoint 演示网站 [，demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 以确认这些功能是否正常工作，并查看这些功能如何工作。

## <a name="how-it-works"></a>运作方式

当 Microsoft Defender 防病毒遇到可疑但未检测到的文件时，它会查询云保护后端。 云后端对文件应用启发式、机器学习和自动分析，以确定文件是否是恶意威胁。

Microsoft Defender 防病毒使用多个检测和防护技术提供准确、智能和实时的保护。 若要了解更多信息，请参阅此博客：了解 Microsoft Defender for Endpoint 下一代保护 [的核心高级技术](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。
![Microsoft Defender AV 引擎列表](images/microsoft-defender-atp-next-generation-protection-engines.png)  

在 Windows 10 版本 1803 或更高版本中，"首次看到时阻止"可以阻止不可移植的可执行文件 (如 JS、VBS 或宏) 可执行文件。

"首次看到时阻止"仅对从 Internet 下载的可执行文件和不可移植的可执行文件或源自 Internet 区域的文件使用云保护后端。 通过云后端检查 .exe 文件的哈希值，以确定该文件以前是否未检测到。

如果云后端无法确定，Microsoft Defender 防病毒将锁定文件，并将其副本上传到云。 云执行其他分析，以在允许文件运行或在将来遇到时阻止它，具体取决于它确定文件是恶意文件还是安全文件。

在许多情况下，此过程可以将新恶意软件的响应时间从几小时缩短到秒。

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>使用 Microsoft Intune 打开"首次看到时阻止"

> [!TIP]
> Microsoft Intune 现在是 Microsoft Endpoint Manager 的一部分。

1. In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) ， navigate to **Devices**  >  **Configuration profiles**.

2. 使用设备限制配置文件类型 **选择或创建** 配置文件。

3. 在设备 **限制** 配置文件的配置设置中，在 Microsoft Defender 防病毒下设置或确认 **以下设置**：

   - **云保护：** 已启用
   - **文件阻止级别**：高
   - **云文件扫描的扩展名**：50
   - **在提交示例之前提示用户**：在不提示的情况下发送所有数据

   ![Intune config](images/defender/intune-block-at-first-sight.png)

4. 保存设置。

> [!TIP]
> - 将文件阻止级别设置为 **"高** "将应用强级别的检测。 如果文件阻止导致对合法文件进行误报检测的不太可能，可以 [还原隔离的文件](./restore-quarantined-files-microsoft-defender-antivirus.md)。
> - 有关在 Intune 中配置 Microsoft Defender 防病毒设备限制的信息，请参阅在 Microsoft Intune 中配置 [设备限制设置](/intune/device-restrictions-configure)。
> - 有关 Intune 中的 Microsoft Defender 防病毒设备限制的列表，请参阅 Intune 中的 [Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) (和) 设备限制。

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>使用 Microsoft Endpoint Manager 打开"首次看到时阻止"

> [!TIP]
> 如果你正在寻找 Microsoft Endpoint Configuration Manager，它现在是 Microsoft Endpoint Manager 的一部分。

1. 在 Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () ，转到 **终结点安全**  >  **防病毒**。

2. 选择现有策略，或者使用 **Microsoft Defender** 防病毒配置文件类型创建新策略。

3. 设置或确认以下配置设置：

   - **启用云保护：** 是
   - **云提供的保护级别**：高
   - **Defender 云扩展超时（以秒数表示）：50**

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="终结点管理器中的&quot;首次看到时阻止&quot;设置":::

4. 将 Microsoft Defender 防病毒配置文件应用于组，如所有用户、所有 **设备** 或 **所有用户和设备**。

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>使用组策略启用"首次看到时阻止"

> [!NOTE]
> 我们建议使用 Intune 或 Microsoft Endpoint Manager 打开"首次看到时阻止"。 

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。 

2. 使用组 **策略管理编辑器** 转到计算机 **配置** 管理  >  **模板**  >  **Windows 组件** Microsoft Defender  >  **防病毒**  >  **MAPS**。 

3. 在"MAPS"部分，双击"配置'首次看到时阻止 **'功能**"，将其设置为"已启用"，然后选择"确定 **"。**

    > [!IMPORTANT]
    > 设置为 **始终提示 (0)** 会降低设备的保护状态。 设置为" **从不发送 (2)** 意味着首次看到时阻止将无法正常工作。

4. 在 MAPS 部分中，双击"需要进一步 **分析时发送文件示例"，** 并将其设置为 **"已启用"。** 在 **"需要进一步分析时发送文件示例"下**，选择 **"发送所有示例**"，然后单击"确定 **"。**

5. 如果更改了任何设置，请在整个网络中重新部署组策略对象，以确保覆盖所有终结点。

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a>确认在个别客户端上启用"首次看到时阻止"

你可以确认使用 Windows 安全设置在个别客户端上启用了"首次看到时阻止"。

只要启用了云提供的保护和自动提交示例，就会自动启用"首次看到时阻止"。

1. 打开 Windows 安全应用。

2. 选择 **病毒&威胁防护**"，然后在"病毒&**威胁防护设置**"下，选择"管理 **设置"。**

   ![Windows 安全应用中的病毒&威胁防护设置标签的屏幕截图](images/defender/wdav-protection-settings-wdsc.png)

3. 确认 **云提供的保护和****自动提交** 示例均已打开。

> [!NOTE]
> - 如果使用组策略配置和部署先决条件设置，本部分中所述的设置将灰出，并且无法用于个别终结点。 
> - 必须先通过组策略对象所做的更改部署到个别终结点，然后才能在 Windows 设置中更新设置。

## <a name="validate-block-at-first-sight-is-working"></a>验证"首次看到时阻止"是否正常工作

若要验证该功能是否正常工作，请按照验证网络和云之间的连接[中的指南。](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)

## <a name="turn-off-block-at-first-sight"></a>关闭"首次看到时阻止"

> [!CAUTION]
> 关闭"首次看到时阻止"将降低设备 (和) 保护状态。

如果你想要保留先决条件设置而不实际使用"首次看到时阻止"保护，你可以选择禁用"首次看到时阻止"。 如果遇到延迟问题或要测试功能对网络的影响，可能会暂时关闭首次看到时阻止。 但是，建议不要永久禁用首次看到时阻止。

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>使用 Microsoft Endpoint Manager 关闭"首次看到时阻止"

1. 转到 Microsoft Endpoint Manager 管理中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 并登录。

2. 转到 **终结点安全**  >  **防病毒**，然后选择你的 Microsoft Defender 防病毒策略。

3. 在 **"管理"** 下，选择"**属性"。**

4. 在"**配置设置"旁边，** 选择"编辑 **"。**

5. 更改以下一个或多个设置：

   - 将 **"启用云提供的保护"设置为****"否**"**或"未配置"。**
   - 将 **云提供的保护级别设置为****"未配置"。**
   - 清除 **"Defender 云扩展超时（以秒表示）"** 框。

6. 查看并保存设置。

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>使用组策略关闭"首次看到时阻止"

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，**然后单击编辑。**

2. 使用组 **策略管理编辑器** 转到计算机 **配置，** 然后单击 **管理模板**。

3. 通过 Windows组件 Microsoft Defender 防病毒 MAPS  >  **展开**  >  **树**。

4. 双击配置 **'首次看到时阻止'功能** ，将选项设置为 **已禁用**。

    > [!NOTE]
    > 禁用"首次看到时阻止"不会禁用或更改先决条件组策略。

## <a name="see-also"></a>另请参阅

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)

- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)