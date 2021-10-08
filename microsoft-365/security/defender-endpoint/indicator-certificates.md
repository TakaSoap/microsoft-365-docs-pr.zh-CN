---
title: 创建基于证书的指示器
ms.reviewer: ''
description: 根据定义实体的检测、防范和排除的证书创建指示器。
keywords: ioc， 证书， 证书， 管理， 允许， 阻止， 阻止， 清理， 恶意， 文件哈希， ip 地址， url， 域
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
ms.openlocfilehash: b87c249fad5f3d6e2dd4f5ce7076a7f1b00506c7
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240088"
---
# <a name="create-indicators-based-on-certificates"></a>创建基于证书的指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)。

你可以为证书创建指示器。 一些常见用例包括：

- 当你需要部署阻止技术（如攻击面减少规则和受控文件夹[](attack-surface-reduction.md)访问权限）但需要允许[](controlled-folders.md)已签名应用程序的行为时，需要在允许列表中添加证书。
- 阻止在整个组织中使用特定的已签名应用程序。 通过创建用于阻止应用程序证书的指示器，Windows Defender AV 将阻止文件执行 (并修正) 自动调查和修正的行为相同。

## <a name="before-you-begin"></a>开始之前

在创建证书指示器之前，了解以下要求很重要：

- 如果你的组织使用基于云的保护Windows Defender 防病毒则此功能可用。 有关详细信息，请参阅 [管理基于云的保护](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。
- 反恶意软件客户端版本必须为 4.18.1901.x 或更高版本。
- 在 Windows 10 版本 1703 或更高版本、Windows Server 2019、Windows Server 2016、Windows Server 2012 R2 和 Windows Server 2022 上支持。
    
    >[!NOTE]
    >Windows Server 2016和 Windows Server 2012 R2 将需要按照[载入 Windows 服务器](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)中的说明载入，此功能将正常工作。 

- 病毒和威胁防护定义必须最新的。
- 此功能当前支持输入 。CER 或 。PEM 文件扩展名。

> [!IMPORTANT]
>
> - 有效的叶证书是具有有效证书路径的签名证书，必须与 Microsoft 信任的 CA (根证书) 证书颁发机构。 或者，只要自定义 (自签名) 证书受客户端 (根 CA 证书的信任，该证书就可以使用在本地计算机"受信任的根证书颁发机构") 下。
> - 允许/阻止证书 IOC 的子级或父级不包括在允许/阻止 IoC 功能中，仅支持叶证书。
> - 无法阻止 Microsoft 签名的证书。

## <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>从设置页面创建证书指示器：

> [!IMPORTANT]
> 创建和删除证书 IoC 可能需要 3 小时。

1. 在导航窗格中，选择"设置规则"下 (\>  \> 终结点) 。 

2. 选择 **"添加指示器"。**

3. 指定以下详细信息：
   - 指示器 - 指定实体详细信息并定义指示器的过期时间。
   - 操作 - 指定要采取的操作并提供说明。
   - Scope - 定义计算机组的范围。

4. 查看"摘要"选项卡中的详细信息，然后单击"保存 **"。**

## <a name="related-topics"></a>相关主题

- [创建指示器](manage-indicators.md)
- [创建文件指示器](indicator-file.md)
- [创建 IP 和 URL/域指示器](indicator-ip-domain.md)
- [管理指示器](indicator-manage.md)
