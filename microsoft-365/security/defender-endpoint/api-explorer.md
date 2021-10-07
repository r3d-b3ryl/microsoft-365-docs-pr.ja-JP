---
title: エンドポイント向け Microsoft Defender の API エクスプローラー
ms.reviewer: ''
description: API エクスプローラーを使用して、API クエリの作成と実行、テスト、および使用可能な API の要求の送信を行う
keywords: api, explorer, send, request, get, post,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3235ed9e3b4f51b9156267e324573f04443eccc6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210043"
---
# <a name="api-explorer"></a>API エクスプローラー

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

Microsoft Defender for Endpoint API Explorer は、さまざまな Defender for Endpoint API を対話的に探索するのに役立つツールです。

API エクスプローラーを使用すると、使用可能な Defender for Endpoint API エンドポイントに対する API クエリの作成と実行、テスト、および要求の送信が容易になります。 API Explorer を使用して、ユーザー インターフェイスでまだ使用できない可能性があるアクションを実行したり、データを見つけたりします。

このツールは、アプリの開発中に役立ちます。 これにより、ユーザー アクセス設定を尊重する API クエリを実行し、アクセス トークンを生成する必要性を減らします。

ツールを使用して、サンプル クエリのギャラリーを探索し、結果コード サンプルをコピーし、デバッグ情報を生成することもできます。

API エクスプローラーを使用すると、次の機能を使用できます。

- 任意のメソッドの要求を実行し、リアルタイムで応答を確認する
- API サンプルをすばやく参照し、サポートするパラメーターを確認する
- API 呼び出しを簡単に行います。管理ポータルのサインインを超えて認証する必要はありません

## <a name="access-api-explorer"></a>Access API Explorer

左側のナビゲーション メニューで、[ **パートナー] を選択& API** \> **API エクスプローラーを選択します**。

## <a name="supported-apis"></a>サポートされている API

API エクスプローラーは、Defender for Endpoint によって提供される API をサポートします。

サポートされている API の一覧は [、API のドキュメントで確認できます](apis-intro.md)。

## <a name="get-started-with-the-api-explorer"></a>API エクスプローラーの使用を開始する

1. 左側のウィンドウには、使用できるサンプル要求の一覧があります。
2. リンクに従い、[クエリの実行 **] をクリックします**。

一部のサンプルでは、URL にパラメーター ({machine- ID} など) を指定する必要があります。

## <a name="faq"></a>よくあるご質問 (FAQ)

**API エクスプローラーを使用するには、API トークンが必要ですか?** <br>
API にアクセスするための資格情報は必要とされません。 API エクスプローラーは、要求を行うたびに Defender for Endpoint 管理ポータル トークンを使用します。

ログインしているユーザー認証資格情報を使用して、API Explorer がユーザーに代わってデータにアクセスする権限を持つかどうかを確認します。

特定の API 要求は、RBAC 特権に基づいて制限されます。 たとえば、"送信インジケーター" への要求は、セキュリティ管理者の役割に制限されます。
