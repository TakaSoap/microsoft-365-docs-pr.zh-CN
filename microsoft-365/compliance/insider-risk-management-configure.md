---
title: 内部风险管理入门
description: 在组织中配置内幕风险管理。
keywords: Microsoft 365，内幕风险管理，风险管理，合规性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 86aa29d0c271869eb1939b8a6a8dfb004e35d2cf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637480"
---
# <a name="get-started-with-insider-risk-management"></a>内部风险管理入门

使用内部风险管理策略确定风险的活动和管理工具，以便对组织中的风险警报执行操作。 完成以下步骤以设置系统必备并配置内幕风险管理策略。

>[!IMPORTANT]
>Microsoft 365 内幕风险管理解决方案提供了租户级选项，可帮助客户在用户级别促进内部治理。 租户级别管理员可以设置权限，以便为组织成员提供对此解决方案的访问权限，并在 Microsoft 365 合规性中心内设置数据连接器，以支持用户级别的可能有风险的活动的用户级别标识。 客户确认与与雇用相关的各个用户的行为、字符或性能相关的见解可由管理员进行计算，并可供组织中的其他人使用。

有关内幕风险策略如何帮助您管理组织中的风险的详细信息，请参阅[Microsoft 365 中的内幕风险管理](insider-risk-management.md)。

## <a name="before-you-begin"></a>准备工作

