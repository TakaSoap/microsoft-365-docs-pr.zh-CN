---
title: 配置具有基线保护的团队
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
description: 了解如何部署具有基线保护级别的团队。
ms.openlocfilehash: 2ab91e28135f05fb7f315ca8869f937f3433099a
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003755"
---
# <a name="configure-teams-with-baseline-protection"></a>配置具有基线保护的团队

本文将介绍如何部署具有基线保护级别的团队。 通过此级别，用户可通过多种方式进行协作，同时提升权限管理，并针对过度共享提供基本保护。 此级别的建议保护包括标识和设备访问策略和恶意软件保护。 此外，可以根据需要应用条件访问策略和数据丢失保护。

## <a name="initial-protections"></a>初始保护

第一步，我们建议配置基本身份和设备访问策略。 有关详细信息，请参阅[保护 Teams 聊天、组和文件的策略建议](https://docs.microsoft.com/microsoft-365/enterprise/teams-access-policies)。

建议启用基本的高级威胁防护功能，防范文档、附件和链接中的恶意软件。 我们建议启用下表中的每个选项。

|选项|信息|
|:------|:-----------|
|适用于 SPO、OneDrive 和 Teams 的 ATP 安全附件|[Office 365 ATP 安全附件](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|ATP 安全文档|[Office 365 高级威胁防护安全文档](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|Teams ATP 安全链接|[Teams 中 Office 365 安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[Office 365 ATP 安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a>团队来宾共享

在每层中，我们都可以选择与组织外部人员共享。 对于敏感和高度敏感层，我们可以选择使用敏感度标签在团队级别关闭来宾共享。 但必须启用“组织级别的来宾共享设置”，以使来宾共享在 Teams 中均可正常工作。

![Teams 来宾访问切换的屏幕截图](../media/teams-guest-access-toggle-on.png)

设定 Teams 来宾访问设置

1. 访问 [https://admin.microsoft.com](https://admin.microsoft.com) 登录到 Microsoft 365 管理中心。
2. 在左侧导航中，单击“**显示全部**”。
3. 在“**管理中心 **”下，单击“**团队**”。
4. 在 Teams 管理中心左侧导航中，展开“**组织范围的设置**”，然后单击“**来宾访问**”。
5. 确保**在 Teams 中允许来宾访问**设置为“**开**”。
6. 对其他来宾设置进行任何所需的更改，然后单击“**保存**”。

> [!NOTE]
> 启用后，Teams 来宾设置最多可能需要二十四个小时才能生效。

默认情况下，Office 365 组和 SharePoint 启用了来宾共享，但如果以前已更改了组织的任何来宾共享设置，建议参阅[在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)，以确保来宾共享在 Teams 中可用。

## <a name="site-and-file-sharing"></a>网站和文件共享

为了降低意外与组织外部人员共享文件或文件夹的风险，建议将 SharePoint 的默认共享链接更改为“*仅限组织中的人员*”。 （如果用户需要在外部共享，并且启用了来宾共享，他们在共享时仍可以更改链接类型。）

更改默认共享链接
1. 打开 [SharePoint 管理中心](https://admin.microsoft.com/sharepoint)。
2. 在“**策略**”下，单击“**共享**”。
3. 在“**文件和文件夹链接**”下，选中“**仅限组织中的人员**”。
4. 单击“**保存**”。

为了获得最佳的来宾共享体验，我们还建议你启用 [SharePoint 和 OneDrive与 Azure AD B2B 集成](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)。

## <a name="create-a-team"></a>创建团队

基线保护级别的其他配置在与团队相关联的 SharePoint 网站中完成。 [创建公共或私人团队](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)，然后再继续进行下一部分。

## <a name="site-sharing-settings"></a>网站共享设置

默认情况下，SharePoint 网站的成员可以邀请其他人加入该网站。 网站是团队的一部分时，团队成员将作为网站成员包括在内。 但是，直接添加到网站的人员不能访问团队的其他成员。 因此，我们建议仅通过团队来管理权限。

为了帮助进行权限管理，我们建议将关联的站点配置为仅允许所有者自己共享该站点。 这简化了权限管理，有助于阻止团队所有者不知道的人员访问。 对需要基线保护的每个团队执行此操作。

更新网站共享设置
1. 在团队的工具栏中，单击“**文件**”。
2. 单击“**在 SharePoint 中打开**”。
3. 在 SharePoint 网站的工具栏中，依次单击设置图标和“**网站权限**”。
4. 在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。
5. 在“**共享权限**”下，选择选择“**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**”，然后单击“**保存**”。

## <a name="additional-protections"></a>附加保护

Microsoft 365 提供了其他用于保护内容的方法。 考虑以下选项是否有助于提高组织的安全性。

- 让来宾用户同意[使用条款](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)。
- 为来宾用户配置“[会话超时策略](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)”。
- 创建“[敏感信息类型](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)”，并使用“[数据丢失保护](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)”来设置有关访问敏感信息的策略。

## <a name="see-also"></a>另请参阅

[管理 Teams 中的会议策略](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[内部风险管理入门](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
