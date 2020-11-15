---
title: 使用终结点数据丢失防护
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 了解如何配置数据丢失防护 (DLP) 策略以使用 Microsoft 365 终结点数据丢失防护 (EPDLP) 位置。
ms.openlocfilehash: 64cdfeab4b527dd3b84e7586d1419e5bf8b383df
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073101"
---
# <a name="using-endpoint-data-loss-prevention"></a>使用端点数据丢失防护

本文将向你介绍创建和修改将设备用作位置的 DLP 策略的三种情况。

## <a name="dlp-settings"></a>DLP 设置

在开始之前，你应该先设置 DLP 设置，该设置将应用于所有设备的 DLP 策略。如果打算创建强制执行的策略，则必须配置这些设置：

- 云出口限制
- 不允许的应用限制

或

- 如果要从监视中排除杂乱的文件路径

  > [!div class="mx-imgBorder"]
  > ![DLP 设置](../media/endpoint-dlp-1-using-dlp-settings.png)

### <a name="file-path-exclusions"></a>文件路径排除

你可能希望从设备上的 DLP 监视、DLP 警报和 DLP 策略执行中排除某些路径，因为它们太杂乱或未包含你所感兴趣的文件。不会审核这些位置中的文件，且在这些位置中创建或修改的任何文件都不会受到 DLP 策略执行的影响。可以在 DLP 设置中将配置路径排除。

可使用此逻辑构建排除路径：

- 以“\”结尾的有效文件路径，仅表示直接位于文件夹下的文件。 <br/>例如：C:\Temp\

- 以“\*”结尾的有效文件路径，仅表示位于子文件夹下的文件，以及直接位于文件夹下方的文件。 <br/>例如：C:\Temp\*

- 以“\”或“\*”结尾的有效文件路径，表示直接位于文件夹和所有子文件夹下的所有文件。 <br/>例如：C:\Temp

- 两端“\”之间带有通配符的路径。 <br/>例如：C:\Users\*\Desktop\

- 两端“\”之间带有通配符，并通过 ‘(number)’ 给出确切的子文件夹数量的路径。 <br/>例如：C:\Users\*(1)\Downloads\

- 带有 SYSTEM 环境变量的路径。 <br/>例如：%SystemDrive%\Test\*

- 综合了上述所有情况。 <br/>例如：%SystemDrive%\Users\*\Documents\*(2)\Sub\

### <a name="service-domains"></a>服务域

可以将域添加到此列表，Microsoft Edge Chromium 会在执行终结点 DLP 策略云上载访问限制时引用该列表。 

如果列表模式设置为 **阻止** ，则用户将无法向这些域上载敏感项目。当因为某个项目符合 DLP 策略而阻止上传操作时，DLP 将产生一个警告或阻止敏感项目的上传。

如果列表模式设置为“ **允许** ”，则用户将* *_只能_* _将敏感项目上载到那些域，并且不允许对所有其他域的上载访问。

### <a name="unallowed-apps"></a>不允许的应用

当开启策略的_ *通过不允许的应用程序和浏览器访问* *设置，并且用户试图使用这些应用程序访问受保护的文件时，将会允许、阻止或者阻止但用户可覆盖限制该活动。会审核所有活动，并可在活动资源管理器中查看。

### <a name="unallowed-browsers"></a>不允许的浏览器

你通过其可执行名称来添加所标识的浏览器，将阻止这些浏览器访问符合强制执行的 DLP 策略条件的文件，其中设置上传到云服务的限制为阻止或阻止覆盖。当访问文件阻止这些浏览器时，最终用户将看到一个 toast 通知要求他们通过 Edge Chromium 打开文件。

[!IMPORTANT]
不包括可执行文件的路径，而仅包括可执行文件的名称（即browser.exe）。

## <a name="tying-dlp-settings-together"></a>将 DLP 设置捆绑在一起

通过端点 DLP 和 Edge Chromium Web 浏览器，可以限制将敏感项目无意中分享到不允许的云应用和服务。Edge Chromium 能够了解终端 DLP策略在何时限制了哪个项目，并执行访问限制。

当使用端点 DLP 作为正确配置的 DLP 策略和 Edge Chromium 浏览器中的位置时，将阻止在这些设置中所定义的不允许的浏览器访问与 DLP 策略控制相匹配的敏感项目。相反，将重定向用户到使用 Edge Chromium，而 Edge Chromium 凭借其对 DLP 施加限制的理解，可以在满足 DLP 策略中的条件时阻止或限制活动。

若要使用此限制，需要配置三个重要的部分：

1. 指定要防止敏感项目共享到的位置（服务、域、IP 地址）。

2. 添加出现 DLP 策略匹配时不允许访问某些敏感项目的浏览器。

3. 通过启用“ **上载到云服务** ”和“ **从不允许的浏览器访问** ”，配置 DLP 策略以定义应限制在这些位置的敏感项目的种类。

