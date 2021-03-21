---
title: Office 365 US Government DOD エンドポイント
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/28/2021
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
description: Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、365 米国政府機関の DoD プランOffice使用しているお客様に対して到達可能である必要があります。
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 925ec5940bd6c2ead7f94e162311f65e67afc502
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923980"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 米国政府機関の DoD エンドポイント

*適用対象: Office 365 Admin*

 Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、365 米国政府機関の DoD プランOffice使用しているお客様に対して到達可能である必要があります。
  
 **Office 365 エンドポイント:** [(GCC を含む) 世界](urls-and-ip-address-ranges.md) | [21Vianet が運営する Office 365](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 ドイツ](microsoft-365-germany-endpoints.md) |  *Office 365 米国政府機関向け DoD* | [Office 365 米国政府 GCC 高](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**最終更新日:** 01/28/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [サブスクリプション](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**ダウンロード:** JSON 形式の完全な [リスト](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 [Office 365 エンドポイントの管理](managing-office-365-endpoints.md)から始めて、このデータを使用してネットワーク接続を管理するための推奨事項を理解してください。 エンドポイントのデータは、毎月初めに必要に応じて更新され、アクティブになる 30 日前に新しい IP アドレスと URL が公開されます。 これにより、新しい接続が必要になる前に、まだ自動更新プログラムを持っていないお客様がプロセスを完了できます。 サポートの拡大、セキュリティ上の問題、その他の緊急な運用要件に対処する為に必要な場合にも、その月の間にエンドポイントを更新する可能性があります。 以下のこのページに示されているデータはすべて、REST ベースの Web サービスから生成されています。 スクリプトまたはネットワーク デバイスを使用してこのデータにアクセスしている場合は、[Web サービス](microsoft-365-ip-web-service.md)に直接アクセスする必要があります。

以下のエンドポイント データは、ユーザーのコンピューターから 365 への接続の要件Office示しています。 Microsoft から顧客ネットワークへのネットワーク接続 (ハイブリッドまたは受信ネットワーク接続とも呼ばれる) は含めではありません。 詳細については、「Web サービス [に含まれていない追加のエンドポイント」を参照してください](additional-office365-ip-addresses-and-urls.md)。 

エンドポイントは 4 つのサービス領域にグループ分けされます。最初の 3 つのサービス領域は個別に接続の選択ができます。4 番目のサービス領域は共通の依存関係 ("Microsoft 365 Common および Office Online" と呼ばれる) で、常時ネットワーク接続されている必要があります。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイントのセットが「最適化」、「許可」または「既定」のどれに分類されているかを示します。これらのカテゴリとその管理ガイダンスについては、[https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md) を参照してください。この列には、ネットワーク接続に必要なエンドポイントのセットが表示されます。ネットワーク接続が必要ないエンドポイントのセットの場合、このコラムには、エンドポイントのセットがブロックされた場合に使えなくなる機能に関する注意書きが書かれます。サービス領域全体を除外する場合は、ネットワーク接続が必要と記載されているエンドポイントのセットの接続は不要です。

- **ER**: エンドポイント **セットが** Azure ExpressRoute でサポートされ、365 ルート プレフィックスOfficeはい。 表示されるルート プレフィックスを含む BGP コミュニティは、一覧表示されているサービス エリアに合わせて配置されます。 ER が **No の場合**、このエンドポイント セットでは ExpressRoute はサポートされません。 ただし、ER が No であるエンドポイント セットに対してアドバタイズされるルートは含めずに使用する **必要があります**。 Azure AD Connect を使用する場合は、「特別な[](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government)考慮事項」セクションを参照して、適切な Azure AD Connect 構成を確認してください。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。
 
- **ポート**: アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
この表に関するメモ :

- セキュリティとコンプライアンス センター (SCC) は、Azure ExpressRoute for Office 365 を提供します。 レポート、監査、高度な電子情報開示、統合 DLP、データ ガバナンスなど、SCC を通じて公開される多くの機能にも同様です。 PST インポートと電子情報開示のエクスポートという 2 つの特定の機能は、現在、Azure Blob Storage への依存関係のため、Office 365 ルート フィルターのみを使用する Azure ExpressRoute をサポートしていない。 これらの機能を使用するには、サポート可能な Azure 接続オプション (インターネット接続または Azure パブリック ルート フィルターを使用した Azure ExpressRoute を含む) を使用して、Azure Blob Storage への個別の接続が必要です。 これらの両方の機能に対するこのような接続の確立を評価する必要があります。 Office 365 情報保護チームは、この制限を認識し、これらの両方の機能に対して Office 365 ルート フィルターに限定される Office 365 の Azure ExpressRoute のサポートを積極的に提供しています。

- Microsoft 365 Apps for enterprise 用の追加のオプション エンドポイントは一覧に記載されていないので、ユーザーがエンタープライズ アプリケーション用 Microsoft 365 Apps を起動し、ドキュメントを編集する必要はありません。 オプションのエンドポイントは Microsoft データセンターでホストされ、顧客データの処理、送信、または保存は行ないます。 これらのエンドポイントへのユーザー接続は、既定のインターネット出力境界に転送することをお勧めします。