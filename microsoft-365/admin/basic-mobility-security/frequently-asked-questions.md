---
title: '基本移动性和安全性常见问题解答 (常见问题) '
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
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
description: 有关基本移动性和安全性的常见问题。
ms.openlocfilehash: 14e12678ec210325f63914594fb6debcf7abb880
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023889"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>基本移动性和安全性常见问题解答 (常见问题) 

本文包含有关基本移动性和安全性的常见问题，这是一项可帮助您在 Microsoft 365 中管理和保护移动设备的功能。 如果找不到问题的答案，请通过在此页面上留下评论来告诉我们，以便我们考虑将问题添加到本文。

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>如何获取基本移动性和安全性？ 我在 Microsoft 365 管理中心中看不到它

1.  通过进入 ["Office 365](https://protection.office.com/) 安全与合规"&激活基本移动性和安全性。

2.  转到"数据丢失防护">设备管理"。

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>如何开始使用基本移动性和安全性中的设备管理？

基本移动性和安全性入门有四个步骤： 

1. 通过访问 Office [365](https://protection.office.com/)安全与合规部激活基本&和安全性。

2. 转到"数据丢失防护">"设备>"策略"。
    
3. 创建设备管理策略，并应用于在安全组中设置的用户组。 建议首先将策略部署到小型测试组。 有关详细信息，请参阅在基本移动性和安全性中 [创建设备安全策略](create-device-security-policies.md)。

4. 在尝试访问 Microsoft 365 数据时，系统会提示应用了策略的用户注册其设备。 有关详细信息，请参阅使用基本 [移动性和安全性注册移动设备](enroll-your-mobile-device.md)。

有关详细信息，请参阅设置 [基本移动性和安全性](set-up.md)。

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>我尝试设置基本移动性和安全性，但它似乎卡住。 Microsoft 365 服务运行状况已显示"预配"一段时间。 我该如何操作？

可能需要一些时间才能准备好服务。 预配完成后，你将看到"基本移动性和安全性"页。 如果已等待 24 小时，状态仍在预配中，请联系支持人员，我们将帮助找出问题是什么。

## <a name="what-can-i-do-if-device-enrollment-fails"></a>如果设备注册失败，我该怎么办？

如果你在注册设备时遇到问题，请首先检查以下内容：

- 确保设备尚未向另一个移动设备管理提供程序（如 Intune）注册。

- 确保设备已设置为正确的日期和时间。

- 在设备上切换到其他 WIFI 或手机网络。

- 对于 Android 或 iOS 设备，卸载并重新安装设备上的 Intune 公司门户应用。
    
如果注册仍无法工作，请参阅解决 [基本移动性和安全性问题](troubleshoot.md)。

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune 与基本移动性和安全性之间有什么区别？

基本移动性和安全性由 Intune 服务托管。 它是作为 Microsoft 365 的附加权益提供的 Intune 服务的子集，是一个基于云的内置解决方案，用于管理组织中设备。 有关两种服务的并行比较，可帮助你确定使用 Intune 或 Microsoft 365 的基本移动性和安全性是否最适合你，请参阅在基本移动性安全性和 [Intune](choose-between-basic-mobility-and-security-and-intune.md)之间选择。

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>策略如何适用于基本移动性和安全性？ 如何设置它们？ 禁用它们？

完成基本移动性和安全性的初始设置后，创建策略，并应用于安全与合规&组。 策略要求策略的用户在基本移动性和安全性中注册其设备，然后设备才能访问 Microsoft 365 数据。 您设置的策略决定了移动设备的设置，例如，必须重置密码多久或是否需要数据加密。 有关详细信息，[请参阅在基本](create-device-security-policies.md)移动性和安全性以及   Microsoft [365 合规中心创建设备安全策略](../../compliance/microsoft-365-compliance-center.md)。

有关创建和部署设备策略的分步说明，请参阅在基本移动性和安全性中创建 [设备安全策略](create-device-security-policies.md)。

如果要将特定组的用户排除在不受策略影响之外，可以将组添加到排除组。

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>我能否从 Exchange ActiveSync管理切换到 Microsoft 365 的基本移动性和安全性？

如果您已经使用 Exchange ActiveSync策略来管理移动设备，可以按照设置基本移动性和安全性的步骤开始使用基本移动性和安全性。 有关详细信息，请参阅保护[用户和设备访问和](../../compliance/protect-access-to-data-and-services.md)[设置基本移动性和安全性](set-up.md)。

当您在基本移动性和安全性中创建的策略应用于用户组时，这些策略会覆盖 Exchange ActiveSync 移动设备邮箱策略以及之前在 Exchange 管理中心为这些用户创建的设备访问规则。

在基本移动性和安全性中注册设备后，Exchange ActiveSync应用于该设备的任何移动设备邮箱策略或设备访问规则将被忽略。

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>我设置了基本移动性和安全性，但现在我想将其删除。 步骤是什么？

遗憾的是，设置基本移动性和安全性后，不能简单地"取消设置"基本移动性和安全性。 但是，可以通过从已创建的设备策略中删除用户安全组来为用户组删除它。 或者，可以通过删除设备策略来为所有人禁用它，以便它们未就位且未强制执行。 有关详细信息，请参阅 [关闭基本移动性和安全性](turn-off.md)。