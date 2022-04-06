---
title: 创建文件指示器
ms.reviewer: ''
description: 创建文件哈希的指示器，以定义实体的检测、防范和排除。
keywords: 文件， 哈希， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: 74859364cb2da004063ffc58922f2d9b399ea8d2
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64474214"
---
# <a name="create-indicators-for-files"></a>创建文件指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)。

通过禁止潜在恶意文件或可疑恶意软件，防止攻击在组织中进一步传播。 如果你知道 PE 文件中可能存在恶意 (可执行) ，可以阻止它。 此操作将阻止在组织的设备上读取、写入或执行该操作。

有三种方法可以创建文件指示器：

- 通过设置页面创建指示器
- 通过使用文件详细信息页中的添加指示器按钮创建上下文指示器
- 通过指示器 [API 创建指示器](ti-indicator.md)

## <a name="before-you-begin"></a>准备工作

在创建文件指示器之前，了解以下先决条件很重要：

- 如果你的组织在活动模式下使用Microsoft Defender 防病毒 (**，) 启用** 基于云的保护，则此功能 **可用**。 有关详细信息，请参阅 [管理基于云的保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。

- 反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。 请参阅 [每月平台和引擎版本](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- 在具有 Windows 10 版本 1703 或更高版本、Windows Server 2019、Windows Server 2016、Windows Server 2012 R2 和 Windows Server 2022 的设备上受支持。
    
   >[!NOTE]
    >Windows Server 2016和 Windows Server 2012 R2 将需要按照[载入 Windows 服务器](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)中的说明载入，此功能将正常工作。 

- 若要开始阻止文件，首先需要打开"阻止或允许["](advanced-features.md)设置。

此功能旨在防止从 web (可疑的恶意软件) 潜在的恶意文件。 它当前支持可移植的可执行 (PE) 文件，包括.exe和.dll文件。 覆盖范围将随着时间的推移而延长。

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>从设置页创建文件指示器

1. 在导航窗格中，选择"\>设置 **"**\>下 (**终结点) 。** 

2. 选择" **文件哈希"** 选项卡。

3. 选择 **"添加项"**。

4. 指定以下详细信息：
    - 指示器 - 指定实体详细信息并定义指示器的过期时间。
    - 操作 - 指定要采取的操作并提供说明。
    - 范围 - 定义设备组的范围。

5. 查看"摘要"选项卡中的详细信息，然后选择"保存 **"**。

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>从文件详细信息页面创建上下文指示器

对文件执行响应 [操作的选项](respond-file-alerts.md) 之一是添加文件指示器。 为文件添加指示器哈希时，可以选择引发警报，并阻止组织中设备尝试运行该文件。

由指示器自动阻止的文件不会显示在文件的"操作中心"中，但警报仍显示在警报队列中。

## <a name="public-preview-alerting-on-file-blocking-actions"></a>公共预览版：针对文件阻止操作发出警报

> [!IMPORTANT]
> 本节中的信息 (公共预览版 **自动** 调查和修正引擎) 预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

文件 IOC 当前支持的操作包括允许、审核、阻止和修正。 选择阻止文件后，可以选择是否需要触发警报。 这样，你将能够控制向安全运营团队发出警报的数量，并确保只引发所需的警报。

In Microsoft 365 Defender， go to **设置** > EndpointsIndicatorsAdd >  >  **New File Hash**.

选择"阻止并修正文件"。

选择是否对文件阻止事件生成警报并定义警报设置：

- 警报标题
- 警报严重性
- 类别
- 说明
- 建议的操作

:::image type="content" source="images/indicators-generate-alert.png" alt-text="文件指示器的警报设置" lightbox="images/indicators-generate-alert.png":::

> [!IMPORTANT]
>
> - 通常，文件块将在几分钟内强制执行和删除，但可能需要 30 分钟以上的时间。
> - 如果存在具有相同强制类型和目标的冲突文件 IoC 策略，将应用更安全哈希的策略。 SHA-256 文件哈希 IoC 策略将超过 SHA-1 文件哈希 IoC 策略，如果哈希类型定义相同的文件，该策略将超过 MD5 文件哈希 IoC 策略。 无论设备组如何，这始终为 true。
> - 在所有其他情况下，如果具有相同强制目标的冲突文件 IoC 策略应用于所有设备和设备组，那么对于设备，设备组的策略将获胜。
> - 如果禁用 EnableFileHashComputation 组策略，则文件 IoC 的阻止准确度将降低。 但是，启用 `EnableFileHashComputation` 可能会影响设备性能。 例如，将大文件从网络共享复制到本地设备（尤其是通过 VPN 连接）可能会影响设备性能。
>
> 有关 EnableFileHashComputation 组策略详细信息，请参阅 [Defender CSP](/windows/client-management/mdm/defender-csp)。

## <a name="public-preview-advanced-hunting-capabilities"></a>公共预览版：高级搜寻功能

> [!IMPORTANT]
> 本节中 (自动调查和修正引擎的公共预览 **版) 预** 发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

你可以提前搜寻查询响应操作活动。 下面是一个示例高级搜寻查询：

```console
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
Timestamp > ago(30d)
| where AdditionalFields contains "EUS:Win32/CustomEnterpriseBlock!cl"
```

有关高级搜寻详细信息，请参阅 [使用高级搜寻主动搜寻威胁](advanced-hunting-overview.md)。

下面是可在上述示例查询中使用的其他线程名称：

文件：

- EUS：Win32/CustomEnterpriseBlock！cl
- EUS：Win32/CustomEnterpriseNoAlertBlock！cl

证书：

- EUS：Win32/CustomCertEnterpriseBlock！cl

响应操作活动还可以在设备时间线中查看。

## <a name="policy-conflict-handling"></a>策略冲突处理

证书和文件 IoC 策略处理冲突将遵循以下顺序：

- 如果应用控制和 AppLocker Windows Defender应用策略/策略不允许该文件，**则阻止**
- 否则，如果文件被排除Microsoft Defender 防病毒 **，则允许**
- 否则，如果阻止或警告文件 IoC 阻止或警告文件，则 **阻止/警告**
- 否则，如果允许文件 IoC 策略允许该文件 **，则允许**
- 否则，如果该文件被 ASR 规则、CFA、AV、SmartScreen 阻止，则 **阻止**
- Else **Allow** (AppLocker Windows Defender应用控制&，任何 IoC 规则都不适用于它) 

>[!NOTE]
> 在将Microsoft Defender 防病毒设置为"阻止"，但 Defender for Endpoint 设置为 **"** 允许"的情况下，策略将默认为 **"允许"**。

如果存在具有相同强制类型和目标的冲突文件 IoC 策略，则更安全的文件 ioC 策略 (这意味着将应用) 哈希时间更长。 例如，如果 SHA-256 文件哈希 IoC 策略定义相同的文件，则策略将超过 MD5 文件哈希 IoC 策略。

> [!WARNING]
> 文件和证书的策略冲突处理与域/URL/IP 地址的策略冲突处理不同。

威胁漏洞管理阻止易受攻击的应用程序功能使用文件 IoC 进行强制执行，并遵循上述冲突处理顺序。

### <a name="examples"></a>示例

<br>

****

|组件|组件强制|文件指示器操作|结果|
|---|---|---|---|
|攻击面减少文件路径排除|允许|阻止|阻止|
|攻击面减少规则|阻止|允许|允许|
|Windows Defender 应用程序控制|允许|阻止|允许|
|Windows Defender 应用程序控制|阻止|允许|阻止|
|Microsoft Defender 防病毒排除|允许|阻止|允许|
|

## <a name="see-also"></a>另请参阅

- [创建指示器](manage-indicators.md)
- [创建 IP 和 URL/域指示器](indicator-ip-domain.md)
- [创建基于证书的指示器](indicator-certificates.md)
- [管理指示器](indicator-manage.md)
