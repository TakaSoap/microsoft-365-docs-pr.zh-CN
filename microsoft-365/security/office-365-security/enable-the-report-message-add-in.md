---
title: 启用报表消息加载项
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或整个组织启用 Outlook 和 Web 上的 Outlook 的"报告邮件"外接程序。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e85af902eaaa41eb82acf8d4b4baedc538e7888
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203200"
---
# <a name="enable-the-report-message-add-in"></a>启用报表消息加载项

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 如果你是具有 Exchange Online 邮箱的 Microsoft 365 组织的管理员，我们建议你使用安全与合规中心中的&门户。 有关详细信息，请参阅使用[管理员提交将可疑的垃圾邮件、网络钓鱼、URL 和文件提交到 Microsoft。](admin-submission.md)

Outlook 和 Web 上的 Outlook 的"报告邮件"和"报告网络钓鱼"外接程序 (以前称为 Outlook Web App) ，使用户能够轻松地将误报 (错误电子邮件报告为错误) 或漏报 (允许) 向 Microsoft 及其关联公司进行分析。

Microsoft 使用这些提交来提高电子邮件保护技术的有效性。 例如，如果用户报告大量使用报告邮件外接程序标记为"非垃圾邮件"的邮件，则组织的安全团队可能需要调整反垃圾邮件 [策略](configure-your-spam-filter-policies.md)。

可以安装"报告邮件"或"报告钓鱼邮件"加载项。 如果希望用户仅报告网络钓鱼邮件，请在你的组织中部署报告网络钓鱼外接程序。 有关详细信息，请参阅 [启用报告网络钓鱼外接程序](enable-the-report-phish-add-in.md)。

报告邮件外接程序提供报告垃圾邮件和网络钓鱼邮件的选项。 管理员可以为组织启用"报告邮件"外接程序，并且各个用户可以自行安装它。

