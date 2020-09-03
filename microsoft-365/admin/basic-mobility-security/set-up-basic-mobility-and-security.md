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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 设置基本移动性和安全性以保护和管理用户的移动设备。
ms.openlocfilehash: 0d62c209d4eb9d0da9096ccd5ca2d4a387becf95
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336744"
---
# <a name="set-up-basic-mobility-and-security"></a>设置基本移动性和安全性

Microsoft 365 的内置基本移动性和安全性可帮助您保护和管理用户的移动设备，如 Iphone、Ipad、Androids 和 Windows phone。 可以创建和管理设备安全策略，远程擦除设备，以及查看详细的设备报告。

有问题？ 有关解决常见问题的常见问题解答，请参阅 [基本移动性和安全常见问题 (FAQ) ](basic-mobility-and-security-frequently-asked-questions.md)。 请注意，不能使用委派的管理员帐户来管理基本的移动性和安全性。 有关详细信息，请参阅 [合作伙伴：提供委派管理](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。 

设备管理是安全 & 合规性中心的一部分，因此您需要转到此处以启动 MDM 安装程序。

## <a name="activate-the-basic-mobility-and-security-service"></a>激活 "基本移动性和安全服务"

1. 使用全局管理员帐户登录到 Microsoft 365。
    

2. 请转到 [激活基本移动性和安全性](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)。
    
    可能需要一段时间来激活基本的移动性和安全性。 完成后，你将收到一封说明要执行的后续步骤的电子邮件。

## <a name="set-up-mobile-device-management"></a>设置移动设备管理

服务准备就绪后，请完成以下步骤以完成安装。

### <a name="step-1-required-configure-domains-for-mdm"></a>步骤1： (必需的) 配置 MDM 域

如果没有与 Microsoft 365 关联的自定义域，或者如果你不管理 Windows 设备，则可以跳过此部分。 否则，您将需要在 DNS 主机上添加域的 DNS 记录。 如果已添加了记录，则在使用 Microsoft 365 设置域的过程中，你已全部设置。 在添加记录后，组织中使用使用您的自定义域的电子邮件地址登录到其 Windows 设备的 Microsoft 365 用户将被重定向，以注册基本移动性和安全性。

需要有关设置记录的帮助吗？ 查找您的域注册机构并选择注册器名称，以转到在 [添加 dns 记录以连接域](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)中提供的列表中创建 DNS 记录的分步帮助。 按照这些说明创建在 [简化 Windows 注册（无需 AZURE AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)）中描述的 CNAME 记录。

在添加两条 CNAME 记录后，请返回到安全 & 合规性中心并转到**数据丢失防护**  >  **设备管理**，   以完成下一步。

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>步骤2： (必需的) 为 iOS 设备配置 APNs 证书

若要管理 iPad 和 Iphone 等 iOS 设备，您需要创建 APNs 证书。

1. 使用全局管理员帐户登录到 Microsoft 365。   

2. 在浏览器中键入：  [https://protection.office.com](https://protection.office.com/) 。  

3. 选择 " **数据丢失防护**   >  **设备管理**"，并**为 iOS 设备选择 APNs 证书**。   

4. 在 "Apple 推送通知证书设置" 页上，选择 " **下一步**"。  

5. 选择 " **下载你的 CSR 文件**   "，并将证书签名请求保存到你将记住的计算机上的某个位置。 选择 " **下一步**"。
    
6. 在 "创建 APNs 证书" 页上：
    
    - 选择 "Apple APNS 门户" 打开 "Apple 推送证书" 门户。
    - Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    - 选择 "创建证书" 并接受 "使用条款"。
    
    - Browseto 从 Microsoft 365 和 selectUpload 下载到您的计算机的证书签名请求。
    
    - 由 Apple 推送证书门户创建到你的计算机的 Downloadthe APN 证书。

    >[!TIP]
    >If you're having trouble downloading the certificate, refresh your browser.

7. 返回到 Microsoft 365，然后选择 " **下一步**"。   

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.   

9. 选择 "  **完成**"。  

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>步骤3：建议 () 设置多重身份验证

通过要求使用第二种形式的身份验证，MFA 可帮助确保登录 Microsoft 365 以进行移动设备注册。 在正确输入工作帐户密码后，用户需要在其移动设备上确认电话呼叫、短信或应用通知。 只有在此第二种形式的身份验证完成后，他们才能注册其设备。 在基本移动性和安全性中对用户设备进行注册后，用户只能使用其工作帐户访问 Microsoft 365 资源。

若要了解如何在 Azure AD 门户中启用 MFA，请参阅 [设置多因素身份验证](https://go.microsoft.com/fwlink/p/?LinkId=519255)。

设置 MFA 后，请返回到安全 & 合规中心，并导航到 **数据丢失防护**   >  **设备管理**   >  **设备策略**   ，以完成下一步。

### <a name="step-4-recommended-manage-device-security-policies"></a>步骤4： (建议) 管理设备安全策略

下一步是创建和部署设备安全策略，以帮助保护 Microsoft 365 组织数据。 例如，如果用户通过创建将策略锁定在5分钟无活动状态并在三次登录失败后擦除设备后锁定设备的策略，则可以帮助防止数据丢失。

1. 使用全局管理员帐户登录到 Microsoft 365。 

2. 选择 " [激活移动设备管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)"。 如果服务处于激活状态，则激活步骤将会看到用于 [管理设备](https://admin.microsoft.com/adminportal/home#/MifoDevices)的链接   。
    
3. 转到 " **设备策略**"。

     :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和移动性策略设置":::

4. 按照在 [基本移动性和安全性中创建设备安全策略中](create-device-security-policies-in-basic-mmobility-and-security.md)的步骤创建和部署适用于您的组织的设备安全策略。

>[!TIP]
    - 当您创建新策略时，您可能希望将策略设置为允许访问和报告策略违规，而用户设备不符合该策略。 这使您可以查看策略影响了多少个移动设备，而不会阻止对 Microsoft 365 的访问。<br/>-在将新策略部署到组织中的所有人之前，我们建议您在少量用户使用的设备上对其进行测试。<br/>-此外，在部署策略之前，让你的组织了解在基本移动性和安全性中注册设备的潜在影响。 根据您设置策略的方式，不符合策略的设备 (不符合的设备) 可能阻止访问 Microsoft 365。 如果擦除设备，则可能会删除已注册设备上的应用程序、照片和其他个人信息，不兼容的设备也可能会被删除。 有关详细信息，请参阅 [在基本移动和安全中擦除移动设备](wipe-mobile-device.md)。
    
## <a name="make-sure-users-enroll-their-devices"></a>确保用户注册其设备

创建并部署移动设备管理策略后，组织中的每个许可的 Microsoft 365 用户在下一次从其移动设备登录到 Microsoft 365 时都将收到一个注册邮件。 他们必须先完成注册和激活步骤，然后才能访问 Microsoft 365 电子邮件和文档。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device-using-basic-mobility-and-security.md)。

>[!IMPORTANT]
>如果注册过程不支持用户的首选语言，则用户可能会在使用其他语言的移动设备上接收注册通知和步骤。 目前，移动设备上的注册过程不支持 Microsoft 365 中支持的所有语言。

具有 Android 或 iOS 设备的用户需要在注册过程中安装公司门户应用程序。

## <a name="related-topics"></a>相关主题

[基本移动性和安全性的功能](capabilities-of-basic-mobility-and-secruity.md)<br/>
[在基本移动性和安全性中创建设备安全策略](create-device-security-policies-in-basic-mmobility-and-security.md)