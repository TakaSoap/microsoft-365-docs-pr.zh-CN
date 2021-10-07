---
title: Microsoft Defender for Endpoint 数据存储和隐私
description: 了解 Microsoft Defender for Endpoint 如何处理它收集的隐私和数据。
keywords: Microsoft Defender for Endpoint， 数据存储和隐私， 存储， 隐私， 许可， 地理位置， 数据保留， 数据
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a435dc0f0fb1858edcc86291c0c4c7b5ef7c565f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166548"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>Microsoft Defender for Endpoint 数据存储和隐私

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

本部分涵盖有关 Defender for Endpoint 的隐私和数据处理的一些最常见的问题。

> [!NOTE]
> 本文档介绍与 Defender for Endpoint 相关的数据存储和隐私详细信息。 有关适用于终结点的 Defender 以及其他产品和服务（如 Microsoft Defender 防病毒 和 Windows）的信息，请参阅 Microsoft[隐私声明](https://go.microsoft.com/fwlink/?linkid=827576)。 有关详细信息[，Windows](https://go.microsoft.com/fwlink/?linkid=827577)隐私常见问题解答。

## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Microsoft Defender for Endpoint 会收集哪些数据？

Microsoft Defender for Endpoint 将在特定于服务的客户专用和隔离租户中收集并存储已配置设备的信息，以用于管理、跟踪和报告目的。

收集的信息包括文件数据 (如文件名、大小和哈希) 、进程数据 (正在运行的进程、哈希) 、注册表数据、网络连接数据 (主机 IP 和端口) 以及设备详细信息 (例如设备标识符、名称和操作系统版本) 。

Microsoft 安全地存储此数据Microsoft Azure根据 Microsoft 隐私实践和 Microsoft 信任[中心策略进行维护](https://go.microsoft.com/fwlink/?linkid=827578)。

此数据使 Defender for Endpoint 能够：

- 主动识别组织中 IA (IA) 攻击指标
- 如果检测到可能的攻击，生成警报
- 为安全操作提供与来自网络的威胁信号相关的设备、文件和 URL 的视图，使你可以调查和探索网络上是否存在安全威胁。

Microsoft 不会将你的数据用于广告。

## <a name="data-protection-and-encryption"></a>数据保护和加密

Defender for Endpoint 服务利用基于安全基础结构的Microsoft Azure技术。

我们的服务需要处理与数据保护相关的各个方面。 加密是最关键之一，它包括静态数据加密、进行中的加密以及密钥保管库的密钥管理。 有关 Defender for Endpoint 服务使用的其他技术详细信息，请参阅 [Azure 加密概述](/azure/security/security-azure-encryption-overview)。

在所有方案中，至少使用 256 位 [AES 加密对数据进行](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 加密。

## <a name="data-storage-location"></a>数据存储位置

Defender for Endpoint 在Microsoft Azure、英国或美国的数据中心运行。 该服务收集的客户数据存储在： () 预配期间标识的租户地理位置; (b) 如果 Defender for Endpoint 使用另一个 Microsoft 联机服务处理此类数据，即其他联机服务的数据存储规则定义的地理位置。

假名形式的客户数据也可以存储在美国的中央存储和处理系统中。

配置后，你无法更改数据存储的位置。 这提供了一种便捷方式，通过主动选择数据将驻留的地理位置来最大程度地降低合规性风险。

## <a name="is-my-data-isolated-from-other-customer-data"></a>我的数据是否与其他客户数据隔离？

可以，数据通过访问身份验证和基于客户标识符的逻辑分离进行隔离。 每个客户只能访问从其自己的组织收集的数据和 Microsoft 提供的一般数据。

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Microsoft 如何防止恶意内部活动和高特权角色的滥用？

根据设计，Microsoft 开发人员和管理员具有足够的权限来履行分配的职责，以运营并改进服务。 Microsoft 部署了预防、检测以及反应控件的组合，包括以下机制，以帮助防止未经授权的开发人员和/或管理活动：

- 对敏感数据的严格访问控制
- 显著增强恶意活动的独立检测的控件组合
- 多个级别的监视、日志记录和报告

此外，Microsoft 对某些操作人员执行后台验证检查，并限制根据后台验证级别对应用程序、系统和网络基础结构的访问。 当运营人员在履行职责时需要访问客户的帐户或相关信息时，他们会遵循正式的流程。

对 Microsoft Azure 政府数据中心中部署的服务的数据的访问权限仅授予经过筛选和批准以处理符合某些政府法规和要求（如 FedRAMP、NIST 800.171 (DIB) 、ITAR、IRS 1075、DoD L4 和 CJIS）的操作人员。

## <a name="is-data-shared-with-other-customers"></a>数据是否与其他客户共享？

不需要。 客户数据与其他客户隔离，不共享。 但是，有关由 Microsoft 处理产生的数据（不包含任何特定于客户的数据）的见解可能会与其他客户共享。 每个客户只能访问从其自己的组织收集的数据和 Microsoft 提供的一般数据。

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Microsoft 将存储我的数据多久？ 什么是 Microsoft 的数据保留策略？

### <a name="at-service-onboarding"></a>在服务载入时

默认情况下，数据保留 180 天;但是，您可以为数据指定数据保留策略。 这将确定适用于终结点的 Window Defender 存储你的数据多久。 可以灵活地选择一个月到六个月，以满足公司的法规合规性需求。

### <a name="at-contract-termination-or-expiration"></a>在合同终止或到期时

当许可证在宽限期或暂停模式下时，你的数据将保留，并且将可供你使用。 在此期限结束时，该数据将从 Microsoft 系统擦除，使其不可恢复，不得晚于合同终止或到期的 180 天。

### <a name="advanced-hunting-data"></a>高级搜寻数据

高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。

## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Microsoft 可以帮助我们维护法规合规性吗？

Microsoft 为客户提供有关 Microsoft 安全与合规计划的详细信息，包括审核报告和合规性包，帮助客户根据自己的法律和法规要求评估适用于 Endpoint 服务的 Defender。 Defender for Endpoint 已获得许多认证，包括 ISO、SOC、FedRAMP High 和 PCI，并继续获得其他特定于国家、区域和行业的认证。

通过为客户提供合规、独立验证的服务，Microsoft 可以让客户更轻松地实现基础结构和所运行的应用程序的合规性。

有关 Defender for Endpoint 认证报告详细信息，请参阅 [Microsoft 信任中心](https://servicetrust.microsoft.com/)。 

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-datastorage-belowfoldlink)。
