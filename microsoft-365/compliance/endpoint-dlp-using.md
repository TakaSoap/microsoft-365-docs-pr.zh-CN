---
title: 使用端点数据丢失防护
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 了解如何配置数据丢失防护 (DLP) 策略以使用 Microsoft 365 终结点数据丢失防护 (EPDLP) 位置。
ms.openlocfilehash: aeb85b883738e94f2d7161cb2bc3434edbb16428
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680019"
---
# <a name="using-endpoint-data-loss-prevention"></a>使用端点数据丢失防护

为了帮助你熟悉终结点 DLP 功能及其在 DLP 策略中的呈现方式，我们整理了一些方案供你遵循。

> [!IMPORTANT]
> 这些终结点 DLP 方案不是创建和优化 DLP 策略的正式过程。 当你需要在常规情况下使用 DLP 策略，请参阅以下主题：
>
>- [了解数据丢失防护](dlp-learn-about-dlp.md)
>- [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)
>- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
>- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)

## <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>方案 1：从模板创建策略，仅审核

这些方案要求你已载入设备并向活动资源管理器浏览器报告。 如果尚未载入设备，请参阅[终结点数据丢失防护入门](endpoint-dlp-getting-started.md)。

1. 打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

2. 选择 **创建策略**。

3. 在此方案中，依次选择“**隐私**”和“**美国个人身份信息 (PII) 数据**”，然后选择“**下一步**”。

4. 将除 **设备** 外的所有位置的 **状态** 字段切换为关闭。选择 **下一步**。

5. 接受默认的“**从模板中查看和自定义设置**”选择，然后选择“**下一步**”。

6. 接受默认的“**保护操作**”值，然后选择“**下一步**”。

7. 选择 **审核或限制 Windows 设备上的活动**，然后将操作设置为 **仅审核**。选择 **下一步**。

8. 接受默认的 **我想首先测试** 值，然后选择 **在测试模式下显示策略提示**。选择 **下一步**。

9. 查看设置，然后选择“**提交**”。

10. 新的 DLP 策略将显示在策略列表中。

11. 检查活动资源管理器中是否存在来自受监视终结点的数据。设置设备的位置筛选器并添加策略，然后按策略名称筛选以查看此策略的影响。如果需要，请参阅 [活动资源管理器入门](data-classification-activity-explorer.md)。

12. 尝试与组织外的人员共享包含将触发美国个人身份信息 (PII) 数据条件内容的测试项。这应该会触发该策略。

13. 检查活动资源管理器中的事件。

## <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>方案 2：修改现有策略，设置警报

1. 打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

2. 选择在方案 1 中创建的“**美国个人身份信息 (PII) 数据**”策略。

3. 选择 **编辑策略**。

4. 转到“**高级 DLP 规则**”页面，然后编辑“**检测到少量内容的美国个人身份信息**”。

5. 向下滚动到“**事件报告**”部分，然后将“**在规则匹配出现时向管理员发送警报**”设置为“**开**”。 系统会将电子邮件警报自动发送给管理员，以及你添加到收件人列表的任何其他人员。 

