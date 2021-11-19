---
title: 对非 Microsoft 云应用使用数据丢失防护策略
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何将 dlp 策略用于非 Microsoft 云应用。
ms.openlocfilehash: b374f9b85d41b6dd6a5281e17347dffd414361da
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61109775"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a>对非 Microsoft 云应用使用数据丢失防护策略

数据丢失防护 (DLP) 策略到非 Microsoft 云应用是 Microsoft 365 DLP 功能套件的一部分;使用这些功能，可以跨 Microsoft 365 服务发现和保护敏感项目。 有关所有 Microsoft DLP 产品/服务的信息，请参阅了解 [数据丢失防护](dlp-learn-about-dlp.md)。

您可以使用 DLP 策略对非 Microsoft 云应用进行监视和检测，以监视和检测何时通过非 Microsoft 云应用使用和共享敏感项目。 使用这些策略可为你提供所需的可见性和控制，以确保正确使用和保护它们，并且有助于防止可能损害它们的风险行为。

## <a name="before-you-begin"></a>准备工作

### <a name="skusubscriptions-licensing"></a>SKU/订阅许可

开始对非 Microsoft 云应用使用 DLP 策略之前，Microsoft 365[订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何加载项。 若要访问和使用此功能，你必须拥有以下订阅或加载项之一：

- Microsoft 365 E5
- Microsoft 365 E5 合规
- Microsoft 365 E5 安全性

### <a name="permissions"></a>权限
创建 DLP 策略的用户应是：

- 全局管理员
- 合规性管理员：在Azure AD
- 合规性数据管理员：在Azure AD

### <a name="prepare-your-defender-for-cloud-apps-environment"></a>为云应用环境准备 Defender

非 Microsoft 云应用的 DLP 策略使用 Defender for Cloud Apps DLP 功能。 若要使用它，你应该为云应用环境准备 Defender。 有关说明，请参阅为应用设置即时可见性、保护 [和管理操作](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。

### <a name="connect-a-non-microsoft-cloud-app"></a>连接非 Microsoft 云应用

若要将 DLP 策略用于特定的非 Microsoft 云应用，该应用必须连接到 Defender for Cloud Apps。 有关信息，请参阅：

- [连接 Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [连接 Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [连接 G-Workspace](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [连接 Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [连接 Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

将云应用连接到 Defender for Cloud Apps 后，你可以为Microsoft 365创建 DLP 策略。

> [!NOTE]
> 还可以使用 Microsoft Defender for Cloud Apps 创建 Microsoft 云应用的 DLP 策略。 但是，建议使用 Microsoft 365 Microsoft 云应用创建和管理 DLP 策略。

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>创建对非 Microsoft 云应用的 DLP 策略

当你选择 DLP 策略的位置时，请打开 **Microsoft Defender for Cloud Apps** 位置。

- 若要选择特定应用或实例，请选择"**选择实例"。**
- 如果未选择实例，该策略将使用 Microsoft Defender for Cloud Apps 租户中所有已连接的应用。

   ![要应用策略的位置。](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General。](../media/2-dlp-non-microsoft-cloud-app-box.png)

你可以为每种受支持的非 Microsoft 云应用选择各种操作。 对于每个应用，可能的操作 (取决于云应用 API) 。

![创建规则。](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

在 DLP 策略中创建规则时，可以选择针对非 Microsoft 云应用的操作。 若要限制第三方应用，请选择"**限制第三方应用"。**

![限制第三方应用。](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> 应用于非 Microsoft 应用的 DLP 策略使用 Microsoft Defender for Cloud Apps。 创建非 Microsoft 应用的 DLP 策略时，将在 Microsoft Defender for Cloud Apps 中自动创建相同的策略。

有关创建和配置 DLP 策略的信息，请参阅创建 [测试和调整 DLP 策略](./create-test-tune-dlp-policy.md)。

## <a name="see-also"></a>另请参阅

- [创建测试和调整 DLP 策略](./create-test-tune-dlp-policy.md)
- [开始使用默认 DLP 策略](./get-started-with-the-default-dlp-policy.md)
- [从模板创建 DLP 策略](./create-a-dlp-policy-from-a-template.md)
