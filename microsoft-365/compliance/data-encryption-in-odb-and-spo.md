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
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business および SharePoint Online におけるデータ暗号化

OneDrive for Business および SharePoint Online におけるデータセキュリティの暗号化の基本要素について説明します。
  
## <a name="security-and-data-encryption-in-office-365"></a>Office 365 のセキュリティとデータ暗号化

Microsoft 365 は、高度なセキュリティで保護された環境で、物理データセンターのセキュリティ、ネットワークセキュリティ、アクセスセキュリティ、アプリケーションセキュリティ、およびデータセキュリティがあります。 この記事では特に、OneDrive for Business および SharePoint Online のデータセキュリティの、送信中およびインプレース暗号化側に焦点を当てます。
  
データの暗号化の仕組みについて、次のビデオをご覧ください。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>転送中データの暗号化

OneDrive for Business と SharePoint Online では、データを入力してデータセンターを終了する2つのシナリオがあります。
  
- **クライアントとサーバーとの通信**インターネット経由での OneDrive for business への通信では、SSL/TLS 接続が使用されます。 すべての SSL 接続は、2048ビットのキーを使用して確立されます。

- **データセンター間のデータ移動**データセンター間でデータを移動する主な理由は、geo レプリケーションを使用して障害復旧を可能にすることです。 たとえば、SQL Server のトランザクションログと blob ストレージのデルタは、このパイプに沿って移動します。 このデータは、プライベートネットワークを使用して既に送信されていますが、クラス最高の暗号化を使用してさらに保護されています。 

## <a name="encryption-of-data-at-rest"></a>保管中データの暗号化

保管中の暗号化には、ユーザー コンテンツの BitLocker ディスク レベル暗号化と、ファイル単位暗号化が関係しています。
  
BitLocker は、OneDrive for business と SharePoint Online のサービス全体に展開されます。 また、ファイルごとの暗号化は、Microsoft 365 マルチテナントと、マルチテナントテクノロジに基づいて構築された新しい専用環境の OneDrive for Business および SharePoint Online にも含まれています。
  
BitLocker 暗号化はディスク上のすべてのデータを暗号化し、ファイル単位暗号化の場合にはファイルごとに固有の暗号化キーを含めてさらに細かく暗号化を行えます。 つまり、各ファイルを更新するたびに独自の暗号化キーを使用して暗号化されます。 保存される前に、暗号化されたコンテンツに対するキーがコンテンツとは物理的に離れた場所に保存されます。 この暗号化の各ステップでは、256 ビット キーによる高度暗号化標準 (Advanced Encryption Standard: AES) が使用され、Federal Information Processing Standard (FIPS) 140-2 に準拠しています。 暗号化されたコンテンツは、データセンターにある多数のコンテナーに配布され、各コンテナーでは固有の資格情報が使用されます。 これらの資格情報はコンテンツまたはコンテンツ キーとは物理的に別の場所に格納されます。
  
FIPS 140-2 準拠の詳細については、「 [fips 140-2 コンプライアンス](https://go.microsoft.com/fwlink/?LinkId=517625)」を参照してください。
  
ファイル レベルでの保管中の暗号化では Blob ストレージを活用し、事実上無制限のストレージ拡張を行ったり、前例のないレベルの保護機能を提供したりできます。 OneDrive for Business と SharePoint Online のすべてのお客様のコンテンツは blob ストレージに移行されます。 データのセキュリティ保護の方法は次のとおりです。
  
1. All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.

2. All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.

3. コンポーネントからファイルを再構築するために使用される "マップ" は、コンテンツデータベースに格納されます。

4. Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.

つまり、ファイル単位の保管中の暗号化には以下のように 3 つの異なる種類のストアがあり、それぞれ別の機能を持っています。
  
- Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.

- コンテンツデータベースは SQL Server データベースです。 Blob ストアに保管されているコンテンツ Blob すべてを見つけて再構築するために必要なマップと、それらの Blob を暗号化解除するために必要なキーが一緒に保管されます。

Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.
