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
description: 通过执行远程擦拭设备等操作，设置基本移动性和安全性以保护和管理用户的移动设备。
ms.openlocfilehash: b26906c0f374f5dc103fe26e4619663195da6ebd
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780822"
---
# <a name="set-up-basic-mobility-and-security"></a>设置基本移动性和安全性

内置的基本移动性和安全性Microsoft 365可帮助你保护和管理用户的移动设备，如 iPhone、iPad、Androids 和Windows手机。 可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。

有问题？ 有关帮助解决常见问题的常见问题解答，请参阅 [常见问题解答 (常见问题解答) ](frequently-asked-questions.yml)。 请注意，不能使用委派的管理员帐户来管理基本移动性和安全性。 有关详细信息，请参阅 [合作伙伴：提供委派的管理](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。 

设备管理是安全&合规中心的一部分，因此需要去那里启动基本移动性和安全性设置。

## <a name="activate-the-basic-mobility-and-security-service"></a>激活基本移动性和安全性服务

1. 使用全局管理员帐户登录到Microsoft 365。

2. 转到 [“激活基本移动性和安全性](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)”。

   激活基本移动性和安全性可能需要一些时间。 完成后，你将收到一封电子邮件，说明接下来要采取的步骤。

## <a name="set-up-mobile-device-management"></a>设置移动设备管理

服务准备就绪后，完成以下步骤以完成设置。

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>步骤 1： (配置基本移动性和安全性所需的域) 

如果没有与Microsoft 365关联的自定义域，或者未管理Windows设备，则可以跳过本部分。 否则，需要在 DNS 主机上为域添加 DNS 记录。 如果已添加记录，则在使用 Microsoft 365 设置域时，将全部设置。 添加记录后，组织中使用使用自定义域的电子邮件地址登录其Windows设备的Microsoft 365用户将重定向以注册基本移动性和安全性。

需要有关设置记录的帮助？ 找到域注册机构，然后选择注册机构名称，以转到在 [添加 DNS 记录](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)中提供的列表中创建 DNS 记录以连接域的分步帮助。 使用这些说明创建简化Windows注册中所述的 CNAME 记录，[而无需Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)。

添加两条 CNAME 记录后，返回到安全&合规中心并转到 **数据丢失防护** > **Device 管理** 以完成下一步。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>步骤 2： (为 iOS 设备配置 APN 证书) 必需

若要管理 iPad 和 iPhone 等 iOS 设备，需要创建 APN 证书。

1. 使用全局管理员帐户登录到Microsoft 365。

2. 在浏览器类型中： [https://protection.office.com](https://protection.office.com/).

3. 选择 **数据丢失防护** > **Device 管理**，并选择 **适用于 iOS 设备的 APN 证书**。

4. 在 Apple 推送通知证书设置页上，选择 **“下一步**”。

5. 选择 **“下载 CSR 文件** ”，并将证书签名请求保存到计算机上你将记住的某个位置。 选择 **下一步**。

6. 在“创建 APN 证书”页上：

   - Select Apple APNS Portal to open the Apple Push Certificates Portal. 
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Select Create a Certificate and accept the Terms of Use.
   - 浏览到从Microsoft 365和 selectUpload 下载到计算机的证书签名请求。
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. 返回Microsoft 365并选择 **“下一步**”。

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. 选择 **“完成”**。

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>步骤 3： (建议) 设置多重身份验证

MFA 要求进行第二种身份验证，从而帮助保护登录以Microsoft 365进行移动设备注册。 用户在正确输入工作帐户密码后，必须在其移动设备上确认电话呼叫、短信或应用通知。 只有在这第二种身份验证形式完成后，他们才能注册其设备。 在基本移动性和安全性中注册用户设备后，用户只能使用其工作帐户访问Microsoft 365资源。

若要了解如何在Azure AD门户中启用 MFA，请[参阅设置多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)。

设置 MFA 后，返回到安全&合规中心并导航到 **数据丢失防护** > **Device** **managementDevice** >  策略以完成下一步。

### <a name="step-4-recommended-manage-device-security-policies"></a>步骤 4： (建议) 管理设备安全策略

下一步是创建和部署设备安全策略，以帮助保护Microsoft 365组织数据。 例如，如果用户丢失设备，可以通过创建策略来锁定处于非活动状态的设备，并在三次登录失败后擦除设备，从而帮助防止数据丢失。

1. 使用全局管理员帐户登录到Microsoft 365。

2. 选择[“激活移动设备管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)”。 如果服务已激活，则会看到“ [管理设备](https://admin.microsoft.com/adminportal/home#/MifoDevices) ”链接的激活步骤。

3. 转到 **设备策略**。

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本的安全性和移动性策略设置。":::

4. 按照“ [在基本移动性和安全性中创建设备安全策略”中的](create-device-security-policies.md)步骤创建和部署适合组织的设备安全策略。

> [!TIP]
>
> - 创建新策略时，可能需要将策略设置为允许在用户设备不符合策略的情况下访问和报告策略冲突。 这样便可以查看策略影响的移动设备数量，而不会阻止访问Microsoft 365。
>
> - 在将新策略部署到组织中的每个人之前，我们建议在少数用户使用的设备上对其进行测试。
>
> - 此外，在部署策略之前，请让组织了解在基本移动性和安全性中注册设备的潜在影响。 根据设置策略的方式，可能会阻止不符合策略 (不合规设备) 设备访问Microsoft 365。 不符合的设备可能还安装了应用、照片和其他个人信息，如果擦除设备，这些信息可能会在已注册的设备上被删除。 有关详细信息，请参阅 [在基本移动性和安全性中擦除移动设备](wipe-mobile-device.md)。

## <a name="make-sure-users-enroll-their-devices"></a>确保用户注册其设备

创建并部署移动设备管理策略后，组织中应用设备策略的每个许可Microsoft 365用户在下次从移动设备登录到Microsoft 365时都会收到注册消息。 他们必须先完成注册和激活步骤，然后才能访问Microsoft 365电子邮件和文档。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device.md)。

> [!IMPORTANT]
> 如果注册过程不支持用户的首选语言，则用户可能会收到另一种语言的移动设备上的注册通知和步骤。 移动设备上的注册过程目前不支持Microsoft 365中支持的所有语言。

在注册过程中，需要使用 Android 或 iOS 设备的用户安装公司门户应用。

## <a name="related-content"></a>相关内容

[基本移动性和安全](capabilities.md) 性功能 (文章) \
[在基本移动性和安全](create-device-security-policies.md) 性 (文章中创建设备安全策略) 
