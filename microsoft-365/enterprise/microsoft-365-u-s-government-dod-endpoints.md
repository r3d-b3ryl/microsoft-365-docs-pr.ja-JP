---
title: Office 365 US Government DOD エンドポイント
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、米国政府機関向け 365 Officeプランのみを使用しているお客様がアクセスできる必要があります。
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 39f48b152f46ab12b1e96cf8869a0fd8050d1c35
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751641"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 U.S. Government DoD エンドポイント

*適用対象: Office 365 Admin*

 Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、米国政府機関向け 365 Officeプランのみを使用しているお客様がアクセスできる必要があります。
  
 **Office 365 エンドポイント:** [(GCC を含む) 世界](urls-and-ip-address-ranges.md) | [21Vianet が運営する Office 365](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 ドイツ](microsoft-365-germany-endpoints.md) |  *Office 365 米国政府機関向け DoD* | [Office 365 米国政府 GCC 高](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Last updated:** 01/04/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**ダウンロード:** JSON 形式の完全な [リスト](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 まず [、Office 365](managing-office-365-endpoints.md) エンドポイントの管理から始め、このデータを使用してネットワーク接続を管理するための推奨事項を理解します。 エンドポイント データは、毎月の初めに更新され、アクティブにされる 30 日前に新しい IP アドレスと URL が公開されます。 これにより、新しい接続が必要になる前に、自動化された更新プログラムをまだお持ちではないお客様がプロセスを完了できます。 サポートのエスカレーション、セキュリティ インシデント、その他の即時運用要件に対応する必要がある場合は、エンドポイントが月中に更新される場合もあります。 以下のページに示すデータはすべて、REST ベースの Web サービスから生成されます。 スクリプトまたはネットワーク デバイスを使用してこのデータにアクセスする場合は、Web サービスに直接 [アクセスする必要](microsoft-365-ip-web-service.md) があります。

以下のエンドポイント データは、ユーザーのコンピューターから 365 への接続の要件Officeします。 Microsoft から顧客のネットワークへのネットワーク接続 (ハイブリッドまたは受信ネットワーク接続とも呼ばれる) は含されません。 詳細については [、Web サービスに含まれていないその他のエンドポイントを参照してください](additional-office365-ip-addresses-and-urls.md)。 

エンドポイントは 4 つのサービス領域にグループ分けされます。最初の 3 つのサービス領域は個別に接続の選択ができます。4 番目のサービス領域は共通の依存関係 ("Microsoft 365 Common および Office Online" と呼ばれる) で、常時ネットワーク接続されている必要があります。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイントのセットが「最適化」、「許可」または「既定」のどれに分類されているかを示します。これらのカテゴリとその管理ガイダンスについては、[https://aka.ms/pnc](https://aka.ms/pnc) を参照してください。この列には、ネットワーク接続に必要なエンドポイントのセットが表示されます。ネットワーク接続が必要ないエンドポイントのセットの場合、このコラムには、エンドポイントのセットがブロックされた場合に使えなくなる機能に関する注意書きが書かれます。サービス領域全体を除外する場合は、ネットワーク接続が必要と記載されているエンドポイントのセットの接続は不要です。

- **ER**: エンドポイント セットが **365** ルート プレフィックスを持つ Azure ExpressRoute でサポートOfficeはい。 表示されるルート プレフィックスを含む BGP コミュニティは、一覧表示されているサービスエリアに合わせて調整されます。 ER が **No の場合**、このエンドポイント セットでは ExpressRoute がサポートされません。 ただし、ER が No であるエンドポイント セットに対してアドバタイズされるルートは想定 **できません**。 Azure AD Connect を使用する予定の場合は、[](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government)特別な考慮事項のセクションを読んで、Azure AD Connect の適切な構成を確認してください。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。
 
- **ポート**: アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
この表に関するメモ :

- セキュリティ/コンプライアンス センター (SCC) は、Azure ExpressRoute for Office 365 をサポートします。 レポート、監査、高度な電子情報開示、統合 DLP、データ ガバナンスなど、SCC によって公開される多くの機能にも同じことが当てはまる。 現在、PST インポートと電子情報開示のエクスポートという 2 つの特定の機能は、Azure Blob Storage への依存のため、Office 365 ルート フィルターのみを使用する Azure ExpressRoute をサポートしていない。 これらの機能を利用するには、インターネット接続や Azure パブリック ルート フィルターを使用した Azure ExpressRoute など、サポート可能な Azure 接続オプションを使用して、Azure Blob Storage に個別に接続する必要があります。 これらの両方の機能について、このような接続の確立を評価する必要があります。 Office 365 Information Protection チームは、この制限を認識し、両方の機能に対して Office 365 ルート フィルターに制限された Office 365 向け Azure ExpressRoute のサポートを積極的に提供するために取り組み中です。

- 一覧に記載されていない Microsoft 365 Apps for enterprise の追加のオプション エンドポイントがあります。ユーザーが Microsoft 365 Apps for enterprise アプリケーションを起動してドキュメントを編集する必要はありません。 オプションのエンドポイントは、Microsoft データセンターでホストされ、顧客データの処理、送信、または保存は行われます。 これらのエンドポイントへのユーザー接続は、既定のインターネット出口境界に転送することをお勧めします。
