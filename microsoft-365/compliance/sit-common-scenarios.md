---
title: 敏感信息类型的常见使用方案
f1.keywords:
- NOCSH
ms.author: chrfox
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 如何实现常见的敏感信息类型用例方案
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 39afa17fc7bf258848de9d5554b3dd56a1ce21b5
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525732"
---
# <a name="common-usage-scenarios-for-sensitive-information-types"></a>敏感信息类型的常见使用方案

本文介绍如何在 SIT 用例方案中 (一) 敏感信息类型。 您可以使用这些过程作为示例，并根据您的特定需求进行调整。

## <a name="protect-credit-card-numbers"></a>保护信用卡号

Contoso Bank 需要将其签发的信用卡号分类为敏感。 他们的信用卡从一组六位数模式开始。 他们希望自定义开箱即用信用卡定义，以仅检测以六位数模式开头的信用卡号。

**建议的解决方案**

1. 创建信用卡 SIT 的副本。 使用复制和 [修改敏感信息类型的步骤复制](create-a-custom-sensitive-information-type.md#copy-and-modify-a-sensitive-information-type) 信用卡 SIT。
1. 编辑高可信度模式。 按照编辑 [或删除敏感信息类型模式中的步骤操作](sit-get-started-exact-data-match-create-rule-package.md#edit-or-delete-the-sensitive-information-type-pattern)。
1. 添加"starts with"检查，并添加未格式化 (的&位) 。 例如，为了确保仅将以 411111 & 433512 作为有效的信用卡，将以下内容添加到列表 4111 11、4111-11、411111、4335 12、4335-12、433512。
1. 对低可信度模式&步骤 2 & 3。

## <a name="test-numbers-similar-to-social-security-numbers"></a>与社会保险号类似的测试号码

Contoso 在 DLP) 策略中的"社会保险号码" (SSN) 数据丢失防护策略中标识了几个九位数的测试号码 (误报) 匹配。 他们希望从 SSN 的有效匹配列表中排除这些数字。

**建议的解决方案**

1. 创建 SSN SIT 的副本。 使用这些步骤复制 [和修改敏感信息类型以](create-a-custom-sensitive-information-type.md#copy-and-modify-a-sensitive-information-type) 复制 SSN SIT。
1. 编辑高可信度模式。 按照编辑 [或删除敏感信息类型模式中的步骤操作](sit-get-started-exact-data-match-create-rule-package.md#edit-or-delete-the-sensitive-information-type-pattern)。
1. 在"排除特定值"附加检查中添加要排除的数字。 例如，若要排除 239-23-532 & 23923532，只需添加23923532即可
1. 针对其他置信&重复步骤 2 & 3

## <a name="phone-numbers-in-signature-trigger-match"></a>电话触发器匹配中的数字

澳大利亚 Contoso 发现电子邮件签名中的电话号码正在触发其澳大利亚公司号码 DLP 策略的匹配。

**建议的解决方案**

使用关键字列表（包含电子邮件签名中常用的关键字，如"电话"、"Mobile"、"email"、"Thanks and regards"等）在支持元素中添加"not"组。保持此关键字列表的邻近度为较小的值（如 50 个字符）以提供更好的准确性。 有关详细信息，请参阅自定义 [敏感信息类型入门](create-a-custom-sensitive-information-type.md)。

## <a name="unable-to-trigger-aba-routing-policy"></a>无法触发 ABA 路由策略

DLP 策略无法在大型 excel 文件中触发 ABA 路由号码策略，因为在 300 个字符内找不到必需的关键字。

**建议的解决方案**

创建内置 SIT 的副本并对其进行编辑，以将关键字列表的邻近度从"300 个字符"更改为"文档中的任意位置"。

> [!TIP]
> 您可以编辑关键字列表以包含/排除与您的组织相关的关键字。

## <a name="unable-to-detect-credit-card-numbers-with-unusual-delimiters"></a>无法检测带异常分隔符的信用卡号

Contoso Bank 已注意到，他们的一些员工使用"/"作为分隔符共享信用卡号，例如 4111/1111/1111/1111/1111，开箱即用信用卡定义未检测到。 Contoso 希望定义自己的正则表达式，然后使用 LuhnCheck 验证它。

**建议的解决方案**

1. 使用自定义内置敏感信息类型中的步骤创建信用卡 SIT [的副本](customize-a-built-in-sensitive-information-type.md)。
1. 添加新模式
1. 在主元素中，选择正则表达式
1. 将包含"/"的正则表达式定义为正则表达式的一部分，然后选择验证程序并选择 luhncheck 或 func_credit_card 以确保正则表达式也通过 LuhnCheck。

## <a name="ignore-a-disclaimer-notice"></a>忽略免责声明通知

许多组织向进入或离开组织的电子邮件的顶部或底部添加法律免责声明、披露声明、签名或其他信息，在某些情况下，甚至包括组织内部。 员工本身会添加签名，包括动机引号、社交消息等。 免责声明或签名可以包含抄送词典中的条款，并且可能会生成大量误报。  

例如，典型的免责声明可能包含敏感或机密等词，并且查找敏感信息的策略会检测为一个事件，从而导致大量误报。 因此，为客户提供忽略免责声明的选项可以减少误报，提高合规性团队的效率。

### <a name="example-of-disclaimer"></a>免责声明示例

请考虑以下免责声明：

重要提示：此电子邮件只供有权接收可能包含机密信息的人员接收。 发送给 Contoso 客户端的电子邮件可能包含机密和合法特权的信息。 请不要阅读、复制、转发或存储此邮件，除非您是邮件的目标收件人。 如果收到错误消息，请将其转发给发件人，然后从计算机系统中完全删除该邮件。

如果 SIT 已配置为检测关键字机密，则每次在电子邮件中使用免责声明时，模式都将调用匹配，从而导致大量误报。

### <a name="ignore-disclaimer-using-prefix-and-suffix-in-sit"></a>在 SIT 中忽略使用前缀和后缀的免责声明

忽略免责声明中的关键字实例的一种方式是排除关键字的实例，这些关键字的前面有前缀，后跟后缀。

请考虑以下免责声明：

重要提示：此电子邮件只供有权接收可能包含机密信息 **的人员接收**。 发送给 Contoso 客户端的电子邮件可能包含机密和合法特权的信息。 请不要阅读、复制、转发或存储此邮件，除非您是邮件的目标收件人。 如果收到错误消息，请将其转发给发件人，然后从计算机系统中完全删除该邮件。

我们有两个关键字"机密"实例，如果我们将 SIT 配置为忽略此关键字的实例，前面是前缀 (在示例) 中用 italicized 表示，后跟示例) 中加粗的后缀 (，那么在大多数情况下，我们可以忽略免责声明。

若要忽略使用前缀和后缀的免责声明，

1. 在当前 SIT 中添加其他检查，以将前缀和后缀文本排除到我们要在免责声明中忽略的关键字。
1. 选择排除前缀，在" **前缀"** 文本框中输入 **包含的信息为** 。
1. 选择排除后缀，在" **后缀** "文本框中输入 **并合法特权**。
1. 对免责声明中关键字的其他实例重复此过程，如下图所示。

### <a name="ignore-disclaimer-by-excluding-secondary-elements"></a>通过排除辅助元素忽略免责声明

在免责声明实例中添加支持元素 (需要) 另一种方式是排除辅助元素。

请考虑以下免责声明：

重要提示：此电子邮件只供有权接收可能包含机密信息的人员接收。 发送给 Contoso 客户端的电子邮件可能包含机密和合法特权的信息。 请不要阅读、复制、转发或存储此邮件，除非您是邮件的目标收件人。 如果收到错误消息，请将其转发给发件人，然后从计算机系统中完全删除该邮件。

我们在此例中具有关键字"confidential"的两个实例。 如果我们将 SIT 配置为忽略免责声明中此关键字的实例 (为红色) ，则在大多数情况下，我们可以忽略免责声明。

:::image type="content" source="../media/sit-scenario-edit-pattern.png" alt-text="你可以向模式添加更多条件以排除免责声明中的其他实例。":::

若要忽略使用辅助元素的免责声明：

1. 在 **支持元素中选择"** 不是这些组的任何一个"。
1. 添加我们要忽略的免责声明实例作为关键字列表/字典。
1. 将关键字添加为要忽略的新行。 请记住，每个文本的长度不能超过 50 个字符。
1. 将此元素的邻近度设置为主元素的 50-60 个字符以内。
