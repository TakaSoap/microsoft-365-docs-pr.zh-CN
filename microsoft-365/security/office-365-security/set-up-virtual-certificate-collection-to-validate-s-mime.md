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
description: 管理员可以了解如何创建虚拟证书集合，该虚拟证书集合将用于验证 Exchange Online 中的 S/MIME 证书。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203891"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="c2536-103">在证书集中设置虚拟证书Exchange Online以验证 S/MIME</span><span class="sxs-lookup"><span data-stu-id="c2536-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c2536-104">作为管理员，您需要在用于验证 S/MIME Exchange Online配置虚拟证书集合。</span><span class="sxs-lookup"><span data-stu-id="c2536-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="c2536-105">此虚拟证书集合设置为具有 SST 文件名扩展名的证书存储。</span><span class="sxs-lookup"><span data-stu-id="c2536-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="c2536-106">SST 文件包含验证 S/MIME 证书时使用的所有根证书和中间证书。</span><span class="sxs-lookup"><span data-stu-id="c2536-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="c2536-107">创建并保存 SST</span><span class="sxs-lookup"><span data-stu-id="c2536-107">Create and save an SST</span></span>

<span data-ttu-id="c2536-108">您可以创建此 SST 证书存储文件，具体方法为使用 Windows PowerShell 中的 **Export-Certificate** cmdlet 从受信任的计算机导出证书，将 _Type_ 值指定为 SST。</span><span class="sxs-lookup"><span data-stu-id="c2536-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="c2536-109">有关说明，请参阅[Export-Certificate。](/powershell/module/pkiclient/export-certificate)</span><span class="sxs-lookup"><span data-stu-id="c2536-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="c2536-110">获得 SST 证书存储文件后，在 Exchange Online PowerShell 中使用以下语法将 SST 文件内容保存在 Exchange Online 虚拟证书存储中。</span><span class="sxs-lookup"><span data-stu-id="c2536-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="c2536-111">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c2536-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="c2536-112">此示例导入 SST 文件 C：\My Documents\Exported Certificate Store.sst。</span><span class="sxs-lookup"><span data-stu-id="c2536-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="c2536-113">有关语法和参数的详细信息，请参阅[Set-SmimeConfig。](/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="c2536-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="c2536-114">确保证书有效</span><span class="sxs-lookup"><span data-stu-id="c2536-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="c2536-115">在Exchange Online中，仅 SST 用于证书验证。</span><span class="sxs-lookup"><span data-stu-id="c2536-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="c2536-116">更多信息</span><span class="sxs-lookup"><span data-stu-id="c2536-116">More Information</span></span>

[<span data-ttu-id="c2536-117">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="c2536-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="c2536-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="c2536-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)