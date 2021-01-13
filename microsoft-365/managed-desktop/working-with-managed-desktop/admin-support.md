---
title: Microsoft 托管桌面的管理员支持
description: 管理员如何获取有关服务的帮助
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9e96a530c61f3f9a94dd84cc79bd3c4c03b61106
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840273"
---
# <a name="admin-support-for-microsoft-managed-desktop"></a>Microsoft 托管桌面的管理员支持

可以使用 Microsoft 托管桌面管理门户向 Microsoft 提交支持票证或反馈请求。 支持请求始终优先处理反馈提交。 支持请求根据严重性分类和管理，如严重性定义表 [所述](#sev)。 将审阅反馈，并请求提供响应。 

>[!IMPORTANT]
>请确保为 [应用打包、](../get-started/add-admin-contacts.md) 设备、安全性和其他设置管理员联系人。 如果未配置管理员联系人，则你无法在任何这些方面提交支持请求。

**提交支持请求**
1. 登录到 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) 并导航到 **"疑难解答 + 支持"** 菜单。
2. 查找 Microsoft 托管桌面部分，选择"**服务请求"。**
3. On **Support requests，** select **+ New Support ticket.**
4. 选择 **与你需要的帮助** 匹配的支持请求类型。 下表概述了这些选项。 
5. 选择 **严重性级别**。 有关详细信息，请参阅支持 [请求严重性定义](#sev)。 

支持请求类型 | 何时使用
--- | ---
事件 | 你需要 Microsoft 托管桌面运营团队进行调查，如变更或安全事件的普遍影响。
信息请求 | 你正在计划更改网络、代理配置、VPN 系统、证书过期，或者只需有关该服务的一些信息。 在组织中传达更改时，建议 Microsoft 托管桌面运营团队做出响应。
更改请求 | 需要 Microsoft 托管桌面操作团队做出更改，如在更新组之间移动设备。

<span id="sev" />

## <a name="support-request-severity-definitions"></a>支持请求严重性定义

初始响应时间是从你提交支持请求到 Microsoft 托管桌面工程师联系你并开始处理支持请求的时间段。 初始响应时间因请求的业务影响而异，具体视请求的严重性而异。

严重级别  | 客户情况 |  初始响应时间   | 预期的客户响应
--- | --- | --- | ---
**严重性 A – 严重影响** |  **关键业务影响**<br><br>客户的业务会显著损失或降低服务，需要立即关注。<br><br>**主要应用程序兼容性影响**<br><br>客户的整个业务因关键功能崩溃或丢失而遇到财务影响 | 初始：< 1 小时<br>更新：60 分钟<br>24x7 可用 | 选择"严重性 A"时，将确认该问题对业务影响严重，服务严重损失和降级。 <br><br>该问题需要立即响应，并且你每天与 Microsoft 团队一起承诺持续 24x7 操作，直到解决方案解决，否则，Microsoft 可能会自行决定将严重性降低至 B 级。<br><br> 此外，还可确保 Microsoft 具有准确的联系信息。 
**严重性 B – 中等影响** |  **中等业务影响**<br><br>客户的业务会中等程度地丢失或降低服务，但工作可能会以受损的方式合理继续。<br><br>**中等应用程序兼容性影响**<br><br>由于崩溃行为或关键功能丢失，特定业务组不再具有生产力。 |  初始：< 4 小时<br>更新：12 小时<br>营业时间 (24x7)  | 选择严重性 B 时，可确认该问题对业务具有中等影响，但服务丢失和降级，但解决方法可实现合理的临时业务连续性。 <br><br>该问题需要紧急响应。 如果在提交支持请求时选择了 24x7，则每天与 Microsoft 团队一起承诺进行持续 24x7 操作，直到解决方案解决，否则，Microsoft 可能会自行决定将严重性降低为 C 级。如果你在提交严重性 B 事件时选择了营业时间支持，Microsoft 将仅在营业时间联系你。<br><br>此外，还可确保 Microsoft 具有准确的联系信息。
**严重性 C – 最小影响** |   **最小业务影响**<br><br> 客户的业务在服务的次要限制下运行。<br><br>**次要应用程序兼容性影响**<br><br>潜在不相关的用户遇到不妨碍工作效率的次要兼容性问题 |    初始：< 8 小时<br>更新：24 小时<br>营业时间  | 选择"严重性 C"时，将确认该问题对业务影响最小，但服务损失较小。<br><br>对于严重级别 C 事件，Microsoft 将仅在营业时间联系你。<br><br>此外，还可确保 Microsoft 具有准确的联系信息

更多详细信息：
- **支持语言** - 所有支持均以英语提供。
- **严重性级别更改** - 如果客户无法提供足够的资源或响应以使 Microsoft 能够继续进行问题解决工作，Microsoft 可能会降级严重性级别。 
- **营业时间** - 对于大多数国家/地区，营业时间为太平洋标准时间上午 9：00 到下午 5：00。
- **应用程序兼容性** - 若要考虑应用程序兼容性问题，在以前版本和当前版本的 Windows 或 Office 之间，必须存在同一版本的应用程序的可重现错误。 若要解决应用程序兼容性问题，Microsoft 需要客户联系点才能使用。 个人必须直接与我们的 Fast Track 团队合作，以调查和解决问题。
- **客户响应时间** 如果客户无法满足预期的响应要求，Microsoft 将请求降级一个严重性级别（最低严重性 C）。如果客户对行动请求没有响应，Microsoft 将在上一个请求的 48 小时内缓解并关闭支持请求。

## <a name="provide-feedback"></a>提供反馈

感谢你的反馈，并使用它改进管理员支持体验。

一旦票证进入"已缓解"或"已解决"状态，你可以分享你有关该特定问题的体验的反馈。 若要共享反馈，请转到 MEM 门户的"疑难解答 **+** 支持"菜单中的"服务请求"页。  选择特定票证。 票证详细信息将显示在右侧"飞入"中，选择"反馈 **"选项卡并提供** 请求的信息。 请注意，不要将任何个人信息包括在反馈表单中。 有关隐私详细信息，请参阅 Microsoft [隐私声明](https://privacy.microsoft.com/privacystatement)。

![反馈表单](../../media/feedback_form.png)



## <a name="more-resources"></a>更多资源
- [用户对 Microsoft 托管桌面的支持](end-user-support.md)。 
- [支持 Microsoft 托管桌面](../service-description/support.md)。 
- 如果已订阅 Microsoft 托管桌面，可以在 Microsoft Endpoint Manager 的"租户管理"菜单的"Microsoft 托管桌面"部分下的 **"联机** 资源"页的 ["Microsoft](https://endpoint.microsoft.com/)托管桌面管理指南"中查找详细过程、流程流、工作说明和常见问题解答。 