如果您是单个用户，您可以为自己启用报告 [邮件外接程序](#get-the-report-message-add-in-for-yourself)。

如果您是全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，您可以为组织启用报告邮件 [外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。 报告消息Add-In现在可以通过集中 [部署获得](../../admin/manage/centralized-deployment-of-add-ins.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 报告邮件外接程序适用于大多数 Microsoft 365 订阅和以下产品：

  - Outlook 网页版
  - Outlook 2013 SP1 或更高版本
  - Outlook 2016 for Mac
  - Microsoft 365 企业应用版中包含的 Outlook
  - 适用于 iOS 和 Android 的 Outlook 应用

- 报告邮件外接程序不适用于本地 Exchange 组织的共享邮箱或邮箱。

- 可以将报告的邮件配置为复制或重定向到指定的邮箱。 有关详细信息，请参阅用户 [提交策略](user-submission.md)。

- 现有的 Web 浏览器应该与报告邮件外接程序一起运行。 但是，如果您注意到外接程序不可用或未正常工作，请尝试其他浏览器。

- 对于组织安装，组织需要配置为使用 OAuth 身份验证。 有关详细信息，请参阅确定加载项的集中部署 [是否适用于你的组织](../../admin/manage/centralized-deployment-of-add-ins.md)。

- 管理员需为全局管理员角色组的成员。 有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="get-the-report-message-add-in-for-yourself"></a>为自己获取报告邮件外接程序

1. 转到 Microsoft AppSource ， <https://appsource.microsoft.com/marketplace/apps> 然后搜索"报告消息"加载项。 若要直接转到"报告邮件"加载项，请转到 <https://appsource.microsoft.com/product/office/wa104381180> 。

2. 单击 **"立即获取"。**

   ![报告邮件 - 现在获取](../../media/ReportMessageGETITNOW.png)

3. 在出现的对话框中，查看使用条款和隐私策略，然后单击"继续 **"。**

4. 使用工作或学校帐户登录 (商业用途) Microsoft 帐户 (供个人) 。

安装并启用加载项后，你将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![Outlook 的"报告邮件"加载项图标](../../media/OutlookReportMessageIcon.png)

- 在 Outlook 网页 Outlook 中，图标如下所示：

  ![Outlook 网页报表邮件外接程序图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

若要了解如何使用外接程序，请参阅使用 [报告邮件外接程序](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>获取并启用组织的"报告邮件"加载项

> [!NOTE]
> 外接程序可能需要 12 个小时才能显示在组织中。

1. In the Microsoft 365 admin center， go to the go to the **Settings** \> **Add-ins** page at ， If you don't <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> see the **Add-in** Page， go to the **Settings** \> **Integrated apps** \> **Add-ins** link on  the top of the Integrated apps page.

2. 选择 **页面顶部的"** 部署外接程序"，然后选择"下一步 **"。**

   ![Microsoft 365 管理中心中的"服务和外接程序"页](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 在出现的 **"部署新的外接程序"** 飞出中，查看信息，然后单击"下一步 **"。**

4. 下一页上，单击 **从应用商店中选择**。

   ![部署新的外接程序页面](../../media/NewAddInScreen2.png)

5. 在出现的 **"选择外接程序"** 页中，单击"搜索"框中，输入"**报告** 邮件"，然后单击"**搜索搜索"** ![ 图标 ](../../media/search-icon.png) 。 在结果列表中，找到"**报告邮件**"，然后单击"添加 **"。**

   ![选择外接程序搜索结果](../../media/NewAddInScreen3.png)

6. 在出现的对话框中，查看许可和隐私信息，然后单击"继续 **"。**

7. 在 **出现的"配置外接程序"** 页中，配置以下设置：

   - **已分配用户**：选择下列值之一：

     - **每个人都** (默认) 
     - **特定用户/组**
     - **就我自己**

   - **部署方法**：选择下列值之一：

     - **修复 (默认) ：** 加载项会自动部署到指定用户，且无法删除。
     - **可用**：用户可以在"主页""获取加载项 \> **""管理员管理**" \> **中安装加载项**。
     - **可选**：外接程序将自动部署到指定用户，但他们可以选择将其删除。

   ![配置外接程序页面](../../media/configure-add-in.png)

   完成后，单击"部署 **"。**

8. 在 **出现的"** 部署报告消息"页中，你将看到一个进度报告，然后确认外接程序已部署。 阅读信息后，单击"下一 **步"。**

   !["部署报告消息"页](../../media/deploy-report-message-page.png)

9. 在出现的 **"宣布外接程序"** 页上，查看信息，然后单击"关闭 **"。**

   !["宣布外接程序"页](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>了解如何使用报告邮件外接程序

分配了外接程序的人将看到以下图标：

- 在 Outlook 中，图标如下所示：

  ![Outlook 的"报告邮件外接程序"图标](../../media/OutlookReportMessageIcon.png)

- 在 Outlook 网页 Outlook 中，图标如下所示：

  ![Outlook 网页报表邮件外接程序图标](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

当您通知用户有关报告邮件外接程序时，请包含一个指向"使用报告邮件 [外接程序"的链接](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>查看或编辑报告邮件外接程序的设置

1. In the Microsoft 365 admin center， go to the go to the **Settings** \> **Add-ins** page at ， If you don't <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> see the **Add-in** Page， go to the **Settings** \> **Integrated apps** \> **Add-ins** link on  the top of the Integrated apps page.

   ![新的 Microsoft 365 Add-Ins中心中的"服务和服务"页面](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. 查找并选择 **"报告邮件** "外接程序。

3. 在出现的 **"编辑报告** 消息"飞出控件中，根据组织情况查看和编辑设置。 完成后，单击“保存”。

   ![报告邮件外接程序的设置](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>查看和查看报告的邮件

若要查看用户报告给 Microsoft 的邮件，可以使用以下选项：

- 使用管理员提交门户。 有关详细信息，请参阅查看 [Microsoft 的用户提交](admin-submission.md#view-user-submissions-to-microsoft)。

- 创建邮件流规则 (也称为传输规则) 传输规则，以发送报告的邮件的副本。 有关说明，请参阅 [使用邮件流规则查看用户向 Microsoft 报告哪些内容](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
