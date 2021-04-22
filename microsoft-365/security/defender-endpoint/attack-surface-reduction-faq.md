---
title: '攻击面减少常见问题解答 (常见问题) '
description: 查找有关适用于终结点的 Microsoft Defender 攻击面减少规则的常见问题的解答。
keywords: 攻击面减少规则， asr， hips， 主机入侵防护系统， 保护规则， 反攻击， 攻击， 感染防护， microsoft defender 终结点
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: martyav
ms.author: v-maave
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cf41dda4ff61137d6b60b2fc735227f15418477e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935589"
---
# <a name="attack-surface-reduction-frequently-asked-questions-faq"></a>攻击面减少常见问题解答 (常见问题) 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="is-attack-surface-reduction-asr-part-of-windows"></a>攻击面减少 (ASR) Windows 的一部分？

ASR 最初是作为 Windows 10 版本 1709 中 Microsoft Defender 防病毒的主要更新引入的一系列攻击防护功能的功能。 Microsoft Defender 防病毒是 Windows 的本机反恶意软件组件。 但是，完整的 ASR 功能集仅适用于 Windows 企业许可证。 另请注意，ASR 规则排除项与 Microsoft Defender 防病毒排除项分开管理。

## <a name="do-i-need-to-have-an-enterprise-license-to-run-asr-rules"></a>是否需要具有企业许可证才能运行 ASR 规则？

只有在你拥有适用于 Windows 10 的企业许可证时，才支持整套 ASR 规则和功能。 在没有企业许可证的情况下，可能只能使用有限数量的规则。 如果你有 Microsoft 365 商业版，请设置 Microsoft Defender 防病毒作为主要安全解决方案，并通过 PowerShell 启用规则。 在不使用企业许可证的情况下使用 ASR 不受正式支持，你将无法使用 ASR 的全部功能。