![turn-on-incident-reports。](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. 出于本方案的目的，请选择“**每次活动与规则匹配时选择发送警报**”。

7. 选择“**保存**”。

8. 通过选择“**下一步**”，然后“**提交**”策略更改来保留所有先前的设置。

9. 尝试与组织外的人员共享包含将触发美国个人身份信息 (PII) 数据条件内容的测试项。这应该会触发该策略。

10. 检查活动资源管理器中的事件。

## <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>方案 3：修改现有策略，阻止操作但允许覆盖

1. 打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

2. 选择在方案 1 中创建的“**美国个人身份信息 (PII) 数据**”策略。

3. 选择 **编辑策略**。

4. 转到“**高级 DLP 规则**”页面，然后编辑“**检测到少量内容的美国个人身份信息**”。

5. 向下滚动到“**审核或限制 Windows 设备上的活动**”部分，并对每个活动将相应的操作设置为“**阻止但允许覆盖**”。

   > [!div class="mx-imgBorder"]
   > ![设置阻止但允许覆盖操作。](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. 选择“**保存**”。

7. 对 **检测到大量内容的美国个人身份信息** 重复步骤 4-7。

8. 通过选择“**下一步**”，然后“**提交**”策略更改来保留所有先前的设置。

9. 尝试与组织外的人员共享包含将触发美国个人身份信息 (PII) 数据条件内容的测试项。这应该会触发该策略。

   客户端设备上将显示如下所示的弹出窗口：

   > [!div class="mx-imgBorder"]
   > ![终结点 DLP 客户端阻止覆盖通知。](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. 检查活动资源管理器中的事件。

## <a name="scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview"></a>方案 4：避免使用自动隔离（预览版）从云同步应用循环 DLP 通知。

### <a name="before-you-begin"></a>开始之前

在此方案中，阻止将文件与 **高度机密** 敏感度标签同步到 OneDrive。 这是具有多个组件和过程的复杂方案。 你将需要：

- 要面向的 AAD 用户帐户和一台已将本地 OneDrive 文件夹与 OneDrive 云存储同步的已载入 Windows 10 计算机。
- 目标 Windows 10 计算机上安装的 Microsoft Word
- 敏感度标签配置和发布—请参阅 [敏感度标签入门](get-started-with-sensitivity-labels.md#get-started-with-sensitivity-labels) 和 [创建和配置敏感度标签及其策略](create-sensitivity-labels.md#create-and-configure-sensitivity-labels-and-their-policies)。

共有三个步骤。

1. 配置终结点 DLP 自动隔离设置。
2. 创建一个策略，用于阻止具有 **高度机密** 敏感度标签的敏感项目。
3. 在 Windows 10 设备上创建一个针对该策略的 Word 文档，应用标签，并将其复制到正在同步的本地 OneDrive 文件夹的用户帐户。  

### <a name="configure-endpoint-dlp-unallowed-app-and-auto-quarantine-settings"></a>配置终结点 DLP 不允许的应用和自动隔离设置

1. 打开 [终结点 DLP 设置](https://compliance.microsoft.com/datalossprevention?viewid=globalsettings)

2. 展开 **不允许的应用**。

3. 选择“**添加或编辑不允许的应用**”，并添加“*OneDrive*”（作为显示名称）和可执行文件名称“*onedrive.exe*”，以禁止 onedrive.exe 访问带有“**高度机密**”标签的项目。

4. 选择 **自动隔离**，然后 **保存**。

5. 在 **自动隔离设置** 下选择 **编辑自动隔离设置**。

6. 为不允许的应用启用 **自动隔离**。

7. 输入要将原始敏感文件移动到本地计算机上文件夹的路径。例如：
   
    **'%homedrive%%homepath%\Microsoft DLP\Quarantine'** 的用户名 *Isaiah langer* 会将移动的项目放在名为以下的文件夹中:  

    *C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive*

    并在原始文件名上附加一个日期和时间戳。
    
    > [!NOTE]
    > DLP 自动隔离将为每个不允许的应用创建文件的子文件夹。 因此，如果在不允许的应用列表中同时有 *Notepad* 和 *OneDrive* ，将为 **\OneDrive** 创建一个子文件夹，并为 **\Notepad** 创建另一个子文件夹。

8. 选择 **将文件替换为包含以下文本 的 .txt 文件**，并在占位符文件中输入所需的文本。例如，名为 *auto quar 1.docx* 的文件：
    
    > %%FileName%% 包含你的组织正在使用数据丢失防护 (DLP) 策略 %%PolicyName%% 保护的敏感信息，并已移动到隔离文件夹: %%QuarantinePath%%。
    
    将保留包含此消息的文本文件:
    
    > auto quar 1.docx 包含组织正在使用数据丢失防护 （DLP） 策略保护的敏感信息，并已移动到隔离文件夹：C：\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive\auto quar 1_20210728_151541.docx。

9. 选择 **保存**

### <a name="configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential"></a>配置策略以阻止 OneDrive 使用敏感度标签"高度机密"同步文件

1. 打开[数据丢失防护页](https://compliance.microsoft.com/datalossprevention?viewid=policies)。

2. 选择 **创建策略**。

3. 对于此方案，请选择 **自定义**，然后 **自定义策略**，并选择 **下一步**。

4. 填写 **名称** 和 **说明** 字段，选择 **下一步**。

5. 将“**设备**”以外所有位置的“**状态**”字段切换为“关”。 如果你有一个要从中测试此项的特定终端用户帐户，请务必在范围内选择它。 选择 **下一步**。

6. 默认情况下，接受 **创建或自定义高级 DLP 规则**，然后选择 **下一步**。

7. 使用以下值创建规则：
    1. **名称** > *方案 4 自动隔离*。
    1. **条件** > **内容包含** > **敏感度标签** > **高度机密**。
    1.  **操作** > **审核或限制 Windows 设备上的活动，** > **不允许的应用访问** > **阻止**。 对于此方案，请清除所有其他活动。
    1. **打开****用户通知** > 。
    1. **终结点设备** >选择 **在活动** （如果尚未启用）时向用户显示策略提示通知。
    
8. 选择 **保存**，然后 **下一步**。

9. 选择 **立即将其打开**。选择 **下一个**。

10. 查看设置，然后选择“**提交**”。

    > [!NOTE]
    > 至少需要一小时才能将新策略复制并应用到目标 Windows 10 计算机。

11. 新的 DLP 策略将显示在策略列表中。

### <a name="test-auto-quarantine-on-the-windows-10-device"></a>在 Windows 10 设备上测试自动隔离

1. 使用你在[中指定的用户帐户登录到Windows 10 计算机。配置策略以阻止使用敏感度标签"高度机密"文件的 OneDrive 同步](#configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential)步骤 5。

2. 创建内容不会同步到 OneDrive 的文件夹。例如：

    *C：\auto-quarantine 源文件夹*

3. 打开 Microsoft Word 并在自动隔离源文件夹中创建文件。 应用 **高机密** 敏感度标签; 请参阅 [Office 中文件和电子邮件的敏感度标签](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。

4. 将刚创建的文件复制到 OneDrive 同步文件夹。 应显示用户通知词，告知你不允许执行该操作，并且该文件将被隔离。 例如，对于用户名 *Isaiah Langer*，以及标题为 *自动隔离文档 1.docx*，你将看到以下消息：

    ![数据丢失防护用户通知弹出窗口，指出指定文件不允许 OneDrive 同步操作，并且文件将被隔离。](../media/auto-quarantine-user-notification-toast.png)
    
    消息将读取：
    
    > 不允许使用此应用打开自动隔离文档 1.docx。 文件将被隔离到‘C：\Users\IsaiahLanger\Microsoft DLP\OneDrive’

5. 选择 **关闭**。

6. 打开占位符文本文件。 将其命名为 **自动隔离文档1.docx_ *date_time*.txt**。 

7. 打开隔离文件夹并确认原始文件存在。
 
8. 检查活动资源管理器中是否存在来自受监视终结点的数据。设置设备的位置筛选器并添加策略，然后按策略名称筛选以查看此策略的影响。如果需要，请参阅 [活动资源管理器入门](data-classification-activity-explorer.md)。

9. 检查活动资源管理器中的事件。

## <a name="scenario-5-restrict-unintentional-sharing-to-unallowed-cloud-apps-and-services"></a>方案 5：将无意共享限制为不允许的云应用和服务

通过终结点 DLP 和 Microsoft Edge Web 浏览器，可以将意外共享敏感项目限制为不允许的云应用和服务。 Microsoft Edge 可以了解终结点 DLP 策略何时限制项目，并实施访问限制。

当你将 **设备** 用作正确配置的 DLP 策略中的位置且使用 Microsoft Edge 浏览器时，你在这些设置中定义的不允许的浏览器将无法访问与 DLP 策略控制匹配的敏感项。 相反，用户将被重定向以使用 Microsoft Edge，该浏览器了解 DLP 施加的限制，因此可以在满足 DLP 策略中的条件时阻止或限制活动。

若要使用此限制，需要配置三个重要部分：

1. 指定要防止敏感项目共享到的位置（服务、域、IP 地址）。

2. 添加出现 DLP 策略匹配时不允许访问某些敏感项目的浏览器。

3. 通过启用“**上载到云服务**”和“**从不允许的浏览器访问**”，配置 DLP 策略以定义应限制在这些位置的敏感项目的种类。

你可以继续添加新的服务、应用和策略，以扩展和扩大你的限制，从而满足业务需求并保护敏感数据。 

此配置将帮助确保你的数据安全，同时避免不必要的限制，防止或限制用户访问和共享不敏感的项目。
## <a name="see-also"></a>另请参阅

- [了解终结点数据丢失防护](endpoint-dlp-learn-about.md)
- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [将 Windows 10 和 Windows 11 设备载入到 Microsoft 365 概述](/microsoft-365/compliance/device-onboarding-overview)
- [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [已加入 Azure Active Directory (AAD)](/azure/active-directory/devices/concept-azure-ad-join)
- [下载基于 Chromium 的新 Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [开始使用默认 DLP 策略](get-started-with-the-default-dlp-policy.md)
- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
