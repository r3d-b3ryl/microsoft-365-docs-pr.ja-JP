---
title: OneDrive for Business および SharePoint Online におけるデータ暗号化
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
description: OneDrive for Business および SharePoint Online におけるデータセキュリティの暗号化の基本要素について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0c78a9ca6e6bad1e4aea707f8be5dec818b7a27
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817926"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="6d672-103">OneDrive for Business および SharePoint Online におけるデータ暗号化</span><span class="sxs-lookup"><span data-stu-id="6d672-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="6d672-104">OneDrive for Business および SharePoint Online におけるデータセキュリティの暗号化の基本要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d672-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="security-and-data-encryption-in-office-365"></a><span data-ttu-id="6d672-105">Office 365 のセキュリティとデータ暗号化</span><span class="sxs-lookup"><span data-stu-id="6d672-105">Security and data encryption in Office 365</span></span>

<span data-ttu-id="6d672-106">Microsoft 365 は、高度なセキュリティで保護された環境で、物理データセンターのセキュリティ、ネットワークセキュリティ、アクセスセキュリティ、アプリケーションセキュリティ、およびデータセキュリティがあります。</span><span class="sxs-lookup"><span data-stu-id="6d672-106">Microsoft 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security.</span></span> <span data-ttu-id="6d672-107">この記事では特に、OneDrive for Business および SharePoint Online のデータセキュリティの、送信中およびインプレース暗号化側に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="6d672-107">This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="6d672-108">データの暗号化の仕組みについて、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d672-108">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="6d672-109">転送中データの暗号化</span><span class="sxs-lookup"><span data-stu-id="6d672-109">Encryption of data in transit</span></span>

<span data-ttu-id="6d672-110">OneDrive for Business と SharePoint Online では、データを入力してデータセンターを終了する2つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="6d672-110">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="6d672-111">**クライアントとサーバーとの通信**インターネット経由での OneDrive for business への通信では、SSL/TLS 接続が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-111">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections.</span></span> <span data-ttu-id="6d672-112">すべての SSL 接続は、2048ビットのキーを使用して確立されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-112">All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="6d672-113">**データセンター間のデータ移動**データセンター間でデータを移動する主な理由は、geo レプリケーションを使用して障害復旧を可能にすることです。</span><span class="sxs-lookup"><span data-stu-id="6d672-113">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery.</span></span> <span data-ttu-id="6d672-114">たとえば、SQL Server のトランザクションログと blob ストレージのデルタは、このパイプに沿って移動します。</span><span class="sxs-lookup"><span data-stu-id="6d672-114">For instance, SQL Server transaction logs and blob storage deltas travel along this pipe.</span></span> <span data-ttu-id="6d672-115">このデータは、プライベートネットワークを使用して既に送信されていますが、クラス最高の暗号化を使用してさらに保護されています。</span><span class="sxs-lookup"><span data-stu-id="6d672-115">While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="6d672-116">保管中データの暗号化</span><span class="sxs-lookup"><span data-stu-id="6d672-116">Encryption of data at rest</span></span>

