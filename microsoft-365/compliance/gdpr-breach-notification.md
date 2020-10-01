---
title: 泄露通知
description: 了解 Microsoft 服务如何避免个人数据泄露，以及 Microsoft 如何在出现数据泄露时答复和通知用户。
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e4750e063c0f049c5f3faa1667aafb7f1afa6586
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305176"
---
# <a name="gdpr-breach-notification"></a>GDPR 泄露通知

一般数据保护条例 (GDPR) 引入了新规定，适用于向欧盟 (EU) 民众提供商品和服务或收集并分析欧盟居民相关数据的组织。无论你或你的企业位于何处，都要遵守该规定。 有关其他详细信息，请参阅 [GDPR 摘要主题](gdpr.md)。 本文档将提供相关信息，以帮助你完成使用 Microsoft 产品和服务的 GDPR 泄露通知。

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>根据 GDPR，什么构成了个人数据泄露行为？

个人数据是指，所有与个人相关、可直接或间接表明身份的信息。 个人数据泄露是指，“导致传输、存储或以其他方式处理的个人数据遭到意外或非法破坏、丢失、更改、未经授权披露或访问的违反安全之事宜。”

## <a name="terminology"></a>术语

本文档中使用的 GDPR 术语的有用定义：

- *数据控制者（控制者）*：单独或与他人共同确定个人数据处理目的和方法的法人、公共机关、机构或其他团体。  
- *个人数据*和*数据主体*：与已识别或可识别的自然人（数据主体）相关的任何信息；可识别的自然人是可以直接或间接识别的自然人。  
- *处理者*：代表控制者处理个人数据的自然人或法人、公共机关、机构或其他团队。  
- *客户数据*：在经营业务的日常运营中生成和存储的数据。

## <a name="microsoft-and-breach-notification"></a>Microsoft 和泄露通知

Microsoft 严格履行一般数据保护条例 (GDPR) 规定的义务。 安全事件/数据泄露是指，存储在 Microsoft 设备或 Microsoft 设施上的客户数据遭到非法访问或可能导致客户数据丢失、泄露或改动的未经授权的访问等事件。

作为数据处理者，Microsoft 将确保服务客户作为数据控制者能够满足 GDPR 的泄露通知要求。 我们的通知提供了进行此评估所需的信息。 Microsoft 会向客户告知任何个人数据泄露，除非确认个人数据难以被人理解（例如，已确认密钥完整性情况下的加密数据）。

数据控制者负责评估数据隐私风险并确定违反是否需要通知客户的 DPA。 Microsoft 提供进行此评估所需的信息以及 GDPR 合规性策略。

初始通知包括对泄露性质、大致的用户影响和缓解步骤（如果适用）的说明。 如果我们的调查在初始通知时还未完成，我们将说明后续的沟通步骤和时间表。 若要详细了解 Microsoft 如何检测和响应个人数据泄露，请参阅服务信任门户中的 [GDPR 数据泄露通知](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)。

下面是有关特定 Microsoft 产品和服务的泄露通知的详细信息。
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft 在系统、流程和人员方面进行了广泛的投资，以减少个人数据泄露的可能性，并快速检测泄露，如果确实发生，则减轻泄露造成的后果。 有关其他详细信息，请参阅 [Office 365 在数据安全性方面的投资](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security)。

    客户可能知道了泄露并希望联系 Microsoft。 在此情况下，请通知 Microsoft 支持团队，该团队随后将与工程团队对接以了解更多信息。

2. **[Azure 和 Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft 拥有全球性的全天候事件响应服务，可用于减轻针对 Microsoft Azure 和 Dynamics 365 的攻击所造成的影响。

    - *检测泄露*：由于 Microsoft 和客户都负有安全义务，因此 Azure 服务采用共同责任模型来定义安全和运营责任。 Microsoft 不会监控或响应客户责任范围内的安全事件。 如果存在相应服务合同，客户事件响应可能涉及与 Azure [客户支持人员](https://azure.microsoft.com/support/options/)进行协作。 Microsoft Azure 还提供各种服务（例如，[ Azure 安全中心](https://azure.microsoft.com/services/security-center/)），客户可以利用这些服务来开发和管理安全事件响应。

        有关在 Microsoft Azure 中触发泄露调查的事件列表，请参阅[检测潜在泄露](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches)。 [Azure 与 GDPR 泄露通知](gdpr-breach-azure-dynamics.md)进一步详细介绍了 Microsoft 如何在 Azure 内调查、管理和响应安全事件。

    - *数据泄露响应*：Microsoft 通过调查事件的功能影响、可恢复性和信息影响来确定泄露的相应优先级和严重性级别。 随着调查的进行，优先级和严重性可能会基于新发现和结论而发生改变。
    Microsoft 安全响应团队与全球法律顾问密切合作，帮助确保根据法律义务和对客户的承诺进行取证。 这些流程在 [Azure 的数据泄露响应](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response)中有详细说明。

    - *客户通知*：Microsoft Azure 会根据需要将数据泄露通知给客户和监管机构。 我们会在声明泄露之时起的 72 小时内送达客户通知，但以下情况除外：

        - Microsoft 认为通知操作将增加其他客户面临的风险。
        - 72 小时时间线可能会留下一些可用的事件详细信息。 这些详细信息将在调查过程中提供给你。

        有关更多详细信息，请参阅[客户通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification)。

3. **[Microsoft 支持和专业服务](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    专业服务的性质意味着某些数据保护事件可能属于客户的责任范围。 当 Microsoft 专业服务识别出数据保护事件时，它会遵循[数据保护事件响应流程的范围和限制](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process)中所述的成文的行业标准响应计划。

## <a name="breach-notification-admin-tools"></a>泄露通知管理工具

- **设置组织的隐私联系人**：租户管理员可以使用 [Azure Active Directory 管理门户](https://go.microsoft.com/fwlink/p/?linkid=2052736)来定义组织的隐私联系人，以供 Microsoft 在必要时联系。

## <a name="learn-more"></a>了解更多

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