在开始使用 "内幕风险管理" 之前，应确认你的[Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。 若要访问和使用内幕风险管理，您的组织必须具有以下订阅或加载项之一：

- Microsoft 365 E5 订阅（付费或试用版）
- Microsoft 365 E3 订阅 + Microsoft 365 E5 合规性加载项
- Microsoft 365 A5 订阅（付费或试用版）
- Microsoft 365 A3 订阅 + Microsoft 365 A5 合规性加载项

必须为内幕风险管理策略中包括的用户分配上述许可证之一。

如果您没有现有的 Microsoft 365 企业版 E5 计划，并且想要尝试使用内幕风险管理，则可以[将 microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)到现有订阅或注册 Microsoft 365 企业版 e5 的[试用版](https://www.microsoft.com/microsoft-365/enterprise)。

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>步骤1（必需）：为内部人员风险管理启用权限

有四个角色组用于配置权限以管理内幕风险管理功能。 若要继续执行这些配置步骤，租户管理员必须首先将您分配给 "**内幕风险管理**" 或 "**内幕风险管理" 管理员**角色组。 若要在初始配置后访问和管理内幕风险管理功能，用户必须是至少一个 "内幕风险管理" 角色组的成员。

根据合规性管理团队的结构，您可以选择将用户分配给特定角色组，以管理不同的内幕风险管理功能集。 配置内幕风险管理时从这些角色组选项中进行选择：

| **角色组** | **角色权限** |
| :---- | :---------------- |
| **内部风险管理** | 使用此角色组可在单个组中管理组织的内幕风险管理。 通过添加指定管理员、分析师和调查人员的所有用户帐户，您可以在单个组中配置内幕风险管理权限。 此角色组包含所有内幕风险管理权限角色。 这是快速开始使用 "内幕风险管理" 的最简单方法，非常适合于不需要为单独的用户组定义单独权限的组织。|
| **内幕风险管理管理员** | 使用此角色组最初配置内幕风险管理和更高版本，以便将内幕风险管理员与定义的组分离。  此角色组中的用户可以创建、读取、更新和删除内幕风险管理策略、全局设置和角色组分配。 |
| **内幕风险管理分析师** | 使用此组可将权限分配给将充当内幕风险案例分析人员的用户。 此角色组中的用户可以访问所有内幕风险管理警报、案例和通知模板。 他们无法访问内幕风险内容浏览器。 |
| **内幕风险管理调查人员** | 使用此组可将权限分配给将充当内部人员风险数据调查人员的用户。 在所有情况下，此角色组中的用户都可以访问所有内幕风险管理警报、案例、通知模板和内容资源管理器。 |

### <a name="add-users-to-an-insider-risk-management-role-group"></a>将用户添加到 "内幕风险管理" 角色组

完成以下步骤以将用户添加到 "内幕风险管理" 角色组：

1. 在 Microsoft [https://protection.office.com/permissions](https://protection.office.com/permissions) 365 组织中登录使用管理员帐户凭据。 "" "" "" ""

2. 在 "安全&amp;合规性中心" 中，转到 "**权限**"。 选择用于查看和管理 Office 365 中的角色的链接。

3. 选择要向其添加用户的 "内幕风险管理" 角色组，然后选择 "**编辑角色组**"。

4. 从左侧导航窗格中选择 "**选择成员**"，然后选择 "**编辑**"。

5. 选择 "**添加**"，然后选中要添加到角色组的所有用户的复选框。

6. 选择 "**添加**"，然后选择 "**完成**"。

7. 选择 "**保存**" 将用户添加到角色组。 选择 "**关闭**" 完成这些步骤。

## <a name="step-2-required-enable-the-audit-log"></a>步骤2（必需）：启用审核日志

内幕风险管理对在策略中配置的用户见解和活动使用审核日志。 审核日志是与内幕风险管理策略关联的所有活动的摘要，也是策略更改的任何时间的摘要。

有关启用审核的分步说明，请参阅[打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。 启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。 您只需执行一次此操作。 有关使用审核日志的详细信息，请参阅[Search the audit log](search-the-audit-log-in-security-and-compliance.md)。

## <a name="step-3-optional-configure-prerequisites-for-templates"></a>步骤3（可选）：配置模板的先决条件

某些内幕风险管理模板具有必须为策略指示器配置的先决条件，以生成相关的活动通知。 根据计划为组织配置的策略配置适当的先决条件。

### <a name="configure-microsoft-365-hr-connector"></a>配置 Microsoft 365 HR 连接器

内幕风险管理支持导入从第三方风险管理和人力资源平台导入的用户和日志数据。 Microsoft 365 人力资源（HR）数据连接器允许您从 CSV 文件中提取人力资源数据，包括用户终止和上次雇用日期。 此数据可帮助推动内幕风险管理策略中的警报指示器，这是在组织中配置完全风险管理覆盖范围的重要部分。

有关为您的组织配置 Microsoft 365 HR 连接器的分步指南，请参阅[设置连接器以导入 HR 数据](import-hr-data.md)主题。 配置 HR 连接器后，请返回到这些配置步骤。

>[!IMPORTANT]
>如果使用 "*传出 emplo'ee 数据失窃*" 模板配置 p'licy，则需要将 HR 连接器配置为使用策略模板的 "完全信号检测" 功能。 如果您为您的组织配置了多个 HR 连接器，内幕风险管理将自动从所有 HR 连接器中提取指示器。

### <a name="configure-data-loss-prevention-dlp-policies"></a>配置数据丢失防护（DLP）策略

内幕风险 man'gement 支持使用 DLP 策略来帮助将敏感信息的有意或无意暴露给不需要的方。 使用*数据泄露*模板配置内幕风险管理策略时，必须向策略分配特定的 DLP 策略。 此策略可帮助将敏感信息的警报指示器驱动为在组织中配置完全风险管理覆盖范围的重要部分。

有关为您的组织配置 DLP 策略的分步指南，请参阅[创建、测试和调整 dlp 策略](create-test-tune-dlp-policy.md)主题。 配置 DLP 策略后，返回到这些配置 "ration 步骤"。 "" "" "" "" "" "" "

>[!IMPORTANT]
>如果使用*数据泄露*模板配置策略，则需要至少将一个 DLP 策略配置为使用策略模板的完全信号检测功能。 如果您为您的组织配置了多个 DLP 策略，则需要为每个 DLP 策略分配一个内幕风险管理策略。
""""""""
## <a name="step-4-required-configure-insider-risk-settings"></a>步骤4（必需）：配置内幕风险设置

[内幕风险设置](insider-risk-management-policies.md#policy-settings)适用于所有内幕风险管理策略，而不管您在创建策略时选择的模板如何。 设置是使用位于所有内幕风险管理选项卡顶部的 "**内幕风险设置**" 控件配置的。 这些设置控制隐私、指示器、监视窗口和智能检测。

在配置策略之前，请定义以下内幕风险设置：

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，并从任意页面右上角选择 "**内幕风险设置**"。
2. 在 "**隐私**" 页上，选择用于显示策略通知的用户名的隐私设置。
3. 在 "**指标**" 页上，选择要应用于所有内幕风险策略的警报指示器。

    >[!IMPORTANT]
    >为了接收在策略中定义的有风险的活动的警报，您必须选择一个或多个指示器。

4. 在 "**策略时段**" 页上，选择[策略](insider-risk-management-policies.md#policy-timeframes)时间段，以便在触发 "内幕风险策略" 的匹配项时对用户生效。
5. 在 "**智能检测**" 页面上，为内幕风险策略配置[异常和冒犯性语言检测](insider-risk-management-policies.md#intelligent-detections)。
6. 选择 "**保存**" 为您的内幕风险策略启用这些设置。

## <a name="step-5-required-create-an-insider-risk-management-policy"></a>步骤5（必需）：创建内幕风险管理策略

内幕风险管理策略包括分配的用户并定义为通知配置的风险指示器类型。 在活动可以触发通知之前，必须配置策略。

1. 在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**策略**" 选项卡。
2. 选择 "**创建策略**" 以打开策略向导
3. 在 "**新建内幕风险策略**" 页上，填写下列字段：
    - **Name （必需）**：输入策略的友好名称。
    - **Description （可选）**：输入策略的说明。
    - **选择 "策略模板（必需）**"：选择一个[策略模板](insider-risk-management-policies.md#policy-templates)来定义风险指示器的类型由策略监视。

    >[!IMPORTANT]
    >如果选择 "*数据泄漏*" 模板，则需要至少配置一个您稍后将在向导中分配的 DLP 策略。 如果选择 "*传出员工数据失窃*" 模板，则需要将 HR 连接器配置为使用策略模板的 "完全信号检测" 功能。

4. 选择 "**下一步**" 继续。
5. 在 "**用户**" 页上，选择 "**添加用户或组**" 以定义将哪些用户包括在策略中，或者选择 "**所有用户" 和 "已启用邮件的组**" 复选框。 选择 "**下一步**" 继续。
6. 在 "**指定要设置优先顺序的内容（可选）** " 页上，您可以为有风险的用户活动分配优先级的源：
    - **SharePoint 网站**：选择 "**添加 SharePoint 网站**"，然后选择要设置优先顺序的 SharePoint 组织。 例如， *"group1@contoso.sharepoint.com/sites/group1"*。
    - **敏感信息类型**：选择 "**添加敏感信息类型**"，然后选择要设置优先级的敏感度类型。 例如， *"美国银行帐户号码"* 和 *"信用卡号码"*。
    - **敏感度标签**：选择 "**添加灵敏度标签**"，然后选择要设置优先顺序的标签。 例如， *"保密"* 和 *"Secret"*。
7. 选择 "**下一步**" 继续。
8. 在 "**通知指示器**" 页上，您将看到您在 "**内幕风险设置** > **指示器**" 页上定义的指示器。 如果在向导的开头选择了 "*数据泄漏*" 模板，则必须从 " **dlp 策略**" 下拉列表中选择一个 dlp 策略。
9. 在 "**选择监视窗口**" 页面上，您将看到 "**内幕风险设置** > **策略**时间段" 页面上的策略的[监视窗口条件](insider-risk-management-policies.md#policy-timeframes)。 如果您选择了 "终止*员工数据失窃*策略" 模板，则可以选中 "*检查活动帖子终止*" 复选框，以在从 Microsoft 365 HR 连接器导入的终止日期后检测活动。
10. 选择 "**下一步**" 继续。
11. 在 "**检查**" 页上，查看您为策略选择的设置。 选择 "**编辑**" 以更改任何策略值，或选择 "**提交**" 以创建并激活策略。

完成这些步骤以创建第一个 "有问必答" 风险管理策略后，您将在大约24小时后开始接收来自活动指示器的警报。 根据需要使用本主题的步骤4中的指导或[创建新的内幕风险策略](insider-risk-management-policies.md#create-a-new-policy)中的步骤配置其他策略。
