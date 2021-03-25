---
title: サポートされている Microsoft Defender for Endpoint API
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198326"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>サポートされている Microsoft Defender for Endpoint API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>エンドポイント URI とバージョン管理

### <a name="endpoint-uri"></a>エンドポイント URI:            

> サービスベース URI は次の値です。 https://api.securitycenter.microsoft.com
> 
> OData に基づくクエリには、'/api' プレフィックスがあります。 たとえば、アラートを取得するには、GET 要求を https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>バージョン管理:

> API はバージョン管理をサポートしています。
> 
> 現在のバージョンは **V1.0 です**。
> 
> 特定のバージョンを使用するには、次の形式を使用します `https://api.securitycenter.microsoft.com/api/{Version}` 。 例: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> 任意のバージョン (例) を指定しない場合 https://api.securitycenter.microsoft.com/api/alerts は、最新バージョンにアクセスします。


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


API 呼び出しを実行できる個々のサポートされるエンティティと、HTTP 要求値、要求ヘッダー、予期される応答などの詳細について説明します。

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
:---|:---
高度なハンティング | API からクエリを実行します。
アラート | アラートの取得、アラートの作成、アラートの更新などの API 呼び出しを実行します。
ドメイン | ドメイン関連デバイスの取得、ドメイン統計などの API 呼び出しを実行します。
Files | ファイル情報の取得、ファイル関連の通知、ファイル関連デバイス、ファイル統計などの API 呼び出しを実行します。
IPs | IP 関連のアラートの取得や IP 統計情報の取得などの API 呼び出しを実行します。
マシン | デバイスの取得、ID によるデバイスの取得、ログオンしているユーザーに関する情報、タグの編集などの API 呼び出しを実行します。
コンピューターのアクション | 分離、ウイルス対策スキャンの実行などの API 呼び出しを実行します。
インジケーター | インジケーターの作成、インジケーターの取得、インジケーターの削除などの API 呼び出しを実行します。
Users | ユーザー関連の通知やユーザー関連デバイスの取得などの API 呼び出しを実行します。
スコア | 露出スコアの取得やデバイスのセキュリティで保護されたスコアの取得などの API 呼び出しを実行します。
ソフトウェア | ソフトウェアによるリストの脆弱性などの API 呼び出しを実行します。
脆弱性 | 脆弱性によるリスト デバイスなどの API 呼び出しを実行します。
推奨事項 | ID による推奨事項の取得などの API 呼び出しを実行します。

## <a name="see-also"></a>関連項目
- [エンドポイント API 用 Microsoft Defender](apis-intro.md)
