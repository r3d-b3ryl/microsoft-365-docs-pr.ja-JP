---
title: サポート対象 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: API 呼び出しを作成できる特定のサポートされている Microsoft Defender for Endpoint エンティティについて説明します。
keywords: apis、サポートされている API、アクター、アラート、デバイス、ユーザー、ドメイン、IP、ファイル、高度なクエリ、高度な検索
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 48cd107e5e2040a8b7d9775d97ab1bd53dfe2534
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167372"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>サポート対象 Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>エンドポイント URI とバージョン管理

### <a name="endpoint-uri"></a>エンドポイント URI

> サービスベース URI は次の値です。 [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> OData に基づくクエリには、'/api' プレフィックスがあります。 たとえば、アラートを取得するには、GET 要求を [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>バージョン管理

> API はバージョン管理をサポートしています。
>
> 現在のバージョンは **V1.0 です**。
>
> 特定のバージョンを使用するには、次の形式を使用します `https://api.securitycenter.microsoft.com/api/{Version}` 。 例: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> 任意のバージョン (例) を指定しない場合 `https://api.securitycenter.microsoft.com/api/alerts` は、最新バージョンにアクセスします。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

API 呼び出しを実行できる個々のサポートされるエンティティと、HTTP 要求値、要求ヘッダー、予期される応答などの詳細について説明します。

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
:---|:---
[高度な追求](run-advanced-query-api.md) | API からクエリを実行します。
[アラート メソッドとプロパティ](alerts.md) | アラートの取得、アラートの作成、アラートの更新などの API \- 呼び出しを実行します。
[デバイスごとの評価方法とプロパティのエクスポート](get-assessment-methods-properties.md) | API 呼び出しを実行して、安全な構成評価のエクスポート、ソフトウェア インベントリ評価のエクスポート、ソフトウェアの脆弱性評価のエクスポート、デルタ エクスポート ソフトウェアの脆弱性評価など、デバイスごとに脆弱性評価を収集します。 \-
[自動調査の方法とプロパティ](investigation.md) | 調査のコレクションを取得する \- などの API 呼び出しを実行します。
[ドメイン関連のアラートを取得する](get-domain-related-alerts.md) | ドメイン関連デバイスの取得、ドメイン統計などの API 呼び出 \- しを実行します。
[ファイル メソッドとプロパティ](files.md) | ファイル情報の取得、ファイル関連の通知、ファイル関連デバイス、ファイル統計などの API 呼び出し \- を実行します。
[インジケーター メソッドとプロパティ](ti-indicator.md) | インジケーターの取得、インジケーターの作成、インジケーターの削除などの API \- 呼び出しを実行します。
[IP 関連のアラートを取得する](get-ip-related-alerts.md) | IP 関連のアラートの取得や IP 統計情報の取得などの \- API 呼び出しを実行します。
[マシン メソッドとプロパティ](machine.md) | デバイスの取得、ID によるデバイスの取得、ログオンしているユーザーに関する情報、タグの編集などの API 呼び出 \- しを実行します。
[マシン アクション メソッドとプロパティ](machineaction.md) | 分離、ウイルス対策スキャンの実行などの API 呼び出し \- を実行します。
[推奨メソッドとプロパティ](recommendation.md) | ID による推奨事項の取得などの \- API 呼び出しを実行します。
[修復アクティビティのメソッドとプロパティ](get-remediation-methods-properties.md) | すべての修復タスクの取得、公開されたデバイス修復タスクの取得、ID による 1 つの修復タスクの取得などの API \- 呼び出しを実行します。
[スコア メソッドとプロパティ](score.md) | 露出スコアの取得やデバイス \- のセキュリティで保護されたスコアの取得などの API 呼び出しを実行します。
[ソフトウェア メソッドとプロパティ](software.md) | ソフトウェアによるリストの脆弱性などの API \- 呼び出しを実行します。
[ユーザー メソッド](user.md) | ユーザー関連の通知やユーザー関連 \- デバイスの取得などの API 呼び出しを実行します。
[脆弱性メソッドとプロパティ](vulnerability.md) | 脆弱性によるリスト デバイスなどの API \- 呼び出しを実行します。

## <a name="see-also"></a>関連項目

- [エンドポイント API 用 Microsoft Defender](apis-intro.md)

- [Microsoft Defender for Endpoint API リリース ノート](api-release-notes.md)