若要了解有关 Windows 许可的更多信息，请参阅 [Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 许可并获取 [适用于 Windows 10 的批量许可指南](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)。

## <a name="is-asr-supported-if-i-have-an-e3-license"></a>如果我有 E3 许可证，是否支持 ASR？

是。 ASR 受 Windows 企业版 E3 及以上版本支持。 

## <a name="which-features-are-supported-with-an-e5-license"></a>E5 许可证支持哪些功能？

E3 支持的所有规则也受 E5 支持。

E5 添加了与 Defender for Endpoint 的更大集成。 使用 E5，可以实时查看警报、微调规则排除项、配置 ASR 规则以及查看事件报告列表。

## <a name="what-are-the-currently-supported-asr-rules"></a>当前支持的 ASR 规则是什么？
ASR 当前支持以下所有规则。

## <a name="what-rules-to-enable-all-or-can-i-turn-on-individual-rules"></a>要启用哪些规则？ 全部启用，或者我能否启用单个规则？
为了帮助你找出最适合你的环境，我们建议你在审核模式下启用 ASR [规则](audit-windows-defender.md)。 通过这种方法，可以确定对组织可能的影响。 例如，业务线应用程序。

## <a name="how-do-asr-rules-exclusions-work"></a>ASR 规则排除如何工作？
对于 ASR 规则，如果添加一个排除项，它将影响每个 ASR 规则。
以下两个特定规则不支持排除项：

|规则名称|GUID|文件&文件夹排除项|
|:--|:--|:--|
|阻止 JavaScript 或 VBScript 启动下载的可执行内容|D3E037E1-3EB8-44C8-A917-57927947596D|不支持|
|通过 WMI 事件订阅阻止持久性|e6db77e5-3df2-4cf1-b95a-636979351e5b|不支持|

ASR 规则排除项支持通配符、路径和环境变量。 若要详细了解如何在 ASR 规则中使用通配符，请参阅配置和验证基于文件扩展名和文件夹位置 [的排除项](/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus)。

请注意以下有关 ASR 规则排除项 (通配符和 env。 变量) ：

- ASR 规则排除项独立于 Defender AV 排除项
- 通配符不能用于定义驱动器号
- 如果要排除多个文件夹，在路径中使用多个 \ 实例来指示多个嵌套文件夹 (\* 例如 c：\Folder \* \* \Test) 
- Microsoft Endpoint Configuration Manager *不支持* 通配符 (* 或 ？) 
- 如果要排除包含随机字符的文件 (自动生成文件) ，可以使用"？"符号 (例如 C：\Folder\fileversion？。docx) 
- 组策略中的 ASR 排除项不支持引号 (引擎将本机处理长路径、空格等，因此无需使用引号) 
- ASR 规则在 NT AUTHORITY\SYSTEM 帐户下运行，因此环境变量仅限于计算机变量。



## <a name="how-do-i-know-what-i-need-to-exclude"></a>我如何知道需要排除哪些内容？
不同的 ASR 规则将具有不同的保护流。 请始终考虑要配置的 ASR 规则如何防范，以及实际执行流程如何平移。

示例：阻止 **从 Windows** 本地安全机构子系统窃取凭据 直接从本地安全机构子系统 (LSASS) 进程进行读取可能会带来安全风险，因为它可能会公开公司凭据。

此规则可防止不受信任的进程直接访问 LSASS 内存。 每当进程尝试使用 OpenProcess () 访问 LSASS（具有 PROCESS_VM_READ 访问权限）时，该规则将专门阻止该访问权限。

:::image type="content" source="images/asrfaq1.png" alt-text="阻止凭据窃取 LSASS":::

看一下上面的示例，如果确实需要为阻止访问权限的进程创建异常，则添加文件名和完整路径将阻止该文件名，在允许访问 LSASS 进程内存之后， 值 0 表示 ASR 规则将忽略此文件/进程，并且不会阻止/审核它。

:::image type="content" source="images/asrfaq2.png" alt-text="排除文件 asr":::

## <a name="what-are-the-rules-microsoft-recommends-enabling"></a>Microsoft 建议启用哪些规则？

我们建议启用每个可能的规则。 但是，在某些情况下不应启用规则。 例如，如果使用的是 Microsoft Endpoint Configuration Manager (或 System Center Configuration Manager - SCCM) 来管理终结点，则不建议启用源自 PSExec 和 WMI 命令规则的阻止进程创建。

我们强烈建议您阅读我们的公共文档中提供的每个特定于规则的信息和/或 [警告](/microsoft-365/security/defender-endpoint/attack-surface-reduction.md)。
跨多个保护支柱，如 Office、凭据、脚本、电子邮件等。Windows 1709 和更高版本支持所有 ASR 规则（通过 WMI 事件订阅阻止持久性除外）：

* [阻止来自电子邮件客户端和 Webmail 的可执行内容](attack-surface-reduction.md#block-executable-content-from-email-client-and-webmail)
* [阻止所有 Office 应用程序创建子进程](attack-surface-reduction.md#block-all-office-applications-from-creating-child-processes)
* [阻止 Office 应用程序创建可执行内容](attack-surface-reduction.md#block-office-applications-from-creating-executable-content)
* [阻止 Office 应用程序将代码注入其他进程](attack-surface-reduction.md#block-office-applications-from-injecting-code-into-other-processes)
* [阻止 JavaScript 或 VBScript 启动下载的可执行内容](attack-surface-reduction.md#block-javascript-or-vbscript-from-launching-downloaded-executable-content)
* [阻止执行可能混淆的脚本](attack-surface-reduction.md#block-execution-of-potentially-obfuscated-scripts)
* [阻止从 Office 宏调用 Win32 API](attack-surface-reduction.md#block-win32-api-calls-from-office-macros)
* [使用高级防护抵御勒索软件](attack-surface-reduction.md#use-advanced-protection-against-ransomware)
* [阻止从 Windows 本地安全机构子系统中窃取](attack-surface-reduction.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem) (lsass.exe) 
* [阻止源自 PSExec 和 WMI 命令的进程创建](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)
* [阻止从 USB 运行的不受信任的和未签名的进程](attack-surface-reduction.md#block-untrusted-and-unsigned-processes-that-run-from-usb)
* [阻止可执行文件运行，除非它们满足普遍标准、年龄或受信任的列表条件](attack-surface-reduction.md#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)
* [阻止 Office 通信应用程序创建子进程](attack-surface-reduction.md#block-office-communication-application-from-creating-child-processes)
* [阻止 Adobe Reader 创建子进程](attack-surface-reduction.md#block-adobe-reader-from-creating-child-processes)
* [通过 WMI 事件订阅阻止持久性](attack-surface-reduction.md#block-persistence-through-wmi-event-subscription)

## <a name="what-are-some-good-recommendations-for-getting-started-with-asr"></a>有关 ASR 入门的一些很好建议是什么？

测试 ASR 规则在一小段时间内在审核模式下运行 ASR 规则对组织的影响。 在审核模式下运行规则时，您可以识别可能错误地被阻止的任何业务线应用程序，并排除在 ASR 中。

大型组织应考虑在"圈"中推出 ASR 规则，通过审核和启用范围越来越广的设备子集中的规则。 可以使用 Intune 或组策略管理工具将组织的设备排列到圈中。

## <a name="how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it"></a>在启用 ASR 规则之前，应在审核模式下测试该规则多久？

将规则保持审核模式大约 30 天，以获得规则在整个组织中可用后如何运行的良好基线。 在审核期间，您可以标识规则可能阻止的任何业务线应用程序，并配置规则以排除它们。

## <a name="im-making-the-switch-from-a-third-party-security-solution-to-defender-for-endpoint-is-there-an-easy-way-to-export-rules-from-another-security-solution-to-asr"></a>我要将第三方安全解决方案切换到 Defender for Endpoint。 是否有一种将规则从另一个安全解决方案导出到 ASR 的"简单"方法？

在大多数情况下，从 [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) 建议的基线建议开始比尝试从另一个安全解决方案导入规则更简单、更好。 然后，使用审核模式、监视和分析等工具配置新解决方案以满足您的独特需求。 

大多数 ASR 规则的默认配置与 Defender for Endpoint 实时保护相结合，可抵御大量攻击和漏洞。

在 Defender for Endpoint 中，可以使用自定义指示器更新防护，以允许和阻止某些软件行为。 ASR 还允许以文件和文件夹排除的形式对规则进行一些自定义。 作为一般规则，最好在一段时间内审核规则，并配置可能被阻止的任何业务线应用程序的排除项。

## <a name="does-asr-support-file-or-folder-exclusions-that-include-system-variables-and-wildcards-in-the-path"></a>ASR 是否支持路径中包括系统变量和通配符的文件或文件夹排除项？

是。 有关从 ASR 规则中排除文件或文件夹的更多详细信息，请参阅从[ASR](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)规则中排除文件和文件夹[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists);有关在排除的文件路径中使用系统变量和通配符的详细信息，请参阅基于文件扩展名和文件夹位置配置和验证排除项。

## <a name="do-asr-rules-cover-all-applications-by-default"></a>默认情况下，ASR 规则是否涵盖所有应用程序？

这取决于规则。 大多数 ASR 规则涵盖 Microsoft Office服务（如 Word、Excel、PowerPoint 和 OneNote 或 Outlook）的行为。 某些 ASR 规则（如阻止 *执行可能混淆的* 脚本）在作用域中更为一般。

## <a name="does-asr-support-third-party-security-solutions"></a>ASR 是否支持第三方安全解决方案？

ASR 使用 Microsoft Defender 防病毒阻止应用程序。 目前无法将 ASR 配置为使用另一个安全解决方案进行阻止。

## <a name="i-have-an-e5-license-and-enabled-some-asr-rules-in-conjunction-with-defender-for-endpoint-is-it-possible-for-an-asr-event-to-not-show-up-at-all-in-defender-for-endpoints-event-timeline"></a>我拥有 E5 许可证，并且与 Defender for Endpoint 一起启用了一些 ASR 规则。 ASR 事件是否可能完全未显示在 Defender for Endpoint 的事件时间线中？

每当 ASR 规则在本地触发通知时，有关事件的报告也会发送到 Defender for Endpoint 门户。 如果在查找事件时遇到问题，可以使用搜索框筛选事件时间线。 您还可以通过访问安全中心任务栏中的配置管理图标 **转到** 攻击面管理来查看 ASR 事件。  攻击面管理页面包含报告检测选项卡，其中包括报告给 Defender for Endpoint 的 ASR 规则事件的完整列表。

## <a name="i-applied-a-rule-using-gpo-now-when-i-try-to-check-the-indexing-options-for-the-rule-in-microsoft-outlook-i-get-a-message-stating-access-denied"></a>我使用 GPO 应用了规则。 现在，当我尝试在 Microsoft Outlook 中检查规则的索引选项时，我收到一条消息，指出"访问被拒绝"。

请尝试直接从 Windows 10 打开索引选项。

1. 选择 Windows **任务栏** 上的"搜索"图标。

1. 在 **搜索框中输入** 索引选项。

## <a name="are-the-criteria-used-by-the-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-configurable-by-an-admin"></a>规则使用的条件"除非可执行文件满足普遍程度、年龄或受信任的列表条件，否则阻止可执行文件运行"是否由管理员配置？

否。 此规则使用的条件由 Microsoft 云保护维护，以使用从世界各地的数据持续更新受信任的列表。 本地管理员没有写入权限来更改此数据。 如果要将此规则配置为为企业定制它，可以将某些应用程序添加到排除列表以防止触发规则。

## <a name="i-enabled-the-asr-rule-block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion-after-some-time-i-updated-a-piece-of-software-and-the-rule-is-now-blocking-it-even-though-it-didnt-before-did-something-go-wrong"></a>我启用了 ASR 规则 *，阻止可执行文件运行，除非它们* 符合普遍、年龄或受信任的列表条件。 一段时间之后，我更新了一个软件，规则现在阻止了它，即使以前没有更新过。 出错了？

此规则依赖于每个具有已知信誉的应用程序，根据受信任应用列表的流行程度、年龄或包含情况进行度量。 阻止或允许应用的规则决定最终由 Microsoft 云保护评估这些条件确定。

通常，云保护可以确定应用程序的新版本与早期版本的相似性，因此无需进行长度重新评估。 但是，在切换版本后（尤其是在进行重大更新后）应用建立信誉可能需要一些时间。 在此期间，您可以将应用程序添加到排除列表，以防止此规则阻止重要应用程序。 如果经常更新和运行新版本的应用程序，可以选择改为在审核模式下运行此规则。

## <a name="i-recently-enabled-the-asr-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-and-i-am-getting-a-large-number-of-notifications-what-is-going-on"></a>我最近启用了 ASR 规则 *，* 阻止从 Windows 本地安全机构子系统 (lsass.exe) 窃取凭据，我收到大量通知。 这是怎么回事？

此规则生成的通知不一定指示恶意活动;但是，此规则仍可用于阻止恶意活动，因为恶意软件通常lsass.exe非法访问帐户。 登录lsass.exe进程将用户凭据存储在内存中。 Windows 使用这些凭据验证用户并应用本地安全策略。

因为一天中有许多合法进程将lsass.exe凭据，所以此规则可能非常干扰。 如果已知的合法应用程序导致此规则生成过多通知，您可以将其添加到排除列表。 与其他大部分 ASR 规则相比，大多数其他 ASR 规则将生成相对较少的通知，因为调用 lsass.exe 是许多应用程序正常运行的典型情况。

## <a name="is-it-a-good-idea-to-enable-the-rule-block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe-alongside-lsa-protection"></a>与 LSA 保护一起启用规则"阻止从 *Windows* 本地安全机构子系统中窃取凭据 (lsass.exe) 是一个好主意吗？

如果还启用了 [LSA](https://docs.microsoft.com/windows-server/security/credentials-protection-and-management/configuring-additional-lsa-protection#BKMK_HowToConfigure) 保护，则启用此规则不会提供额外的保护。 由于规则保护和 LSA 保护的运行方式都相同，因此同时运行这两个保护将非常多余。 但是，有时你可能无法启用 LSA 保护。 在这种情况下，您可以启用此规则，以针对目标恶意软件lsass.exe。

## <a name="see-also"></a>另请参阅

* [攻击面减少概述](attack-surface-reduction.md)
* [评估减少攻击面规则](evaluate-attack-surface-reduction.md)
* [自定义减少攻击面规则](customize-attack-surface-reduction.md)
* [启用攻击面减少规则](enable-attack-surface-reduction.md)
* [Microsoft Defender 与其他防病毒/反恶意软件的兼容性](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
