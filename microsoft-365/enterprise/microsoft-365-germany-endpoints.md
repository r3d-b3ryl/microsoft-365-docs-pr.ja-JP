---
title: Office 365 エンドポイント
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
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: この記事では、ドイツの Office 365 を使用しているお客様が到達可能なエンドポイントについて説明します。
hideEdit: true
ms.openlocfilehash: 767c7dd570ac03ae1ceb784b4917ee816837530a
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751629"
---
# <a name="office-365-germany-endpoints"></a>Office 365 Germany のエンドポイント

 *適用対象: Office 365 Admin*

Office 365 にはインターネットへの接続が必要です。 以下のエンドポイントは **、365 Germany** プランを使用しているOffice到達可能である必要があります。
  
 **Office 365 エンドポイント:** [(GCC を含む) 世界](urls-and-ip-address-ranges.md)  | [21Vianet が運営する Office 365](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 ドイツ* |  [Office 365 米国政府機関向け DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 米国政府 GCC 高](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**Last updated:** 01/04/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**ダウンロード:** 1 つの [JSON 形式](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)リスト内のすべての必須およびオプションの宛先。  <br/> |

まず [、Office 365](managing-office-365-endpoints.md) エンドポイントの管理から始め、このデータを使用してネットワーク接続を管理するための推奨事項を理解します。 エンドポイント データは、毎月の初めに更新され、アクティブにされる 30 日前に新しい IP アドレスと URL が公開されます。 これにより、新しい接続が必要になる前に、自動化された更新プログラムをまだお持ちではないお客様がプロセスを完了できます。 サポートのエスカレーション、セキュリティ インシデント、その他の即時運用要件に対応する必要がある場合は、エンドポイントが月中に更新される場合もあります。 いつでも変更ログのサブスクリプション [を参照できます](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。

以下のページに示すデータはすべて、REST ベースの Web サービスから生成されます。 スクリプトまたはネットワーク デバイスを使用してこのデータにアクセスする場合は、Web サービスに直接 [アクセスする必要](microsoft-365-ip-web-service.md) があります。

以下のエンドポイント データは、ユーザーのコンピューターから 365 への接続の要件Officeします。 Microsoft から顧客のネットワークへのネットワーク接続 (ハイブリッドまたは受信ネットワーク接続とも呼ばれる) は含されません。

エンドポイントは 4 つのサービス領域にグループ分けされます。最初の 3 つのサービス領域は個別に接続の選択ができます。4 番目のサービス領域は共通の依存関係 ("Microsoft 365 Common および Office Online" と呼ばれる) で、常時ネットワーク接続されている必要があります。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイントのセットが「最適化」、「許可」または「既定」のどれに分類されているかを示します。これらのカテゴリとその管理ガイダンスについては、[https://aka.ms/pnc](https://aka.ms/pnc) を参照してください。この列には、ネットワーク接続に必要なエンドポイントのセットが表示されます。ネットワーク接続が必要ないエンドポイントのセットの場合、このコラムには、エンドポイントのセットがブロックされた場合に使えなくなる機能に関する注意書きが書かれます。サービス領域全体を除外する場合は、ネットワーク接続が必要と記載されているエンドポイントのセットの接続は不要です。

- **ER**: 「**はい**」とある場合、エンドポイントのセットは Office 365 のルート プレフィックスを使用して Azure ExpressRoute でサポートされています。表示されているルートのプレフィックスを含む BGP コミュニティは、記載されているサービス領域と整合します。ER に「**いいえ**」とある場合、ExpressRoute はそのエンドポイントのセットでサポートされていないことを意味します。ただし、ER に「**いいえ**」とある場合でも、アドバタイズされたルートが 1 つも無いとは判断しないようにします。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。
 
- **ポート**: アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

