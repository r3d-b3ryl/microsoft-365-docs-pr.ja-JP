---
title: Office 365 米国政府機関の高 GCC エンドポイント
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
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
description: この記事では、米国政府機関の高いプランを使用しているOffice 365エンドポイントGCC見つける予定です。
hideEdit: true
ms.openlocfilehash: c29ea7c69528b734f3083138501224e071848c1d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59165246"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365 米国政府機関の高 GCC エンドポイント

*適用対象: Office 365 Admin*

Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、米国政府機関および高Office 365プランのみを使用しているGCCアクセスできる必要があります。
  
 **Office 365 エンドポイント:** [](urls-and-ip-address-ranges.md) \| [21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [](microsoft-365-germany-endpoints.md) \| [](microsoft-365-u-s-government-dod-endpoints.md) \|  Office 365 ドイツ Office 365 が運営するワールドワイド (GCC を含 Office 365む) Office 365 米国政府機関 GCC High

<br>

****

|備考|ダウンロード|
|---|---|
|**最終更新日:** 05/28/2021 - ![ RSS。](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [ログ サブスクリプションの変更](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**ダウンロード:** JSON 形式の完全な [リスト](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

 [Office 365 エンドポイントの管理](managing-office-365-endpoints.md)から始めて、このデータを使用してネットワーク接続を管理するための推奨事項を理解してください。 エンドポイントのデータは、毎月初めに必要に応じて更新され、アクティブになる 30 日前に新しい IP アドレスと URL が公開されます。 これにより、新しい接続が必要になる前に、まだ自動更新プログラムを持っていないお客様がプロセスを完了できます。 サポートの拡大、セキュリティ上の問題、その他の緊急な運用要件に対処する為に必要な場合にも、その月の間にエンドポイントを更新する可能性があります。 以下のこのページに示されているデータはすべて、REST ベースの Web サービスから生成されています。 スクリプトまたはネットワーク デバイスを使用してこのデータにアクセスしている場合は、[Web サービス](microsoft-365-ip-web-service.md)に直接アクセスする必要があります。

次のエンドポイント データは、ユーザーのコンピューターを Office 365 に接続するための要件の一覧です。Microsoft からお客様のネットワークへの接続 (“ハイブリッド ネットワーク接続” や ”受信ネットワーク接続” と呼ばれる場合があります) は含まれません。

エンドポイントは 4 つのサービス領域にグループ分けされます。最初の 3 つのサービス領域は個別に接続の選択ができます。4 番目のサービス領域は共通の依存関係 ("Microsoft 365 Common および Office Online" と呼ばれる) で、常時ネットワーク接続されている必要があります。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイントのセットが「最適化」、「許可」または「既定」のどれに分類されているかを示します。これらのカテゴリとその管理ガイダンスについては、[https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md) を参照してください。この列には、ネットワーク接続に必要なエンドポイントのセットが表示されます。ネットワーク接続が必要ないエンドポイントのセットの場合、このコラムには、エンドポイントのセットがブロックされた場合に使えなくなる機能に関する注意書きが書かれます。サービス領域全体を除外する場合は、ネットワーク接続が必要と記載されているエンドポイントのセットの接続は不要です。

- **ER**: エンドポイント セットが **Azure** ExpressRoute でサポートされている場合は、ルート プレフィックスOffice 365です。 表示されるルート プレフィックスを含む BGP コミュニティは、一覧表示されているサービス エリアに合わせて配置されます。 ER が **No の場合**、このエンドポイント セットでは ExpressRoute はサポートされません。 ただし、ER が No であるエンドポイント セットに対してアドバタイズされるルートは含めずに使用する **必要があります**。 Azure AD Connectを使用する場合は、「特別な考慮事項[](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government)」セクションを参照して、適切な Azure AD Connectしてください。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。

- **ポート**: アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。

[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

この表に関するメモ :

- セキュリティとコンプライアンス センター (SCC) は、Azure ExpressRoute のサポートを提供Office 365。 レポート、監査、監査、統合 DLP、データ ガバナンスなど、SCC を通じて公開Advanced eDiscovery機能も同様です。 PST インポートと電子情報開示のエクスポートという 2 つの特定の機能は、現在、Azure Blob Storage への依存により、Office 365 ルート フィルターのみを使用する Azure ExpressRoute をサポートStorage。 これらの機能を使用するには、サポート可能な Azure 接続オプション (インターネット接続や Azure パブリック ルート フィルターを使用した Azure ExpressRoute など) を使用して、Azure Blob Storage への個別の接続が必要です。 これらの両方の機能に対するこのような接続の確立を評価する必要があります。 Office 365情報保護チームは、この制限を認識し、これらの両方の機能の Office 365 ルート フィルターに限定される Office 365 の Azure ExpressRoute のサポートを積極的に提供しています。

- 一覧に表示されない、Microsoft 365 Apps for enterpriseアプリケーションを起動してドキュメントを編集するためにユーザーに必要Microsoft 365 Apps for enterpriseオプションのエンドポイントが追加されています。 オプションのエンドポイントは Microsoft データセンターでホストされ、顧客データの処理、送信、または保存は行ないます。 これらのエンドポイントへのユーザー接続は、既定のインターネット出力境界に転送することをお勧めします。
