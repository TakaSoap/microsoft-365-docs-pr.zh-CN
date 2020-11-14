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
description: 了解如何使用 Microsoft 合规性配置分析器立即与 Microsoft 合规性管理器一起运行。
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071992"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a>适用于合规性管理器的 Microsoft 合规性配置分析器

**本文内容：** 了解如何安装和运行 Microsoft 合规性配置分析器工具以快速开始使用 Microsoft 合规性管理器。

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a>Microsoft MCCA 兼容性配置分析器 () 概述

Microsoft 合规性配置分析器 (MCCA) 是一种可帮助您开始使用 [Microsoft 合规性管理器](compliance-manager.md)的工具。 MCCA 是基于 PowerShell 的实用工具，它将获取组织的当前配置，并针对 Microsoft 365 建议的最佳实践对其进行验证。 这些最佳做法基于一组控件，其中包括针对数据保护和数据管理的关键法规和标准。

MCCA 可帮助您快速查看合规性管理器中的哪些改进操作适用于您当前的 Microsoft 365 环境。 由 MCCA 标识的每个操作都将为您提供实施建议，其中包含指向合规性管理器的直接链接以及开始采取纠正措施的适用解决方案。

要了解 MCCA 的其他资源，请访问 [GitHub 上的自述文件说明](https://github.com/OfficeDev/MCCA#overview)。 此页面提供了有关先决条件的详细信息，并提供了完整的安装说明。 您不需要 GitHub 帐户即可访问此页面。

## <a name="install-mcca-and-run-a-report"></a>安装 MCCA 并运行报告

您可以使用 Windows PowerShell 安装 MCCA 工具。 下载并安装该工具后，无需重复这些步骤即可运行报告。 每次打开 MCCA 时，它都会询问您登录凭据，并将生成一个新的更新的报告。

#### <a name="step-1-install-windows-powershell"></a>步骤1：安装 Windows PowerShell
若要开始，你将需要 Exchange Online PowerShell 模块 (v 2.0.3 或更高版本的 PowerShell 库中提供的) 。 [获取安装说明](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。

#### <a name="step-2-install-mcca"></a>步骤2：安装 MCCA

若要安装 MCCA，请首先在管理员模式下使用 PowerShell。 请按照以下步骤操作：

1. 选择 "Windows **开始** " 按钮。
2. 键入 **PowerShell** ，右键单击 " **Windows PowerShell** "，然后选择 " **以管理员身份运行** "。
1. 在命令提示符处，键入以下内容：

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>步骤3：运行报告

安装 MCCA 后，可以运行 MCCA 并生成报告。 运行报告：

1. 打开 PowerShell
2. 运行以下 cmdlet：

    ```powershell
    Get-MCCAReport
    ```
3. 在 MCCA 运行后，它会执行初始版本检查并要求提供凭据。 在输入用户名提示符处，使用 Microsoft 365 帐户电子邮件地址登录 ([查看符合创建报告的角色](#role-based-reporting)) 。 然后在密码提示符处输入您的密码。

您的报告将需要大约2-5 分钟的时间来生成。 完成后，浏览器窗口将打开并显示您的 HTML 报告。 每次运行该工具时，它都会要求你提供凭据并生成新报告。 此报告在本地存储在以下目录中：

C:\Users \<username> \AppData\Local\Microsoft\MCCA。 

您可以从此目录访问以前生成的报告。

## <a name="understanding-your-report"></a>了解你的报告

您的报告将根据数据生成的日期和时间反映数据。 上面的部分提供了有关何时生成、组织名称和租户 ID 的详细信息。

#### <a name="geolocation-based-reporting"></a>基于地理位置的报告

" **注释** " 部分显示您的报告根据租户的地理位置进行自定义。 工具中列出的建议将特定于您所在的国家或地区。

您的地理位置选择用于评估与该地理位置相关 () 的敏感信息类型，并生成与您的国家或地区相符的报告。 根据租户中的数据选择 "geolocations"。

若要更改报表的位置信息，您需要提供一个地理位置 ( Geo) 输入参数。 你可以选择适用于你的租户的一个或多个 geolocations。

按照以下说明运行基于特定位置的报表：

1. 打开 PowerShell
2. 若要指定某个区域，您将使用下表中与该国家或地区对应的编号运行 cmdlet。 通过用逗号分隔来输入多个数字。 例如，下面的 cmdlet 将为 Asia-Pacific 和日本运行自定义报告：

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  国家或地区 | 
  | :------------- | :------------: |
  | 1  | 亚太地区 |
  | 2  | 澳大利亚 |
  | 第三章 | 加拿大 |
  | 4  | 欧洲 (不包括法国) /中部东部/非洲 |
  | 5  | 法国 |
  | 6  | 印度 |
  | 7  | 日本 |
  | 8  | 韩国 |
  | 9  | 北美 (不包括加拿大)  |
  | 10   | 南美洲 |
  | 11  | 南非 |
  | 12  | 瑞士 |
  | 13  | 阿拉伯联合酋长国 |
  | 14  | 英国 |


 > [!NOTE]
> 该报告将始终包含 MCCA 支持的国际敏感信息类型，如 SWIFT 代码、信用卡号等。

#### <a name="role-based-reporting"></a>基于角色的报告

您的报告也将根据您的角色进行自定义。

下表显示了哪些角色有权访问报表的哪些部分。 组织中的其他角色 (下表中未列出) 可能无法运行该工具，也可能会运行该工具，并且对最终报告中的信息具有有限的访问权限。

![MCCA-角色](../media/compliance-manager-mcca-roles.png "MCCA 角色")

例外情况如下：
1. 用户不能在 "使用 Exchange Online IRM" 部分生成 IP 报告。
2. 用户将能够针对 "使用 Exchange Online IRM" 部分生成 IP 报告。
3. 用户将能够生成 IP 报告，而不是 "在 O365 中启用通信合规性" 部分。
4. 用户将无法生成 IP 报告 "在 Office 365 中启用审核" 部分。
5. 用户将能够生成 IP 报告 "在 Office 365 中启用审核" 部分。

#### <a name="solutions-summary-section"></a>"解决方案摘要" 部分

报告的 " **解决方案摘要** " 部分概述了贵组织可在合规性管理器中采取的改进措施，以帮助改进合规性状况。

![MCCA-解决方案摘要](../media/compliance-manager-mcca-solutions.png "MCCA 解决方案摘要屏幕")

MCCA 评估当前配置是否符合合规性管理器中建议的改进措施。 此部分列出了由 MCCA 工具所做的任何改进操作（如有需要注意）。

每个 Microsoft 解决方案旁边都有颜色编码框，指示合规性管理器中与改进操作对应的项目数。 这些操作分为三个状态状态：

- **确定** ：满足推荐条件并在此时间不需要注意的操作
- **改进** ：需要注意的操作
- **建议** ：不需要注意的操作，但我们建议的最佳做法
 
选择一个框以查看改进和建议。

**具有改进状态的项目**

选择 "改进" 操作右侧的 " **改善** " 标签旁边的下拉列表。 你将看到有关当前设置和建议的改进操作的快速摘要和详细信息。 此摘要包括指向合规性管理器的直接链接、Microsoft 365 合规性中心中适用的解决方案以及相关文档。

单击 "合规性管理器" 链接将转到该解决方案中尚未实施的所有改进操作的筛选视图。 在这里，你可以看到可实现的点数，以增加 [合规性分数](compliance-score-calculation.md)、应用的评估以及适用的法规和证书。

对于 DLP，有一个 " **补救脚本** " 按钮，它根据建议的建议为您提供预生成的 PowerShell 脚本。 您可以直接在 PowerShell 控制台中复制并粘贴它。 它将在测试模式下创建 DLP 策略

**具有建议状态的项目**

选择 "改进" 操作右侧的 " **建议** " 标签旁边的下拉列表。 你将看到组织的当前 Microsoft 365 环境与改进操作相关的摘要，以及建议的最佳实践。

## <a name="resources"></a>资源

有关安装、设置和使用 MCCA 的更多详细信息，请参阅 [GitHub 上的自述文件说明](https://github.com/OfficeDev/MCCA#overview) (不需要 GitHub 帐户) 。

有关 Windows PowerShell 的详细信息，请从 [如何使用 PowerShell 文档](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)入手。 另请参阅 [启动 Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)。
