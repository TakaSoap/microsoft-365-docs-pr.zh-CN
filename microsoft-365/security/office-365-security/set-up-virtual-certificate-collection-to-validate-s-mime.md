---
title: 设置虚拟证书集合 - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理员可以了解如何创建将用于在 Exchange Online 中验证 S/MIME 证书的虚拟证书集合。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4537ecfa6d800294af9572e462ce18491ce2c441
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290473"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>在 Exchange Online 中设置虚拟证书集合以验证 S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


作为管理员，您需要在 Exchange Online 中配置将用于验证 S/MIME 证书的虚拟证书集合。 此虚拟证书集合设置为具有 SST 文件名扩展名的证书存储。 SST 文件包含验证 S/MIME 证书时使用的所有根证书和中间证书。

## <a name="create-and-save-an-sst"></a>创建并保存 SST

您可以通过使用 Windows PowerShell 中的 **Export-Certificate** cmdlet 从受信任计算机导出证书，并指定 _类型_ 值作为 SST 来创建此 SST 证书存储文件。 有关说明，请参阅[Export-Certificate。](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)

拥有 SST 证书存储文件后，在 Exchange Online PowerShell 中使用以下语法将 SST 文件内容保存在 Exchange Online 虚拟证书存储中。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

此示例导入 SST 文件 C：\My Documents\Exported Certificate Store.sst。

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

有关语法和参数的详细信息，请参阅[Set-SmimeConfig。](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>确保证书有效

在 Exchange Online 中，仅 SST 用于证书验证。

## <a name="more-information"></a>更多信息

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
