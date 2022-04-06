---
title: 对文件执行响应操作Microsoft Defender for Endpoint
description: 通过停止和隔离文件或阻止文件并检查活动详细信息，对与文件相关的警报执行响应操作。
keywords: 响应、停止和隔离、阻止文件、深度分析
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
ms.openlocfilehash: 8bfa08a92a011d32cdc30e2f68052715b4075fdf
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665505"
---
# <a name="take-response-actions-on-a-file"></a>对文件执行响应操作

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-responddile-abovefoldlink)。

通过停止和隔离文件或阻止文件来快速响应检测到的攻击。 对文件执行操作后，可以在操作中心检查活动详细信息。

文件的详细配置文件页上提供了响应操作。 在此页面上，可以通过切换 **新文件页** 在新页面和旧页面布局之间切换。 本文的其余部分介绍较新的页面布局。

响应操作沿文件页顶部运行，包括：

- 停止和隔离文件
- 添加指示器
- 下载文件
- 咨询威胁专家
- 操作中心

还可以提交文件进行深入分析，以便在安全的云沙盒中运行该文件。 分析完成后，你将收到一份详细的报表，其中提供了有关文件行为的信息。 可以通过选择" **深度** 分析"选项卡提交文件以进行深入分析并读取过去的报表。它位于文件信息卡片下方。

某些操作需要某些权限。 下表描述了某些权限可以对可移植可执行文件 (PE) 和非 PE 文件执行的操作：

|权限|PE 文件|非 PE 文件|
|---|:---:|:---:|
|查看数据|X|X|
|警报调查|&#x2611;|X|
|实时响应基本|X|X|
|实时响应高级|&#x2611;|&#x2611;|

有关角色的详细信息，请参阅 [创建和管理基于角色的访问控制的角色](user-roles.md)。

## <a name="stop-and-quarantine-files-in-your-network"></a>停止并隔离网络中的文件

可以通过停止恶意进程并隔离观察到的文件，在组织中包含攻击。

