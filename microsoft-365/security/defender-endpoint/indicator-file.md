---
title: 创建文件指示器
ms.reviewer: ''
description: 创建文件哈希的指示器，以定义实体的检测、防范和排除。
keywords: 文件， 哈希， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: 6d92cbacba72210c6accbbb1e5ecf25de660fc3c
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730528"
---
# <a name="create-indicators-for-files"></a>创建文件指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

通过禁止潜在恶意文件或可疑恶意软件，防止攻击在组织中进一步传播。 如果你知道 PE 文件中可能存在恶意 (可执行) ，可以阻止它。 此操作将阻止在组织的设备上读取、写入或执行该操作。

有三种方法可以创建文件指示器：

- 通过设置页面创建指示器
- 通过使用文件详细信息页面中的"添加指示器"按钮创建上下文指示器
- 通过指示器 [API 创建指示器](ti-indicator.md)

## <a name="before-you-begin"></a>准备工作

在创建文件指示器之前，了解以下先决条件很重要：

- 如果你的组织在活动模式下使用 **Microsoft Defender 防病毒 (，) 启用** 基于云的保护，则此功能 **可用**。 有关详细信息，请参阅 [管理基于云的保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。

- 反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。 请参阅 [每月平台和引擎版本](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- 在具有 Windows 10 版本 1703 或更高版本、Windows Server 2016 2019 的设备上受支持。

- 若要开始阻止文件，首先需要打开"阻止或允许 ["设置。](advanced-features.md)

此功能旨在防止从 web (可疑恶意软件) 潜在恶意文件。 它目前支持可移植的可执行 (PE) 文件，包括.exe和.dll文件。 覆盖范围将随着时间的推移而延长。

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>从设置页创建文件指示器

1. 在导航窗格中，选择 **"设置 >标记"。**

2. 选择" **文件哈希"**   选项卡。

3. 选择 **"添加指示器"。**

4. 指定以下详细信息：
    - Indicator - 指定实体详细信息并定义指示器的过期时间。
    - 操作 - 指定要采取的操作并提供说明。
    - 范围 - 定义设备组的范围。

5. 查看"摘要"选项卡中的详细信息，然后选择"保存 **"。**

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>从文件详细信息页面创建上下文指示器

对文件执行响应 [操作的选项](respond-file-alerts.md)之一是   添加文件指示器。 为文件添加指示器哈希时，可以选择引发警报，并阻止组织中设备尝试运行该文件。

由指示器自动阻止的文件不会显示在文件的"操作中心"中，但警报仍显示在警报队列中。

>[!IMPORTANT]
>- 通常，文件块将在几分钟内强制执行和删除，但可能需要 30 分钟以上的时间。
>- 如果存在冲突的文件指示器策略，则应用更安全的策略的强制策略。 例如，如果两种哈希类型都定义了相同的文件，则 SHA-256 文件哈希指示器策略优先于 MD5 文件哈希指示器策略。
>- 如果禁用 EnableFileHashComputation 组策略，则文件 IoC 的阻止准确度将降低。 但是，启用 EnableFileHashComputation 可能会影响设备性能。
>    - 例如，将大文件从网络共享复制到本地设备（尤其是通过 VPN 连接）可能会影响设备性能。
>    - 有关 EnableFileHashComputation 组策略详细信息，请参阅 [Defender CSP](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>策略冲突处理  

证书和文件 IoC 策略处理冲突将遵循以下顺序：

- 如果应用程序控制和 AppLocker Windows Defender策略不允许该文件，**则阻止**

- 否则，如果文件被排除Microsoft Defender 防病毒，**则允许**

- 否则，如果阻止或警告文件 IoC 阻止或警告文件，则 **阻止/警告**

- 否则，如果允许文件 IoC 策略允许该文件 **，则允许**

- 否则，如果该文件被 ASR 规则、CFA、AV、SmartScreen 阻止，则 **阻止**  

- Else **Allow** (AppLocker 策略Windows Defender应用程序控制&，任何 IoC 规则都不适用于它) 

如果存在具有相同强制类型和目标的冲突文件 IoC 策略，则更安全的文件 ioC 策略 (这意味着将应用) 哈希时间更长。 例如，如果 SHA-256 文件哈希 IoC 策略定义同一个文件，它将在 MD5 文件哈希 IoC 策略中获胜。

请注意，危险和漏洞管理阻止易受攻击的应用程序功能使用文件 IoC 进行强制执行，并且将遵循上述冲突处理顺序。

### <a name="examples"></a>示例

|组件 |组件强制 |文件指示器操作 |结果
|--|--|--|--|
|攻击面减少文件路径排除 |允许 |阻止 |阻止
|攻击面减少规则 |阻止 |允许 |允许
|Windows Defender 应用程序控制 |允许 |阻止 |允许 |
|Windows Defender 应用程序控制 |阻止 |允许 |阻止
|Microsoft Defender 防病毒排除 |允许 |阻止 |允许

## <a name="see-also"></a>另请参阅

- [创建指示器](manage-indicators.md)
- [创建 IP 和 URL/域指示器](indicator-ip-domain.md)
- [创建基于证书的指示器](indicator-certificates.md)
- [管理指示器](indicator-manage.md)
