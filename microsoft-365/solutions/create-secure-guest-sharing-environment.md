---
title: 创建安全的来宾共享环境
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.localizationpriority: high
f1.keywords: NOCSH
recommendations: false
description: 了解可用于在 Microsoft 365 中创建安全来宾共享环境的选项，提供来宾访问以改进协作。
ms.openlocfilehash: 97b9c3c26fce137ad4471bbf080d4b7340c8b622
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323789"
---
# <a name="create-a-secure-guest-sharing-environment"></a>创建安全的来宾共享环境

在本文中，我们将介绍多种在 Microsoft 365 中创建安全来宾共享环境的选项。 这些示例可让你大致了解可用选项。 你可以在不同的组合中使用这些过程，以满足组织的安全性和合规性需求。

本文包括：

- 为来宾设置多重身份验证。
- 设置来宾的使用条款。
- 设置每季度来宾访问评审，以定期验证来宾是否继续需要团队和站点的权限。
- 限制来宾仅对非托管设备进行仅 Web 访问。
- 配置会话超时策略，确保来宾每天进行身份验证。
- 为高度敏感的项目创建敏感信息类型。
- 自动为包含敏感信息类型的文档分配敏感度标签。
- 自动从带有敏感度标签的文件中删除来宾访问。

本文中所述的某些选项要求来宾在 Azure Active Directory 中具有帐户。 若要确保在与来宾共享文件和文件夹时在目录中包含这些来宾，请使用[与 Azure AD B2B 预览版的 SharePoint 和 OneDrive 集成](/sharepoint/sharepoint-azureb2b-integration-preview)。

请注意，我们不在本文中讨论如何启用来宾共享设置。 有关为不同方案启用来宾共享的详细信息，请参阅[与组织外部人员进行协作](collaborate-with-people-outside-your-organization.md)。

## <a name="set-up-multi-factor-authentication-for-guests"></a>为来宾设置多重身份验证

多重身份验证可显著降低帐户被盗的机率。 由于来宾对个人电子邮件帐户的使用可能不符合任何管理策略或最佳做法，因此要求对来宾进行多重身份验证尤为重要。 如果来宾的用户名和密码被盗，则要求进行双重身份验证可大大降低未知方获得对网站和文件的访问权限的机率。

在此示例中，我们将使用 Azure Active Directory 中的条件访问策略为来宾设置多重身份验证。

为来宾设置多重身份验证

1. 转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。
2. 在“**条件访问 | 策略**”边栏选项卡上，单击“**新建策略**”。
3. 在“**名称**”字段中，输入名称。
4. 在“**分配**”下，单击“**用户和组**”。
5. 在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。
6. 在“**分配**”下，单击“**云应用或操作**”。
7. 在“**云应用或操作**”边栏选项卡中，选择“**包含**”选项卡上的“**所有云应用**”。
8. 在“**访问控制**”下，单击“**授予**”。
9. 在“**授予**”边栏选项卡上，选中“**要求多重身份验证**”复选框，然后单击“**选择**”。
10. 在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。

现在，来宾需要在多重身份验证中进行注册，然后才能访问共享内容、网站或团队。

### <a name="more-information"></a>更多信息

