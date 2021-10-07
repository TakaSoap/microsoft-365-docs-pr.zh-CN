---
title: 设置基本移动性和安全性
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 设置基本移动性和安全性，通过执行远程擦除设备等操作保护和管理用户的移动设备。
ms.openlocfilehash: bbf7cf84dd996a0e548a76978e8fbba58f40c070
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165960"
---
# <a name="set-up-basic-mobility-and-security"></a>设置基本移动性和安全性

内置的基本移动性和安全性 Microsoft 365可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Android 和 Windows 电话。 可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。

有问题？ 有关帮助解决常见问题的常见问题解答，请参阅 Basic [Mobility and Security Faq (Faq) ](frequently-asked-questions.yml)。 请注意，不能使用委派管理员帐户管理基本移动性和安全性。 有关详细信息，请参阅合作伙伴 [：提供委派管理](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。 

设备管理是安全与合规&的一部分，因此你需要前往开始基本移动性和安全性设置。

## <a name="activate-the-basic-mobility-and-security-service"></a>激活基本移动性和安全性服务

1. 登录以Microsoft 365全局管理员帐户登录。

2. 转到 [激活基本移动性和安全性](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。

   激活基本移动性和安全性可能需要一些时间。 完成后，你将收到一封电子邮件，说明要采取的步骤。

## <a name="set-up-mobile-device-management"></a>设置移动设备管理

服务准备就绪后，请完成以下步骤以完成设置。

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>步骤 1： (配置) 移动性和安全性的域的必需步骤

如果你没有与自定义域关联的自定义域Microsoft 365或者如果你未管理 Windows设备，你可以跳过此部分。 否则，您需要在 DNS 主机上添加域的 DNS 记录。 如果已添加记录，作为设置域的一Microsoft 365，则一切都已设置。 添加记录后，Microsoft 365组织中使用使用自定义域的电子邮件地址登录 Windows 设备的用户将被重定向以注册基本移动性和安全性。

需要帮助设置记录？ 查找你的域注册机构，然后选择注册机构名称，以转到添加 DNS 记录以连接你的域中提供的有关创建 [DNS 记录的分步帮助](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。 使用这些说明创建简化注册过程中描述的 CNAME [Windows，而无需Azure AD Premium。](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

添加两条 CNAME 记录后，返回到安全与&中心，然后转到数据丢失防护 设备管理以完成下一  >     步。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>步骤 2： (为) iOS 设备配置 APNs 证书时所需的步骤

若要管理 iOS 设备iPad和 iPhone，需要创建 APNs 证书。

1. 登录以Microsoft 365全局管理员帐户登录。

2. 在浏览器类型中  [https://protection.office.com](https://protection.office.com/) ：。

3. 选择  **"数据丢失防护**   >  **""设备管理**"，然后选择"**适用于 iOS 设备的 APNs 证书"。**

4. 在"Apple 推送通知证书设置页上，选择"下一 **步"。**

5. 选择 **"下载 CSR 文件**"，将证书签名请求保存到计算机上将记住   的某个位置。 选择" **下一步"。**

6. 在"创建 APNs 证书"页上：

   - 选择 Apple APNS 门户以打开 Apple 推送证书门户。
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - 选择"创建证书"并接受使用条款。
   - 浏览到从计算机下载的证书签名请求，Microsoft 365选择"更新"。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. 返回到"下一Microsoft 365，然后选择"下一 **步"。**

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. 选择"  **完成"。**

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>步骤 3： (推荐) 设置多重身份验证

MFA 通过要求第二种形式的身份验证Microsoft 365登录以确保移动设备注册的安全。 正确输入工作帐户密码后，用户需要确认其移动设备上的电话呼叫、短信或应用通知。 他们只能在完成第二种形式的身份验证后注册设备。 在基本移动性和安全性中注册用户设备后，用户Microsoft 365工作帐户访问资源。

若要了解如何在 Azure AD 门户中启用 MFA，请参阅 [设置多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)。

设置 MFA 后，返回到安全与合规&并导航到数据丢失防护 设备管理 **** 设备策略以完成下一   >     >  ****   步。

### <a name="step-4-recommended-manage-device-security-policies"></a>步骤 4： (建议) 管理设备安全策略

下一步是创建和部署设备安全策略，以帮助保护你的Microsoft 365数据。 例如，如果用户丢失设备，可以通过创建一个策略，在 5 分钟不活动后锁定设备，在三次登录失败后擦除设备，以帮助防止数据丢失。

1. 登录以Microsoft 365全局管理员帐户登录。

2. 选择 ["激活移动设备管理"。](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) 如果服务已激活，而是激活步骤，你将看到一个指向"管理设备 ["的链接](https://admin.microsoft.com/adminportal/home#/MifoDevices)   。

3. 转到设备 **策略**。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全和移动策略设置。":::

4. 按照在基本移动性和安全性中创建设备安全策略中的步骤，创建和部署适合 [你的组织的设备安全策略](create-device-security-policies.md)。

> [!TIP]
>
> - 创建新策略时，你可能希望设置该策略以允许访问，并报告用户设备不符合策略的策略违反。 这允许你查看受策略影响的移动设备数，而不会阻止对移动设备Microsoft 365。
>
> - 在向组织中的每个人部署新策略之前，我们建议在少量用户使用的设备上测试该策略。
>
> - 此外，在部署策略之前，请让组织了解在基本移动性和安全性中注册设备的潜在影响。 根据策略的设置方式， (不符合策略的设备) 访问Microsoft 365。 不兼容的设备可能还安装了应用、照片和其他个人信息，在注册的设备上，如果擦除设备，这些应用、照片和其他个人信息可能会被删除。 有关详细信息，请参阅 [Basic Mobility and Security](wipe-mobile-device.md)中的擦除移动设备。

## <a name="make-sure-users-enroll-their-devices"></a>确保用户注册其设备

创建并部署移动设备管理策略后，组织中应用设备策略的每个许可 Microsoft 365 用户下次从移动设备登录 Microsoft 365 时会收到注册消息。 他们必须完成注册和激活步骤，然后才能访问Microsoft 365文档。 有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)。

> [!IMPORTANT]
> 如果注册过程不支持用户的首选语言，则用户可能会以另一种语言在移动设备上收到注册通知和步骤。 移动设备注册过程Microsoft 365支持的语言。

使用 Android 或 iOS 设备的用户需要安装 公司门户 应用，这是注册过程的一部分。

## <a name="related-content"></a>相关内容

[基本移动性和安全性](capabilities.md) 功能 (文章) \
[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article) 