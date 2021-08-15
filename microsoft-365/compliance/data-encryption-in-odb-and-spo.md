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
ms.openlocfilehash: a7dfbe142e065ef1afcf21c7652b08a0f1277e855b6b3b40af6b6e70a3745e65
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53860813"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business および SharePoint Online におけるデータ暗号化

オンラインおよびオンラインでのデータ セキュリティの暗号化の基本的なOneDrive for BusinessについてSharePointします。
  
## <a name="security-and-data-encryption-in-office-365"></a>セキュリティとデータの暗号化 (Office 365

Microsoft 365は、物理データ センター のセキュリティ、ネットワーク セキュリティ、アクセス セキュリティ、アプリケーション セキュリティ、データ セキュリティなど、複数の層で広範な保護を提供する高度にセキュリティの高い環境です。 この記事では、オンラインおよびオンラインのデータ セキュリティの転送中および保存時の暗号化OneDrive for BusinessにSharePointします。
  
データの暗号化の仕組みについて、次のビデオをご覧ください。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>転送中データの暗号化

オンラインOneDrive for Businessおよび SharePointでは、データがデータセンターに入り、データセンターを終了する 2 つのシナリオがあります。
  
- **サーバーとのクライアント通信** インターネット上OneDrive for Business通信では、SSL/TLS 接続が使用されます。 すべての SSL 接続は、2048 ビット キーを使用して確立されます。

- **データセンター間のデータ移動** データセンター間でデータを移動する主な理由は、障害復旧を有効にする geo レプリケーションです。 たとえば、トランザクション ログSQL Server BLOB ストレージデルタは、このパイプに沿って移動します。 このデータは既にプライベート ネットワークを使用して送信されていますが、クラス最高の暗号化によってさらに保護されます。 

## <a name="encryption-of-data-at-rest"></a>保管中データの暗号化

保管中の暗号化には、ユーザー コンテンツの BitLocker ディスク レベル暗号化と、ファイル単位暗号化が関係しています。
  
BitLocker は、サービス全体OneDrive for BusinessオンラインSharePoint展開されます。 ファイルごとの暗号化は、OneDrive for Business および SharePoint Online Microsoft 365 マルチテナントテクノロジ上に構築された新しい専用環境にも含まれます。
  
BitLocker 暗号化はディスク上のすべてのデータを暗号化し、ファイル単位暗号化の場合にはファイルごとに固有の暗号化キーを含めてさらに細かく暗号化を行えます。 つまり、各ファイルを更新するたびに独自の暗号化キーを使用して暗号化されます。 暗号化されたコンテンツのキーは、格納される前に、コンテンツとは物理的に別の場所に格納されます。 この暗号化の各ステップでは、256 ビット キーによる高度暗号化標準 (Advanced Encryption Standard: AES) が使用され、Federal Information Processing Standard (FIPS) 140-2 に準拠しています。 暗号化されたコンテンツは、データセンターにある多数のコンテナーに配布され、各コンテナーでは固有の資格情報が使用されます。 これらの資格情報はコンテンツまたはコンテンツ キーとは物理的に別の場所に格納されます。
  
FIPS 140-2 コンプライアンスの詳細については [、「FIPS 140-2 コンプライアンス」を参照してください](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))。
  
ファイル レベルでの保管中の暗号化では Blob ストレージを活用し、事実上無制限のストレージ拡張を行ったり、前例のないレベルの保護機能を提供したりできます。 [オンライン] および [OneDrive for Business] SharePointのすべての顧客コンテンツは、BLOB ストレージに移行されます。 データをセキュリティで保護する方法を次に示します。
  
1. すべてのコンテンツが暗号化されます。その場合、複数のキーを使用して暗号化されることもあります。暗号化されたデータはデータセンターで分散されます。格納される各ファイルはサイズに応じて 1 つ以上のチャンクに分けられます。その後、各チャンクは固有のキーを使用して暗号化されます。更新作業も同様に処理されます。つまり、ユーザーによって送信された一連の変更または差分がチャンクに分けられ、それぞれが独自のキーで暗号化されます。

2. これらのチャンク ファイル、ファイル セット、更新差分すべては Blob ストア内で Blob として格納されます。これらのファイルはまた、複数の Blob コンテナーでランダムに分散されます。

3. コンポーネントからファイルを再アセンブルするために使用される "マップ" は、コンテンツ データベースに格納されます。

4. それぞれの Blob コンテナーには、アクセスの種類 (読み取り、書き込み、列挙、削除) ごとに独自の資格情報があります。各資格情報セットはセキュリティが確保されたキー ストアで保管され、定期的に更新されます。

つまり、ファイル単位の保管中の暗号化には以下のように 3 つの異なる種類のストアがあり、それぞれ別の機能を持っています。
  
- Blob ストアには、コンテンツが暗号化 Blob として格納されます。コンテンツの各チャンクのキーが暗号化されて、コンテンツ データベースに別個に格納されます。コンテンツ自体は、暗号化解除方法に関する糸口を含めずに保持されます。

- コンテンツ データベースは、SQL Serverデータベースです。 Blob ストアに保管されているコンテンツ Blob すべてを見つけて再構築するために必要なマップと、それらの Blob を暗号化解除するために必要なキーが一緒に保管されます。

これら 3 つのコンポーネント (Blob ストア、コンテンツ データベース、キー ストア) はそれぞれ物理的に別の場所にあります。いずれかのコンポーネントに保管されている情報は、それ自体では使用できません。それにより、これまでにないレベルのセキュリティが実現します。これら 3 つのすべてのコンポーネントにアクセスしない限りは、チャンクのカギを取得すること、キーを暗号化解除して使用できるようにすること、キーと対応するチャンクを関連付けること、チャンクを暗号化解除すること、構成チャンクからドキュメントを再構築することはいずれも不可能です。