[规划 Azure Active Directory 多重身份验证部署](/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>设置来宾的使用条款

在某些情况中，来宾可能未与贵组织签署保密协议或其他法律协议。 你可以要求来宾在访问与之共享的文件之前同意使用条款。 可在他们首次尝试访问共享文件或网站时显示使用条款。

若要创建使用条款，首先需要在 Word 或其他创作程序中创建文档，然后将其另存为 .pdf 文件。之后可将此文件上传到 Azure AD。

创建 Azure AD 使用条款

1. 以全局管理员、安全管理员或条件访问管理员的身份登录到 Azure。
2. 导航到“[使用条款](https://aka.ms/catou)”。
3. 单击“**新建条款**”。

   ![Azure AD 新使用条款设置的屏幕截图。](../media/azure-ad-guest-terms-of-use.png)

4. 键入“**名称**”和“**显示名称**”。
6. 对于“**使用条款文档**”，浏览至你创建的 pdf 文件并选择它。
7. 选择使用条款文档的语言。
8. 将“**要求用户展开使用条款**”设置为“**打开**”。
9. 在“**条件访问**”下的“**强制实施条件访问策略模板**”列表中，选择“**稍后创建条件访问策略**”。
10. 单击“**创建**”。

创建使用条款后，下一步是创建对来宾显示使用条款的条件访问策略。

创建条件访问策略

1. 转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。
2. 在“**条件访问 | 策略**”边栏选项卡上，单击“**新建策略**”。
3. 在“**名称**”框中，键入名称。
4. 在“**分配**”下，单击“**用户和组**”。
5. 在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。
6. 在“**分配**”下，单击“**云应用或操作**”。
7. 在“**包括**”选项卡上，选择“**选择应用**”，然后单击“**选择**”。
8. 在“**选择**”边栏选项卡上，选择“**Microsoft Teams**”、“**Office 365 SharePoint Online**”和“**Outlook Groups**”，然后单击“**选择**”。
9. 在“**访问控制**”下，单击“**授予**”。
10. 在“**授予**”边栏选项卡上，选择“**来宾使用条款**”，然后单击“**选择**”。
11. 在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。

现在，当来宾首次尝试访问组织中的内容、团队或网站时，必须接受使用条款。

> [!NOTE]
> 使用条件访问需要 Azure AD Premium P1 许可证。 有关详细信息，请参阅[什么是条件访问](/azure/active-directory/conditional-access/overview)。

### <a name="more-information"></a>更多信息

[Azure Active Directory 使用条款](/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>设置来宾访问评审

借助 Azure AD 中的访问评审功能，可以自动定期评审用户对各个团队和组的访问权限。 通过特别要求对来宾进行访问评审，可帮助确保来宾只在规定时间内拥有对组织敏感信息的访问权限。

设置来宾访问评审

1. 在 [Identity Governance](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) 页面上的左侧菜单中，单击“**访问评审**”。
2. 单击“**新建访问评审**”。
3. 选择 “**Microsoft Teams + Microsoft 365 组**” 选项。
4. 选择“**所有含来宾用户的Microsoft 365 组**”选项。 如果需要排除任何组，单击“**选择要排除的组**”。
5. 选择“**仅来宾用户**”选项，然后单击“**下一步：审阅**”。
6. 在“**选择评审员**”下，选择“**组所有者**”。
7. 单击“**选择回退评审员**”，选择回退评审员，然后单击“**选择**”。
8. 在“**指定定期评审**”，选择“**每季**”。
9. 选择开始日期与持续时间。
10. 在“**结束**”处，选择“**从不**”，然后单击“**下一步：设置**”。

    ![Azure AD 访问“审阅”选项卡的屏幕截图。](../media/azure-ad-create-access-review.png)

11. 在“**设置**”选项卡中，查看设置是否符合你的业务规则。

    ![Azure AD 访问审阅设置选项卡的屏幕截图。](../media/azure-ad-create-access-review-settings.png)

12. 单击“**下一步: 评审+创建**”。
13. 键入“**评审姓名**”然后查看设置。
14. 单击“**创建**”。

请务必注意，对于 SharePoint 和 OneDrive 位置，在检测到敏感信息后，无论是否为共享文档，都将为所有外部用户立即主动阻止文档，而内部用户将继续有权访问文档。

### <a name="more-information"></a>更多信息

[使用 Azure AD 访问评审管理来宾访问权限](/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[在 Azure AD 访问评审中针对组或应用程序创建访问评审](/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guests"></a>为来宾用户设置仅 Web 访问权限

通过要求来宾仅使用 Web 浏览器来访问团队、网站和文件，可以减少攻击面并简化管理。

对于 Microsoft 365 组和团队，这是通过 Azure AD 条件访问策略完成的。 对于 SharePoint，这是在 SharePoint 管理中心中进行配置的。 （还可[使用敏感度标签限制来宾进行仅限于 Web 的访问](../compliance/sensitivity-labels-teams-groups-sites.md)。）

限制来宾对团队和组进行仅 Web 访问：

1. 转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。
2. 在“**条件访问 - 策略**”边栏选项卡上，单击“**新建策略**”。
3. 在“**名称**”框中，键入名称。
4. 在“**分配**”下，单击“**用户和组**”。
5. 在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。
6. 在“**分配**”下，单击“**云应用或操作**”。
7. 在“**包括**”选项卡上，选择“**选择应用**”，然后单击“**选择**”。
8. 在“**选择**”边栏选项卡上，选择“**Microsoft Teams**”和“**Outlook Groups**”，然后单击“**选择**”。
9. 在“**分配**”下，单击“**条件**”。
10. 在“**条件**”边栏选项卡上，单击“**客户端应用**”。
11. 在“**客户端应用**”边栏选项卡上，为“**配置**”单击“**是**”，然后选择“**移动应用和桌面客户端**”、“**Exchange ActiveSync 客户端**”和“**其他客户端**”设置。清除“**浏览器**”复选框。

    ![Azure AD 条件访问客户端应用设置的屏幕截图。](../media/azure-ad-conditional-access-client-mobile.png)

12. 单击“**完成**”。
13. 在“**访问控制**”下，单击“**授予**”。
14. 在“**授予**”边栏选项卡上，选择“**需要标记为兼容的设备**”和“**需要加入混合 Azure AD 的设备**”。
15. 在“**对于多个控件**”，选择“**需要某一已选控件**”，然后单击“**选择**”。
16. 在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。

限制来宾对 SharePoint 进行仅 Web 访问

1. 在 SharePoint 管理中心中，展开“**策略**”，然后选择“<a href="https://go.microsoft.com/fwlink/?linkid=2185071" target="_blank">**访问控制**</a>”。
2. 选择“**未托管的设备**”。
3. 选择“**允许仅限 web 的受限访问**”，然后选择“**保存**”。

注意，SharePoint 管理中心中的此设置在 Azure AD 中创建了支持条件访问策略。

## <a name="configure-a-session-timeout-for-guests"></a>为来宾配置会话超时策略

如果来宾用户的设备不安全，则定期要求来宾进行身份验证可以降低未知用户访问组织内容的可能性。 可以在 Azure AD 中为来宾配置会话超时条件访问策略。

配置来宾会话超时策略

1. 转到 “[ Azure 条件访问策略](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)”。
2. 在“**条件访问 - 策略**”边栏选项卡上，单击“**新建策略**”。
3. 在“**名称**”框中，键入“*来宾会话超时*”。
4. 在“**分配**”下，单击“**用户和组**”。
5. 在“**用户和组**”边栏选项卡上，选择“**选择用户和组**”，然后选中“**所有来宾和外部用户**”复选框。
6. 在“**分配**”下，单击“**云应用或操作**”。
7. 在“**包括**”选项卡上，选择“**选择应用**”，然后单击“**选择**”。
8. 在“**选择**”边栏选项卡上，选择“**Microsoft Teams**”、“**Office 365 SharePoint Online**”和“**Outlook Groups**”，然后单击“**选择**”。
9. 在“**访问控制**”下，单击“**会话**”。
10. 在“**会话**”边栏选项卡上，选择“**登录频率**”。
11. 为时间段选择 **1** 和“**天**”，然后单击“**选择**”。
12. 在“**新建**”边栏选项卡中的“**启用策略**”下面，单击“**打开**”，然后单击“**创建**”。

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>为高度敏感的项目创建敏感信息类型

敏感信息类型是预定义的字符串，可以在策略工作流中使用这些字符串来强制执行合规性要求。 Microsoft 365 合规中心提供一百多种敏感信息类型，包括驾驶执照号码、信用卡号、银行帐号等。

你可以创建自定义敏感信息类型，以帮助管理特定于组织的内容。 在此示例中，我们将为高度敏感项目创建自定义敏感信息类型。 然后，可使用此敏感信息类型自动应用敏感度标签。

创建敏感信息类型

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)的左侧导航中，展开“**分类**”，然后单击“**敏感信息类型**”。
2. 单击“**创建**”。
3. 对于“**名称**”和“**说明**”，键入“**土星项目**”，然后单击“**下一步**”。
4. 单击“**添加元素**”。
5. 在“**检测内容包含**”列表上，选择“**关键字**”，然后在“关键字”框中键入“*土星项目*”。
6. 单击“**下一步**”，再单击“**完成**”。
7. 如果系统询问你是否要测试敏感信息类型，请单击“**否**”。

### <a name="more-information"></a>更多信息

[自定义敏感信息类型](/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a>创建自动标记策略以基于敏感信息类型分配敏感度标签

如果在组织中使用敏感度标签，则可以将标签自动应用于包含定义的敏感信息类型的文件。 

创建自动标记策略

1. 打开 [Microsoft 365 合规管理中心](https://compliance.microsoft.com)。
2. 在左侧导航栏中，单击“**信息保护**”。
3. 在“**自动标记**”标签上，单击“**创建自动标记策略**”。
4. 在“**选择要将此标签要应用于的信息**”页面上，选择“**自定义**”，然后选择“**下一步**”。
5. 输入策略的名称和描述，然后单击“**下一步**”。
6. 在”**选择要应用标签的位置**“页面上，打开“**SharePoint网站**”，然后单击“**选择网站**”。
7. 添加要启用自动标记的网站 URL，然后单击“**完成**”。
8. 单击“**下一步**”。
9. 在“**设置通用或高级规则**”页面上，选择“**通用规则**”，然后单击“**下一步**”。
10. 在“**定义所有位置的内容规则**”页面上，单击“**新建规则**”。
11. 在“**新建规则**”页面上，为规则命名，单击“**添加条件**”，然后单击“**内容包含敏感信息类型**”。
12. 单击“**添加**”，单击“**敏感信息类型**”，选择要使用的敏感信息类型，单击“**添加**”，然后单击“**保存**”。
13. 单击“**下一步**”。
14. 单击“**选择标签**”，选择要使用的标签，然后单击“**添加**”。
15. 单击“**下一步**”。
16. 将策略置于模拟模式，然后单击“**下一步**”。
17. 单击“**创建策略**”，然后单击“**完成**”。

实施策略后，当用户在文档中键入“Project Saturn”时，自动标记策略将在扫描文件时自动应用指定的标签。

### <a name="more-information"></a>更多信息

[将敏感度标签自动应用于内容](../compliance/apply-sensitivity-label-automatically.md)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a>创建 DLP 策略以删除来宾对高度敏感文件的访问

可使用 [数据丢失防护（DLP）](../compliance/dlp-learn-about-dlp.md) 阻止不需要的敏感内容访客共享。 数据丢失防护可以根据文件的敏感度标签采取措施并删除来宾访问权限。

创建 DLP 规则

1. 在 Microsoft 365 合规性管理中心中，转到“[数据丢失防护页面](https://compliance.microsoft.com/datalossprevention)”。
2. 单击“**创建策略**”。
3. 选择“**自定义**”，然后单击“**下一步**”。
4. 键入策略名称，并单击“**下一步**”。
5. 在“**要应用该策略的位置**”页面上，关闭除 “**SharePoint 网站**”和 “**OneDrive 帐户**”之外的所有设置，然后单击“**下一步**”。
6. 在“**定义策略设置**”页面上，单击“**下一步**”。
7. 在“**自定义高级 DLP 规则**”页面上，单击“**创建规则**”并输入规则名称。
8. 在“**条件**”下，单击“**添加条件**”，然后选择“**内容包含**”。
9. 单击“**添加**”，选择“**敏感度标签**”，选择要使用的标签，然后单击“**添加**”。

   ![条件选项、敏感信息类型、敏感度标签和保留标签的屏幕截图。](../media/limit-accidental-exposure-dlp-conditions.png)

10. 在“**操作**”下，单击“**添加操作**”，然后选择“**限制访问或对 Microsoft 365 位置中的内容进行加密**”。
11. 选中“**限制访问或对 Microsoft 365 位置中的内容进行加密**”复选框，然后选择“**仅限组织外部人员**”选项。

      ![DLP 规则操作选项的屏幕截图。](../media/dlp-remove-guest-access-sensitive-files.png)

12. 单击“**保存**”，然后单击“**下一步**”。
13. 选择测试选项，然后单击“**下一步**”。
14. 单击“**提交**”，然后单击“**完成**”。

请务必注意，如果来宾是整个网站或团队的成员，则此策略不会删除访问权限。 如果计划将网站或团队中的高度机密文档与来宾成员进行共享，请考虑使用 [Teams 中的专用频道](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e)并仅允许组织成员在专用频道中共享。

## <a name="additional-options"></a>其他选项

Microsoft 365 和 Azure Active Directory 中提供部分选项，可帮助保护来宾共享环境的安全。

- 可创建允许或拒绝的共享域的列表，限制用户可以与之共享的人员。 有关详细信息，请参见“[按域限制共享 SharePoint 和 OneDrive 内容”](/sharepoint/restricted-domains-sharing)和“[允许或组织邀请指定组织的 B2B 用户](/azure/active-directory/b2b/allow-deny-list)”。
- 可限制用户连接至的其他 Azure Active Directory 租户。 参见“[使用租户限制管理对 SaaS 云应用程序的访问权限](/azure/active-directory/manage-apps/tenant-restrictions)”了解详细信息。
- 可创建合作伙伴能够帮助管理访客用户的托管环境。 有关信息，请参见“[创建有访客用户的 B2B 外联网](/Office365/Enterprise/b2b-extranet)”。

## <a name="see-also"></a>另请参阅

[与来宾共享时限制文件意外曝光](share-limit-accidental-exposure.md)

[有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)

[创建托管有来宾的 B2B 外联网](b2b-extranet.md)
