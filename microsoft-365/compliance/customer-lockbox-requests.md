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
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom: admindeeplinkMAC
description: 了解客户密码箱请求，这些请求允许你控制 Microsoft 支持工程师在遇到问题时如何访问数据。
ms.openlocfilehash: 8f875f485830d59af733c6c76a5a3d297bedb2cc
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759934"
---
# <a name="customer-lockbox-in-office-365"></a>Office 365中的客户密码箱

本文提供客户密码箱的部署和配置指南。 客户密码箱支持在 Exchange Online、SharePoint Online、OneDrive for Business 和 Teams 中访问数据的请求。 若要建议支持其他服务，请在 [反馈门户](https://feedbackportal.microsoft.com)中提交请求。

若要查看允许用户从符合性产品/服务Microsoft 365中受益的选项，请[参阅有关安全性&合规性的Microsoft 365许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

客户密码箱可确保未经你的明确批准，Microsoft 无法访问你的内容来执行服务操作。 客户密码箱将你引入 Microsoft 用于确保仅授权请求允许访问内容的审批工作流过程。 若要详细了解 Microsoft 的工作流过程，请参阅 [Microsoft 365 中的 Privileged 访问管理](privileged-access-management-solution-overview.md)。

有时，Microsoft 工程师会帮助排查和解决服务中出现的问题。 通常，工程师使用 Microsoft 为其服务提供的大量遥测和调试工具来修复问题。 但是，在某些情况下，Microsoft 工程师需要访问你的内容，以确定根本原因并解决此问题。 客户密码箱要求工程师向你请求访问权限，作为审批工作流的最后一步。 这使你可以选择批准或拒绝组织的请求，并提供对内容的直接访问控制。

## <a name="customer-lockbox-overview-video"></a>客户密码箱概述视频

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>客户密码箱工作流

这些步骤概述了 Microsoft 工程师启动客户密码箱请求时的典型工作流：

1. 组织中的某人在其 Microsoft 365 邮箱中遇到了问题。

2. 当用户排除了问题但无法解决后，就会向 Microsoft 支持部门打开支持请求。

3. Microsoft 支持工程师会评审服务请求，并确定需要访问组织的租户来修复此问题。

4. Microsoft 支持工程师登录客户密码箱请求工具，提出数据访问请求，其中包括组织的租户名称、服务请求号和工程师需要访问数据的预计时间。

5. 在 Microsoft 支持部门经理批准该请求后，客户密码箱会向组织中指定的批准者发送一封关于 Microsoft 的未决访问请求电子邮件通知。

    ![客户密码箱电子邮件通知的示例。](../media/CustomerLockbox1.png)

   在Microsoft 365 管理中心中分配有[客户密码箱访问审批者](/office365/admin/add-users/about-admin-roles)管理员角色的任何人都可以批准客户密码箱请求。

6. 审批者登录到Microsoft 365 管理中心并批准请求。 此步骤会触发创建审核记录，可通过搜索审核日志获得该审核记录。 有关详细信息，请参阅 [审核客户密码箱请求](#auditing-customer-lockbox-requests)。

   如果客户拒绝请求或在 12 小时内未批准请求，则请求将过期，并且不会向 Microsoft 工程师授予访问权限。

   > [!IMPORTANT]
   > Microsoft 在客户密码箱电子邮件通知中不包括任何链接，要求你登录到Office 365。

7. 组织审批者批准请求后，Microsoft 工程师将收到批准消息，登录到租户，并修复客户的问题。 Microsoft 工程师对修复这个问题有要求期限，之后访问将自动撤销。

> [!NOTE]
> Microsoft 工程师执行的所有操作都会记录在审计日志中。 你可以搜索和查看这些审核记录。

## <a name="turn-customer-lockbox-requests-on-or-off"></a>打开或关闭客户密码箱请求

你可以在 Microsoft 365 管理中心中启用客户密码箱控件。 打开客户密码箱时，Microsoft 必须在访问租户的任何内容之前获得组织的批准。

1. 使用分配了全局管理员或 **客户密码箱访问审批者** 角色的工作或学校帐户，转到 [https://admin.microsoft.com](https://admin.microsoft.com) 并登录。

2. 选择 **设置** > **Org 设置** > **安全性&隐私**。

3. 选择 **“安全&隐私**”，然后在左侧列中选择 **“客户密码箱** ”。 选中 **“需要批准所有数据访问请求** ”复选框，并保存更改以启用该功能。

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4-new.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>批准或拒绝客户密码箱请求

1. 使用分配了全局管理员或 **客户密码箱访问审批者** 角色的工作或学校帐户，转到 [https://admin.microsoft.com](https://admin.microsoft.com) 并登录。

2. 选择 **支持>客户密码箱请求**。

    ![单击“支持”，然后单击“客户密码箱请求”。](../media/CustomerLockbox5.png)

    将显示客户密码箱请求的列表。

    ![客户密码箱请求列表。](../media/CustomerLockbox6.png)

3. 选择客户密码箱请求，然后选择 **“批准** ”或 **“拒绝**”。

    ![批准客户密码箱请求。](../media/CustomerLockbox7.png)

    将显示有关客户密码箱请求审批的确认消息。

    ![拒绝客户密码箱请求。](../media/CustomerLockbox8.png)

> [!NOTE]
> 使用 Set-AccessToCustomerDataRequest cmdlet 批准、拒绝或取消 Microsoft 365 客户密码箱请求，以控制 Microsoft 支持工程师对你数据的访问权限。 有关详细信息，请参阅 [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest)。

## <a name="auditing-customer-lockbox-requests"></a>审核客户密码箱请求

与客户密码箱请求对应的审核记录将记录在Microsoft 365审核日志中。 可以使用Microsoft 365 合规中心中的[审核日志搜索工具访问这些日志](search-the-audit-log-in-security-and-compliance.md)。 与接受或拒绝客户密码箱请求相关的操作以及 Microsoft 工程师在批准访问请求时执行的操作 () 也记录在审核日志中。 你可以搜索和查看这些审核记录。

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>在审核日志中搜索与客户密码箱请求相关的活动

在使用审核日志跟踪客户密码箱的请求之前，需要执行一些步骤来设置审核日志记录，包括分配搜索审核日志的权限。 有关详细信息，请参阅[Microsoft 365中设置基本审核](set-up-basic-audit.md)。 完成设置后，请使用以下步骤创建审核日志搜索查询，以返回与客户密码箱相关的审核记录：

1. 转到 <https://compliance.microsoft.com>。
  
2. 使用已分配相应权限的帐户登录以搜索审核日志。

3. 在合规中心的左窗格中，选择 **“审核**”。

    将显示“**审核**”页上的“**搜索**”选项卡。

    ![审核日志搜索页。](../media/auditlogsearch1.png)
  
4. 配置以下搜索条件：

   1. **开始日期** 和 **结束日期**。 选择日期和时间范围，以显示在这段时间内发生的事件。  

   2. **活动**。 将此字段留空，以便搜索返回所有活动的审核记录。 这是返回与客户密码箱请求和 Microsoft 工程师执行的相应活动相关的任何审核记录所必需的。

   3. **用户**。 将此字段留空。

   4. **文件、文件夹或网站**。 将此字段留空。

5. 单击“**搜索**”以使用搜索条件运行搜索。

    搜索结果会在片刻后显示。 更多的搜索结果将添加到页面，直到搜索完成。

6. 单击 **“活动** ”列中的标头，根据 **“活动** ”列中的值按字母顺序对结果进行排序。

7. 向下滚动并查找具有 **Set-AccessToCustomerDataRequest** 活动的审核记录。 此活动的记录与组织中批准或拒绝客户密码箱请求的审批者相关。

8. 或者，单击 **“用户** ”列中的标头，使用 **“用户** ”列中的值按字母顺序对结果进行排序。 查找 **Microsoft Operator** 的值，该值指示 Microsoft 工程师为响应已批准的客户密码箱请求而执行的活动。 “ **活动** ”列显示工程师执行的操作。

      ![筛选“Microsoft 运算符”以显示审核记录](../media/CustomerLockbox10.png)

9. 在结果列表中，单击审核记录以显示它。

### <a name="export-the-audit-log-search-results"></a>导出审核日志搜索结果

还可以将审核日志搜索结果导出到 CSV 文件，然后在Excel中打开该文件，以使用筛选和排序功能，以便更轻松地查找和查看与客户密码箱访问请求相关的审核记录。

若要导出审核记录，请使用前面的步骤搜索审核日志。 搜索完成后，选择“ **导出>下载搜索结果页顶部的所有结果** 。 导出过程完成后，可以将 CSV 文件下载到本地计算机。 有关更详细的说明，请参阅 [导出、配置和查看审核日志记录](export-view-audit-log-records.md)。

下载文件后，可以在Excel中打开该文件，然后在 **“操作”** 列上进行筛选，以显示 **Set-AccessToCustomerDataRequest** 活动的审核记录。 还可以使用值 **Microsoft 运算符**) 来筛选 **UserIds** 列 (，以显示 Microsoft 工程师执行的活动审核记录。

> [!NOTE]
> 查看 CSV 文件中的审核记录时， **AuditData** 列中包含其他信息。 此列中的信息包含在 JSON 对象中，该对象包含多个配置为 *属性：值* 对（用逗号分隔）的属性。 可以使用 Excel 中Power Query 编辑器中的 JSON 转换功能将 **AuditData** 列中 JSON 对象中的每个属性拆分为多个列，以便每个属性都有自己的列。 这样可以更轻松地解释此信息。 有关详细说明，请参阅[使用Power Query 编辑器设置导出的审核日志的格式](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)。

### <a name="use-powershell-to-search-and-export-audit-records"></a>使用 PowerShell 搜索和导出审核记录

在 Microsoft 365 合规中心 中使用审核搜索工具的替代方法是在 Exchange Online PowerShell 中运行 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet。 使用 PowerShell 的一个优点是，可以专门搜索与客户密码箱请求相关的 Microsoft 工程师执行的 **Set-AccessToCustomerDataRequest** 活动或活动。

[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 后，运行以下命令之一。 将占位符替换为特定日期范围。

`Set-AccessToCustomerDataRequest`搜索活动

```powershell
Search-UnifiedAuditLog -StartDate xx/xx/xxxx -EndDate xx/xx/xxxx -Operations Set-AccessToCustomerDataRequest
```

搜索 Microsoft 工程师执行的活动

```powershell
Search-UnifiedAuditLog -StartDate xx/xx/xxxx -EndDate xx/xx/xxxx -UserIds "Microsoft Operator"
```

有关详细信息和示例，请参阅 [使用 PowerShell 搜索和导出审核日志记录](export-view-audit-log-records.md#use-powershell-to-search-and-export-audit-log-records)。

我们还提供了一个 PowerShell 脚本，可用于搜索审核日志并将结果导出到 CSV 文件。 有关详细信息，请参阅 [使用 PowerShell 脚本搜索审核日志](audit-log-search-script.md)。

### <a name="audit-record-for-a-customer-lockbox-request"></a>客户密码箱请求的审核记录

当组织中的人员批准或拒绝客户密码箱请求时，审核日志中记录的审核记录包含以下信息。

| 审核记录属性| 描述|
|:---------- |:----------|
| 日期       | 批准或拒绝客户密码箱请求的日期和时间。
| IP 地址 | 审批者用于批准或拒绝请求的计算机的 IP 地址。 |
| 用户       | 服务帐户BOXServiceAccount@\[customerforest.prod.outlook.com\]。            |
| 活动   | Set-AccessToCustomerDataRequest；这是批准或拒绝客户密码箱请求时记录的审核活动。                                |
| Item       | 客户密码箱请求的 Guid                             |

以下屏幕截图显示了与已批准的客户密码箱请求相对应的审核记录的示例。 如果客户密码箱请求被拒绝，则参数的 `ApprovalDecision` 值将为 `Deny`。

![已批准的客户密码箱请求的审核记录。](../media/CustomerLockbox9.png)

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Microsoft 工程师执行的操作的审核记录

批准客户密码箱请求后，Microsoft 工程师执行的操作（可能导致访问客户内容）将记录在审核日志中。这些记录包含以下信息。

| 审核记录属性| 描述|
|:---------- |:----------|
| 日期       | 执行操作的日期时间。 执行此操作的时间将在客户密码箱请求获得批准后的 4 小时内完成。              |
| IP 地址 | Microsoft 工程师使用的计算机的 IP 地址。 |
| 用户       | Microsoft 运算符;此值指示记录与客户密码箱请求相关。                                  |
| 活动   | Microsoft 工程师执行的活动的名称。|
| 项目       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a>客户密码箱适用于哪些Microsoft 365服务？

Exchange Online、SharePoint联机、OneDrive for Business和Teams目前支持客户密码箱。

### <a name="is-customer-lockbox-available-to-all-customers"></a>客户密码箱是否可供所有客户使用？

客户密码箱包含在Microsoft 365或Office 365 E5订阅中，可以使用信息保护和合规性或高级合规性加载项订阅添加到其他计划。 有关详细信息，请参阅 [计划和定价](https://products.office.com/business/office-365-enterprise-e5-business-software) 。

### <a name="what-is-customer-content"></a>什么是客户内容？

客户内容是由Microsoft 365服务和应用程序的用户创建的数据。 客户内容的示例包括：

- 电子邮件正文或电子邮件附件

- SharePoint 网站内容

- SharePoint 文件正文中的信息

- Skype for Business演示文稿文件正文

- 即时消息 (IM) 或语音对话

- Teams聊天和Teams频道中输入的文本，例如 1：1 聊天、群聊、共享频道、专用频道和会议聊天

- 粘贴到Teams聊天线程中的其他数据，例如代码片段、图像、音频和视频消息以及链接

- Teams聊天和Teams频道中的应用和机器人数据

- Teams活动源

- Teams会议记录和脚本

- 语音邮件

- 发布到Teams聊天和Teams频道的文件

- 客户生成的 Blob 或结构化存储数据（例如 SQL 容器）

- 客户拥有的安全信息（例如证书、加密密钥和密码）

- 如果客户内容仍然存在，则推理和所有后续推理

有关Office 365中的客户内容的详细信息，请参阅[Office 365信任中心](https://products.office.com/business/office-365-trust-center-privacy/)。

### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>当有访问我内容的请求时，Who会收到通知？

系统会通知全局管理员和分配有客户密码箱访问审批者管理员角色的任何人。 这些用户也是可以批准客户密码箱请求的用户。

### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>Who可以在组织中批准或拒绝这些请求？

全局管理员和分配了客户密码箱访问审批者管理员角色的任何人都可以批准客户密码箱请求。 客户在其组织中控制这些角色分配。

### <a name="how-do-i-opt-in-to-customer-lockbox"></a>如何实现选择加入客户密码箱？

全局管理员可以在Microsoft 365 管理中心中启用和配置客户密码箱。

### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>如果我批准客户密码箱请求，工程师可以做什么，如何知道 Microsoft 工程师做了什么？

批准客户密码箱请求后，Microsoft 工程师授予了使用预批准的 cmdlet 访问客户内容所需的权限。 Microsoft 工程师为响应客户密码箱请求而执行的操作会记录在安全&合规中心的审核日志中并可访问。

### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>如何实现知道 Microsoft 遵循审批过程？

可以使用[Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中的客户密码箱请求历史记录交叉引用发送给组织中的管理员和审批者的电子邮件审批通知。

客户密码箱包含在最新的 [SOC 1 SSAE 16 审核报告中](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)。 有关更多详细信息，可以在 [Microsoft 服务信任门户](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)中找到最新报表。

### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Microsoft 是否可以修改租户的审批者列表？ 如果没有，如何阻止它？

只有组织中的全局管理员才能指定谁可以批准客户密码箱请求。 这意味着，只有Azure Active Directory中全局管理员组的成员可以指定谁可以批准请求。 Azure Active Directory中全局管理员组的成员身份仅由组织管理。

### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>如果我需要有关内容访问请求的详细信息来批准它，该怎么办？

每个客户密码箱请求都包含一个Microsoft 365服务请求号。 可以联系Microsoft 支持部门并引用此服务号码以获取有关请求的详细信息。

### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>当客户密码箱请求获得批准时，权限有效期有多长？

目前，Microsoft 工程师可获得访问权限的最长时间是 4 小时。Microsoft 工程师也可以要求更短的期限。

### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>如何获取所有客户密码箱请求的历史记录？

在[Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中查看所有客户密码箱请求。

### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>如何实现将内容访问请求与相关审核日志相关联？

合规中心活动源包含客户密码箱的日志活动。 客户可以根据收到的电子邮件请求从活动源交叉引用客户密码箱日志活动。

### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>当客户未响应客户密码箱请求时会发生什么情况？

客户密码箱请求的默认持续时间为 12 小时。 如果未在 12 小时内响应请求，请求将过期。

### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>当客户拒绝客户密码箱请求时，Microsoft 会怎么做？

如果客户拒绝客户密码箱请求，则不会访问客户内容。 如果组织中的用户继续遇到要求 Microsoft 访问客户内容来解决问题的服务问题，则服务问题可能会持续存在，Microsoft 会将此问题告知用户。

### <a name="how-do-i-set-up-alerts-whenever-a-request-has-been-approved"></a>如何实现在请求获得批准时设置警报？

没有用于提醒管理员的内置选项。 但是，管理员可以使用[Microsoft Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security#to-create-policies)设置警报。

### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>客户密码箱是否可以防范来自执法机构或其他第三方的数据请求？

不是。 Microsoft 认真对待第三方客户数据请求。 作为云服务提供商，Microsoft 始终提倡客户数据的隐私。 如果收到传票，Microsoft 始终会尝试将第三方重定向到客户以获取信息。  (阅读布拉德·史密斯的博客： [保护客户数据免受政府窥探](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)) 。 我们定期发布有关 Microsoft 收到的执法请求的 [详细信息](https://www.microsoft.com/corporate-responsibility/lerr) 。

有关第三方数据请求的 [Microsoft 信任中心](https://www.microsoft.com/trustcenter/default.aspx) ，请参阅 [联机服务条款](https://www.microsoft.com/Licensing/product-licensing/products.aspx) 中的“客户数据披露”部分，了解详细信息。

### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Microsoft 如何确保其员工在Office 365应用程序中没有对客户内容的常用访问权限？

Microsoft 通过访问控制系统和检测措施实施广泛的预防措施，以识别和解决规避这些访问控制系统的尝试。 Microsoft 365按照最低特权和实时访问的原则进行操作。 因此，任何 Microsoft 人员都无权持续访问客户内容。 如果授予权限，则其持续时间有限。

Microsoft 365使用名为 *“密码箱*”的访问控制系统来处理请求权限，以授予在服务中执行操作和管理功能的能力。 操作员必须使用 Lockbox 请求对客户内容的访问权限，然后要求第二个人对请求 (采取措施，例如，在授予访问权限之前) 批准它。 第二个人不能是请求者，必须指定才能批准对客户内容的访问。 仅当请求获得批准时，操作员才能获取对客户内容的临时访问权限。 提升期过期后，密码箱将撤销访问权限。

有关 Microsoft 常规安全做法的更多详细信息，请参阅 [联机服务条款](https://www.microsoft.com/licensing/product-licensing/products) 。

### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>在什么情况下，Microsoft 工程师需要访问我的内容？

Microsoft 工程师需要访问客户内容的最常见情况是客户发出支持请求，要求访问进行故障排除。 Microsoft 365的一个基本原则是，服务在没有 Microsoft 访问客户内容的情况下运行。 几乎所有由 Microsoft 执行的服务操作都是完全自动化的，并且人工参与受到高度控制，并从客户内容中抽象化。 Microsoft 365的目标是，在客户批准特定的 Microsoft 访问请求之前，不需要访问客户内容来支持服务。

### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>我已经认为我的数据在 Microsoft 云中是安全的，那么为什么我需要客户密码箱呢？

客户密码箱提供额外的控制层，让客户能够为服务操作提供显式访问授权。 通过演示显式数据访问授权的过程已就绪，客户密码箱还可帮助客户履行某些合规性义务，例如 HIPAA 和 FEDRAMP。
