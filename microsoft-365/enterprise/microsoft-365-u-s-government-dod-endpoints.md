---
title: Office 365米国政府機関の DOD エンドポイント
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/01/2022
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、Office 365米国政府機関の DoD プランのみを使用しているお客様に対して到達可能である必要があります。
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cebd2c7e4ceefa52785c4c21163666d12091fe6c
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66493467"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365米国政府機関の DoD エンドポイント

*適用対象: Office 365 Admin*

Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、Office 365米国政府機関の DoD プランのみを使用しているお客様に対して到達可能である必要があります。
  
**Office 365 エンドポイント:** [世界 (GCC を含む)](urls-and-ip-address-ranges.md) \| [Office 365 21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| *Office 365米国政府機関 DoD* \| [Office 365米国政府機関 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) によって運用されています

<br>
****

|備考|ダウンロード|
|---|---|
|**最終更新日:** 2022 年 6 月 1 日 - ![RSS。](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [変更ログのサブスクリプション](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**ダウンロード:** [JSON 形式](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)の完全な一覧|
|

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)から始めて、このデータを使用してネットワーク接続を管理するための推奨事項を理解してください。 エンドポイントのデータは、毎月初めに必要に応じて更新され、アクティブになる 30 日前に新しい IP アドレスと URL が公開されます。 これにより、自動更新をまだ行っていないお客様は、新しい接続が必要になる前にプロセスを完了できます。 サポートの拡大、セキュリティ上の問題、その他の緊急な運用要件に対処する為に必要な場合にも、その月の間にエンドポイントを更新する可能性があります。 以下のこのページに示されているデータはすべて、REST ベースの Web サービスから生成されています。 スクリプトまたはネットワーク デバイスを使用してこのデータにアクセスする場合は、 [Web サービス](microsoft-365-ip-web-service.md) に直接アクセスする必要があります。

以下のエンドポイント データは、ユーザーのコンピューターから Office 365 への接続の要件を示しています。 これには、Microsoft から顧客ネットワークへのネットワーク接続 (ハイブリッドまたは受信ネットワーク接続とも呼ばれる) は含まれません。 詳細については、「 [Web サービスに含まれていないその他のエンドポイント」を](additional-office365-ip-addresses-and-urls.md)参照してください。

エンドポイントは 4 つのサービス領域にグループ分けされます。最初の 3 つのサービス領域は個別に接続の選択ができます。4 番目のサービス領域は共通の依存関係 ("Microsoft 365 Common および Office Online" と呼ばれる) で、常時ネットワーク接続されている必要があります。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイント セットが "最適化"、"許可"、または "既定値" に分類されているかどうかを示します。 これらのカテゴリと、それらの管理に関するガイダンスについては、以下をご覧 [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md)ください。 この列には、ネットワーク接続に必要なエンドポイント セットも一覧表示されます。 ネットワーク接続を必要としないエンドポイント セットの場合、エンドポイント セットがブロックされた場合に欠落する機能を示すメモをこのフィールドに示します。 サービス領域全体を除外する場合は、必要に応じて一覧表示されているエンドポイント セットに接続は必要ありません。

- **ER**: これは、エンドポイント セットが、Office 365ルート プレフィックスを持つ Azure ExpressRoute でサポートされている場合は **はい** です。 表示されるルート プレフィックスを含む BGP コミュニティは、一覧表示されているサービス領域と一致します。 ER が **No** の場合、これは、このエンドポイント セットで ExpressRoute がサポートされていないことを意味します。 ただし、ER が **No** であるエンドポイント セットのルートがアドバタイズされないと想定しないでください。 Azure AD Connect を使用する予定の場合は、 [特別な考慮事項に関するセクション](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) を参照して、適切な Azure AD Connect 構成を確保してください。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。

- **ポート**: アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。

[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
この表に関するメモ :

- セキュリティとコンプライアンス センター (SCC) は、azure ExpressRoute for Office 365のサポートを提供します。 これは、レポート、監査、電子情報開示 (Premium)、統合 DLP、データ ガバナンスなど、SCC を通じて公開される多くの機能にも当てはまります。 PST インポートと電子情報開示エクスポートという 2 つの特定の機能は、現在、Azure Blob Storageへの依存のため、Office 365 ルート フィルターのみで Azure ExpressRoute をサポートしていません。 これらの機能を使用するには、サポート可能な Azure 接続オプション (インターネット接続や Azure Public ルート フィルターを使用した Azure ExpressRoute など) を使用して、Azure Blob Storageに個別の接続が必要です。 これらの両方の機能に対するこのような接続の確立を評価する必要があります。 Office 365 Information Protection チームは、この制限を認識しており、両方の機能のルート フィルターをOffice 365に限定して、Office 365向けの Azure ExpressRoute のサポートを積極的に行います。

- 一覧に表示されず、ユーザーがアプリケーションMicrosoft 365 Apps for enterprise起動してドキュメントを編集する必要のない、Microsoft 365 Apps for enterprise用の追加のオプション エンドポイントがあります。 省略可能なエンドポイントは Microsoft データセンターでホストされており、顧客データの処理、送信、保存は行いません。 これらのエンドポイントへのユーザー接続は、既定のインターネットエグレス境界に送信することをお勧めします。
