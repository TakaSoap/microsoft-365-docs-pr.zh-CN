---
title: 客户密码箱请求
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解客户密码箱请求，该请求允许你控制 Microsoft 支持工程师在遇到问题时如何访问你的数据。
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922706"
---
# <a name="customer-lockbox-in-office-365"></a>Office 365 中的客户密码箱

本文提供客户密码箱的部署和配置指南。 客户密码箱支持访问 Exchange Online、SharePoint Online 和 OneDrive for Business 中数据的请求。 若要推荐支持其他服务，请在 [Office 365 UserVoice](https://office365.uservoice.com/)提交请求。

若要查看从 2020 年 4 月 1 日起允许用户从 Microsoft 365 合规性产品/服务（包括此产品/服务）中获益的选项，请参阅 Microsoft [365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)安全与合规&指南。

客户密码箱可确保未经您的明确批准，Microsoft 无法访问您的内容以执行服务操作。 客户密码箱可让你进入对访问内容的请求的审批工作流。

有时，Microsoft 工程师可帮助排查并解决客户报告的支持过程中的问题。 通常，通过 Microsoft 已针对其服务提供了大量遥测和调试工具来修复问题。 但是，在某些情况下，Microsoft 工程师需要访问客户内容来确定根本原因并修复该问题。 客户密码箱要求工程师请求客户访问，这是审批工作流的最后一步。 这使组织可以选择批准或拒绝这些请求，并为客户提供直接访问控制。

### <a name="customer-lockbox-overview-video"></a>客户密码箱概述视频

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>客户密码箱工作流

以下步骤概述了 Microsoft 工程师启动客户密码箱请求时的典型工作流：

1. 组织内部人员在 Microsoft 365 邮箱中遇到问题。

2. 在用户解决问题，但无法解决问题后，他们向 Microsoft 支持人员打开支持请求。

3. Microsoft 支持工程师检查服务请求并确定需要访问组织的租户来修复 Exchange Online 中的问题。

4. Microsoft 支持工程师登录到客户密码箱请求工具，并发送数据访问请求，其中包括组织的租户名称、服务请求号以及工程师需要访问数据的估计时间。

5. 在 Microsoft 支持经理批准请求后，客户密码箱会向组织指定的审批者发送一封有关 Microsoft 的待处理访问请求的电子邮件通知。

    ![客户密码箱电子邮件通知示例](../media/CustomerLockbox1.png)

   在 Microsoft 365 管理中心中分配有客户密码箱 [访问](/office365/admin/add-users/about-admin-roles) 审批者管理员角色的任何人都可以批准客户密码箱请求。

6. 审批者登录 Microsoft 365 管理中心并批准请求。 此步骤通过搜索审核记录来触发创建可用的审核日志。 有关详细信息，请参阅审核 [客户密码箱请求](#auditing-customer-lockbox-requests)。

   如果客户拒绝请求或者未在 12 小时内批准请求，该请求将过期，并且不会向 Microsoft 工程师授予任何访问权限。

   > [!IMPORTANT]
   > Microsoft 不会在要求你登录 Office 365 的客户密码箱电子邮件通知中包括任何链接。

7. 组织审批者批准请求后，Microsoft 工程师会收到审批消息，登录到 Exchange Online 中的租户，并修复客户的问题。 Microsoft 工程师具有请求的持续时间来修复此问题，之后将自动撤消访问权限。

> [!NOTE]
> Microsoft 工程师执行的所有操作都记录在审核日志。 可以搜索和查看这些审核记录。

## <a name="turn-customer-lockbox-requests-on-or-off"></a>打开或关闭客户密码箱请求

可以在 Microsoft 365 管理中心中打开客户密码箱控件。 当你打开客户密码箱时，Microsoft 必须在访问你的任何租户内容之前获得组织的批准。

1. 使用分配了全局管理员或客户密码箱访问审批者角色的工作或学校帐户，转到 [https://admin.microsoft.com](https://admin.microsoft.com) 并登录。

2. 选择 **"设置>"组织设置"。**

3. 选择 **"&** 客户密码箱编辑"，然后将开关移到"开"或"关"以  >    >  打开或关闭功能。  

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>批准或拒绝客户密码箱请求

1. 使用分配了全局管理员或客户密码箱访问审批者角色的工作或学校帐户，转到 [https://admin.microsoft.com](https://admin.microsoft.com) 并登录。

2. Choose **Support > Customer Lockbox Requests**.

    ![单击"支持"，然后单击"客户密码箱请求"](../media/CustomerLockbox5.png)

    将显示客户密码箱请求列表。

    ![客户密码箱请求列表](../media/CustomerLockbox6.png)

3. 选择客户密码箱请求，然后选择 **批准或拒绝。** 

    ![批准或拒绝客户密码箱请求](../media/CustomerLockbox7.png)

    将显示有关客户密码箱请求审批的确认消息。

    ![批准或拒绝客户密码箱请求](../media/CustomerLockbox8.png)

> [!NOTE]
> 使用 Set-AccessToCustomerDataRequest cmdlet 批准、拒绝或取消 Microsoft 365 客户密码箱请求，以控制 Microsoft 支持工程师对你数据的访问权限。 有关详细信息，请参阅 [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest)。


## <a name="auditing-customer-lockbox-requests"></a>审核客户密码箱请求

与客户密码箱请求对应的审核记录将记录在审核日志。 可以使用安全与合规中心审核日志 [搜索工具](search-the-audit-log-in-security-and-compliance.md) 访问&日志。 与接受或拒绝客户密码箱请求相关的操作以及 Microsoft 工程师 (访问请求获得批准时执行的操作) 也会记录在审核日志。 可以搜索和查看这些审核记录。

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>搜索审核日志客户密码箱请求相关的活动

在可以使用 审核日志跟踪客户密码箱请求之前，需要执行一些步骤来设置审核日志记录。 有关详细信息，请参阅在安全[与审核日志搜索&搜索。](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin) 完成设置后，使用以下步骤创建一个审核日志搜索查询，以返回与客户密码箱相关的审核记录：

1. 转到 [https://protection.office.com](https://protection.office.com)。
  
2. 使用工作或学校帐户进行登录。

3. 在安全与合规中心的&窗格中，选择"搜索&**调查**  >  **审核日志搜索"。**

    将显示 **"审核日志搜索** "页。

    ![审核日志搜索页](../media/auditlogsearch1.png)
  
4. 配置以下搜索条件：

    1. **Activities** - 将此字段留空，以便搜索返回所有活动的审核记录。 这是返回与客户密码箱请求和 Microsoft 工程师执行的相应活动相关的任何审核记录所必需的。

    1. **开始日期** 和 **结束日期** - 选择日期和时间范围以显示该时段内发生的事件。

    1. **用户** - 将此字段留空。

    1. **文件、文件夹或网站** - 将此字段留空。

5. 单击“**搜索**”以使用搜索条件运行搜索。

    将加载搜索结果，片刻后，它们将显示在"审核日志搜索"页上的"结果 **"** 下。

6. 单击 **搜索结果** 页上的"筛选结果"，然后执行下列操作之一：

   - 若要显示与组织中审批或拒绝客户密码箱请求的审批者相关的审核记录：在"活动"列下的框中，键入 **Set-AccessToCustomerDataRequest**。

   - 若要显示与 Microsoft 工程师为响应已批准的客户密码箱请求而执行的操作相关的审核记录：在"用户"列下的框中，键入 **"Microsoft 操作员"。** " **活动** "列显示工程师执行的操作。

      ![筛选"Microsoft 操作员"以显示审核记录](../media/CustomerLockbox10.png)

7. 在结果列表中，单击审核记录以显示该记录。

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>客户密码箱访问请求的审核记录

当组织内部人员批准或拒绝客户密码箱请求时，审核记录将记录在审核日志。 此记录包含以下信息。

| 审核记录属性| 描述|
|:---------- |:----------|
| 日期       | 批准或拒绝客户密码箱请求的日期和时间。
| IP 地址 | 审批者用来批准或拒绝请求的机器的 IP 地址。 |
| User       | 客户帐户BOXServiceAccount@ \[ \] .prod.outlook.com。            |
| 活动   | Set-AccessToCustomerDataRequest;这是在批准或拒绝客户密码箱请求时记录的审核活动。                                |
| Item       | 客户密码箱请求的 Guid                             |

以下屏幕截图显示了与批准的客户密码箱请求审核日志记录的示例。 如果客户密码箱请求被拒绝， **则 ApprovalDecision** 参数的值为 **Deny**。

![批准的客户密码箱请求的审核记录](../media/CustomerLockbox9.png)

> [!TIP]
> 若要在审核记录中显示更多详细信息，请单击"**详细信息"。**

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>由 Microsoft 工程师执行的操作的审核记录

Microsoft 工程师在客户密码箱请求获得批准后执行的操作 (并且可能会导致访问客户内容) 记录在审核日志。 这些记录包含以下信息。

| 审核记录属性| 描述|
|:---------- |:----------|
| 日期       | 操作执行的日期时间。 请注意，执行此操作的时间将在客户密码箱请求得到批准后 4 小时内完成。              |
| IP 地址 | Microsoft 工程师所使用的计算机 IP 地址。 |
| User       | Microsoft 运算符;此值指示此记录与客户密码箱请求相关。                                  |
| 活动   | 由 Microsoft 工程师执行的活动的名称。|
| Item       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a>常见问题

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a>客户密码箱适用于哪些 Microsoft 365 服务？

Exchange Online、SharePoint Online 和 OneDrive for Business 当前支持客户密码箱。

#### <a name="is-customer-lockbox-available-to-all-customers"></a>客户密码箱是否可供所有客户使用？

客户密码箱包含在 Microsoft 365 或 Office 365 E5 订阅中，并且可以使用信息保护和合规性订阅或高级合规性附加订阅添加到其他计划中。 有关详细信息 [，请参阅计划和](https://products.office.com/business/office-365-enterprise-e5-business-software) 定价。

#### <a name="what-is-customer-content"></a>什么是客户内容？

客户内容是由 Microsoft 365 服务和应用程序的用户创建的数据。 客户内容的示例包括：

- 电子邮件正文或电子邮件附件

- SharePoint 网站内容

- SharePoint 文件正文中的信息

- Skype for Business 演示文稿文件正文

- 即时消息 (IM) 或语音对话

- 客户生成的 blob 或结构化存储 (例如，SQL容器) 

- 客户拥有的安全 (例如，证书、加密密钥和密码) 

- 如果客户内容保留，则推断以及所有后续推断

有关 Office 365 中的客户内容的其他信息，请参阅 [Office 365 信任中心](https://products.office.com/business/office-365-trust-center-privacy/)。

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>当有访问我的内容的请求时，谁会收到通知？

将通知全局管理员和分配有客户密码箱访问审批者管理员角色的任何人。 这些用户也是可以批准客户密码箱请求的用户。

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>谁可以在我的组织中批准或拒绝这些请求？

全局管理员和分配有客户密码箱访问审批者管理员角色的任何人都可以批准客户密码箱请求。 客户控制其组织中这些角色分配。

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>如何选择加入客户密码箱？

全局管理员可以在 Microsoft 365 或 Microsoft 365 管理中心中启用和配置客户密码箱。

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>如果我批准客户密码箱请求，工程师可以做什么，如何知道 Microsoft 工程师做什么？

批准客户密码箱请求后，Microsoft 工程师授予了使用预批准的 cmdlet 访问客户内容所需的权限。 Microsoft 工程师为响应客户密码箱请求而采取的操作将记录在安全与合规审核日志中&访问。

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>我如何知道 Microsoft 遵循审批流程？

可以使用 Microsoft 365 管理中心中的客户密码箱请求历史记录交叉引用发送给组织中管理员和审批者的电子邮件审批通知。

客户密码箱包含在最新的 [SOC 1 SSAE 16 审核报告中](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)。 有关详细信息，可以在 Microsoft 服务信任门户 [中查找最新报告](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)。

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Microsoft 能否修改我的租户的审批者列表？ 如果不是，如何阻止它？

只有贵组织的全局管理员可以指定谁可以批准客户密码箱请求。 这意味着只有 Azure Active Directory 中的全局管理员组的成员可以指定谁可以批准请求。 Azure Active Directory 中全局管理员组的成员身份仅由你的组织管理。

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>如果我需要有关内容访问请求的更多信息来批准它，应该怎么做？

每个客户密码箱请求都包含一个 Microsoft 365 服务请求号码。 可以联系 Microsoft 支持部门并参考此服务号码，获取有关请求详细信息。

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>当客户密码箱请求得到批准时，权限的有效期是多久？

目前，授予 Microsoft 工程师的访问权限的最大期限为 4 小时。 Microsoft 工程师还可以请求较短的期限。

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>如何获取所有客户密码箱请求的历史记录？

所有客户密码箱请求均在 Microsoft 365 管理中心中查看。

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>如何将内容访问请求与相关的审核日志关联？

合规性中心活动源包含客户密码箱的日志活动。 客户可以针对他们收到的电子邮件请求交叉引用活动源中的客户密码箱日志活动。

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>当客户未响应客户密码箱请求时，会发生什么情况？

客户密码箱请求的默认持续时间为 12 小时。 如果在 12 小时内未响应请求，请求将过期。

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>当客户拒绝客户密码箱请求时，Microsoft 会做什么？

如果客户拒绝客户密码箱请求，则不访问客户内容。 如果贵组织的用户继续遇到需要 Microsoft 访问客户内容才能解决问题的服务问题，则服务问题可能仍然存在，Microsoft 会通知用户此问题。

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>客户密码箱是否防止来自执法机构或其他第三方的数据请求？

不正确。 Microsoft 非常重视客户数据的第三方请求。 作为云服务提供商，Microsoft 始终宣传客户数据的隐私。 如果我们收到一个子请求，Microsoft 将始终尝试将第三方重定向到客户以获取信息。  (Brad Smith 的博客：保护客户数据免受 [政府](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 窥探) 。 我们定期 [发布有关](https://www.microsoft.com/corporate-responsibility/lerr) Microsoft 收到的执法机构请求的详细信息。

有关详细信息，[请参阅联机](https://www.microsoft.com/trustcenter/default.aspx)服务条款中有关第三方数据请求的 Microsoft 信任中心和"客户数据泄露"[](https://www.microsoft.com/Licensing/product-licensing/products.aspx)部分。

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Microsoft 如何确保其员工没有长期访问 Office 365 应用程序中的客户内容？

Microsoft 通过访问控制系统和检测性措施实施广泛的预防措施，以识别和解决试图避开这些访问控制系统的尝试。 Microsoft 365 采用最小特权和实时访问原则运行。 因此，任何 Microsoft 人员都无权持续访问客户内容。 如果授予权限，则其持续时间有限。 

Microsoft 365 使用称为 *"* 密码箱"的访问控制系统处理权限请求，这些权限授予了在服务内执行操作和管理功能的能力。 操作员必须使用密码箱请求访问客户内容，然后要求第二个人对请求采取操作 (例如，在授予访问权限之前) 批准它。 第二个人不能是请求者，必须被指定为批准访问客户内容。 只有在请求得到批准后，操作员才能临时访问客户内容。 提升期到期后，密码箱将撤销访问权限。

有关 Microsoft [一](https://www.microsoft.com/licensing/product-licensing/products) 般安全实践的更多详细信息，请参阅联机服务条款。

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>在什么情况下，Microsoft 工程师需要访问我的内容？

Microsoft 工程师需要访问客户内容的最常见情形是，客户提出需要访问进行疑难解答的支持请求。 Microsoft 365 的一个基础原则是该服务在 Microsoft 不访问客户内容的情况下运行。 几乎所有由 Microsoft 执行的服务操作都完全自动化，并且人员参与受到严格控制，并且从客户内容中抽象。 Microsoft 365 的目标是在客户批准 Microsoft 访问的特定请求之前，访问客户内容以支持服务。

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>我已经认为我的数据在 Microsoft 云中是安全的，那么为什么我需要客户密码箱？

客户密码箱通过为客户提供为服务操作提供显式访问授权的能力，提供了一层额外的控制。 通过证明针对显式数据访问授权已制定相关过程，客户密码箱还帮助客户履行某些合规性义务，如 HIPAA 和 FEDRAMP。