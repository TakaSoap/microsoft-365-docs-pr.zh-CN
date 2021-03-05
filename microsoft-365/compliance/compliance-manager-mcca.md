---
title: 适用于合规性管理器的 Microsoft 合规性配置分析器
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用 Microsoft 合规性配置分析器快速启动并运行 Microsoft 合规性管理器。
ms.openlocfilehash: 272477251efed7ebf13bd2e644869eaf2aad1bc2
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454683"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>适用于合规性管理器的 Microsoft 合规性配置分析器 (预览) 

**本文内容：** 了解如何安装和运行 Microsoft 合规性配置分析器工具，以快速开始使用 Microsoft 合规性管理程序。

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Microsoft 合规性配置分析 (MCCA)  (预览) 概述

Microsoft 合规性配置分析器 (MCCA) 是一个预览工具，可帮助你开始使用 [Microsoft 合规性管理器](compliance-manager.md)。 MCCA 是基于 PowerShell 的实用工具，它将提取组织的当前配置，并针对 Microsoft 365 建议的最佳方案验证它们。 这些最佳做法基于一组控制措施，其中包括数据保护和数据管理的关键法规和标准。

MCCA 可帮助你快速查看合规性管理程序中的哪些改进操作适用于当前的 Microsoft 365 环境。 MCCA 确定的每个操作都将提供实施建议，并直接链接到合规性管理器和适用的解决方案以开始采取纠正措施。