<span data-ttu-id="6d672-117">保管中の暗号化には、ユーザー コンテンツの BitLocker ディスク レベル暗号化と、ファイル単位暗号化が関係しています。</span><span class="sxs-lookup"><span data-stu-id="6d672-117">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="6d672-118">BitLocker は、OneDrive for business と SharePoint Online のサービス全体に展開されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-118">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="6d672-119">また、ファイルごとの暗号化は、Microsoft 365 マルチテナントと、マルチテナントテクノロジに基づいて構築された新しい専用環境の OneDrive for Business および SharePoint Online にも含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d672-119">Per-file encryption is also in OneDrive for Business and SharePoint Online in Microsoft 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="6d672-120">BitLocker 暗号化はディスク上のすべてのデータを暗号化し、ファイル単位暗号化の場合にはファイルごとに固有の暗号化キーを含めてさらに細かく暗号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="6d672-120">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file.</span></span> <span data-ttu-id="6d672-121">つまり、各ファイルを更新するたびに独自の暗号化キーを使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-121">Further, every update to every file is encrypted using its own encryption key.</span></span> <span data-ttu-id="6d672-122">保存される前に、暗号化されたコンテンツに対するキーがコンテンツとは物理的に離れた場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-122">Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content.</span></span> <span data-ttu-id="6d672-123">この暗号化の各ステップでは、256 ビット キーによる高度暗号化標準 (Advanced Encryption Standard: AES) が使用され、Federal Information Processing Standard (FIPS) 140-2 に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="6d672-123">Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant.</span></span> <span data-ttu-id="6d672-124">暗号化されたコンテンツは、データセンターにある多数のコンテナーに配布され、各コンテナーでは固有の資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-124">The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials.</span></span> <span data-ttu-id="6d672-125">これらの資格情報はコンテンツまたはコンテンツ キーとは物理的に別の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-125">These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="6d672-126">FIPS 140-2 準拠の詳細については、「 [fips 140-2 コンプライアンス](https://go.microsoft.com/fwlink/?LinkId=517625)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d672-126">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="6d672-127">ファイル レベルでの保管中の暗号化では Blob ストレージを活用し、事実上無制限のストレージ拡張を行ったり、前例のないレベルの保護機能を提供したりできます。</span><span class="sxs-lookup"><span data-stu-id="6d672-127">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection.</span></span> <span data-ttu-id="6d672-128">OneDrive for Business と SharePoint Online のすべてのお客様のコンテンツは blob ストレージに移行されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-128">All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage.</span></span> <span data-ttu-id="6d672-129">データのセキュリティ保護の方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d672-129">Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="6d672-130">All content is encrypted, potentially with multiple keys, and distributed across the datacenter.</span><span class="sxs-lookup"><span data-stu-id="6d672-130">All content is encrypted, potentially with multiple keys, and distributed across the datacenter.</span></span> <span data-ttu-id="6d672-131">Each file to be stored is broken into one or more chunks, depending its size.</span><span class="sxs-lookup"><span data-stu-id="6d672-131">Each file to be stored is broken into one or more chunks, depending its size.</span></span> <span data-ttu-id="6d672-132">Then, each chunk is encrypted using its own unique key.</span><span class="sxs-lookup"><span data-stu-id="6d672-132">Then, each chunk is encrypted using its own unique key.</span></span> <span data-ttu-id="6d672-133">Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span><span class="sxs-lookup"><span data-stu-id="6d672-133">Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="6d672-134">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store.</span><span class="sxs-lookup"><span data-stu-id="6d672-134">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store.</span></span> <span data-ttu-id="6d672-135">They also are randomly distributed across multiple blob containers.</span><span class="sxs-lookup"><span data-stu-id="6d672-135">They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="6d672-136">コンポーネントからファイルを再構築するために使用される "マップ" は、コンテンツデータベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-136">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="6d672-137">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete).</span><span class="sxs-lookup"><span data-stu-id="6d672-137">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete).</span></span> <span data-ttu-id="6d672-138">Each set of credentials is held in the secure Key Store and is regularly refreshed.</span><span class="sxs-lookup"><span data-stu-id="6d672-138">Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="6d672-139">つまり、ファイル単位の保管中の暗号化には以下のように 3 つの異なる種類のストアがあり、それぞれ別の機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="6d672-139">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="6d672-140">Content is stored as encrypted blobs in the blob store.</span><span class="sxs-lookup"><span data-stu-id="6d672-140">Content is stored as encrypted blobs in the blob store.</span></span> <span data-ttu-id="6d672-141">The key to each chunk of content is encrypted and stored separately in the content database.</span><span class="sxs-lookup"><span data-stu-id="6d672-141">The key to each chunk of content is encrypted and stored separately in the content database.</span></span> <span data-ttu-id="6d672-142">The content itself holds no clue as to how it can be decrypted.</span><span class="sxs-lookup"><span data-stu-id="6d672-142">The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="6d672-143">コンテンツデータベースは SQL Server データベースです。</span><span class="sxs-lookup"><span data-stu-id="6d672-143">The Content Database is a SQL Server database.</span></span> <span data-ttu-id="6d672-144">Blob ストアに保管されているコンテンツ Blob すべてを見つけて再構築するために必要なマップと、それらの Blob を暗号化解除するために必要なキーが一緒に保管されます。</span><span class="sxs-lookup"><span data-stu-id="6d672-144">It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="6d672-145">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate.</span><span class="sxs-lookup"><span data-stu-id="6d672-145">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate.</span></span> <span data-ttu-id="6d672-146">The information held in any one of the components is unusable on its own.</span><span class="sxs-lookup"><span data-stu-id="6d672-146">The information held in any one of the components is unusable on its own.</span></span> <span data-ttu-id="6d672-147">This provides an unprecedented level of security.</span><span class="sxs-lookup"><span data-stu-id="6d672-147">This provides an unprecedented level of security.</span></span> <span data-ttu-id="6d672-148">Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span><span class="sxs-lookup"><span data-stu-id="6d672-148">Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>
