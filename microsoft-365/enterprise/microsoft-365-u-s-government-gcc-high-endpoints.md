---
title: Office 365 米国政府機関 GCC High エンドポイント
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
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: この記事では、365 米国政府機関 GCC High プランを使用しているOfficeに到達可能なエンドポイントについて説明します。
hideEdit: true
ms.openlocfilehash: 4f7e1f8e6a0cc631e5df8302694ed96663a20c53
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50596934"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365 米国政府機関 GCC High エンドポイント

 *適用対象: Office 365 Admin*

Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、365 米国政府機関 GCC High プランOffice使用しているお客様に対して到達可能である必要があります。
  
 **Office 365 エンドポイント:** [(GCC を含む) 世界](urls-and-ip-address-ranges.md) | [21Vianet が運営する Office 365](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 ドイツ](microsoft-365-germany-endpoints.md)  |  [Office 365 米国政府機関向け DoD](microsoft-365-u-s-government-dod-endpoints.md) | *Office 365 米国政府 GCC 高* |
  
|||
|:-----|:-----|
|**最終更新日:** 01/28/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [サブスクリプション](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**ダウンロード:** JSON 形式の完全な [リスト](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 [365 Officeの](managing-office-365-endpoints.md)管理から始め、このデータを使用してネットワーク接続を管理するための推奨事項を理解します。 エンドポイント データは、毎月の初めに必要に応じて更新され、アクティブの 30 日前に新しい IP アドレスと URL が公開されます。 これにより、新しい接続が必要になる前に、まだ自動更新プログラムを持っていないお客様がプロセスを完了できます。 サポートエスカレーション、セキュリティ インシデント、その他の即時運用要件に対応するために必要な場合は、月の間にエンドポイントが更新される場合もあります。 以下のこのページに示すデータはすべて、REST ベースの Web サービスから生成されます。 スクリプトまたはネットワーク デバイスを使用してこのデータにアクセスする場合は、Web サービスに直接 [アクセスする必要](microsoft-365-ip-web-service.md) があります。

次のエンドポイント データは、ユーザーのコンピューターを Office 365 に接続するための要件の一覧です。Microsoft からお客様のネットワークへの接続 (“ハイブリッド ネットワーク接続” や ”受信ネットワーク接続” と呼ばれる場合があります) は含まれません。

エンドポイントは 4 つのサービス領域にグループ分けされます。最初の 3 つのサービス領域は個別に接続の選択ができます。4 番目のサービス領域は共通の依存関係 ("Microsoft 365 Common および Office Online" と呼ばれる) で、常時ネットワーク接続されている必要があります。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイントのセットが「最適化」、「許可」または「既定」のどれに分類されているかを示します。これらのカテゴリとその管理ガイダンスについては、[https://aka.ms/pnc](https://aka.ms/pnc) を参照してください。この列には、ネットワーク接続に必要なエンドポイントのセットが表示されます。ネットワーク接続が必要ないエンドポイントのセットの場合、このコラムには、エンドポイントのセットがブロックされた場合に使えなくなる機能に関する注意書きが書かれます。サービス領域全体を除外する場合は、ネットワーク接続が必要と記載されているエンドポイントのセットの接続は不要です。

- **ER**: エンドポイント **セットが** Azure ExpressRoute でサポートされ、365 ルート プレフィックスOfficeはい。 表示されるルート プレフィックスを含む BGP コミュニティは、一覧表示されているサービス エリアに合わせて配置されます。 ER が **No の場合**、このエンドポイント セットでは ExpressRoute はサポートされません。 ただし、ER が No であるエンドポイント セットに対してアドバタイズされるルートは含めずに使用する **必要があります**。 Azure AD Connect を使用する場合は、「特別な[](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government)考慮事項」セクションを参照して、適切な Azure AD Connect 構成を確認してください。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。
 
- **ポート**: アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

この表に関するメモ :

- セキュリティとコンプライアンス センター (SCC) は、Azure ExpressRoute for Office 365 を提供します。 レポート、監査、高度な電子情報開示、統合 DLP、データ ガバナンスなど、SCC を通じて公開される多くの機能にも同様です。 PST インポートと電子情報開示のエクスポートという 2 つの特定の機能は、現在、Azure Blob Storage への依存関係のため、Office 365 ルート フィルターのみを使用する Azure ExpressRoute をサポートしていない。 これらの機能を使用するには、サポート可能な Azure 接続オプション (インターネット接続または Azure パブリック ルート フィルターを使用した Azure ExpressRoute を含む) を使用して、Azure Blob Storage への個別の接続が必要です。 これらの両方の機能に対するこのような接続の確立を評価する必要があります。 Office 365 情報保護チームは、この制限を認識し、これらの両方の機能に対して Office 365 ルート フィルターに限定される Office 365 の Azure ExpressRoute のサポートを積極的に提供しています。

- Microsoft 365 Apps for enterprise 用の追加のオプション エンドポイントは一覧に記載されていないので、ユーザーがエンタープライズ アプリケーション用 Microsoft 365 Apps を起動し、ドキュメントを編集する必要はありません。 オプションのエンドポイントは Microsoft データセンターでホストされ、顧客データの処理、送信、または保存は行ないます。 これらのエンドポイントへのユーザー接続は、既定のインターネット出力境界に転送することをお勧めします。

