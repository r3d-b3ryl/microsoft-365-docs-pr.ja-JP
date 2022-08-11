---
title: サポート対象 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: API 呼び出しを作成できる、サポートされている特定のMicrosoft Defender for Endpoint エンティティについて説明します。
keywords: apis, サポートされている API, アクター, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度なクエリ, 高度な捜索
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
ms.openlocfilehash: 9b8009af5bd88c1dfd37dc7e8297e3c7e05f1356
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "67280765"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>サポート対象 Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/index.yml)

> [!IMPORTANT]
> 高度なハンティング機能は Defender for Business には含まれません。 [Microsoft Defender for Endpoint プラン 1 とMicrosoft Defender for Businessを比較する方法 2 を](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)参照してください。


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>エンドポイントの URI とバージョン管理

### <a name="endpoint-uri"></a>エンドポイント URI

> サービス ベースの URI は次のとおりです。 [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> クエリベースの OData には、'/api' プレフィックスがあります。 たとえば、アラートを取得するには、GET 要求を送信できます。 [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>バージョン管理

> API はバージョン管理をサポートしています。
>
> 現在のバージョンは **V1.0 です**。
>
> 特定のバージョンを使用するには、次の形式を使用します `https://api.securitycenter.microsoft.com/api/{Version}`。 例: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> バージョン (例: `https://api.securitycenter.microsoft.com/api/alerts`) を指定しない場合は、最新バージョンにアクセスします。

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

API 呼び出しを実行できる個々のサポートされるエンティティと、HTTP 要求値、要求ヘッダー、予想される応答などの詳細について説明します。

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
:---|:---
[**高度なハンティング** メソッド](run-advanced-query-api.md) | API からクエリを実行します。
[**Alert** メソッドとプロパティ](alerts.md) | アラートの取得、アラートの作成、アラートの更新などの \- API 呼び出しを実行します。
[デバイスごとの **評価** のメソッドとプロパティをエクスポートする](get-assessment-methods-properties.md) | API 呼び出しを実行して、セキュリティで保護された構成評価のエクスポート、ソフトウェア インベントリ評価のエクスポート、ソフトウェアの脆弱性評価のエクスポート、差分エクスポート ソフトウェアの脆弱性評価など \- 、デバイスごとに脆弱性評価を収集します。
[**自動調査** の方法とプロパティ](investigation.md) | 調査のコレクションを取得するなど、 \- API 呼び出しを実行します。
[デバイス正常性のメソッドとプロパティをエクスポートする](device-health-api-methods-properties.md) | GET /api/public/avdeviceshealth などの API 呼び出しを実行します。
[**ドメイン** 関連のアラート](get-domain-related-alerts.md) | ドメイン関連デバイスの取得、ドメイン統計などの \- API 呼び出しを実行します。
[**ファイル** のメソッドとプロパティ](files.md) | ファイル情報の取得、ファイル関連のアラート、ファイル関連デバイス、ファイル統計などの \- API 呼び出しを実行します。
[**Indicators メソッド** とプロパティ](ti-indicator.md) | インジケーターの取得、インジケーターの作成、インジケーターの削除などの \- API 呼び出しを実行します。
[**IP** 関連のアラート](get-ip-related-alerts.md) | IP 関連のアラートの取得や IP 統計の取得などの \- API 呼び出しを実行します。
[**コンピューターの** メソッドとプロパティ](machine.md) | デバイスの取得、ID によるデバイスの取得、ログオンユーザーに関する情報、タグの編集などの \- API 呼び出しを実行します。
[**Machine Action の** メソッドとプロパティ](machineaction.md) | 分離、ウイルス対策スキャンの実行などの \- API 呼び出しを実行します。
[**推奨事項** のメソッドとプロパティ](recommendation.md) | ID による推奨事項の取得などの \- API 呼び出しを実行します。
[**修復アクティビティ** のメソッドとプロパティ](get-remediation-methods-properties.md) | すべての修復タスクの取得、公開されたデバイスの修復タスクの取得、ID による 1 つの修復タスクの取得など \- 、API 呼び出しを実行します。
[メソッドとプロパティを **スコア付** けする](score.md) | 公開スコアの取得やデバイスのセキュリティスコアの取得などの \- API 呼び出しを実行します。
[**ソフトウェア** のメソッドとプロパティ](software.md) | ソフトウェアによる脆弱性の一覧表示などの \- API 呼び出しを実行します。
[**ユーザー** のメソッドとプロパティ](user.md) | ユーザー関連のアラートやユーザー関連デバイスの取得などの \- API 呼び出しを実行します。
[**脆弱性の** メソッドとプロパティ](vulnerability.md) | 脆弱性によるデバイスの一覧表示などの \- API 呼び出しを実行します。

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint API](apis-intro.md)

- [Microsoft Defender for Endpoint API リリース ノート](api-release-notes.md)
