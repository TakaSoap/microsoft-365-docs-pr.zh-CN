---
title: OneDrive for Business 和 SharePoint Online 中的数据加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解 OneDrive for Business 和 SharePoint Online 中数据安全加密的基本元素。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0c78a9ca6e6bad1e4aea707f8be5dec818b7a27
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817921"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business 和 SharePoint Online 中的数据加密

了解 OneDrive for Business 和 SharePoint Online 中数据安全加密的基本元素。
  
## <a name="security-and-data-encryption-in-office-365"></a>Office 365 中的安全性和数据加密

Microsoft 365 是一个高度安全的环境，可在多个层中提供广泛保护：物理数据中心安全性、网络安全性、访问安全性、应用程序安全性和数据安全性。 本文特别侧重于 OneDrive for Business 和 SharePoint Online 数据安全的中转和静态加密端。
  
观看以下视频，了解数据加密的工作方式。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>中转数据的加密

在 OneDrive for Business 和 SharePoint Online 中，有两种数据进入和退出数据中心的方案。
  
- **Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.

- **Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption. 

## <a name="encryption-of-data-at-rest"></a>静态数据的加密

静态加密包括两个组件：BitLocker 磁盘级别加密和客户内容的每个文件加密。
  
已为 OneDrive for Business 和 SharePoint Online 跨服务部署 BitLocker。 在 Microsoft 365 多租户和基于多租户技术的新专用环境中，每个文件加密也位于 OneDrive for Business 和 SharePoint Online 中。
  
While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.
  
有关 FIPS 140-2 合规性的详细信息，请参阅[FIPS 140-2 合规性](https://go.microsoft.com/fwlink/?LinkId=517625)。
  
File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:
  
1. All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.

2. All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.

3. 用于从文件的组件重组此文件的"映射"存储在内容数据库中。

4. Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.

换言之，静态的每个文件加密涉及三种不同存储类型，每种类型都有不同的功能：
  
- Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.

- The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.

Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.
