---
title: '使用非 Microsoft 云应用的数据丢失防护策略 (预览) '
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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用非 Microsoft 云应用的 dlp 策略。
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649653"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>使用非 Microsoft 云应用的数据丢失防护策略 (预览) 

对非 Microsoft 云应用 (DLP) 策略的数据丢失防护是 Microsoft 365 DLP 功能套件的一部分;使用这些功能，您可以跨 Microsoft 365 服务发现和保护敏感项目。 有关所有 Microsoft DLP 产品的详细信息，请参阅 [数据丢失防护概述](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)。

您可以使用 DLP 策略来监视和检测何时使用敏感项目，并通过非 Microsoft 云应用共享这些应用。 使用这些策略，您将能够确保正确使用和保护它们所需的可见性和控制，并有助于防止可能危害它们的风险行为。

## <a name="before-you-begin"></a>准备工作

### <a name="skusubscriptions-licensing"></a>SKU/订阅许可

在开始对非 Microsoft 云应用使用 DLP 策略之前，请确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 和任何加载项。 若要访问和使用此功能，您必须具有以下订阅或加载项之一：

- Microsoft 365 E5
- Microsoft 365 E5 合规
- Microsoft 365 E5 安全版

### <a name="prepare-your-cloud-app-security-environment"></a>准备云应用安全环境

对非 Microsoft 云应用的 DLP 策略使用云应用安全 DLP 功能。 若要使用它，应准备云应用安全环境。 有关说明，请参阅 [为您的应用程序设置即时可见性、保护和调控操作](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。

### <a name="connect-a-non-microsoft-cloud-app"></a>连接非 Microsoft 云应用

若要将 DLP 策略用于特定的非 Microsoft 云应用，应用必须连接到云应用安全性。 有关信息，请参阅：

- [连接框](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [连接收存箱](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [连接 G 套件](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [连接 Salesforce](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [连接 Cisco Webex](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

将云应用程序连接到云应用安全性之后，可以为其创建 Microsoft 365 DLP 策略。

>[!NOTE]
>此外，还可以使用 Microsoft 云应用安全为 Microsoft 云应用创建 DLP 策略。 但是，建议使用 Microsoft 365 创建和管理针对 Microsoft 云应用的 DLP 策略。

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>创建到非 Microsoft 云应用的 DLP 策略

当您选择 DLP 策略的位置时，请打开 **Microsoft 云应用安全** 位置。

- 若要选择特定的应用或实例，请选择 " **选择实例**"。
- 如果不选择实例，策略将使用 Microsoft Cloud App Security 租户中的所有已连接应用。

   ![应用策略的位置](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

您可以为每个受支持的非 Microsoft 云应用程序选择各种操作。 每个应用程序都有不同的可能操作 (取决于云应用程序 API) 。

![创建规则](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

在 DLP 策略中创建规则时，可以为非 Microsoft 云应用程序选择操作。 若要限制第三方应用，请选择 " **限制第三方应用**"。

![限制第三方应用程序](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

有关创建和配置 DLP 策略的信息，请参阅 [Create test and 调谐 a dlp policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)。

## <a name="see-also"></a>另请参阅

- [创建测试并优化 DLP 策略](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [开始使用默认 DLP 策略](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [从模板创建 DLP 策略](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
