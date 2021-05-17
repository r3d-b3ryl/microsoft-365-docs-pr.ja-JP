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
description: オンラインおよびオンラインでのデータ セキュリティの暗号化の基本的なOneDrive for BusinessについてSharePointします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca93d04fa21487ad054cd9cb924dff1fc15abfbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922631"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="ad918-103">OneDrive for Business および SharePoint Online におけるデータ暗号化</span><span class="sxs-lookup"><span data-stu-id="ad918-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="ad918-104">オンラインおよびオンラインでのデータ セキュリティの暗号化の基本的なOneDrive for BusinessについてSharePointします。</span><span class="sxs-lookup"><span data-stu-id="ad918-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="security-and-data-encryption-in-office-365"></a><span data-ttu-id="ad918-105">セキュリティとデータの暗号化 (Office 365</span><span class="sxs-lookup"><span data-stu-id="ad918-105">Security and data encryption in Office 365</span></span>

<span data-ttu-id="ad918-106">Microsoft 365は、物理データ センター のセキュリティ、ネットワーク セキュリティ、アクセス セキュリティ、アプリケーション セキュリティ、データ セキュリティなど、複数の層で広範な保護を提供する高度にセキュリティの高い環境です。</span><span class="sxs-lookup"><span data-stu-id="ad918-106">Microsoft 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security.</span></span> <span data-ttu-id="ad918-107">この記事では、オンラインおよびオンラインのデータ セキュリティの転送中および保存時の暗号化OneDrive for BusinessにSharePointします。</span><span class="sxs-lookup"><span data-stu-id="ad918-107">This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="ad918-108">データの暗号化の仕組みについて、次のビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad918-108">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="ad918-109">転送中データの暗号化</span><span class="sxs-lookup"><span data-stu-id="ad918-109">Encryption of data in transit</span></span>

<span data-ttu-id="ad918-110">オンラインOneDrive for Businessおよび SharePointでは、データがデータセンターに入り、データセンターを終了する 2 つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="ad918-110">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="ad918-111">**サーバーとのクライアント通信** インターネット上OneDrive for Business通信では、SSL/TLS 接続が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-111">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections.</span></span> <span data-ttu-id="ad918-112">すべての SSL 接続は、2048 ビット キーを使用して確立されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-112">All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="ad918-113">**データセンター間のデータ移動** データセンター間でデータを移動する主な理由は、障害復旧を有効にする geo レプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="ad918-113">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery.</span></span> <span data-ttu-id="ad918-114">たとえば、トランザクション ログSQL Server BLOB ストレージデルタは、このパイプに沿って移動します。</span><span class="sxs-lookup"><span data-stu-id="ad918-114">For instance, SQL Server transaction logs and blob storage deltas travel along this pipe.</span></span> <span data-ttu-id="ad918-115">このデータは既にプライベート ネットワークを使用して送信されていますが、クラス最高の暗号化によってさらに保護されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-115">While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="ad918-116">保管中データの暗号化</span><span class="sxs-lookup"><span data-stu-id="ad918-116">Encryption of data at rest</span></span>

<span data-ttu-id="ad918-117">保管中の暗号化には、ユーザー コンテンツの BitLocker ディスク レベル暗号化と、ファイル単位暗号化が関係しています。</span><span class="sxs-lookup"><span data-stu-id="ad918-117">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="ad918-118">BitLockerは、サービス全体OneDrive for BusinessオンラインSharePoint展開されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-118">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="ad918-119">ファイルごとの暗号化は、OneDrive for Business および SharePoint Online Microsoft 365 マルチテナントテクノロジ上に構築された新しい専用環境にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad918-119">Per-file encryption is also in OneDrive for Business and SharePoint Online in Microsoft 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="ad918-120">BitLocker 暗号化はディスク上のすべてのデータを暗号化し、ファイル単位暗号化の場合にはファイルごとに固有の暗号化キーを含めてさらに細かく暗号化を行えます。</span><span class="sxs-lookup"><span data-stu-id="ad918-120">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file.</span></span> <span data-ttu-id="ad918-121">つまり、各ファイルを更新するたびに独自の暗号化キーを使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-121">Further, every update to every file is encrypted using its own encryption key.</span></span> <span data-ttu-id="ad918-122">暗号化されたコンテンツのキーは、格納される前に、コンテンツとは物理的に別の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-122">Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content.</span></span> <span data-ttu-id="ad918-123">この暗号化の各ステップでは、256 ビット キーによる高度暗号化標準 (Advanced Encryption Standard: AES) が使用され、Federal Information Processing Standard (FIPS) 140-2 に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="ad918-123">Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant.</span></span> <span data-ttu-id="ad918-124">暗号化されたコンテンツは、データセンターにある多数のコンテナーに配布され、各コンテナーでは固有の資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-124">The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials.</span></span> <span data-ttu-id="ad918-125">これらの資格情報はコンテンツまたはコンテンツ キーとは物理的に別の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-125">These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="ad918-126">FIPS 140-2 コンプライアンスの詳細については [、「FIPS 140-2 コンプライアンス」を参照してください](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))。</span><span class="sxs-lookup"><span data-stu-id="ad918-126">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).</span></span>
  
