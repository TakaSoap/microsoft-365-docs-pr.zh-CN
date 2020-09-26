---
title: 双重密钥加密概述和 FAQ
description: 适用于 Microsoft 365 的双重密钥加密的常见问题。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 98c61e66155e21624e8ecba460ebc3041e72ada5
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277649"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>双重密钥加密常见问题

有关于双密钥加密工作方式的问题？ 在此处查找答案。

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Microsoft 365 (DKE) 的双重密钥加密是什么？

Microsoft 365 的双重密钥加密使客户能够保护高度敏感的数据，以满足专门的要求。 它可帮助客户维护对其加密密钥的完全控制。 它使用两个键来保护数据;您的控件中有一个密钥，另一个密钥在 Microsoft Azure 中安全存储。 查看使用双重密钥加密保护的数据需要对这两个密钥的访问权限。 由于 Microsoft 只能访问其中的一个注册表项，因此 Microsoft 无法访问受保护的数据，从而确保您可以完全控制您的数据隐私和安全性。  

您可以在所选位置 (本地密钥管理服务器或云) 中承载用于请求密钥的双密钥加密服务。 您可以像维护任何其他应用程序一样维护服务。 通过双密钥加密，可以控制对双密钥加密服务的访问。 您可以将高度敏感的数据存储在本地，也可以将其移动到云。 你可以确信阻止第三方访问，因为你可以保持对密钥的完全控制。 通过双密钥加密，可以将数据和密钥存储在相同的位置。

DKE 帮助您跨几个法规和标准（如常规 Data Protection 规章 (GDPR) 、健康保险可移植性和责任法案 (HIPAA) 、格雷姆里奇-比利雷法案 (GLBA) 、俄罗斯的数据本地化法–联邦法律）来满足法规要求。 242-FZ、澳大利亚的联邦隐私法案1988和新西兰的隐私法案1993。

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>是否可以对 Microsoft Office 内置敏感度标签使用双密钥加密？

您需要使用 Azure 信息保护统一标签客户端，以使用双密钥加密来保护文档。 目前，不能使用 Microsoft Office 的内置敏感度标签。 

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>我可以在 DKE 中使用哪些 Microsoft 365 应用？

您可以使用 DKE 标签来保护使用 Windows 上的 Word、Excel 和 PowerPoint 的桌面版本的文档。 确保在 Windows 上使用12711或更高版本 (Word、PowerPoint 和 Excel) 的桌面版本。

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>双密钥加密与现有保留的不同之处 HYOK) 解决方案中您自己的密钥 (？

双密钥加密使用两个密钥对数据进行加密。 你的加密密钥在你的控制中，第二个密钥存储在 Microsoft Azure 中，这样你就可以将加密的数据移动到云。 HYOK 仅使用一个密钥来保护你的内容，并且密钥始终在本地。  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>是否可以在外部共享双密钥加密的文档？

您可以在单独的租户上与用户共享双密钥加密的文档，只要这些用户具有以下条件：

- 拥有访问您的双重密钥加密服务中的密钥所需的权限。

- 拥有在 Microsoft Azure 中访问密钥所需的权限。

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>通过 HYOK 保护的文档会发生什么情况？

部署双重密钥加密不会影响现有的 HYOK 设置。 但是，我们建议您在与 HYOK 并行使用时开始使用双密钥加密。

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>我是否可以在我的非 Microsoft 无成本环境中运行双重密钥加密？

DKE 不支持这些环境，因为该服务需要访问 Microsoft Azure。

## <a name="where-can-i-store-double-key-encrypted-documents"></a>在哪里可以存储双密钥加密文档？

您可以在本地或在云中存储双密钥加密的文档。 在云中，你可以将加密的内容移动到 SharePoint Online 和 OneDrive for Business。 由于 Microsoft 对你的私钥没有访问权限，因此加密的数据在 Microsoft 中保持不透明。 这也意味着您无法在 Office Web Apps 中联机查看加密的文档。

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>哪些区域和语言是可在中使用的双密钥加密？ 在全球范围内是否可以使用双重密钥加密？

DKE 标签与 Microsoft 信息保护中的其他敏感度标签本地化为相同的语言。 双重密钥加密在全球范围内可用。

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>是否可以将非 DKE 标签转换为 DKE 标签？

否。 创建标签后，不能向其添加 DKE。 相反，您必须选择 " **使用双密钥加密** "，并在创建标签时提供您的双密钥加密服务的 URL。

## <a name="how-do-i-roll-my-dke-keys"></a>如何滚动我的 DKE 键？

有关滚动 (也称为 "旋转或重新加密) 在 Azure 中存储的密钥的说明，请参阅 [Azure 信息保护租户密钥的操作](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)。

有关为 DKE 服务创建新密钥的信息，请参阅 [租户和关键设置](double-key-encryption.md#tenant-and-key-settings) 。

创建密钥时，需要设置名称和 GUID。 然后，如果您旋转某个键，则保留具有名称和 GUID 的旧记录，但添加一个名称相同但 GUID 不同的新记录。 新密钥设置为活动，以便公钥 API 开始为新的加密返回它。 这两个密钥都可用于解密，以便可以解密新内容和旧内容。
