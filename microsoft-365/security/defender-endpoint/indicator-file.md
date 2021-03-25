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
ms.openlocfilehash: d78f90e78a50d5902070f441a1d60693a5f531c8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185715"
---
# <a name="create-indicators-for-files"></a>创建文件指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

通过禁止潜在恶意文件或可疑恶意软件，可防止攻击在组织中进一步传播。 如果你知道 PE 文件中可能存在恶意 (可执行) ，可以阻止它。 此操作将阻止在组织中计算机上读取、写入或执行该操作。

有两种方法可以创建文件指示器：
- 通过设置页面创建指示器
- 通过使用文件详细信息页面中的"添加指示器"按钮创建上下文指示器

### <a name="before-you-begin"></a>准备工作
在创建文件指示器之前，了解以下先决条件很重要：

- 如果你的组织使用防病毒和基于云的Windows Defender，此功能可用。 有关详细信息，请参阅通过云提供的保护使用 [Microsoft Defender 防病毒中的下一代技术](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。
- 反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。
- 在 Windows 10 版本 1703 或更高版本、Windows Server 2016 和 2019 上的计算机上受支持。
- 若要开始阻止文件，首先需要打开"设置"[**中的"阻止或**](advanced-features.md)允许"功能。
- 此功能旨在防止从 web (可疑恶意软件) 潜在恶意文件。 它当前支持可移植的可执行 (PE) 文件，包括 _.exe_ 和 _.dll_ 文件。 覆盖范围将随着时间的推移而延长。

>[!IMPORTANT]
>- 如果文件分类存在于允许或阻止操作之前的设备的缓存中，则不能对文件执行允许或阻止功能 
>- 受信任的已签名文件将受到不同的处理。 Defender for Endpoint 经过优化，可处理恶意文件。 在某些情况下，尝试阻止受信任的已签名文件可能有性能影响。

 
>[!NOTE]
>通常，文件块将在几分钟内强制执行，但可能需要 30 分钟以上的时间。

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>从设置页创建文件指示器

1. 在导航窗格中，选择"**设置**  >  **""指示器"。**  

2. 选择" **文件哈希"** 选项卡。

3. 选择 **"添加指示器"。**

4. 指定以下详细信息：
   - Indicator - 指定实体详细信息并定义指示器的过期时间。
   - 操作 - 指定要采取的操作并提供说明。
   - Scope - 定义计算机组的范围。

5. 查看"摘要"选项卡中的详细信息，然后单击"保存 **"。**

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>从文件详细信息页面创建上下文指示器
对文件执行响应 [操作的选项](respond-file-alerts.md) 之一是添加文件指示器。 

为文件添加指示器哈希时，可以选择引发警报，并阻止组织中计算机尝试运行该文件。

由指示器自动阻止的文件不会显示在文件的"操作中心"中，但警报仍显示在警报队列中。


## <a name="related-topics"></a>相关主题
- [创建指示器](manage-indicators.md)
- [为 IP 和 URL/域创建指示器](indicator-ip-domain.md)
- [创建基于证书的指示器](indicator-certificates.md)
- [管理指示器](indicator-manage.md)