<span data-ttu-id="ad918-127">ファイル レベルでの保管中の暗号化では Blob ストレージを活用し、事実上無制限のストレージ拡張を行ったり、前例のないレベルの保護機能を提供したりできます。</span><span class="sxs-lookup"><span data-stu-id="ad918-127">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection.</span></span> <span data-ttu-id="ad918-128">[オンライン] および [OneDrive for Business] SharePointのすべての顧客コンテンツは、BLOB ストレージに移行されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-128">All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage.</span></span> <span data-ttu-id="ad918-129">データをセキュリティで保護する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad918-129">Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="ad918-p107">すべてのコンテンツが暗号化されます。その場合、複数のキーを使用して暗号化されることもあります。暗号化されたデータはデータセンターで分散されます。格納される各ファイルはサイズに応じて 1 つ以上のチャンクに分けられます。その後、各チャンクは固有のキーを使用して暗号化されます。更新作業も同様に処理されます。つまり、ユーザーによって送信された一連の変更または差分がチャンクに分けられ、それぞれが独自のキーで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-p107">All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="ad918-p108">これらのチャンク ファイル、ファイル セット、更新差分すべては Blob ストア内で Blob として格納されます。これらのファイルはまた、複数の Blob コンテナーでランダムに分散されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-p108">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="ad918-136">コンポーネントからファイルを再アセンブルするために使用される "マップ" は、コンテンツ データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-136">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="ad918-p109">それぞれの Blob コンテナーには、アクセスの種類 (読み取り、書き込み、列挙、削除) ごとに独自の資格情報があります。各資格情報セットはセキュリティが確保されたキー ストアで保管され、定期的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-p109">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="ad918-139">つまり、ファイル単位の保管中の暗号化には以下のように 3 つの異なる種類のストアがあり、それぞれ別の機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="ad918-139">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="ad918-p110">Blob ストアには、コンテンツが暗号化 Blob として格納されます。コンテンツの各チャンクのキーが暗号化されて、コンテンツ データベースに別個に格納されます。コンテンツ自体は、暗号化解除方法に関する糸口を含めずに保持されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-p110">Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="ad918-143">コンテンツ データベースは、SQL Serverデータベースです。</span><span class="sxs-lookup"><span data-stu-id="ad918-143">The Content Database is a SQL Server database.</span></span> <span data-ttu-id="ad918-144">Blob ストアに保管されているコンテンツ Blob すべてを見つけて再構築するために必要なマップと、それらの Blob を暗号化解除するために必要なキーが一緒に保管されます。</span><span class="sxs-lookup"><span data-stu-id="ad918-144">It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="ad918-p112">これら 3 つのコンポーネント (Blob ストア、コンテンツ データベース、キー ストア) はそれぞれ物理的に別の場所にあります。いずれかのコンポーネントに保管されている情報は、それ自体では使用できません。それにより、これまでにないレベルのセキュリティが実現します。これら 3 つのすべてのコンポーネントにアクセスしない限りは、チャンクのカギを取得すること、キーを暗号化解除して使用できるようにすること、キーと対応するチャンクを関連付けること、チャンクを暗号化解除すること、構成チャンクからドキュメントを再構築することはいずれも不可能です。</span><span class="sxs-lookup"><span data-stu-id="ad918-p112">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>