> [!IMPORTANT]
> 只有在以下情况下才能执行此操作：
>
> - 正在执行操作的设备正在运行Windows 10版本 1703 或更高版本，并且Windows 11
> - 该文件不属于受信任的第三方发布者或未由 Microsoft 签名
> - Microsoft Defender 防病毒至少必须在被动模式下运行。 有关详细信息，请参阅[Microsoft Defender 防病毒兼容性](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

**"停止和隔离文件**"操作包括停止正在运行的进程、对文件进行隔离，以及删除永久性数据（如注册表项）。

此操作对具有 Windows 10 版本 1703 或更高版本的设备生效，Windows 11，在过去 30 天内观察到该文件。

> [!NOTE]
> 你将能够随时从隔离区还原文件。

### <a name="stop-and-quarantine-files"></a>停止和隔离文件

1. 选择要停止和隔离的文件。 可以从以下任何视图中选择文件，也可以使用"搜索"框：

   - **警报** - 单击警报故事时间线中的"说明"或"详细信息"中的相应链接
   - **搜索框** - 从下拉菜单中选择 **"文件** "，然后输入文件名

   > [!NOTE]
   > 停止和隔离文件操作限制为最多 1000 台设备。 若要在更多设备上停止文件，请参阅 [添加指示器来阻止或允许文件](#add-indicator-to-block-or-allow-a-file)。

2. 转到顶部栏并选择 **"停止和隔离文件**"。

   :::image type="content" source="images/atp-stop-quarantine-file.png" alt-text="停止和隔离文件操作" lightbox="images/atp-stop-quarantine-file.png":::

3. 指定原因，然后选择 **"确认**"。

   :::image type="content" source="images/atp-stop-quarantine.png" alt-text="&quot;停止和隔离&quot;文件页" lightbox="images/atp-stop-quarantine.png":::

   操作中心显示提交信息：

   :::image type="content" source="images/atp-stopnquarantine-file.png" alt-text="停止和隔离文件操作中心" lightbox="images/atp-stopnquarantine-file.png":::

   - **提交时间** - 显示提交操作的时间。
   - **成功** - 显示已停止和隔离文件的设备数。
   - **失败** - 显示操作失败的设备数以及有关故障的详细信息。
   - **挂起** - 显示文件尚未停止和隔离的设备数。 如果设备处于脱机状态或未连接到网络，这可能需要一些时间。

4. 选择任何状态指示器以查看有关操作的详细信息。 例如，选择 **"失败** "以查看操作失败的位置。

#### <a name="notification-on-device-userf"></a>设备用户端上的通知

从设备中删除文件时，将显示以下通知：

:::image type="content" source="images/atp-notification-file.png" alt-text="设备上用户的通知" lightbox="images/atp-notification-file.png":::

在设备时间线中，为停止和隔离文件的每个设备添加一个新事件。

在针对在整个组织中广泛使用的文件实施操作之前，会显示警告。 它用于验证操作是否为预期。

## <a name="restore-file-from-quarantine"></a>从隔离区还原文件

如果在调查后确定文件是干净的，则可以回滚并从隔离区中删除文件。 在隔离文件的每个设备上运行以下命令。

1. 在设备上打开提升的命令行提示符：

   1. 转到“**开始**”并键入“_cmd_”。

   1. 右键单击“**命令提示符**”，然后选择“**以管理员身份运行**”。

2. 输入以下命令，然后按 **Enter**：

   ```dos
   "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -Name EUS:Win32/CustomEnterpriseBlock -All
   ```

   > [!NOTE]
   > 在某些情况下， **ThreatName** 可能显示为：EUS：Win32/CustomEnterpriseBlock！cl。
   >
   > Defender for Endpoint 将还原过去 30 天内在此设备上隔离的所有自定义阻止文件。

> [!IMPORTANT]
> 被隔离为潜在网络威胁的文件可能无法恢复。 如果用户尝试在隔离后还原文件，则该文件可能无法访问。 这可能是由于系统不再具有访问该文件的网络凭据。 通常，这是临时登录到系统或共享文件夹的结果，并且访问令牌已过期。

## <a name="download-or-collect-file"></a>下载或收集文件

通过响应操作选择 **"下载文件** "，可以下载包含文件的受密码保护的本地.zip存档。 浮出控件将显示，你可以在其中记录下载文件的原因并设置密码。

默认情况下，应能够下载处于隔离状态的文件。

:::image type="content" source="images/atp-download-file-action.png" alt-text="下载文件操作" lightbox="images/atp-download-file-action.png":::

### <a name="download-quarantined-files"></a>下载隔离的文件

已由Microsoft Defender 防病毒或安全团队隔离的文件将根据[示例提交配置](enable-cloud-protection-microsoft-defender-antivirus.md)以符合性的方式保存。 安全团队可以通过"下载文件"按钮直接从文件的详细信息页下载文件。 **默认情况下，此预览功能将启用"打开"。**

位置取决于组织 (欧盟、英国或美国) 的地理设置。 每个组织只收集一次隔离文件。 从服务信任门户了解有关 Microsoft 数据保护的详细信息 https://aka.ms/STP。

启用此设置有助于安全团队检查潜在的错误文件，并以风险较低的方式快速调查事件。 但是，如果需要关闭此设置，请转到 **设置** \> **终结点** \> **高级功能** \> **下载隔离的文件** 以调整设置。 [详细了解高级功能](advanced-features.md)

#### <a name="backing-up-quarantined-files"></a>备份隔离的文件

系统可能会提示用户在备份隔离文件之前提供显式同意，具体取决于示 [例提交配置](enable-cloud-protection-microsoft-defender-antivirus.md#use-group-policy-to-turn-on-cloud-protection)。

如果关闭示例提交，则此功能将不起作用。 如果自动示例提交设置为请求用户的权限，则只会收集用户同意发送的示例。

> [!IMPORTANT]
> 下载隔离的文件要求：
>
> - 组织在活动模式下使用Microsoft Defender 防病毒
> - 防病毒引擎版本为 1.1.17300.4 或更高版本。 请参阅 [每月平台和引擎版本](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)
> - 已启用基于云的保护。 请参阅 [启用云提供的保护](enable-cloud-protection-microsoft-defender-antivirus.md)
> - 示例提交已启用
> - 设备Windows 10版本 1703 或更高版本，或Windows服务器 2016 或 2019、Windows Server 2022 或Windows 11

### <a name="collect-files"></a>收集文件

如果Microsoft Defender for Endpoint尚未存储文件，则无法下载它。 相反，会在同一位置看到 **"收集文件** "按钮。 如果过去 30 天内未在组织中看到文件，则将禁用 **收集文件** 。
> [!Important]
> 被隔离为潜在网络威胁的文件可能无法恢复。 如果用户尝试在隔离后还原文件，则该文件可能无法访问。 这可能是由于系统不再具有访问该文件的网络凭据。 通常，这是临时登录到系统或共享文件夹的结果，并且访问令牌已过期。

## <a name="add-indicator-to-block-or-allow-a-file"></a>添加指示器以阻止或允许文件

通过禁止潜在的恶意文件或可疑恶意软件，防止在组织中进一步传播攻击。 如果知道可能恶意的可移植可执行文件 (PE) 文件，则可以阻止它。 此操作将阻止在组织中的设备上读取、写入或执行该操作。

> [!IMPORTANT]
>
> - 如果你的组织使用Microsoft Defender 防病毒并且启用了云传递的保护，则此功能可用。 有关详细信息，请参阅 [管理云提供的保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。
>
> - 反恶意软件客户端版本必须是 4.18.1901.x 或更高版本。
> - 此功能旨在防止从 Web 下载可疑恶意软件 (或潜在的恶意文件) 。 它目前支持可移植的可执行 (PE) 文件，包括 _.exe_ 和 _.dll_ 文件。 覆盖范围将随时间推移而延长。
> - 此响应操作适用于Windows 10、版本 1703 或更高版本以及Windows 11上的设备。
> - 如果允许或阻止操作之前设备缓存上存在文件的分类，则不能对文件执行允许或阻止函数。

> [!NOTE]
> PE 文件需要位于设备时间线中，才能执行此操作。
>
> 在执行操作和阻止实际文件之间，可能会有几分钟的延迟。

### <a name="enable-the-block-file-feature"></a>启用块文件功能

若要开始阻止文件，首先需要在设置中 [打开 **"阻止"或"允许**"功能](advanced-features.md)。

### <a name="allow-or-block-file"></a>允许或阻止文件

为文件添加指示器哈希时，可以选择在组织中的设备尝试运行该文件时引发警报并阻止该文件。

由指示器自动阻止的文件不会显示在文件的操作中心，但警报在警报队列中仍然可见。

有关阻止和引发文件警报的更多详细信息，请参阅 [管理指示](manage-indicators.md) 器。

若要停止阻止文件，请删除指示器。 可以通过文件配置文件页上的 **"编辑指示器** "操作来执行此操作。 在添加指示器之前，此操作将显示在 **添加指示器** 操作所在的相同位置。

还可以在"**规则** \> **指示器**"下编辑 **设置** 页中的指示器。 指示器按其文件的哈希在此区域中列出。

## <a name="consult-a-threat-expert"></a>咨询威胁专家

请咨询 Microsoft 威胁专家，详细了解可能遭到入侵的设备或已遭入侵的设备。 Microsoft 威胁专家直接从Microsoft 365 Defender门户中进行，以便及时、准确地响应。 专家提供有关可能遭到入侵的设备的见解，并帮助你了解复杂的威胁和有针对性的攻击通知。 它们还可以提供有关警报或你在门户仪表板上看到的威胁情报上下文的信息。

有关详细信息 [，请参阅 Microsoft 威胁专家](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) 。

## <a name="check-activity-details-in-action-center"></a>在操作中心检查活动详细信息

**操作中心** 提供有关在设备或文件上执行的操作的信息。 可以查看以下详细信息：

- 调查包集合
- 防病毒扫描
- 应用限制
- 设备隔离

还会显示所有其他相关详细信息，例如提交日期/时间、提交用户以及操作是否成功或失败。

:::image type="content" source="images/action-center-details.png" alt-text="包含信息的操作中心" lightbox="images/action-center-details.png":::

## <a name="deep-analysis"></a>深度分析

网络安全调查通常由警报触发。 警报与一个或多个观察到的文件相关，这些文件通常是新文件或未知文件。 选择文件会转到文件视图，可在其中查看文件的元数据。 若要扩充与文件相关的数据，可以提交文件进行深入分析。

深度分析功能在安全且经过完全检测的云环境中执行文件。 深度分析结果显示文件的活动、观察到的行为以及关联的项目，例如删除的文件、注册表修改和与 IP 的通信。
深度分析目前支持对可移植可执行文件 (PE) 文件进行广泛的分析， (包括 _.exe_ 和 _.dll文件)_ 。

对文件进行深入分析需要几分钟时间。 完成文件分析后，"深度分析"选项卡将更新以显示摘要以及最新可用结果的日期和时间。

深度分析摘要包括观察到 *的行为* 列表，其中一些行为可能指示恶意活动，以及 *可观察到的行为*，包括已联系的 IP 和在磁盘上创建的文件。 如果未找到任何信息，这些部分将显示简短消息。

深度分析的结果与威胁情报相匹配，任何匹配项都将生成适当的警报。

使用深度分析功能来调查任何文件的详细信息，通常是在调查警报期间，或者出于怀疑恶意行为的任何其他原因。 此功能在文件的配置文件页上的 **"深度分析** "选项卡中可用。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4aAYy?rel=0]

当该文件在 Defender for Endpoint 后端示例集合中可用，或者在支持提交到深度分析的Windows 10设备上观察到该文件时，将启用提交以进行 **深入** 分析。

> [!NOTE]
> 只能自动收集来自Windows 10和Windows 11的文件。

如果 [未在Windows 10设备 (或Windows 11)](https://www.microsoft.com/security/portal/submission/submit.aspx)上观察到文件，也可以通过Microsoft 365 Defender门户提交示例，并等待"提交"**深度分析** 按钮可用。

> [!NOTE]
> 由于Microsoft 365 Defender门户中的后端处理流，文件提交和 Defender for Endpoint 中深度分析功能的可用性之间可能存在长达 10 分钟的延迟。

### <a name="submit-files-for-deep-analysis"></a>提交文件以进行深入分析

1. 选择要提交以进行深度分析的文件。 可以从以下任何视图中选择或搜索文件：

    - **警报** - 从"警报故事"时间线中的 **"说明** "或 **"详细信息** "中选择文件链接
    - **设备列表** - 从 **"组织中的设备**"部分的 **"说明**"或 **"详细信息**"中选择文件链接
    - **搜索框** - 从下拉菜单中选择 **"文件** "，然后输入文件名

2. 在文件视图的" **深度分析** "选项卡中，选择" **提交**"。

   :::image type="content" source="images/submit-file.png" alt-text="&quot;提交 PE 文件&quot;按钮" lightbox="images/submit-file.png":::

   > [!NOTE]
   > 仅支持 PE 文件，包括 _.exe_ 和 _.dll_ 文件。

   显示进度栏，并提供有关分析不同阶段的信息。 然后，可以在分析完成后查看报表。

> [!NOTE]
> 根据设备可用性，示例收集时间可能会有所不同。 示例集合有 3 小时超时。 如果当时没有联机Windows 10设备 (或Windows 11) 报告，则集合将失败，操作将中止。 可以重新提交文件以进行深入分析，以获取文件上的新数据。

### <a name="view-deep-analysis-reports"></a>查看深度分析报告

查看提供的深度分析报告，查看有关提交的文件的更多深入见解。 此功能在文件视图上下文中可用。

可以查看提供以下部分详细信息的综合报表：

- Behaviors
- 可观测项

提供的详细信息可以帮助你调查是否有潜在攻击的迹象。

1. 选择提交以进行深入分析的文件。
2. 选择" **深度分析** "选项卡。如果有任何以前的报表，则报表摘要将显示在此选项卡中。

   :::image type="content" source="images/analysis-results-nothing500.png" alt-text="显示多个类别的详细信息的深度分析报告" lightbox="images/analysis-results-nothing500.png":::

#### <a name="troubleshoot-deep-analysis"></a>深入分析疑难解答

如果在尝试提交文件时遇到问题，请尝试以下每个故障排除步骤。

1. 确保该文件是 PE 文件。 PE 文件通常 _(_ 可执行程序或应用程序 _)_ 具有.exe或.dll扩展名。

2. 确保服务有权访问该文件，该文件仍然存在，并且尚未损坏或修改。

3. 稍等片刻，然后再次尝试提交文件。 队列可能已满，或者出现临时连接或通信错误。

4. 如果未配置示例集合策略，则默认行为是允许示例收集。 如果已配置，请在再次提交文件之前验证策略设置是否允许示例收集。 配置示例集合时，请检查以下注册表值：

    ```text
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 - block sample collection
      Value = 1 - allow sample collection
    ```

5. 通过组策略更改组织单位。 有关详细信息，请参阅使用[组策略进行配置](configure-endpoints-gp.md)。

6. 如果这些步骤无法解决问题，请联系支持人员。

## <a name="related-topics"></a>相关主题

- [在设备上执行响应操作](respond-machine-alerts.md)
- [调查文件](investigate-files.md)
- [Microsoft Defender for Endpoint计划 1 中的手动响应操作](defender-endpoint-plan-1.md#manual-response-actions)