另一个了解 MCCA 的资源是访问 [GitHub 上的自述文件说明](https://github.com/OfficeDev/MCCA#overview)。 此页面提供有关必备组件的详细信息，并提供完整安装说明。 无需 GitHub 帐户来访问此页面。

**可用性**：MCCA 适用于拥有 Office 365 和 Microsoft 365 许可证的所有组织以及美国政府社区 (GCC) 中等和 GCC 高客户，并且计划将服务扩展到 DOD 客户。

## <a name="install-mcca-and-run-a-report"></a>安装 MCCA 并运行报告

可以使用软件安装 MCCA Windows PowerShell。 下载并安装该工具后，无需重复这些步骤，即运行报告。 每次打开 MCCA 时，都会要求您提供登录凭据，并生成新的更新报告。

#### <a name="step-1-install-windows-powershell"></a>步骤 1：安装Windows PowerShell
首先，你需要 PowerShell 库中提供的 Exchange Online PowerShell 模块 (v2.0.3 或) 或更高版本。 [获取安装说明](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。

#### <a name="step-2-install-mcca"></a>步骤 2：安装 MCCA

若要安装 MCCA，请首先在管理员模式下使用 PowerShell。 请按照以下步骤操作：

1. 选择"Windows **开始"** 按钮。
2. 键入 **PowerShell，** 右键单击 **Windows PowerShell，** 然后选择"以 **管理员角色运行"。**
1. 在命令提示符处，键入以下内容：

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>步骤 3：运行报告

安装 MCCA 后，可以运行 MCCA 并生成报告。 若要运行报告，

1. 打开 PowerShell
2. 运行以下 cmdlet：

    ```powershell
    Get-MCCAReport
    ```

   如果你是 GCC 高客户，则需要提供其他输入参数来运行报告：

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. MCCA 运行后，它将执行初始版本检查并请求凭据。 在"输入用户名"提示符下，使用 Microsoft 365 帐户电子邮件地址登录 ([查看有资格创建](#role-based-reporting) 报告) 。 然后在密码提示符下输入密码。

然后，报告将大约需要 2-5 分钟生成。 完成后，浏览器窗口将打开并显示 HTML 报表。 每次运行该工具时，该工具都会要求您提供凭据并生成一个新报告。 此报告本地存储在以下目录中：

C：\Users \<username> \AppData\Local\Microsoft\MCCA。 

可以从此目录访问以前生成的报告。

## <a name="understanding-your-report"></a>了解报告

你的报告根据生成数据的日期和时间反映数据。 The top section provides details on when it was generated， your organization name， and tenant ID.

#### <a name="geolocation-based-reporting"></a>基于地理位置的报告

" **注释** "部分显示根据租户的地理位置自定义报表。 该工具中列出的建议将特定于你的国家/地区。

您的地理位置选择用于评估与 (地理位置) 的敏感信息类型，并生成与你的国家/地区或区域一致的报告。 根据租户中拥有的数据选择地理位置。

若要更改报告的位置信息，需要提供地理位置 (-地理位置) 输入参数。 可以选择适用于租户的一个或多个地理位置。

按照以下说明基于特定位置运行报告：

1. 打开 PowerShell
2. 若要指定特定区域，您将使用下表中对应于该国家/地区的数字运行 cmdlet。 输入多个数字，用逗号分隔它们。 例如，以下 cmdlet 将为日本Asia-Pacific自定义报告：

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  国家或地区 | 
  | :------------- | :------------: |
  | 1  | 亚太地区 |
  | 2  | 澳大利亚 |
  | 3  | 加拿大 |
  | 4  | 欧洲 (法国/) /中东/非洲 |
  | 5  | 法国 |
  | 6  | 印度 |
  | 7  | 日本 |
  | 8  | 韩国 |
  | 9  | 北美 (加拿大)  |
  | 10   | 南美洲 |
  | 11 | 南非 |
  | 12  | Switzerland（瑞士） |
  | 13  | 阿拉伯联合酋长国 |
  | 14  | 英国 |


 > [!NOTE]
> 报告将始终包括 MCCA 支持的国际敏感信息类型，如 SWIFT 代码、信用卡号等。

#### <a name="role-based-reporting"></a>基于角色的报告

你的报告也会根据您的角色进行自定义。

下表显示了哪些角色有权访问报告的哪些部分。 贵组织 (未在下表中列出的其他角色) 可能无法运行该工具，或者他们可能会运行该工具，并且对最终报告中的信息具有有限的访问权限。

![MCCA - 角色](../media/compliance-manager-mcca-roles.png "MCCA 角色")

例外情况如下：
1. 用户无法生成除"使用 Exchange Online 的 IRM"部分之外 IP 的报告。
2. 用户将能够生成除"对 Exchange Online 使用 IRM"部分之外 IP 的报告。
3. 用户将能够生成除"在 O365 中启用通信合规性"部分之外 IP 的报告。
4. 除了"在 Office 365 中启用审核"部分，用户将无法生成 IP 报告。
5. 用户将能够生成除"在 Office 365 中启用审核"部分之外 IP 的报告。

#### <a name="solutions-summary-section"></a>"解决方案摘要"部分

该报告 **的** "解决方案摘要"部分概述了组织在合规性管理器中可采取的改进操作，以帮助改善合规性状态。

![MCCA - 解决方案摘要](../media/compliance-manager-mcca-solutions.png "MCCA 解决方案摘要屏幕")

MCCA 根据合规性管理器中建议的改进操作评估当前配置。 本节中将列出 MCCA 工具标识为需要关注的任何改进操作。

每个 Microsoft 解决方案旁边都有颜色编码框，用于指示合规性管理器中与改进操作对应的项目数。 操作分为三种状态：

- **确定**：满足建议条件且此时无需关注的操作
- **改进**：需要关注的操作
- **建议**：不需要关注但建议最佳做法的操作
 
选择一个框以查看改进和建议。

**具有"改进"状态的项目**

选择改进操作右侧"改进"标签旁边的下拉列表。 你将看到有关当前设置以及建议改进操作的快速摘要和详细信息。 摘要包括合规性管理器的直接链接、Microsoft 365 合规中心中的适用解决方案和相关文档。

单击合规性管理器链接可让你查看该解决方案中尚未实施的所有改进措施的筛选视图。 你可以从其中查看可用于提高合规性分数的点数、适用的评估以及适用的法规[](compliance-score-calculation.md)和认证。

对于 DLP，有一个 **修正** 脚本按钮，可基于建议的内容为你提供预生成的 PowerShell 脚本。 可以直接在 PowerShell 控制台中复制并粘贴它。 它将在测试模式下创建 DLP 策略

**具有"建议"状态的项目**

选择改进操作右侧 **"建议** "标签旁边的下拉列表。 你将看到与改进操作相关的组织当前 Microsoft 365 环境的摘要，以及建议的最佳实践。

## <a name="resources"></a>资源

有关安装、设置和使用 MCCA 的更多详细信息，请参阅 [GitHub](https://github.com/OfficeDev/MCCA#overview) 上的自述 (无需 GitHub 帐户) 。

有关此Windows PowerShell，请 [从如何使用 PowerShell 文档开始](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)。 另请参阅 ["开始Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)。
