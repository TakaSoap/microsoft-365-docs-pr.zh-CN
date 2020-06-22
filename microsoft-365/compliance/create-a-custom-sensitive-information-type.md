---
title: 在安全与合规中心内创建自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全与合规中心的图形用户界面中为 DLP 创建、修改、删除和测试自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f702582a0e2c53b0846cd0586295d9bbea657e3c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818061"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a>在安全与合规中心内创建自定义敏感信息类型

阅读本文，以在安全与合规中心 ([https://protection.office.com](https://protection.office.com)) 内创建[自定义敏感信息类型](custom-sensitive-info-types.md)。 使用此方法创建的自定义敏感信息类型将添加到名为 `Microsoft.SCCManaged.CustomRulePack` 的规则包中。

此外，还可以使用 PowerShell 和精确的数据匹配功能创建自定义敏感信息类型。 若要了解有关这些方法的详细信息，请参阅：
- [使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [使用精确数据匹配 (EDM) 为 DLP 创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a>准备工作

> [!NOTE]
> 应该拥有全局管理员或合规性管理员权限，以便可以通过 UI 创建、测试和部署自定义的敏感信息类型。 请参阅 Office 365 中的[关于管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide)。

- 组织必须具有包含数据丢失防护 (DLP) 的订阅（如 Office 365 企业版）。 请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。 

- Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).

  在创建自定义分类或正则表达式模式时，不可从 Microsoft 客户服务和支持获取帮助。 支持工程师可对功能提供有限的支持，例如提供用于测试目的的示例正则表达式，或者帮助排查未如期触发的现有正则表达式模式的问题，但无法保证所有自定义内容匹配开发都将满足你的要求或义务。

- DLP 使用搜索爬网程序来确定 SharePoint Online 和 OneDrive for Business 网站中的敏感信息并对其分类。 要确定现有内容中新的自定义敏感信息类型，必须对该内容重新爬网。 根据计划对内容进行爬网，但你可手动重新爬网内容来查找网站集、列表或库。 有关详细信息，请参阅[Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content)（手动请求对网站、库或列表进行爬网和重新编制索引）。

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a>在安全与合规中心内创建自定义敏感信息类型

在安全与合规中心内，依次转到“分类”****\>“敏感信息类型”****，再单击“创建”****。

设置的含义相当显而易见，而且向导中的相关页也对这些设置进行了说明：

- **名称**

- **说明**

- **临近度**

- **可信度**

- **主要模式元素**（关键字、正则表达式或字典）

- 可选**支持性模式元素**（关键字、正则表达式或字典）和相应**最低成本**值。

Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:

1. 在安全与合规中心内，依次转到“分类”****\>“敏感信息类型”****，再单击“创建”****。

    ![“敏感信息类型”和“创建”按钮的位置](../media/scc-cust-sens-info-type-new.png)

2. 在随即打开的“选择名称和说明”**** 页中，输入以下值：

  - **名称**：员工 ID。

  - **说明**：检测 9 位数 Contoso 员工 ID 号。

    ![名称和说明页](../media/scc-cust-sens-info-type-new-name-desc.png)

    完成后，单击“下一步”****。

3. 在随即打开的“匹配要求”**** 页中，单击“添加元素”****，以配置下列设置：

    - **检测内容包含**：
 
      a. Click **Any of these** and select **Regular expression**.

      b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).
  
    - **支持性元素**：单击“添加支持性元素”****，再选择“包含此关键字列表”****。

    - 在随即显示的“包含此关键字列表”**** 区域中，配置下列设置：

      - **关键字列表**：输入以下值：员工、ID、徽章。

      - **最小计数**：保留默认值 1。

    - 保留“可信度”**** 默认值 60。 

    - 保留“字符临近度”**** 默认值 300。

    ![匹配页面要求](../media/scc-cust-sens-info-type-new-reqs.png)

    完成后，单击“下一步”****。

4. 在随即打开的“检查并最终确定”**** 页中，检查设置并单击“完成”****。

    ![检查并完成页面](../media/scc-cust-sens-info-type-new-review.png)

5. The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.

    ![测试建议页](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证是否已成功新建敏感信息类型，请按以下任一步骤操作：

  - 依次转到“分类”****\>“敏感信息类型”****，并验证新自定义敏感信息类型是否已列出。

  - Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a>在安全与合规中心内修改自定义敏感信息类型

**注意**：
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).

- You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.

在安全与合规中心内，依次转到“分类”****\>“敏感信息类型”****，选择要修改的自定义敏感信息类型，然后单击“编辑”****。

  ![“敏感信息类型”和“编辑”按钮的位置](../media/scc-cust-sens-info-type-edit.png)

The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功修改敏感信息类型，请按以下任一步骤操作：

  - 依次转到“分类”****\>“敏感信息类型”****，以验证修改后的自定义敏感信息类型的属性。 

  - Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a>在安全与合规中心内删除自定义敏感信息类型 

**注意**：

- 只能删除自定义敏感信息类型；不能删除内置敏感信息类型。

- 删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。

1. 在安全与合规中心内，依次转到“分类”****\>“敏感信息类型”****，并选择一个或多个要删除的自定义敏感信息类型。

2. 在随即打开的弹出窗口中，单击“删除”****（或“删除多个敏感信息类型”****，如果选择了多个类型的话）。

    ![“敏感信息类型”和“删除”按钮的位置](../media/scc-cust-sens-info-type-delete.png)

3. 在随即显示的警告消息中，单击“是”****。

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功删除自定义敏感信息类型，请依次转到“分类”****\>“敏感信息类型”****，以验证自定义敏感信息类型是否已不再列出。

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a>在安全与合规中心内测试自定义敏感信息类型

1. 在安全与合规中心内，依次转到“分类”****\>“敏感信息类型”****。

2. Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).

    ![“敏感信息类型”和“测试类型”按钮的位置](../media/scc-cust-sens-info-type-test.png)

3. 在随即打开的“上传测试文件”**** 页面上，拖放文件或单击“浏览”**** 并选择文件，以上传要测试的文档。

    ![“上传测试文件”页](../media/scc-cust-sens-info-type-test-upload.png)

4. 单击“测试”**** 按钮，以测试文档的模式匹配情况。

5. 在“匹配结果”**** 页上，单击“完成”****。

    ![匹配结果](../media/scc-cust-sens-info-type-test-results.png)
