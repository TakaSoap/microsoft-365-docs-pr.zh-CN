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
ms.openlocfilehash: a671fc9234f76c63ff7336369c87e680a4432cc3
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920286"
---
# <a name="gdpr-breach-notification"></a>GDPR 泄露通知

The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located. Additional details can be found in the [GDPR Summary topic](gdpr.md). This document leads you to information on the completion of Breach Notifications under the GDPR using Microsoft products and services.

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>根据 GDPR，什么构成了个人数据泄露行为？

Personal data means any information related to an individual that can be used to identify them directly or indirectly. A personal data breach is 'a breach of security leading to the accidental or unlawful destruction, loss, alteration, unauthorized disclosure of, or access to, personal data transmitted, stored, or otherwise processed'.

## <a name="terminology"></a>术语

本文档中使用的 GDPR 术语的有用定义：

- *数据控制者（控制者）* ：单独或与他人共同确定个人数据处理目的和方法的法人、公共机关、机构或其他团体。  
- *个人数据* 和 *数据主体* ：与已识别或可识别的自然人（数据主体）相关的任何信息；可识别的自然人是可以直接或间接识别的自然人。  
- *处理者* ：代表控制者处理个人数据的自然人或法人、公共机关、机构或其他团队。  
- *客户数据* ：在经营业务的日常运营中生成和存储的数据。

## <a name="microsoft-and-breach-notification"></a>Microsoft 和泄露通知

Microsoft takes its obligations under the General Data Protection Regulation (GDPR) seriously. A security incident/data breach refers to events such as unlawful access to customer's data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such that has the potential to result in the loss, disclosure, or alteration of customer data.

As a data processor, Microsoft ensures that service customers are able to meet the GDPR's breach notification requirements as data controllers. Our notification provides the information needed to make that assessment. Microsoft notifies customers of any personal data breach, except for those cases where personal data is confirmed to be unintelligible (for example, encrypted data where integrity of the keys is confirmed).

Data controllers are responsible for assessing risks to data privacy and determining whether a breach requires notification of a customer's DPA. Microsoft provides the information needed, along with your GDPR compliance policy, to make that assessment.

Initial notification includes a description of the nature of the breach, approximate user impact, and mitigation steps (if applicable). If our investigation is not complete at the time of initial notification, we will indicate next steps and timelines for subsequent communication. For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.

下面是有关特定 Microsoft 产品和服务的泄露通知的详细信息。
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft invests extensively in systems, processes, and personnel to reduce the likelihood of personal data breach and to quickly detect and mitigate consequence of breach if it does occur. Additional details can be read at [Office 365 Investments in Data Security](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).

    A customer may become aware of a breach and wish to contact Microsoft. In this case, notify Microsoft Support, which will then interface with engineering teams for more information.

2. **[Azure 和 Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft 拥有全球性的全天候事件响应服务，可用于减轻针对 Microsoft Azure 和 Dynamics 365 的攻击所造成的影响。

    - *检测泄露* ：由于 Microsoft 和客户都负有安全义务，因此 Azure 服务采用共同责任模型来定义安全和运营责任。Microsoft 不监视或响应客户的责任范围内的安全事件。鉴于适当的服务合同，客户事件响应可能涉及到与 Azure [客户支持](https://azure.microsoft.com/support/options/)的合作。Microsoft Azure 还提供了各种服务（例如 [Azure Defender](https://azure.microsoft.com/services/security-center/)），客户可以利用这些服务来开发和管理安全事件响应。

        For a list of events that trigger a breach investigation in Microsoft Azure, see [Detection of Potential Breaches](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches). [Azure and Breach Notification under the GDPR](gdpr-breach-azure-dynamics.md) further details how Microsoft investigates, manages, and responds to security incidents within Azure.

    - *Data Breach Response* : Microsoft determines appropriate priority and severity levels of a breach by investigating the functional impact, recoverability, and information impact of the incident. Priority and severity may change over the course of the investigation, based on new findings and conclusions. Microsoft's security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. These processes are detailed in [Azure's Data Breach Response](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).

    - *Customer Notification* : Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances:

        - Microsoft 认为通知操作将增加其他客户面临的风险。
        - The 72-hour timeline may leave some incident details available. These details will be provided to you as the investigation proceeds.

        有关更多详细信息，请参阅[客户通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification)。

3. **[Microsoft 支持和专业服务](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    The nature of professional services means that some data protection incidents may fall within the customer's realm of responsibility. When Microsoft Professional Services identifies a data protection incident, it follows documented industry standard response plan as outlined in [Scope & Limits of Data Protection Incident Response Process](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).

## <a name="breach-notification-admin-tools"></a>泄露通知管理工具

- **设置组织的隐私联系人** ：租户管理员可以使用 [Azure Active Directory 管理门户](https://go.microsoft.com/fwlink/p/?linkid=2052736)来定义组织的隐私联系人，以供 Microsoft 在必要时联系。

## <a name="learn-more"></a>了解更多

- [Microsoft 信任中心](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