你可以继续添加新的服务、应用和策略，以扩展和扩大你的限制，从而满足业务需求并保护敏感数据。 

此配置将帮助确保你的数据安全，同时避免不必要的限制，防止或限制用户访问和共享不敏感的项目。

## <a name="endpoint-dlp-policy-scenarios"></a>终结点 DLP 策略方案

为了帮助你熟悉端点 DLP 功能以及其在 DLP 策略中所呈现的方式，我们整理了一些方案。当终点 DLP 变得公开可用时，所有的终点 DLP 内容将折叠到主 DLP 内容集中。

> [!IMPORTANT]
> 这些端点 DLP 方案不是创建和优化 DLP 策略的正式过程。当你需要在一般情况下使用 DLP 策略时，请参考以下主题：
>- [数据丢失防护概述](data-loss-prevention-policies.md)
>- [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)
>- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
>- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>方案 1：从模板创建策略，仅审核

这些方案要求你已登录设备，并向Activity explorer报告。如果你尚未登录设备，请参阅[使用端点数据丢失防护入门](endpoint-dlp-getting-started.md)。

1. 打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

2. 选择 **创建策略** 。

3. 在此方案中，依次选择“ **隐私** ”和“ **美国个人身份信息 (PII) 数据** ”，然后选择“ **下一步** ”。

4. 将除 **设备** 外的所有位置的 **状态** 字段切换为关闭。选择 **下一步** 。

5. 接受默认的“ **从模板中查看和自定义设置** ”选择，然后选择“ **下一步** ”。

6. 接受默认的“ **保护操作** ”值，然后选择“ **下一步** ”。

7. 选择 **审核或限制 Windows 设备上的活动** ，然后将操作设置为 **仅审核** 。选择 **下一步** 。

8. 接受默认的 **我想首先测试** 值，然后选择 **在测试模式下显示策略提示** 。选择 **下一步** 。

9. 查看设置，然后选择“ **提交** ”。

10. 新的 DLP 策略将显示在策略列表中。

11. 检查活动资源管理器中是否有来自受监视终结点的数据。设置设备的位置筛选器并添加策略，然后按策略名称筛选以查看此策略的影响。如果需要，请参阅 [活动资源管理器入门](data-classification-activity-explorer.md)。

12. 尝试与组织外的人员共享包含将触发美国个人身份信息（PII）数据条件的内容的测试。这应该会触发该政策。

13. 检查活动资源管理器中的事件。

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>方案 2：修改现有策略，设置警报

1. 打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

2. 选择在方案 1 中创建的“ **美国个人身份信息 (PII) 数据** ”策略。

3. 选择 **编辑策略** 。

4. 转到“ **高级 DLP 规则** ”页面，然后编辑“ **检测到少量内容的美国个人身份信息** ”。

5. 向下滚动到 **事件报告** 部分，然后将 **在规则匹配出现时向管理员发送警报** 设置为 **开启** 。电子邮件警报将会自动发送给管理员，以及你所添加到收件人列表中的其他人员。 

   > [!div class="mx-imgBorder"]
   > ![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. 出于本方案的目的，请选择“ **每次活动与规则匹配时选择发送警报** ”。

7. 选择“ **保存** ”。

8. 通过选择“ **下一步** ”，然后“ **提交** ”策略更改来保留所有先前的设置。

9. 尝试与组织外的人员共享包含将触发美国个人身份信息（PII）数据条件的内容的测试。这应该会触发该政策。

10. 检查活动资源管理器中的事件。

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>方案 3：修改现有策略，阻止操作但允许覆盖

1. 打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

2. 选择在方案 1 中创建的“ **美国个人身份信息 (PII) 数据** ”策略。

3. 选择 **编辑策略** 。

4. 转到“ **高级 DLP 规则** ”页面，然后编辑“ **检测到少量内容的美国个人身份信息** ”。

5. 向下滚动到“ **审核或限制 Windows 设备上的活动** ”部分，并对每个活动将相应的操作设置为“ **阻止但允许覆盖** ”。

   > [!div class="mx-imgBorder"]
   > ![设置阻止但允许覆盖操作](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. 选择“ **保存** ”。

7. 对 **检测到大量内容的美国个人身份信息** 重复步骤 4-7。

8. 通过选择“ **下一步** ”，然后“ **提交** ”策略更改来保留所有先前的设置。

9. 尝试与组织外的人员共享包含将触发美国个人身份信息（PII）数据条件的内容的测试。这应该会触发该政策。

   客户端设备上将显示如下所示的弹出窗口：

   > [!div class="mx-imgBorder"]
   > ![终结点 DLP 客户端阻止覆盖通知](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. 检查活动资源管理器中的事件。

## <a name="see-also"></a>另请参阅

- [了解终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
- [数据丢失防护概述](data-loss-prevention-policies.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 设备的装载工具和方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [已加入 Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)
- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
