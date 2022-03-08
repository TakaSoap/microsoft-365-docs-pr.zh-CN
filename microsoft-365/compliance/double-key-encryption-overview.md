---
title: 双密钥加密概述和常见问题解答
description: 有关双密钥加密的常见问题Microsoft 365。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 02/28/2022
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 269937e78ffee6956df5a4dc8dc978fa30043912
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320979"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>双密钥加密常见问题

对双密钥加密的工作原理有一个问题？ 请在此处查看答案。

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>What is Double Key Encryption for Microsoft 365 (DKE) ？

双密钥加密Microsoft 365使客户能够保护其高度敏感的数据以满足特定要求。 它帮助客户保持对加密密钥的完全控制。 它使用两个密钥来保护数据;控件中的一个键，另一个密钥安全地存储在Microsoft Azure。 查看受双密钥加密保护的数据需要访问这两个密钥。 由于 Microsoft 只能访问其中一个密钥，因此受保护数据仍无法访问 Microsoft，从而确保你可以完全控制数据隐私和安全性。  

可以在本地密钥管理服务器或云管理服务器中 (用于请求密钥的双密钥加密服务) 。 像维护任何其他应用程序一样维护服务。 双密钥加密使您能够控制对双密钥加密服务的访问。 可以在本地存储高度敏感的数据或将其移动到云中。 你可以确信阻止第三方访问，因为你保持对密钥的完全控制。 双密钥加密允许您将数据和密钥存储在同一位置。

DKE 可帮助你满足多项法规和标准，如《一般数据保护条例》 (GDPR) 、健康保险可移植性和责任法案 (HIPAA) 、格雷姆-格雷姆-拉雷法案 (GLBA) 、俄罗斯的数据本地化法 – 联邦法律第 2004。 242-FZ、澳大利亚联邦隐私法案 1988 和新西兰隐私法案 1993。

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>能否将双密钥加密Microsoft Office内置敏感度标签？

你需要使用 Azure 信息保护统一标签客户端通过双密钥加密来保护文档。 目前，你无法Microsoft Office内置敏感度标签。

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>我Microsoft 365 应用版 DKE 使用哪些功能？

可以使用 DKE 标签来保护使用桌面版本的 Word、Excel 和 PowerPoint 版本的Windows。 确保使用的是 *.12711 或更高版本 (桌面版本的 Word、PowerPoint 和 Excel) Windows。

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>双密钥加密与 HYOK 解决方案中现有的密钥 (不同) ？

双密钥加密使用两个密钥加密数据。 你的加密密钥在你的控件中，第二个密钥存储在Microsoft Azure，以便你可以将加密数据移动到云。 HYOK 仅使用一个密钥保护内容，并且该密钥始终位于本地。  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>能否在外部共享双密钥加密文档？

你可以与单独租户上的用户共享双密钥加密文档，只要这些用户：

- 拥有访问双密钥加密服务中的密钥所需的权限。

- 拥有访问密钥所需的权限Microsoft Azure。

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>使用 HYOK 保护的文档会发生什么情况？

部署双密钥加密不会影响现有的 HYOK 设置。 但是，我们建议您开始与 HYOK 并行使用双密钥加密。

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>能否在我的非 Microsoft 空心环境中运行双密钥加密？

DKE 不支持这些环境，因为该服务需要访问Microsoft Azure。

## <a name="where-can-i-store-double-key-encrypted-documents"></a>在哪里可以存储双密钥加密文档？

可以在本地或云中存储双密钥加密文档。 在云中，你可以将加密内容移动到 SharePoint Online 和 OneDrive for Business。 由于 Microsoft 无法访问你的私钥，加密数据对 Microsoft 保持不透明。 这也意味着你无法联机查看 Web 应用中的Office文档。

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>What regions and languages is Double Key Encryption available in？ 双密钥加密是否在全球可用？

DKE 标签本地化为与 DKE 中其他敏感度标签Microsoft 信息保护。 双密钥加密在全球范围内可用。

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>能否将非 DKE 标签转换为 DKE 标签？

否。 创建 DKE 后，不能将 DKE 添加到标签。 相反，你必须选择" **使用双密钥加密"** ，并创建标签时提供双密钥加密服务的 URL。

## <a name="how-do-i-roll-my-dke-keys"></a>如何滚动 DKE 密钥？

有关滚动密钥 (也称为旋转或重新) Azure 中存储的密钥，请参阅 [Azure 信息](/azure/information-protection/operations-customer-managed-tenant-key)保护租户密钥的操作。

有关 [为](double-key-encryption.md#tenant-and-key-settings) DKE 服务创建新密钥的信息，请参阅租户和密钥设置。

创建密钥时，将设置名称和 GUID。 然后，如果旋转一个键，则保留具有名称和 GUID 的旧记录，但添加一个名称相同但 GUID 不同的新记录。 新密钥设置为活动，以便公钥 API 开始返回它以用于新加密。 这两个密钥都可用于解密，以便可以解密新内容和旧内容。