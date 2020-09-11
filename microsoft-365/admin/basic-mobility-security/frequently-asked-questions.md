---
title: '基本移动性和安全性常见问题 (FAQ) '
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
ms.openlocfilehash: e05815392510ad54bb530457d7f0f6490ece4a95
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430092"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>基本移动性和安全性常见问题 (FAQ) 

本文包含有关基本移动性和安全性的常见问题，可帮助您在 Microsoft 365 中管理和保护移动设备的功能。 如果找不到您的问题的答案，请通过在页面上留下注释来告知我们，以便我们可以考虑将您的问题添加到本文中。

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>如何获取基本的移动性和安全性？ 我在 Microsoft 365 管理中心中看不到它

1.  转到 [Office 365 Security & 合规性](https://protection.office.com/) 页面，以激活基本移动性和安全性。   

2.  转到 "数据丢失防护" > 设备管理 "。   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>如何开始在基本移动性和安全性方面实现设备管理？

基本移动性和安全性入门的四个步骤如下： 

1. 通过转到 [Office 365 安全 & 合规性](https://protection.office.com/)来激活基本移动性和安全性。
    
2. 转到数据丢失防护 > 设备管理 > 设备策略。
    
3. 创建设备管理策略，并将其应用到安全组中设置的用户组。 我们建议您首先将策略部署到一个小的测试组。 有关详细信息，请参阅 [在基本移动性和安全性中创建设备安全策略](create-device-security-policies.md)。      

4. 应用了策略的用户在尝试访问 Microsoft 365 数据时，系统会提示他们注册其设备。 有关详细信息，请参阅 [使用基本移动性和安全性注册移动设备](enroll-your-mobile-device.md)。

有关更多详细信息，请参阅 [设置基本移动性和安全性](set-up.md)。

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>我尝试设置基本移动性和安全性，但似乎仍处于粘滞状态。 Microsoft 365 服务运行状况已在一段时间里显示 "设置"。 我该如何操作？

可能需要一段时间才能为你准备好服务。 设置完成后，你将看到 "Microsoft 365 的移动设备管理" 页。 如果你已等待24小时，且状态仍为 "正在设置"，请联系支持人员，我们将帮助找出问题是什么。 有关支持选项，请参阅 [仍需要帮助？](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>如果设备注册失败，我该怎么办？

如果您在注册设备时遇到问题，请首先检查以下内容：

- 确保设备尚未使用其他移动设备管理提供程序（如 Intune）进行注册。
    
- 请确保该设备已设置为正确的日期和时间。
    
- 切换到设备上的不同 WIFI 或蜂窝网络。
    
- 对于 Android 或 iOS 设备，请在设备上卸载并重新安装 Intune 公司门户应用。
    
如果注册仍不起作用，请参阅 [基本移动性和安全性疑难解答](troubleshoot.md)。

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune 与基本移动性和安全性之间有何区别？

基本移动性和安全性由 Intune 服务托管。 它是作为 Microsoft 365 的额外优点提供的 Intune 服务的子集，是用于管理组织中的设备的内置云解决方案。 若要对这两个服务进行并行比较，以帮助你决定使用 Intune 还是 Microsoft 365 的基本移动性和安全性是最适合你的，请参阅在 [基本移动安全性和 Intune 之间进行选择](choose-between-basic-mobility-and-security-and-intune.md)。

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>策略在基本移动性和安全性方面的工作原理是什么？ 如何设置？ 是否禁用它们？

完成初始设置以实现基本移动性和安全性后，您可以创建策略并将其应用到安全 & 合规中心中的用户组。 策略要求策略用户在基本移动性和安全性中注册其设备，然后才能使用设备访问 Microsoft 365 数据。 设置的策略决定了移动设备的设置，例如，密码必须重置的频率或是否需要数据加密。 有关详细信息，请参阅[在基本移动性和安全性](create-device-security-policies.md)   和[Microsoft 365 合规性中心](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)中创建设备安全策略。

有关创建和部署设备策略的分步说明，请参阅 [在基本移动和安全中创建设备安全策略](create-device-security-policies.md)。

如果要将特定用户组排除在受策略影响，可以将组添加到排除组。

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>我能否从 Exchange ActiveSync 设备管理切换为 Microsoft 365 的基本移动性和安全性？

如果已在使用 Exchange ActiveSync 策略来管理移动设备，则可以按照设置基本移动性和安全性的步骤开始使用基本移动性和安全性。 有关详细信息，请参阅 [保护用户和设备访问](https://go.microsoft.com/fwlink/?LinkId=615145) 和 [设置基本移动性和安全性](set-up.md)。

当您将在基本移动性和安全性中创建的策略应用于用户组时，这些策略将覆盖您先前在 Exchange 管理中心为这些用户创建的 Exchange ActiveSync 移动设备邮箱策略和设备访问规则。

在基本移动性和安全性中注册设备后，应用于该设备的任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则都会被忽略。

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>我设置了基本移动性和安全性，但现在我想将其删除。 有哪些步骤？

遗憾的是，在您进行设置后，不能简单地 "取消设置" 基本移动性和安全性。 但您可以通过从已创建的设备策略中删除用户安全组，将其从用户组中删除。 或者，您可以删除设备策略，使其不会生效且不强制实施，从而为每个人禁用它。 有关详细信息，请参阅 [关闭基本移动性和安全性](turn-off.md)。

