---
title: Office 365 エンドポイント
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
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
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: この記事では、ドイツで 365 を使用しているお客様Officeエンドポイントについて説明します。
hideEdit: true
ms.openlocfilehash: deabb590376a46580a2cd9d4a5dc498aacc3c5ef
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597048"
---
# <a name="office-365-germany-endpoints"></a>Office 365 Germany のエンドポイント

 *適用対象: Office 365 Admin*

Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは、ドイツの **365** プランのみを使用しているOfficeに到達できる必要があります。
  
 **Office 365 エンドポイント:** [(GCC を含む) 世界](urls-and-ip-address-ranges.md)  | [21Vianet が運営する Office 365](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 ドイツ* |  [Office 365 米国政府機関向け DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 米国政府 GCC 高](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**最終更新日:** 12/01/2020 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [サブスクリプション](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**ダウンロード:** 1 つの [JSON 形式](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)リスト内のすべての必須およびオプションの宛先。  <br/> |

[365 Officeの](managing-office-365-endpoints.md)管理から始め、このデータを使用してネットワーク接続を管理するための推奨事項を理解します。 エンドポイント データは、毎月の初めに必要に応じて更新され、アクティブの 30 日前に新しい IP アドレスと URL が公開されます。 これにより、新しい接続が必要になる前に、まだ自動更新プログラムを持っていないお客様がプロセスを完了できます。 サポートエスカレーション、セキュリティ インシデント、その他の即時運用要件に対応するために必要な場合は、月の間にエンドポイントが更新される場合もあります。 いつでも変更ログサブスクリプション [を参照できます](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。

以下のこのページに示すデータはすべて、REST ベースの Web サービスから生成されます。 スクリプトまたはネットワーク デバイスを使用してこのデータにアクセスする場合は、Web サービスに直接 [アクセスする必要](microsoft-365-ip-web-service.md) があります。

以下のエンドポイント データは、ユーザーのコンピューターから 365 への接続の要件Office示しています。 Microsoft から顧客ネットワークへのネットワーク接続 (ハイブリッドまたは受信ネットワーク接続とも呼ばれる) は含めではありません。

エンドポイントは 4 つのサービス領域にグループ分けされます。最初の 3 つのサービス領域は個別に接続の選択ができます。4 番目のサービス領域は共通の依存関係 ("Microsoft 365 Common および Office Online" と呼ばれる) で、常時ネットワーク接続されている必要があります。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイントのセットが「最適化」、「許可」または「既定」のどれに分類されているかを示します。これらのカテゴリとその管理ガイダンスについては、[https://aka.ms/pnc](https://aka.ms/pnc) を参照してください。この列には、ネットワーク接続に必要なエンドポイントのセットが表示されます。ネットワーク接続が必要ないエンドポイントのセットの場合、このコラムには、エンドポイントのセットがブロックされた場合に使えなくなる機能に関する注意書きが書かれます。サービス領域全体を除外する場合は、ネットワーク接続が必要と記載されているエンドポイントのセットの接続は不要です。

- **ER**: 「**はい**」とある場合、エンドポイントのセットは Office 365 のルート プレフィックスを使用して Azure ExpressRoute でサポートされています。表示されているルートのプレフィックスを含む BGP コミュニティは、記載されているサービス領域と整合します。ER に「**いいえ**」とある場合、ExpressRoute はそのエンドポイントのセットでサポートされていないことを意味します。ただし、ER に「**いいえ**」とある場合でも、アドバタイズされたルートが 1 つも無いとは判断しないようにします。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。
 
- **ポート**: アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

