---
title: Microsoft 365Connectivity Optics
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: この記事では、Connectivity Optics のMicrosoft 365説明します。
ms.openlocfilehash: 952990a63d4ad064b2027c6f2364e8082342fa34
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53455979"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365Connectivity Optics

このドキュメントでは、Microsoft が通常お客様のデバイスから収集する接続光学の一部について説明し、Microsoft がこのようなデータを使用してサービス配信を分析および最適化し、可能な限り最高のエンド ユーザー エクスペリエンスを評価および確認する方法について説明します。

接続光学は、一般に Microsoft アプリケーションから収集されます。これは、エンド ユーザー デバイスにインストールされている場合や、ブラウザーからアクセスされる場合があります。 Microsoft 365 サービス内のオプションのデータ収集とは異なり、ここで説明する接続光学の多くは、Microsoft が可用性とパフォーマンスに関する顧客へのコミットメントを満たすために不可欠です。 これらの光学機能を使用すると、Microsoft はエンド ユーザーと Microsoft サービス エンドポイント間の接続パスの問題を迅速に検出して対応できます。 これらの光学機器の一部は、Microsoft 365 管理[センターでネットワーク接続などの機能を有効にするために使用されます](office-365-network-mac-perf-overview.md)。

## <a name="optics-collected-from-microsoft-365-applications"></a>アプリケーションから収集Microsoft 365光学

光学は現在、すべてのデバイスでまれなサンプリングを使用して収集されます。 一般的な問題として、特定のイテレーションで測定される光学および宛先 (サービス エンドポイント) の特定のセットは、サービス要件に基づいて Microsoft によって構成され、サンプリング目的でランダム化されます。
各光学コレクション間隔で、次の測定値の 1 つ以上を測定元としてエンド ユーザー デバイスを使用し、Microsoft 365 サービス エンドポイントを測定先として収集できます。

| 測定 | 説明 |
| --- | --- |
| 遅延 | HTTP 経由で小さなファイルを取得するために必要な時間 |
| スループット | HTTP 経由で大きなファイルを取得するために必要な時間 (帯域幅の過剰消費を避けるためにほとんど測定されない) |
| ラウンド トリップ時間 (RTT) | ICMP ping |
| Traceroute | ICMP traceroute |

各測定値は通常、次の項目を含む追加情報に関連付けられる場合があります。

| 項目 | 説明 |
| --- | --- |
| テナント ID | エンド ユーザー デバイスに関連付けられているAzure Active Directoryの一意の識別子。 |
| モニター ID | 測定を実行しているクライアント アプリケーションによって提供される要求 (Outlook、OneDrive など) を生成するアプリケーションの識別子。 |
| 要求 ID | Microsoft が提供する測定構成で指定された測定要求の識別子。 |
| リモート IP | クライアントからサービス エンドポイントへの要求に関連付けられたマスクされたソース IP。測定要求を受信したサーバーによって提供され、Microsoft に表示されるクライアント ソース IP アドレスに基づいて計算されます。 IP アドレスは、IPv4 アドレスの /24 サブネット、または IPv6 アドレスの /48 サブネットにマスクされ、Microsoft が個々のデバイスまたはユーザーを識別できないことを確認します。 |
| フロントエンド | Microsoft 365要求を受け取ったサーバーによって提供されるサービス フロントエンド識別子。 |
| Endpoint | Microsoft 365を受け取ったサーバーによって提供されるサービス エンドポイントの場所を指定します。 |
| 発行者の証明書 | サービス エンドポイントへの接続中に提示される SSL 証明書の "発行された証明書" プロパティ 。これは、サービス エンドポイントに証明書を発行した証明機関を示します。 |
| 証明書の拇印 | サービス エンドポイントへの接続中に提示される SSL 証明書の "証明書拇印" プロパティ 。これは、証明書の一意の一意の識別子です。 |
| 緯度/経度 | エンド ユーザー デバイスの抽象化された緯度と経度。 これは、エンド ユーザー デバイスで Windows Location Service を有効にし、Microsoft 365 管理ポータルでこの情報のコレクションを有効にしている[テナントにのみ収集されます](office-365-network-mac-perf-overview.md#1-enable-windows-location-services)。 |

## <a name="measurement-process"></a>測定プロセス

各エンド ユーザー デバイスは、通常、(インストールされているアプリケーションの) スケジュールに基づいて、またはブラウザー ページの読み込み (Web ベースのアプリケーションの場合) のアクションに基づいて測定を実行します。 測定アクティビティはバックグラウンド操作として実行され、ユーザーのアプリケーション エクスペリエンスには影響を与えいません。 このプロセスの特定の反復に使用される測定の種類と宛先がランダム化される場合、お客様は、通常のアプリケーション接続のためにエンド ユーザー デバイスが行った一般的な要求に似た地域の Microsoft サービス エンドポイントへの要求に気付く場合があります。 さらに、お客様は、ローカル地域の外にある Microsoft サービス エンドポイントへの要求に気付く場合があります。 これらの測定値は、顧客と ISP インフラストラクチャの変更により、Microsoft が要求ルーティング ポリシーを継続的に変更する必要がある場合があるなど、最適なサービス エンドポイントへの顧客要求の最適なルーティングを確保するためによく使用されます。 Microsoft がトラフィックを最適なサービス エンドポイントにルーティングする方法と、Microsoft 365 ネットワーク接続の概要で Microsoft 365 サービスへの接続を最適化する方法についてMicrosoft 365説明[します](microsoft-365-networking-overview.md)。

## <a name="service-endpoints"></a>サービス エンドポイント

これらの測定値の宛先として使用される Microsoft サービス エンドポイントは、公開されている URL と[IP アドレスOffice 365内に含まれる。](urls-and-ip-address-ranges.md) これらの接続光学機器のコレクションでは、追加のサービス エンドポイントへのアクセスは必要ありません。
